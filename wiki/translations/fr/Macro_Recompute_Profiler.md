 {{Macro/fr
|Name=Macro Recompute Profiler
|icone=Macro_Recompute_Profiler.png
|Description=Cette macro chronomètre le temps nécessaire pour recalculer chaque fonction.
|Author=DeepSOIC
|Version=0.1
|Date=2017-04-03
|FCVersion=0.17.10644 et au dessus
|Download=[https://www.freecadweb.org/wiki/images/c/ca/Macro_Recompute_Profiler.png ToolBar Icon]
}}

## Description

Cette macro vous permet de localiser quelles fonctionnalités provoquent de longs retards dans les mises à jour de votre projet. cette macro chronomètre le temps nécessaire pour recalculer chaque fonction.

## Utilisation

Cette macro requiers FreeCAD 0.17.10644 ou plus

Sauvez la macro dans un fichier

1\. Ouvrez votre projet

2\. Faites clic droit sur votre objet dans la vue 3D, et cliquez sur \"Mark to recompute\"

3\. Lancez cette macro

Une barre de progression apparait. Votre objet est recalculé, une ligne est affichée dans la vue rapport contenant le temps et le label de l\'objet. Si le recalcul de l\'objet n\'est pas possible, la macro affiche une erreur et termine le processus.

## Macro

ToolBar Icon ![](images/Macro_Recompute_Profiler.png )

**RecomputeProfiler.FCMacro**


{{MacroCode|code=
__Title__="Macro Recompute Profiler"
__Author__ = "DeepSOIC"
__Version__ = "0.1"
__Date__    = "03.04.2017"

__Comment__ = "Measures time it takes to recmpute features in a project"
__Wiki__ = "https://www.freecadweb.org/wiki/index.php?title=Macro_Recompute_Profiler"
__Help__ = "Right-click an object, and pick 'Mark to recompute', then run this macro. This will only profile recomputing the subgraph. To profile the whole project, right-click the project in tree view, and pick 'Mark to recompute', then run this macro. Results will be printed to report view."
__Status__ = "experimental"
__Requires__ = "freecad 0.17.10644"
__Communication__ = "https://forum.freecadweb.org/memberlist.php?mode=viewprofile&u=3888" 

import FreeCAD as App

import FreeCADGui as Gui

class ExecutionError(Exception):
    pass

class CancelError(Exception):
    pass

def execute(feature):
    feature.recompute()
    if 'Invalid' in feature.State:
        raise ExecutionError("Feature '{label}' failed to recompute".format(label= feature.Label))

def msgbox(title, text):
    from PySide import QtGui
    mb = QtGui.QMessageBox()
    mb.setIcon(mb.Icon.Information)
    mb.setText(text)
    mb.setWindowTitle(title)
    mb.exec_()

def log(string):
    App.Console.PrintWarning(string+"\n")

def getAllDependent(feat_list):
    '''getAllDependent(feat_list): gets all features that depend on features in feat_list, directly or indirectly.
    Returns a set. Features from feat_list are not included, unless there are interdependencies between them.'''

    list_traversing_now = feat_list
    set_of_deps = set()
    list_of_deps = []

    while len(list_traversing_now) > 0:
        list_to_be_traversed_next = []
        for feat in list_traversing_now:
            for dep in feat.InList:
                if not (dep in set_of_deps):
                    set_of_deps.add(dep)
                    list_of_deps.append(dep)
                    list_to_be_traversed_next.append(dep)

        list_traversing_now = list_to_be_traversed_next

    return set_of_deps


def run():
    touched = [obj for obj in App.ActiveDocument.Objects if 'Touched' in obj.State]

    if len(touched) == 0:
        App.ActiveDocument.RecomputesFrozen = True
        msgbox("Macro Recompute Profiler", "Project was switched to suspend recomputes. Please modify an object that triggers a recompute, and run this macro again. The macro will perform a step-by-step recompute, and measure the time it takes to recompute features.")
        return

    log("{n} features are touched".format(n= len(touched)))

    log("Generating execution order...")

    to_be_executed = set.union(getAllDependent(touched), set(touched))
    log("Number of features to execute: {n}".format(n= len(to_be_executed)))

    exec_list = []
    for obj in App.ActiveDocument.TopologicalSortedObjects[::-1]:
        if obj in to_be_executed:
            exec_list.append(obj)
    assert(len(exec_list) == len(to_be_executed))
    n = len(exec_list)

    log("Execution order:")
    for obj in exec_list:
        log("    "+obj.Label)


    import PySide
    progress = PySide.QtGui.QProgressDialog(u"Preparing to recompute....", u"Abort", 0, n+1)
    progress.setModal(True)
    progress.show()try:
        log("Recomputing... (time in seconds, label)")
        import time
        for obj in exec_list:
            progress.setValue(progress.value()+1)
            progress.setLabelText("Recomputing {feature}...".format(feature= obj.Label))
            if progress.wasCanceled():
                raise CancelError()

            time_start = time.time()
            try:
                execute(obj)
            finally:
                exec_time = time.time()-time_start
                log("\t{time}\t{label}".format(time= exec_time, label= obj.Label))

        progress.setValue(n+1)
        msgbox("Macro Recompute Profiler", "Recompute completed. Results are in report view.")

        for obj in exec_list:
            obj.purgeTouched()

    except Exception as err:
        msgbox("Macro Recompute Profiler", "An error occured: {err}".format(err= str(err)))
    finally:
        progress.hide()
        App.ActiveDocument.RecomputesFrozen = False

run()
}}

## Post-processing resultats {#post_processing_resultats}

La sortie de la macro sera entrelacée avec les messages généraux générés par le recalcul des fonctionnalités. Cela ressemble généralement à ceci: {{code|code=
Recomputing... (time in seconds, label)
Sketcher::setUpSketch()-T:0
Sketcher::Solve()-DogLeg-T:0
    0.00999999046326    Sketch - master section
    0.0199999809265 Clone of Sketch - master section (2D)001
Sketcher::setUpSketch()-T:0
Sketcher::Solve()-DogLeg-T:0
    0.00999999046326    Sketch013
Sketcher::setUpSketch()-T:0
Sketcher::Solve()-DogLeg-T:0
    0.00999999046326    Sketch011
    0.0 Clone of Sketch - master section (2D)
Sketcher::setUpSketch()-T:0
Sketcher::Solve()-DogLeg-T:0
    0.0 Sketch008
    0.130000114441  LinearArray
Sketcher::setUpSketch()-T:0
Sketcher::Solve()-DogLeg-T:0
...
}} Le résultat des lignes ont une signature facilement séparable: elles commencent par un onglet. Donc, si vous copiez-copiez l\'intégralité du bloc dans un tableur, les messages génériques se retrouveront dans la colonne 1, tandis que les résultats se trouvent dans les colonnes 2 et 3. Vous pouvez donc trier selon la colonne 2 pour obtenir une belle table : {{code|code=
0.59100008  Slice
0.352999926 Populate LinearArray with Compound
0.160000086 CompoundFilter
0.138999939 Cut
0.130000114 LinearArray
0.108999968 Fusion
0.069999933 Moved CompoundFilter
0.067000151 Module - spokes
0.029999971 Sweep
0.019999981 Clone of Sketch - master section (2D)001
0.010999918 ArrayFilter003
...
}} (Pour MS-Excel, après avoir copié le texte dans la vue rapport coller le texte dans le Bloc-notes et le recopier depuis Bloc-notes puis coller-le dans MS-Excel \... la copie dans la vue rapport ne sépare pas les colonnes car les tabulations sont inexplicablement perdues.)

## FC version {#fc_version}

Cette macro nécessite FreeCAD 0.17.10644 ou plus, qui sont les versions où App.ActiveDocument.RecomputesFrozen est disponible. Elle ne fonctionnera pas avec la version v0.16.

Cette macro a été créée avec cette version de FreeCAD: 
```python
OS: Windows 10
Word size of OS: 64-bit
Word size of FreeCAD: 64-bit
Version: 0.17.10665 (Git)
Build type: Release
Branch: master
Hash: 47847513a85ff6615774ef628230f79e37471daf
Python version: 2.7.8
Qt version: 4.8.7
Coin version: 4.0.0a
OCC version: 7.0.0
```



