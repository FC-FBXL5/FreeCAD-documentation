---
- GuiCommand:/fr
   Name:Std_Paste
   Name/fr:Std Coller
   MenuLocation:Edition → Coller
   Workbenches:Tous
   Shortcut:**Ctrl** + **V**
   SeeAlso:[Std Couper](Std_Cut/fr.md), [Std Copier](Std_Copy/fr.md), [Std Dupliquer une sélection](Std_DuplicateSelection/fr.md)
---

## Description

La commande **Std Coller** colle les objets du Presse-papiers dans le document actif.

## Utilisation

1.  Il existe plusieurs façons d\'appeler la commande:
    -   Appuyez sur le bouton **<img src="images/Std_Paste.svg" width=16px> [Opération de collage](Std_Paste/fr.md)**.
    -   Sélectionnez l\'option {{MenuCommand|Edition → <img src="images/Std_Paste.svg" width=16px> Coller}} dans le menu.
    -   Sélectionnez l\'option {{MenuCommand|<img src="images/Std_Paste.svg" width=16px> Coller}} dans le menu contextuel de la [vue en arborescence](tree_view/fr.md). Notez que cette option n\'est disponible que lorsqu\'un objet sortant a été sélectionné.
    -   Utilisez le raccourci clavier: **Ctrl**+**V**.

## Remarques

-   FreeCAD changera automatiquement les noms internes et, selon les préférences, les étiquettes des objets pour éviter les conflits de noms.
-   Un alias de cellule de feuille de calcul qui existe déjà dans la feuille de calcul ne sera pas collé.
-   Lorsque vous travaillez dans une fenêtre de texte FreeCAD, une zone de saisie ou une feuille de calcul, le raccourci clavier standard **Ctrl**+**V**, dans presque tous les cas, n\'appelle pas \'\'\' Std Coller \'\'\' mais utilise la fonction Coller du système d\'exploitation à la place.
-   Il n\'est pas possible de copier-coller des objets natifs entre FreeCAD et d\'autres applications.

## Préférences

-   Les étiquettes en double sont autorisées si {{MenuCommand|Outils → Editer les paramètres... → BaseApp → Preferences → Document → DuplicateLabels}} est défini sur `True`. Ce paramètre peut également être modifié dans l\'[Editeur de préférences](Preferences_Editor/fr#Document.md).

## Script

La commande **Std Coller** ne peut être appliquée qu\'après avoir exécuté la commande **[Std Copier](Std_Copy/fr.md)**:


```python
FreeCADGui.runCommand('Std_Copy')
FreeCADGui.runCommand('Std_Paste')
```





{{Std Base navi

}}  