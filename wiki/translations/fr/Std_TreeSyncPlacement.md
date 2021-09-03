---
- GuiCommand:/fr
   Name:Std TreeSyncPlacement
   Name/fr:Std Arborescence Synchroniser le placement
   MenuLocation:Affichage → Configuration de l'arborescence → Synchroniser le placement
   Workbenches:Tous
   Shortcut:**T** **3**
   Version:0.19
---

## Description

La commande **Std Synchroniser le placement** bascule la [vue en arborescence](tree_view/fr.md) dans le mode SyncPlacement. Si ce mode est activé, {{PropertyData/fr|Placement}} des objets est automatiquement ajusté lorsqu\'ils sont glissés et déposés d\'un conteneur dans un autre conteneur avec un système de coordonnées différent, en préservant leur placement par rapport au système de coordonnées global.

## Utilisation

1.  Il existe plusieurs façons d\'appeler la commande:
2.  \* Cliquez sur la flèche noire vers le bas à droite du bouton **<img src="images/Std_TreeSyncView.svg" width=16px>** et sélectionnez l\'option {{MenuCommand|Sync placement}} dans le menu déroulant. Remarque: l\'image du bouton changera en fonction de l\'option sélectionnée.
    -   Sélectionnez l\'option {{MenuCommand|Affichage → Configuration de l'arborescence →  <img src="images/Std_TreeSyncPlacement.svg" width=16px> Synchroniser le placement}} dans le menu.
    -   Utilisez le raccourci clavier: **T** puis **3**.

## Préférences

Le mode Synchronisation placement arborescence est stocké: {{MenuCommand|Outils → Editer paramètres... → BaseApp → Preferences → TreeView → SyncPlacement}}. Il s\'agit d\'une valeur booléenne, la valeur par défaut est `False`.





{{Std Base navi

}}  