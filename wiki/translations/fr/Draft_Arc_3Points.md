---
- GuiCommand:/fr
   Name:Draft Arc 3Points
   Name/fr:Draft Arc par 3 points
   MenuLocation:Drafting → Outils Arc → Arc by 3 points
   Workbenches:[Draft](Draft_Workbench/fr.md), [Arch](Arch_Workbench/fr.md)
   Version:0.19
   SeeAlso:[Draft Arc](Draft_Arc/fr.md), [Draft Cercle](Draft_Circle/fr.md)
---

## Description

La commande <img alt="" src=images/Draft_Arc_3Points.svg  style="width:24px;"> **Draft Arc par 3 points** crée un arc de cercle dans le [plan de travail](Draft_SelectPlane/fr.md) en cours à partir de trois points qui définissent sa circonférence. Le centre et le rayon sont calculés à partir de ces points.

Un Draft Arc est en fait un [Draft Cercle](Draft_Circle/fr.md) dont la {{PropertyData/fr|First Angle}} n\'est pas la même que sa {{PropertyData/fr|Last Angle}}.

<img alt="" src=images/Draft_Arc_3Points_example.png  style="width:400px;"> 
*Arc defini par trois points passant par la circonférence*

## Utilisation

Voir aussi : [Draft La barre](Draft_Tray/fr.md), [Draft Accrochage](Draft_Snap/fr.md) et [Draft Contrainte](Draft_Constrain/fr.md).

1.  Il existe plusieurs façons d\'invoquer la commande :
    -   Appuyez sur le **<img src="images/Draft_Arc_3Points.svg" width=16px> [Draft Arc par 3 points](Draft_Arc_3Points/fr.md)**.
    -   Sélectionnez l\'option {{MenuCommand|Drafting → Outils arc → <img src="images/Draft_Arc_3Points.svg" width=16px> Arc par 3 points}} dans le menu.
2.  Le panneau de tâches {{MenuCommand|Arc par 3 points}} s\'ouvre. Voir [Options](#Options.md) pour plus d\'informations.
3.  Choisissez le premier point dans la [Vue 3D](3D_view/fr.md) ou rentrez des coordonnées et appuyez sur le bouton **<img src="images/Draft_AddPoint.svg" width=16px> Entrez le point**.
4.  Choisissez le deuxième point dans la [Vue 3D](3D_view/fr.md) ou rentrez des coordonnées et appuyez sur le bouton **<img src="images/Draft_AddPoint.svg" width=16px> Entrez le point**.
5.  Choisissez le troisième point dans la [Vue 3D](3D_view/fr.md) ou rentrez des coordonnées et appuyez sur le bouton **<img src="images/Draft_AddPoint.svg" width=16px> Entrez le point**.

## Options

Les raccourcis clavier à caractère unique disponibles dans le panneau des tâches peuvent être modifiés. Voir [Draft Préférences](Draft_Preferences/fr.md). Les raccourcis mentionnés ici sont les raccourcis par défaut.

-   Pour saisir manuellement des coordonnées, entrez la composante X, Y et Z, et appuyez sur **Entrée** après chacune. Ou vous pouvez appuyer sur le bouton **<img src="images/Draft_AddPoint.svg" width=16px> Entrez le point** lorsque vous avez les valeurs souhaitées. Il est conseillé de déplacer le pointeur hors de la [Vue 3D](3D_view/fr.md) avant de saisir les coordonnées.
-   Appuyez sur **R** ou cliquez sur la case {{MenuCommand|Relative}} pour activer le mode relatif. Si le mode relatif est activé, les coordonnées sont relatives au dernier point, si disponible, sinon elles sont relatives à l\'origine du système de coordonnées.
-   Appuyez sur **G** ou cliquez sur la case {{MenuCommand|Global}} pour activer le mode global. Si le mode global est activé, les coordonnées sont relatives au système de coordonnées global, sinon elles sont relatives au système de coordonnées du [plan de travail](Draft_SelectPlane/fr.md). {{Version/fr|0.20}}
-   Appuyez sur **S** pour activer ou désactiver [Draft Accrochage](Draft_Snap/fr.md).
-   Appuyez sur **Echap** ou sur le bouton **Fermer** pour abandonner la commande.

## Remarques

-   Un Draft Arc peut être édité avec la commande [Draft Editer](Draft_Edit/fr.md).

## Préférences

Voir aussi : [Réglage des préférences](Preferences_Editor/fr.md) et [Draft Préférences](Draft_Preferences/fr.md).

-   Pour modifier le nombre de décimales utilisées pour la saisie des coordonnées, des rayons et des angles : {{MenuCommand|Édition → Préférences... → Général → Unités → Système d'unités → Nombre de décimales}}.
-   Si {{MenuCommand|Édition → Préférences... → Draft → Paramètres généraux → Options des outils de Draft → Utiliser les primitives de Part si possibles}} est cochée, la commande créera une [Part Feature](Part_Feature/fr.md) non modifiable au lieu d\'un Draft Cercle.

## Propriétés

Voir [Draft Cercle](Draft_Circle/fr#Propri.C3.A9t.C3.A9s.md).

## Script

Voir aussi : [Autogenerated API documentation](https://freecad.github.io/SourceDoc/) et [Débuter avec les scripts FreeCAD](FreeCAD_Scripting_Basics/fr.md).

Pour créer un Draft Arc par 3 points, utilisez la méthode `make_arc_3points` du module Draft :


```python
arc = make_arc_3points(points, placement=None, face=False, support=None, map_mode="Deactivated", primitive=False)
```

-   Crée un objet `arc` à partir de la liste donnée `points`.
-   Si un `placement` est donné, le centre de l\'arc circulaire sera déplacé à cet endroit. Voir [Positionnement](Placement/fr.md) pour plus d\'informations.
-   Si `face` est `True`, l\'arc fera une surface, c\'est-à-dire qu\'il apparaîtra rempli.
-   Si `support` est donné, c\'est un `LinkSubList`, c\'est-à-dire une liste indiquant un objet et un sous-élément de cet objet. Ceci est utilisé pour que l\'objet apparaisse référencé à ce support.

:   Par exemple, support=[(obj, ("Face1"))]

-   Si `map_mode` est donné, il s\'agit d\'une chaîne définissant un type de mappage, par exemple, map_mode='FlatFace', map_mode='ThreePointsPlane' etc. Voir [Part Accrochage](Part_Attachment/fr.md) pour plus d\'informations.
-   Si `primitive` est `True`, l\'arc créé sera un simple [Part Fonctionnalité](Part_Feature/fr.md), non un objet Draft complexe.

Exemple :


```python
import FreeCAD as App
import Draft

doc = App.newDocument()

points = [App.Vector(0, 0, 0),
          App.Vector(5, 10, 0),
          App.Vector(10, 0, 0)]

arc = Draft.make_arc_3points(points)

doc.recompute()
```





 