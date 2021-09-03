


{{TutorialInfo/fr
|Topic=Exportation de fichier STL ou OBJ
|Level=Débutant
|Time=20 minutes
|Author=r-frank
|FCVersion=0.16.6703
}}

## Introduction

Dans ce tutoriel, nous allons découvrir comment exporter les fichiers de FreeCAD au formats STL/OBJ. Les formats de maillage STL/OBJ n\'ont aucune dimension. L\'exportation par FreeCAD supposera que l\'unité utilisée dans le modèle est exprimée en mm. Si cela n\'est pas le cas, vous devrez convertir votre projet en mm. Une façon de faire est d\'utiliser <img alt="" src=images/Draft_Scale.svg  style="width:24px;"> [Draft Échelle](Draft_Scale/fr.md).

## Faire un test {#faire_un_test}

Vous pouvez utiliser votre propre fichier FreeCAD, mais vous pouvez aussi créer un fichier test

-   ouvrir FreeCAD
-   Créer un nouveau document
-   Basculer sur l\'<img alt="" src=images/Workbench_Part.svg  style="width:24px;"> [atelier Part](Part_Workbench/fr.md)
-   Insérer un cube <img alt="" src=images/Part_Box.svg  style="width:32px;"> [Part Cube](Part_Box/fr.md)
-   Insérer un cône <img alt="" src=images/Part_Cone.svg  style="width:32px;"> [Part Cône](Part_Cone/fr.md)
-   Sélectionnez les deux objets dans la [Vue en arborescence](Tree_view/fr.md)
-   Créer une fusion avec les deux éléments <img alt="" src=images/Part_Fuse.svg  style="width:32px;"> [Part Union](Part_Fuse/fr.md)
-   Sauvegarder votre fichier.

## Méthode d\'exportation 1: Utilisation de \"Fichier → Exporter\" {#méthode_dexportation_1_utilisation_de_fichier_exporter}

-   Sélectionnez le solide à exporter dans la vue arborescente.
-   Choisissez **Fichier** → **Exporter...** et définissez le type de fichier sur \"STL mesh (\*.stl \*.ast)\".
-   Entrez votre nom de fichier. L\'extension par défaut est \".stl\". Vous devez inclure l\'extension \".ast\" dans le nom du fichier pour générer un fichier .ast. Choisissez **Sauvegarder**.

## Méthode d\'exportation 2: Utiliser l\'atelier Mesh dans FreeCAD {#méthode_dexportation_2_utiliser_latelier_mesh_dans_freecad}

-   Basculez vers le <img alt="" src=images/Workbench_Mesh.svg  style="width:24px;"> [Atelier Mesh](Mesh_Workbench/fr.md).
-   Sélectionnez le solide à mailler dans la vue arborescente.
-   Choisissez **Maillages** → **<img src="images/Mesh_FromPartShape.svg" width=32px> Créez un maillage à partir de la forme...** à partir du menu principal (supérieur).
-   Sélectionnez l\'un des mailleurs disponibles et spécifiez les options disponibles. Pour plus d\'informations, voir [Mesh Maillage à partir d\'une forme‏‎](Mesh_FromPartShape/fr.md).
-   Choisissez **OK**. L\'objet maillé sera créé dans l\'arborescence (avec l\'icône de maillage verte <img alt="" src=images/Workbench_Mesh.svg  style="width:16px;">).
-   Cliquez avec le bouton droit de la souris sur l'objet maillé dans l'arborescence et choisissez **<img src="images/Mesh_ExportMesh.png" width=32px> Exporter le maillage...**.
-   Remplissez le nom du fichier; l\'extension n\'est pas nécessaire. L\'extension sera définie en fonction du type de fichier. Si vous incluez une extension qui ne correspond pas au type de fichier sélectionné, une extension pour le type sélectionné sera ajoutée lors de l\'enregistrement du fichier. Si vous incluez une extension qui correspond au type de fichier, aucune extension supplémentaire ne sera ajoutée.
-   Le type de fichier par défaut est un \"Binary STL (\*.stl)\". Changez le type si vous le souhaitez.
-   Choisissez **Sauvegarder**.

## Quelle méthode choisir? {#quelle_méthode_choisir}

La méthode 2 doit être préférée. Parmi les raisons:

-   Lorsque vous avez plusieurs corps à convertir, vous pouvez utiliser les outils de l\'<img alt="" src=images/Workbench_Mesh.svg  style="width:24px;"> [Atelier Mesh](Mesh_Workbench/fr.md). Par exemple, vous pouvez fusionner des maillages avant d'exporter.
-   Les surfaces courbes sont représentées en STL comme une série de segments en ligne droite générés par tessellation. Il en résulte des dimensions intérieures légèrement sous-dimensionnées pour les surfaces courbes. Si vous exportez pour une utilisation en impression 3D, cela peut entraîner un trou de taille insuffisante, par exemple. Dans ce cas, vous aurez peut-être besoin d\'une valeur de tessellation plus fine. Lors de l\'exportation à partir d\'un autre atzlier, utilisez **Fichier** → **Exporter...**, le pavage est contrôlé par le pavage d\'affichage général défini dans **Edition** → **Préférences...** → Part Design → Mode d\'affichage. Cependant, étant donné que ces paramètres contrôlent le pavage utilisé pour rendre les formes à l'affichage, leur diminution ralentira le rendu de l'affichage, de manière significative. De plus, l\'exportation immédiatement après avoir changé la valeur de préférence de pavage d\'affichage n\'aura pas l\'effet souhaité, car le pavage d\'affichage n\'est pas mis à jour immédiatement. Il faut forcer un changement dans le modèle sous-jacent pour recalculer la tessellation - par exemple, en modifiant un paramètre d\'esquisse (le ramener à sa valeur initiale suffira).

## Liens

-   [Importer un fichier STL ou OBJ](Import_from_STL_or_OBJ/fr.md)
-   [Import Export](Import_Export/fr.md)




[Category:File\_Formats{{\#translation:}}](Category:File_Formats.md)