---
- GuiCommand:/fr
   Icon:Points_Import.svg
   Name:Points Import
   Name/fr:Points Importer
   MenuLocation:Points → Importer des points...
   Workbenches:[Points](Points_Workbench/fr.md)
   SeeAlso:[Points Exporter](Points_Export/fr.md)
---

## Description

La commande **Points Importer** importe un nuage de points à partir d\'un fichier.

## Utilisation

1.  Il existe plusieurs façons d\'appeler la commande:
    -   Appuyez sur le bouton <img alt="" src=images/Points_Import.svg  style="width:16px;"> [Importer les points](Points_Import/fr.md).
    -   Utilisez l\'option {{MenuCommand|Points → <img src="images/Points_Import.svg" width=16px> Importer des points...}} depuis le menu.
2.  Sélectionnez le fichier de nuage de points.
3.  Appuyez sur le bouton **Ouvrir**.

## Propriétés

Voir [Points Conversion](Points_Convert/fr.md).

## Format du fichier du nuage de points {#format_du_fichier_du_nuage_de_points}

-   Un fichier de nuage de points doit avoir l\'extension {{FileName|.asc}}, {{FileName|.pcd}} ou {{FileName|.ply}}.
-   Chaque ligne du fichier doit lister les coordonnées X, Y et Z d\'un point.
-   Les coordonnées doivent être séparées par des espaces.
-   Les coordonnées doivent utiliser un point décimal, pas une virgule décimale.

## Exemple de fichier de nuage de points {#exemple_de_fichier_de_nuage_de_points}

0 0 0
1.4562 -7.2354 12.2367
5.9423 3.1728 -17.6439

Pour tester, vous pouvez utiliser ce fichier [Ce fichier](https://raw.githubusercontent.com/FreeCAD/Examples/master/Point_cloud_ExampleFiles/PointCloud-Data_Stanford-Bunny.asc) qui est une version à faible polygone du [Stanford Bunny](http://graphics.stanford.edu/data/3Dscanrep/).





{{Points Tools navi

}} 