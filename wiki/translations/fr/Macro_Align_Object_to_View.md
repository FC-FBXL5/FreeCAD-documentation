 {{Macro/fr
|Name=Macro Align Object to View
|Icon=Macro_Align_Object_to_View.png
|Translate=Macro Align Object to View
|Description=Cette macro aligne l'objet sélectionné sur la vue 3D.
|Author=Mario52
|Version=0.1
|Date=2015-01-16
|FCVersion=All
|Download=[https://www.freecadweb.org/wiki/images/f/f4/Macro_Align_Object_to_View.png ToolBar Icon]
|SeeAlso=[32px|FCCamera](File:FCCamera_00.png.md) [Macro_FCCamera](Macro_FCCamera/fr.md)
}}

## Description

Cette macro aligne l\'objet sélectionné sur la vue 3D.

## Utilisation

-   Dirigez votre vue, sélectionnez votre objet et lancez la macro
-   Votre objet est dirigé sur la position de la caméra

## Script

ToolBar Icon ![](images/Macro_Align_Object_to_View.png )

**Macro\_Align\_Object\_to\_View.FCMacro**


{{MacroCode|code=
# This macro place your object selected to the position ActiveView (camera)
# extact FCCamera
# 16/01/2015

__title__  ="Align Object to View"
__author__ = "Mario52"
__date__   = "16/01/2015"
__version__= "0.1"

import pivy
from pivy import coin

sel = FreeCADGui.Selection.getSelection()
Nameelement = sel[0].Name
App.Console.PrintMessage(str(Nameelement)+"\n")

pl = FreeCAD.Placement()
pl.Rotation = FreeCADGui.ActiveDocument.ActiveView.getCameraOrientation()
pl.Base = FreeCAD.Vector(0.0,0.0,0.0)

App.ActiveDocument.getObject(Nameelement).Placement=pl

}}

## Exemple


<center>

Image:Macro Align Object to View 01.png\|Votre objet dans sa position originale XY. Image:Macro Align Object to View 02.png\|Faites une rotation de l\'écran X? Y? Z? ou utilisez cette macro [Macro\_Rotate\_View](Macro_Rotate_View.md) pour une rotation précise.


</center>


<center>

Image:Macro Align Object to View 03.png\|Sélectionnez l\'objet et lancez la macro (l\'objet fait face à l\'écran). Image:Macro Align Object to View 04.png\|Votre objet vient de prendre les positions XY et (Placement, Angle)


</center>

## Credits

Merci rentlau\_64 pour avoir simplifié le code



