---
- GuiCommand:/fr
   Name:Std ProjectUtil
   Name/fr:Std Utilitaire de projet
   MenuLocation:Outils → Utilitaire de projet
   Workbenches:Tous
---

## Description

La commande **Std Utilitaire de projet** vous permet d\'extraire des fichiers à partir d\'un fichier de projet FreeCAD ({{FileName|*.FCStd}}) qui est en fait un [ZIP](https://fr.wikipedia.org/wiki/ZIP_(format_de_fichier)) et, après les modifications manuelles, crée un nouveau fichier de projet à partir d\'eux.

![](images/Project_utility_en.png ) *La boîte de dialogue de l'Utilitaire de projet*

## Utilisation

### Extraire le projet {#extraire_le_projet}

1.  Sélectionnez l\'option {{MenuCommand|Outils → <img src="images/Std_ProjectUtil.svg" width=16px> Utilitaire de projet...}} dans le menu.
2.  La boîte de dialogue Utilitaire de projet s\'ouvre.
3.  Appuyez sur le bouton **...** à droite de {{MenuCommand|Extraire le projet → Source}}.
4.  Sélectionnez le fichier {{FileName|*.FCStd}} que vous souhaitez modifier.
5.  Appuyez sur le bouton **...** à droite de {{MenuCommand |Extraire le projet → Destination}}.
6.  Sélectionnez un dossier dans lequel le fichier de projet doit être extrait. Il est conseillé de sélectionner un dossier vide.
7.  Appuyez sur le bouton **Extraire**.
8.  Appuyez sur le bouton **Fermer** pour fermer la boîte de dialogue.

### Modifications manuelles {#modifications_manuelles}

Il est important de réaliser que les fichiers contenus dans un fichier de projet FreeCAD sont liés entre eux. La modification seule d\'un seul fichier entraînera généralement des erreurs. Pour effectuer des modifications cohérentes sur plusieurs fichiers, utilisez un bon éditeur de code, tel que [Notepad ++](http://notepad-plus-plus.org/) (pour le système d\'exploitation Windows) ou [Notepadqq](https://notepadqq.com/s/) (pour le système d\'exploitation Linux).

### Créer un projet {#créer_un_projet}

1.  Sélectionnez l\'option {{MenuCommand|Outils → <img src="images/Std_ProjectUtil.svg" width=16px> Utilitaire de projet......}} dans le menu.
2.  La boîte de dialogue Utilitaire de projet s\'ouvre.
3.  Appuyez sur le bouton **...** à droite de {{MenuCommand|Créer un projet → Source}}.
4.  Sélectionnez le fichier {{FileName|Document.xml}}. La commande trouvera automatiquement tous les fichiers liés.
5.  Appuyez sur le bouton **...** à droite de {{MenuCommand|Créer un projet → Destination}}.
6.  Sélectionnez un dossier dans lequel le nouveau fichier de projet doit être créé.
7.  Appuyez sur le bouton **Créer**.
8.  Un nouveau fichier de projet avec un nom fixe, {{FileName|project.fcstd}}, est créé dans le dossier sélectionné. Il n\'y a aucun avertissement si un fichier portant ce nom existe déjà.
9.  Cochez éventuellement la case {{CheckBox|TRUE|Charger le fichier de projet après sa création}}.
10. Appuyez sur le bouton **Fermer** pour fermer la boîte de dialogue.

## Remarques

-   Pour plus d\'informations sur le format de fichier du projet FreeCAD, voir [Fichier au format FCStd](File_Format_FCStd/fr.md).





{{Std Base navi

}}  