---
- GuiCommand:/es
   Name:Draft CircularArray
   Name/es:Borrador ArregloCircular
   MenuLocation:Modificación → Herramientas de  Arreglo → Arreglo Circular
   Workbenches:[Borrador](Draft_Module/es.md), [Arquitectura](Arch_Module/es.md)
   Version:0.19
   SeeAlso:[Borrador OrthoArray](Draft_OrthoArray/es.md), [Borrador ArregloPolar](Draft_PolarArray/es.md), [Borrador ArregloRuta](Draft_PathArray/es.md), [Borrador ArregloEnlaceRuta](Draft_PathLinkArray/es.md), [Borrador ArregloPunto](Draft_PointArray/es.md), [Borrador ArregloEnlacePunto](Draft_PointLinkArray/es.md)
---


</div>

## Descripción

El <img alt="" src=images/Draft_CircularArray.svg  style="width:24px;"> comando **Borrador ArregloCircular** crea un arreglo a partir de un objeto seleccionado colocando copias a lo largo de circunferencias concéntricas. El comando puede crear opcionalmente un arreglo [Enlace](App_Link/es.md), que es más eficiente que un arreglo normal.


<div class="mw-translate-fuzzy">

El comando puede usarse en objetos 2D creados con el [Ambiente de Trabajo Borrador](Draft_Module/es.md) o [Ambiente de Trabajo Dibujo](Sketcher_Workbench/es.md), pero también en muchos objetos 3D como los creados con el [Ambiente de Trabajo Pieza](Part_Workbench/es.md), [Ambiente de Trabajo DiseñoPieza](PartDesign_Workbench/es.md) o [Ambiente de Trabajo Arquitectura](Arch_Workbench/es.md).


</div>

<img alt="" src=images/Draft_CircularArray_example.png  style="width:400px;"> 
*Borrador ArregloCircular*

## Utilización

Ver también: [Borrador Atrapar](Draft_Snap/es.md)

1.  Opcionalmente selecciona un objeto.
2.  Hay varias formas de invocar el comando:
    -   Pulsar el **<img src="images/Draft_CircularArray.svg" width=16px> [Borrador ArregloCircular](Draft_CircularArray/es.md)**.
    -   Selecciona la opción {{MenuCommand|Modificación → Herramientas de arreglo →<img src="images/Draft_CircularArray.svg" width=16px> Arreglo circular}} opción del menú.
3.  Se abre el panel de tareas {{MenuCommand|Arreglo circular}}. Ver [Opciones](#Opciones.md) para más información.
4.  Si aún no ha seleccionado ningún objeto: seleccione un objeto.
5.  Introduzca los parámetros necesarios en el panel de tareas.
6.  Para terminar el comando haga una de las siguientes cosas:
    -   Elija un punto en la [Vista 3D](3D_view/es.md) para el {{MenuCommand|Centro de rotación}}.
    -   Pulsa **Enter**.
    -   Pulsar el botón **Aceptar**.

## Opciones

-   Enter the {{MenuCommand|Radial distance}} to specify the distance between the circular layers, and between the center and the first circular layer.
-   Enter the {{MenuCommand|Tangential distance}} to specify the distance between the elements on the same circular layer. Must be larger than zero.
-   Enter the {{MenuCommand|Number of circular layers}}. The element at the center counts as one layer. Must be at least {{Value|2}}. The maximum that can be entered in the task panel is {{Value|99}}, but higher values are possible by changing the **Number Circles** property of the array.
-   Enter the {{MenuCommand|Symmetry}} value. This number determines how the elements are distributed. A value of {{Value|3}}, for example, results in a pattern with three equal 120° pie segments. Larger values for the {{MenuCommand|Symmetry}} and the {{MenuCommand|Tangential distance}} result in fewer or even no elements on the inner layers.
-   Pick a point in the [3D view](3D_view.md), note that this will also finish the command, or type coordinates for the {{MenuCommand|Center of rotation}}. The rotation axis of the array will pass through this point. It is advisable to move the pointer out of the [3D view](3D_view.md) before entering coordinates.
-   Press the {{MenuCommand|Reset point}} button to reset the {{MenuCommand|Center of rotation}} to the origin.
-   If the {{MenuCommand|Fuse}} checkbox is checked overlapping elements in the array are fused. This does not work for Link arrays.
-   If the {{MenuCommand|Link array}} checkbox is checked a Link array instead of a regular array is created. A Link array is more efficient because its elements are [App Link](App_Link.md) objects.
-   Press **Esc** or the **Cancel** button to abort the command.

## Notas

-   The default rotation axis for the array is the positive Z axis. This can be changed by editing its **Axis** property.
-   A Draft CircularArray can be turned into a [Draft OrthoArray](Draft_OrthoArray.md) or a [Draft PolarArray](Draft_PolarArray.md) by changing its **Array Type** property.
-   A Link array cannot be turned into a regular array or vice versa. The type of array must be decided at creation time.

## Preferences

See also: [Preferences Editor](Preferences_Editor.md) and [Draft Preferences](Draft_Preferences.md).

-   To change the number of decimals used for the input of coordinates and distances: {{MenuCommand|Edit → Preferences... → General → Units → Units settings → Number of decimals}}.

## Propiedades

See [Draft OrthoArray](Draft_OrthoArray#Properties.md).

## Guión

See also: [Autogenerated API documentation](https://freecad.github.io/SourceDoc/) and [FreeCAD Scripting Basics](FreeCAD_Scripting_Basics.md).

To create a circular array use the `make_array` method (<small>(v0.19)</small> ) of the Draft module. This method replaces the deprecated `makeArray` method. The `make_array` method can create [Draft OrthoArrays](Draft_OrthoArray.md), [Draft PolarArrays](Draft_PolarArray.md) and Draft CircularArrays. For each array type one or more wrappers are available.

The main method:


```python
array = make_array(base_object, arg1, arg2, arg3, arg4=None, arg5=None, arg6=None, use_link=True)
```

The wrapper for circular arrays is:


```python
array = make_circular_array(base_object,
                            r_distance=100, tan_distance=50,
                            number=3, symmetry=1,
                            axis=App.Vector(0, 0, 1), center=App.Vector(0, 0, 0),
                            use_link=True)
```

-    `base_object`is the object to be arrayed. It can also be the `Label` (string) of an object in the current document.

-    `r_distance`and `tan_distance` are the radial and tangential distances between the elements.

-    `number`is the number of circular layers in the pattern, the original object counts as the first layer.

-    `symmetry`is an integer used in some calculations that affect the way the elements are distributed around the circumferences. Usual values are from 1 to 6. Higher values are not recommended and will make the elements in the inner layers disappear.

-    `axis`and `center` are vectors that describe the direction of the axis of rotation, and a point through which that axis passes.

-   If `use_link` is `True` the created elements are [App Links](App_Link.md) instead of regular copies.

-    `array`is returned with the created array object.

Ejemplo:


```python
import FreeCAD as App
import Draft

doc = App.newDocument()

tri = Draft.make_polygon(3, 600)

array = Draft.make_circular_array(tri, 1800, 1200, 4, 1)
doc.recompute()
```


<div class="mw-translate-fuzzy">





</div>


 