


<div class="mw-translate-fuzzy">





</div>

## Description


<div class="mw-translate-fuzzy">

En plus de l\'exportateur standard FreeCAD **[.OBJ](http://fr.wikipedia.org/wiki/Objet_3D_(format_de_fichier))**, l\'[atelier Arch](Arch_Module/fr.md) dispose d\'une solution alternative d\'exportation qui exporte les faces coplanaires comme des faces OBJ entières, au lieu de trianguler les objets basés sur les [Shape](Shape/fr.md), comme le fait l\'exportateur standard.


</div>

## Exporter sans GUI {#exporter_sans_gui}

L\'exportation sans l\'interface graphique est possible à partir de la ligne de commande, en utilisant uniquement l\'exportateur de l\'[atelier Mesh](Mesh_Workbench/fr.md).

Dans cet exemple, un fichier STEP est importé, les couleurs de [Shape](Shape/fr.md) sont sauvegardées, puis un maillage est généré, les couleurs de l\'objet d\'origine sont réappliquées sur les faces du nouveau maillage, qui est ensuite exporté au format OBJ. Comme cela est fait avec l\'Atelier Mesh, le résultat est un maillage triangulé.


```python
import Mesh
import MeshPart
import Import

data = Import.open("example.stp")
shape = data[0][0].Shape
shape_colors = data[0][1]

mesh = MeshPart.meshFromShape(Shape=shape, LinearDeflection=0.1, Segments=True)

face_colors = [(0, 0, 0)] * mesh.CountFacets

for i in range(mesh.countSegments()):
    color = shape_colors[i]
    segm = mesh.getSegment(i)
    for j in segm:
        face_colors[j] = color

mesh.write(Filename="new_example.obj", Material=face_colors, Format="obj")
```

## Plus d\'informations {#plus_dinformations}

-   [Convertir STEP en Wavefront OBJ avec les couleurs des faces](https://forum.freecadweb.org/viewtopic.php?f=8&t=37452)

## Tutoriels

-   [Importe un fichier STL ou OBJ](Import_from_STL_or_OBJ/fr.md)
-   [Exporte un fichier STL ou OBJ](Export_to_STL_or_OBJ/fr.md)


<div class="mw-translate-fuzzy">





</div>


 

[Category:File Formats{{\#translation:}}](Category:File_Formats.md)