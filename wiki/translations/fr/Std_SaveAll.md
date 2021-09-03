---
- GuiCommand:/fr
   Name:Std SaveAll
   Name/fr:Std Tout enregistrer
   MenuLocation:Fichier → Tout enregistrer
   Workbenches:Tous
   SeeAlso:[Std Enregistrer](Std_Save/fr.md)
---

## Description

La commande **Std Tout enregistrer** enregistre tous les documents actifs.

## Utilisation

1.  Sélectionnez l\'option {{MenuCommand|Fichier → <img src="images/Std_SaveAll.svg" width=16px> Enregistrer tout}} dans le menu.
2.  Pour les nouveaux documents: saisissez un nom de fichier dans la boîte de dialogue et appuyez sur le bouton **Enregistrer**.

## Options

-   Appuyez sur **Echap** ou sur le bouton **Annuler** pour annuler la commande.

## Préférences

-   Le dernier emplacement de fichier utilisé est stocké: {{MenuCommand|Outils → Editer les paramètres... → BaseApp → Preferences → General → FileOpenSavePath}}.

## Script


**Voir aussi:**

[FreeCAD Script de base](FreeCAD_Scripting_Basics/fr.md).

Pour enregistrer un document, utilisez la méthode `save` de l\'objet document. Un nouveau document doit d\'abord être enregistré avec la méthode `saveAs` de l\'objet document. Pour un exemple de script, voir [Std Nouveau](Std_New/fr.md).





{{Std Base navi

}}  