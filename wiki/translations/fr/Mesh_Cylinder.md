---
- GuiCommand:/fr
   Name:Mesh BuildRegularSolid
   Name/fr:Mesh Solide régulier
   MenuLocation:Maillages → Solide régulier...
   Workbenches:[Mesh](Mesh_Workbench/fr.md)
---

## Description

La commande **Mesh Solide régulier** crée un solide paramétrique, maillé régulier.

## Utilisation

1.  Il existe plusieurs façons d\'appeler la commande:
    -   Appuyez sur le bouton **<img src="images/Mesh_BuildRegularSolid.svg" width=16px> [Construire un solide régulier](Mesh_BuildRegularSolid/fr.md)
**
    -   Sélectionnez l\'option {{MenuCommand|Maillages → <img src="images/Mesh_BuildRegularSolid.svg" width=16px> Solide régulier...}} dans le menu.
2.  La boîte de dialogue {{MenuCommand|Solide régulier}} s\'ouvre.
3.  Sélectionnez d\'abord un type d\'objet maillé dans la liste déroulante:
    -   
        {{MenuCommand|<img src="images/Mesh_Cube.svg" width=16px> Cube}}
        

    -   
        {{MenuCommand|<img src="images/Mesh_Cylinder.svg" width=16px> Cylindre}}
        

    -   
        {{MenuCommand|<img src="images/Mesh_Cone.svg" width=16px> Cône}}
        

    -   
        {{MenuCommand|<img src="images/Mesh_Sphere.svg" width=16px> Sphère}}
        

    -   
        {{MenuCommand|<img src="images/Mesh_Ellipsoid.svg" width=16px> Ellipsoïde}}
        

    -   
        {{MenuCommand|<img src="images/Mesh_Torus.svg" width=16px> Tore}}
        
4.  Spécifiez les paramètres requis. Les paramètres disponibles dépendent du type d\'objet maillé. Voir [Propriétés](#Properties.md).
5.  Pour les maillages avec des surfaces courbes: une valeur {{MenuCommand|Numérisation}} plus élevée donne un maillage plus fin.
6.  Appuyez sur le bouton {{button|Créer}} pour créer l\'objet maillage.
7.  Créez éventuellement plus d\'objets maillés.
8.  Appuyez sur le bouton {{button|Fermer}} pour fermer la boîte de dialogue et terminer la commande.

## Remarques

-   Les objets maillés créés avec cette commande sont paramétriques. A chaque fois qu\'ils sont recalculés, par exemple après avoir changé l\'un de leurs paramètres, leur maillage est reconstruit. Cela signifie que les manipuler avec des commandes telles que [Mesh Affinage](Mesh_RemeshGmsh/fr.md), [Mesh Echelle](Mesh_Scale/fr.md) etc\... n\'a généralement pas de sens.

## Propriétés

Les objets maillés créés avec cette commande héritent de toutes les propriétés [Mesh Feature](Mesh_Feature/fr.md). De plus, chaque type d\'objet maillé a un certain nombre de propriétés pour contrôler son comportement paramétrique:

### <img alt="" src=images/Mesh_Cube.svg  style="width:32px;"> Cube {#mesh_cube.svg_cube}

### Données


{{TitleProperty|Cube}}

-    {{PropertyData/fr|Hauteur|FloatConstraint}}: hauteur du cube.

-    {{PropertyData/fr|Longueur|FloatConstraint}}: longueur du cube.

-    {{PropertyData/fr|Largeur|FloatConstraint}}: largeur du cube.

### <img alt="" src=images/Mesh_Cylinder.svg  style="width:32px;"> Cylindre {#mesh_cylinder.svg_cylindre}

### Données {#données_1}


{{TitleProperty|Base}}

-    {{PropertyData/fr|Fermé|Bool}}: s\'il est défini sur `False`, les extrémités planes du cylindre restent ouvertes.

-    {{PropertyData/fr|Longueur du contour|FloatConstraint}}: longueur d\'arête des faces dans le maillage.

-    {{PropertyData/fr|Longueur|FloatConstraint}}: longueur du cylindre.

-    {{PropertyData/fr|Rayon|FloatConstraint}}: rayon du cylindre.

-    {{PropertyData/fr|Numérisation|IntegerConstraint}}: nombre de faces le long de la surface courbe.

### <img alt="" src=images/Mesh_Cone.svg  style="width:32px;"> Cône {#mesh_cone.svg_cône}

### Données {#données_2}


{{TitleProperty|Base}}

-    {{PropertyData/fr|Fermé|Bool}}: si mis à `False`, la ou les extrémités planes du cône restent ouvertes.

-    {{PropertyData/fr|Longueur du contour|FloatConstraint}}: longueur d\'arête des faces dans le maillage.

-    {{PropertyData/fr|Longueur|FloatConstraint}}: longueur du cône.

-    {{PropertyData/fr|Rayon 1|FloatConstraint}}: premier rayon du cône. Peut être {{value|0}}.

-    {{PropertyData/fr|Rayon 2|FloatConstraint}}: deuxième rayon du cône. Peut être {{value|0}}.

-    {{PropertyData/fr|Numérisation|IntegerConstraint}}: nombre de faces le long de la surface courbe.

### <img alt="" src=images/Mesh_Sphere.svg  style="width:32px;"> Sphère {#mesh_sphere.svg_sphère}

### Données {#données_3}


{{TitleProperty|Base}}

-    {{PropertyData/fr|Rayon|FloatConstraint}}: rayon de la sphère.

-    {{PropertyData/fr|Numérisation|IntegerConstraint}}: nombre de faces le long des deux directions de la surface courbe.

### <img alt="" src=images/Mesh_Ellipsoid.svg  style="width:32px;"> Ellipsoïde {#mesh_ellipsoid.svg_ellipsoïde}

### Données {#données_4}


{{TitleProperty|Base}}

-    {{PropertyData/fr|Rayon 1|FloatConstraint}}: premier rayon de l\'ellipsoïde.

-    {{PropertyData/fr|Rayon 2|FloatConstraint}}: deuxième rayon de l\'ellipsoïde.

-    {{PropertyData/fr|Numérisation|IntegerConstraint}}: nombre de faces le long des deux directions de la surface courbe.

### <img alt="" src=images/Mesh_Torus.svg  style="width:32px;"> Tore {#mesh_torus.svg_tore}

### Données {#données_5}


{{TitleProperty|Base}}

-    {{PropertyData/fr|Rayon 1|FloatConstraint}}: premier rayon (le principal) du tore.

-    {{PropertyData/fr|Rayon 2|FloatConstraint}}: deuxième rayon du tore.

-    {{PropertyData/fr|Numérisation|IntegerConstraint}}: nombre de faces le long des deux directions de la surface courbe.





{{Mesh Tools navi

}}  