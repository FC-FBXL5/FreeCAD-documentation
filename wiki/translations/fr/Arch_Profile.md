---
- GuiCommand:/fr
   Name:Arch Profile
   Name/fr:Arch Profilé
   Workbenches:[Arch](Arch_Module/fr.md)
   MenuLocation:Arch → Profilé
   Version:0.19
---


</div>

## Description

L\'outil Profilé crée un objet de profil 2D paramétrique. Cet objet peut ensuite être utilisé comme base dans différents autres outils qui effectuent des extrusions tels que [Arch Ossature](Arch_Frame/fr.md), [Arch Mur-rideau](Arch_CurtainWall/fr.md) ou [Part Extrusion](Part_Extrude/fr.md).

Voir la [liste des préréglages disponibles](https://github.com/FreeCAD/FreeCAD/blob/master/src/Mod/Arch/Presets/profiles.csv).

L\'outil Profilé est également intégré à l\'outil [Arch Structure](Arch_Structure/fr.md), tous les profilés prédéfinis y sont également disponibles.

## Utilisation

1.  Appuyez sur le bouton **<img src="images/Arch_Profile.svg" width=16px> [Arch Créer un objet profilé](Arch_Profile/fr.md)
**
2.  Sélectionnez un préréglage dans le panneau des tâches de l\'outil
3.  Cliquez sur un point de la vue 3D pour placer le profilé

## Propriétés

### Données

-    {{PropertyData/fr|Height}}: hauteur globale du profilé

-    {{PropertyData/fr|Width}}: largeur globale du profilé

-    {{PropertyData/fr|Diameter}}: diamètre du profilé (profils circulaires uniquement)

-    {{PropertyData/fr|Thickness}}: épaisseur de la paroi du tube (profilés creux circulaires et rectangulaires uniquement)

-    {{PropertyData/fr|Web Thickness}}: épaisseur de l\'âme du profilé (profilés H et I uniquement)

-    {{PropertyData/fr|Flange Thickness}}: épaisseur de la semelle du profilé (profilés H et I uniquement)

## Ajouter des profilés personnalisés {#ajouter_des_profilés_personnalisés}

Un fichier CSV supplémentaire peut être créé par l\'utilisateur contenant des définitions des profilés personnalisés. Il doit être nommé `profiles.csv` et placé dans 
```python
$FREECAD_USER_DIR/Arch/
```

Le `$FREECAD_USER_DIR` peut être obtenu à partir de la [console Python](Python_console/fr.md): 
```python
FreeCAD.getUserAppDataDir()
```

Le contenu de votre fichier `profiles.csv` personnalisé doit être calqué sur les mêmes règles que les profils intégrés [profiles.csv](https://github.com/FreeCAD/FreeCAD/blob/master/src/Mod/Arch/Presets/profiles.csv) dans le code source:

Le fichier CSV doit contenir une ligne par profilé disponible est formaté comme suit:

-   Pour les profilés C: catégorie, nom, classe, diamètre, épaisseur
-   Pour les profilés H et U: catégorie, nom, classe, largeur, hauteur, épaisseur de l\'âme, épaisseur de la semelle
-   Pour les profilés R: catégorie, nom, classe, largeur, hauteur
-   Pour les profilés RH: catégorie, nom, classe, largeur, hauteur, épaisseur

Toutes les mesures doivent être en millimètres. Les classes possibles de profilés sont:

-   C: tube circulaire
-   H: profil H ou I
-   R: rectangulaire
-   RH: creux rectangulaire
-   U: profil en U

Des types de profilé supplémentaires peuvent être créés mais une classe correspondante doit d\'abord être définie dans [ArchProfile.py](https://github.com/FreeCAD/FreeCAD/blob/master/src/Mod/Arch/ArchProfile.py)

## Script

L\'outil Profilé peut être utilisé dans une [macro](macros/fr.md) et à partir de la console [Python](Python/fr.md) en utilisant la fonction suivante :


```python
profile = makeProfile(profile_list)
```

Où profile\_list contient les différents éléments d\'une liste dans le fichier CSV.

Exemple:


```python
import Arch
Arch.makeProfile([0,'REC','REC100x100','R',100,100])
```

Lorsque le premier élément de la liste est un numéro ordonné pas encore utilisé.


<div class="mw-translate-fuzzy">





</div>


 