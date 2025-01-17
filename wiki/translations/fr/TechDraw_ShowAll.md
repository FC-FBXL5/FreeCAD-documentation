---
- GuiCommand:/fr
   Name:TechDraw ShowAll
   Name/fr:TechDraw Montrer tout
   MenuLocation:TechDraw → Afficher/Masquer les arrêtes cachées
   Workbenches:[TechDraw](TechDraw_Workbench/fr.md)
   Version:0.19
   SeeAlso:[TechDraw Apparence des lignes](TechDraw_DecorateLine/fr.md)
---

# TechDraw ShowAll/fr

## Description

L\'outil Montrer tout affiche ou masque les lignes invisibles dans une vue. Notez que \"invisible\" est un état esthétique, à ne pas confondre avec les lignes cachées qui sont des constructions géométriques.

## Utilisation

1.  Sélectionnez une vue sur une page ou dans l\'arborescence.
2.  Appuyez sur le bouton **<img src="images/TechDraw_ShowAll.svg" width=16px> [Afficher/Masquer les arrêtes cachées](TechDraw_ShowAll/fr.md)**.
3.  L'état des lignes invisibles dans la vue sera inversé.

## Propriétés

L\'outil Montrer tout n\'a aucune propriété car il ne s\'agit pas d\'un objet du document.

## Script

Voir aussi : [Autogenerated API documentation](https://freecad.github.io/SourceDoc/) et [FreeCAD Débuter avec les scripts](FreeCAD_Scripting_Basics/fr.md).

Les effets de l\'outil Montrer tout peut être dupliqué dans la [macro](Macros/fr.md) ou la console [Python](Python/fr.md). 
```python
>>> v = App.ActiveDocument.View
>>> vvo = v.ViewObject
>>> vvo.ShowAllEdges = True
>>> App.activeDocument().recompute()
```





{{TechDraw Tools navi

}}



---
![](images/Right_arrow.png) [documentation index](../README.md) > [TechDraw](TechDraw_Workbench.md) > TechDraw ShowAll/fr
