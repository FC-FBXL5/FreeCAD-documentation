

## Introduction

Depuis la v0.17, il est facile d\'ajouter des [ateliers externes](external_workbenches/fr.md) en utilisant le [gestionnaire d\'addons](Std_AddonMgr/fr.md). Un utilisateur régulier n\'a pas besoin de faire plus que d\'utiliser cet outil.

Lire la suite pour plus d\'informations concernant l\'installation des ateliers.

## Description globale {#description_globale}

Les ateliers ne sont rien de plus que des collections de fichiers placés dans un dossier. Ce dossier est généralement compressé dans une archive zip. Lors de l\'installation, ce dossier est simplement décompressé et copié dans 
```python
$ROOT_DIR/Mod/
``` où `$ROOT_DIR` est un des premiers répertoires recherché par FreeCAD au démarrage. C\'est essentiellement ce que fait l\'[Addon Manager](Std_AddonMgr/fr.md).

Les répertoires `Mod /` sont analysés à chaque démarrage de FreeCAD et les ateliers disponibles sont automatiquement ajoutés.

## Installation à l\'échelle du système {#installation_à_léchelle_du_système}

Les ateliers installés de cette manière seront disponibles pour tous les utilisateurs. Selon votre système, vous pourriez avoir besoin de privilèges d\'administrateur pour accéder au répertoire d\'installation.

Copiez le répertoire de l\'atelier dans `$INSTALL_DIR/Mod/` où `$INSTALL_DIR` correspond au répertoire d\'installation de FreeCAD.

-   Pour Linux, c\'est généralement `/usr/share/freecad/Mod/`
-   Pour Windows, c\'est généralement `C:\Program Files\FreeCAD\Mod\`
-   Pour macOS, c\'est généralement `/Applications/FreeCAD/Mod/`

## Installation pour un seul utilisateur {#installation_pour_un_seul_utilisateur}

Les ateliers installés de cette manière ne seront disponibles que pour un seul utilisateur mais ne nécessiteront aucun privilège d\'administrateur.

Copiez le dossier de l\'atelier dans `$USER_DIR/Mod/` où `$USER_DIR` est le répertoire FreeCAD d\'un `nom d'utilisateur` spécifique.

-   Pour Linux, c\'est généralement `/home/username/.FreeCAD/Mod/`
-   Pour Windows, c\'est `%APPDATA%\FreeCAD\Mod\`, lequel est généralement `C:\Users\''username''\Appdata\Roaming\FreeCAD\Mod\`
-   Pour macOS, c\'est généralement `/Users/username/Library/Preferences/FreeCAD/Mod/`. Une manière d\'accéder au répertoire des préférences consiste à utiliser le menu \"Finder\" {{MenuCommand|Aller → Aller au dossier}} et à entrer `~/Library/Preferences/FreeCAD`.

## Informations supplémentaires {#informations_supplémentaires}

Pour plus d\'informations pour créer votre propre atelier, allez sur [Documentation pour utilisateurs avancés](Power_users_hub/fr.md) et sur [Documentation pour développeurs](Power_users_hub/fr.md).

Voir aussi une description détaillée sur la page [Comment installer un atelier supplémentaire](How_to_install_additional_workbenches/fr.md).


{{Powerdocnavi

}} 

[Category:Developer Documentation{{\#translation:}}](Category:Developer_Documentation.md)