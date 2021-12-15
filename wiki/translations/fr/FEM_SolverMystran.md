---
- GuiCommand:/fr
   Name:FEM SolverMystran
   Name/fr:FEM Solveur Mystran
   MenuLocation:Solve → Solver Mystran
   Workbenches:[FEM](FEM_Workbench/fr.md)
   Shortcut:**S** **M**
   SeeAlso:[FEM Tutoriel](FEM_tutorial/fr.md)
---

# FEM SolverMystran/fr

## Description

A faire

## Utilisation

A faire

## Fonction du fichier 

Sous Mod\\Fem\\femsolver\\mystran, il y a ces fichiers :


```python
add_con_displacement.py
add_con_fixed.py
add_con_force.py
add_femelement_geometry.py
add_femelement_material.py
add_mesh.py
add_solver_control.py
writer.py
solver.py
tasks.py
```

Les fonctions de chaque fichier sont les suivantes :

writer.py - fichier de contrôle principal


```python
model = BDF()
model = add_solver_control.add_solver_control(pynasf, model, self)
model = add_femelement_geometry.add_femelement_geometry(pynasf, model, self)
model = add_mesh.add_mesh(pynasf, model, self)
model = add_femelement_material.add_femelement_material(pynasf, model, self)
model = add_con_fixed.add_con_fixed(pynasf, model, self)
model = add_con_displacement.add_con_displacement(pynasf, model, self)
model = add_con_force.add_con_force(pynasf, model, self)
```

BDF() - Crée un fichier de cas vide.


```python
$pyNastran: version=msc
$pyNastran: punch=False
$pyNastran: encoding=utf-8
$pyNastran: nnodes=0
$pyNastran: nelements=0
ENDDATA
```

add\_solver\_control.py - Ajout du DECK DE CONTRÔLE EXÉCUTIF et du DECK DE CONTRÔLE DE CASE.


```python
$EXECUTIVE CONTROL DECK
SOL 101
CEND
$CASE CONTROL DECK
ECHO = NONE
TITLE = pyNastran for generating solverinput for for Mystran
SUBCASE 1
    DISPLACEMENT(SORT1,REAL) = ALL
    LOAD = 1
    SPC = 1
    SPCFORCES(SORT1,REAL) = ALL
    STRESS(SORT1,REAL,VONMISES,BILIN) = ALL
    SUBTITLE = Default
BEGIN BULK
$PARAMS
PARAM       POST      -1
```

add\_femelement\_geometry.py - Ajout de cartes GRID

add\_mesh.py - Ajout de cartes d\'éléments

add\_femelement\_material.py - Ajout de la carte MAT1

add\_con\_fixed.py - Ajout des cartes SPCADD et SPC1

add\_con\_displacement.py - Ajout des cartes SPCADD et SPC1

add\_con\_force.py - Ajout de cartes FORCE





{{FEM Tools navi

}}

---
[documentation index](../README.md) > FEM SolverMystran/fr