---
- GuiCommand:/es
   Name:Draft Edit
   Name/es:Borrador Edición
   MenuLocation:Modificación → Editar<br>Utilidades → Editar
   Workbenches:[Borrador](Draft_Workbench/es.md), [Arquirectura](Arch_Workbench/es.md)
   Shortcut:**D** **E**
   SeeAlso:[Std Edición](Std_Edit/es.md)
---


</div>

## Descripción

El <img alt="" src=images/Draft_Edit.svg  style="width:24px;"> comando **Borrador Edición** pone los objetos seleccionados en modo de Borrador Edición. En este modo las propiedades de los objetos pueden ser editadas gráficamente. Típicamente los nodos pueden ser movidos y en algunos casos las opciones del menú contextual pueden ser seleccionadas. El comando puede manejar la mayoría de los objetos de borrador, pero también algunos otros objetos. Ver [Objetos soportados](#Objetos_soportados.md). Los objetos de borrador soportados también pueden ponerse en modo de edición de borrador con el comando [Std Edición ](Std_Edit/es.md).

![](images/Draft_Edit_example.png ) *4 objetos en el modo de Borrador Edición: un Borrador Hilo (rojo), un Borrador Arco (negro), un Borrador BSpline (verde) y un Borrador de BezCurva (magenta)*

## Utilización

Ver también: [Borrador Atrapar](Draft_Snap/es.md) y [Borrador Restringir](Draft_Constrain/es.md).

1.  Opcionalmente, seleccione uno o más objetos. Tenga en cuenta que aunque varios objetos pueden estar en modo de edición de borrador, los objetos sólo pueden editarse de uno en uno.
2.  Hay varias formas de invocar el comando:
    -   Si aún no ha seleccionado un objeto: haga doble clic en un objeto en la [Vista de árbol](Tree_view.md). Esto sólo funciona para los objetos de borrador compatibles.
    -   Pulse el **<img src="images/Draft_Edit.svg" width=16px> [Borrador Edición ](Draft_Edit/es.md)**.
    -   Seleccione la opción {{MenuCommand|Modificación → <img src="images/Draft_Edit.svg" width=16px> Editar}} del menú.
    -   Seleccione la opción {{MenuCommand|Utilidades → <img src="images/Draft_Edit.svg" width=16px> Editar}} en el menú.
    -   Utilice el atajo de teclado: **D** y luego **E**.
3.  Si aún no ha seleccionado ningún objeto: seleccione un objeto en la [Vista 3D](3D_view/es.md).
4.  Los objetos seleccionados se marcan con nodos temporales, y se abre el [Panel de tareas principales](#Panel_de_tareas_principales.md). Ver [Opciones](#Opciones.md) para más información.
5.  Opcionalmente utilizar un menú contextual de nodos o aristas. Estos menús contextuales sólo están disponibles para algunos objetos de borrador. Ver [Objetos soportados](#Objetos_soportados.md) para más información.
    -   Haga una de las siguientes cosas:
        -   En todos los sistemas operativos: mantenga pulsada **E** y haga clic en el nodo o borde. Para usar **E** puede que tengas que hacer clic en la [vista 3D](3D_view/es.md) una vez para asegurarte de que tiene el foco.
        -   En Windows: mantén pulsado **Alt** y haz clic en el nodo o borde.
        -   En Linux: mantén pulsado **Shift**+**Alt**, **Ctrl**+**Alt** o **Alt**, y haz clic en el nodo o borde.
        -   En macOS: mantén pulsado **Option** y haz clic en el nodo o arista.
    -   Selecciona una opción del menú contextual.
    -   Si la opción seleccionada requiere la introducción de puntos:
        -   Se abre el [Panel\_de\_tareas\_del\_nodo](#Panel_de_tareas_del_nodo.md). Ver [Opciones](#Opciones.md) para más información.
        -   Elige un punto en la [Vista 3D](3D_view/es.md), o escribe las coordenadas y pulsa el **<img src="images/Draft_AddPoint.svg" width=16px> Introducir punto** botón.
6.  Opcionalmente mueva un nodo:
    -   Haz clic en el nodo en la [Vista 3D](3D_view/es.md).
    -   Se abre el [Panel de tareas del nodo](#Panel_de_tareas_del_nodo.md). Ver [Opciones](#Opciones.md) para más información.
    -   Elige un punto en la [Vista 3D](3D_view/es.md), o escribe las coordenadas y pulsa el **<img src="images/Draft_AddPoint.svg" width=16px> Introducir punto** botón.
    -   El resultado depende del objeto y del nodo seleccionado.
7.  Presiona **Esc** o el botón **Close** para finalizar el comando

## Opciones

Los atajos de teclado de un solo carácter mencionados aquí pueden ser cambiados. Véase [Borrador Preferencias](Draft_Preferences/es.md).

### Panel de tareas Principal {#panel_de_tareas_principal}

-   Pulse **O** o el **<img src="images/Draft_CloseLine.svg" width=16px> Cerrar** para finalizar el comando. Si se ha seleccionado un solo [Borrador Hilo](Draft_Wire/es.md) se cierra el hilo.
-   Pulse **Esc** o el botón **Close** para finalizar el comando.

### Panel de tareas Nodo {#panel_de_tareas_nodo}

-   Para introducir manualmente las coordenadas introduzca el componente X, Y y Z, y pulse **Enter** después de cada una. O puede pulsar el **<img src="images/Draft_AddPoint.svg" width=16px> Introducir punto** cuando tenga los valores deseados. Es aconsejable mover el puntero fuera de la [Vista 3D](3D_view/es.md) antes de introducir las coordenadas.
-   Para utilizar coordenadas polares introduzca un valor para el {{MenuCommand|Length}} y un valor para el {{MenuCommand|Angle}}, y pulse **Enter** después de cada uno.
-   Marque la casilla {{MenuCommand|Angle}} para restringir el puntero al ángulo especificado.
-   La casilla {{MenuCommand|Relative}} no tiene sentido para este comando.
-   Pulse **G** o haga clic en la casilla {{MenuCommand|Global}} para activar el modo global. Si el modo global está activado, las coordenadas son relativas al sistema de coordenadas global, de lo contrario son relativas al sistema de coordenadas del [plano de trabajo](Draft_SelectPlane/es.md). {{Versión|0.20}}
-   La casilla {{MenuCommand|Continue}} no tiene ningún propósito para este comando.
-   Pulse **S** para activar o desactivar el ajuste de borradores.
-   El **<img src="images/Draft_UndoLine.svg" width=16px> Deshacer** no tiene ningún propósito para este comando.

## Objetos soportados {#objetos_soportados}

### <img alt="" src=images/Draft_Line.svg  style="width:24px;"> [Borrador Línea](Draft_Line/es.md) and <img alt="" src=images/Draft_Wire.svg  style="width:24px;"> [Borrador Hilo](Draft_Wire/es.md) {#draft_line.svg_borrador_línea_and_draft_wire.svg_borrador_hilo}

-   Si el nodo inicial o final de un cable abierto se mueve de forma que coincidan, el cable se cierra.
-   Menú contextual del nodo: {{Value|borrar punto}}. Deben quedar al menos dos puntos.
-   Menú contextual de la arista: {{Value|añadir punto}}, {{Value|invertir cable}} ({{Version/es|0.20}}).

### <img alt="" src=images/Draft_Arc.svg  style="width:24px;"> [Borrador Arco](Draft_Arc/es.md) y <img alt="" src=images/Draft_Arc_3Points.svg  style="width:24px;"> [Borrador Arco 3Puntos](Draft_Arc_3Points/es.md) {#draft_arc.svg_borrador_arco_y_draft_arc_3points.svg_borrador_arco_3puntos}

-   Menú contextual del nodo central: {{Value|mover arco}}.
-   Menú contextual del nodo de inicio: {{Value|poner el primer ángulo}}.
-   Menú contextual del nodo final: {{Value|poner el último ángulo}}.
-   Menú contextual del nodo medio: {{Value|poner radio}}.
-   Menú contextual del borde: {{Value|invertir arco}}. Actualmente esto no funciona.

### <img alt="" src=images/Draft_Circle.svg  style="width:24px;"> [Borrador Círculo](Draft_Circle/es.md) {#draft_circle.svg_borrador_círculo}

-   No hay menús contextuales para este objeto.

### <img alt="" src=images/Draft_Ellipse.svg  style="width:24px;"> [Borrador Elipse](Draft_Ellipse/es.md) {#draft_ellipse.svg_borrador_elipse}

-   No hay menús contextuales para este objeto.

### <img alt="" src=images/Draft_Rectangle.svg  style="width:24px;"> [Borrador Rectángulo](Draft_Rectangle/es.md) {#draft_rectangle.svg_borrador_rectángulo}

-   No hay menús contextuales para este objeto.

### <img alt="" src=images/Draft_Polygon.svg  style="width:24px;"> [Borrador Polígono](Draft_Polygon/es.md) {#draft_polygon.svg_borrador_polígono}

-   No hay menús contextuales para este objeto.

### <img alt="" src=images/Draft_BSpline.svg  style="width:24px;"> [Borrador BSpline](Draft_BSpline/es.md) {#draft_bspline.svg_borrador_bspline}

-   Si el nodo inicial o final de una spline abierta se mueve de forma que coincidan, la spline se cierra.
-   Menú contextual del nodo: {{Value|borrar punto}}. Para una spline abierta deben quedar al menos dos puntos. Para una spline cerrada el número mínimo de puntos es de tres.
-   Menú contextual de la arista: {{Value|añadir punto}}.

### <img alt="" src=images/Draft_CubicBezCurve.svg  style="width:24px;"> [Borrador CúbicaBezCurva](Draft_CubicBezCurve/es.md) y <img alt="" src=images/Draft_BezCurve.svg  style="width:24px;"> [Borrador BezCurva](Draft_BezCurve/es.md) {#draft_cubicbezcurve.svg_borrador_cúbicabezcurva_y_draft_bezcurve.svg_borrador_bezcurva}

-   If the start or end node of an open curve is moved so that they coincide, the curve is closed.
-   Node context menu: {{Value|make sharp}}, {{Value|make tangent}}, {{Value|make symmetric}} and {{Value|delete point}}.
-   Edge context menu: {{Value|add point}}.

### <img alt="" src=images/Draft_Dimension.svg  style="width:24px;"> [Draft Dimension](Draft_Dimension.md) {#draft_dimension.svg_draft_dimension}

-   Angular dimensions cannot be edited.
-   The start and end nodes of parametric dimensions cannot be moved.
-   No context menus for this object.

### <img alt="" src=images/Arch_Wall.svg  style="width:24px;"> [Arch Wall](Arch_Wall.md) {#arch_wall.svg_arch_wall}

-   A single node to control the height of the wall is displayed above the **Placement** of the wall.
-   No context menus for this object.

### <img alt="" src=images/Arch_Structure.svg  style="width:24px;"> [Arch Structure](Arch_Structure.md) {#arch_structure.svg_arch_structure}

-   No hay menús contextuales para este objeto.

### <img alt="" src=images/Arch_Window.svg  style="width:24px;"> [Arch Window](Arch_Window.md) {#arch_window.svg_arch_window}

-   No hay menús contextuales para este objeto.

### <img alt="" src=images/Arch_Space.svg  style="width:24px;"> [Arch Space](Arch_Space.md) {#arch_space.svg_arch_space}

-   No hay menús contextuales para este objeto.

### <img alt="" src=images/Arch_Panel_Cut.svg  style="width:24px;"> [Arch Panel Cut](Arch_Panel_Cut.md) {#arch_panel_cut.svg_arch_panel_cut}

-   No hay menús contextuales para este objeto.

### <img alt="" src=images/Arch_Panel_Sheet.svg  style="width:24px;"> [Arch Panel Sheet](Arch_Panel_Sheet.md) {#arch_panel_sheet.svg_arch_panel_sheet}

-   No hay menús contextuales para este objeto.

### <img alt="" src=images/Part_Box.svg  style="width:24px;"> [Part Box](Part_Box.md) {#part_box.svg_part_box}

-   No hay menús contextuales para este objeto.

### <img alt="" src=images/Part_Cylinder.svg  style="width:24px;"> [Part Cylinder](Part_Cylinder.md) {#part_cylinder.svg_part_cylinder}

-   No hay menús contextuales para este objeto.

### <img alt="" src=images/Part_Sphere.svg  style="width:24px;"> [Part Sphere](Part_Sphere.md) {#part_sphere.svg_part_sphere}

-   No hay menús contextuales para este objeto.

### <img alt="" src=images/Part_Cone.svg  style="width:24px;"> [Part Cone](Part_Cone.md) {#part_cone.svg_part_cone}

-   No hay menús contextuales para este objeto.

### <img alt="" src=images/Part_Line.svg  style="width:24px;"> [Part Line](Part_Line.md) {#part_line.svg_part_line}

-   No hay menús contextuales para este objeto.

### <img alt="" src=images/Sketcher_NewSketch.svg  style="width:24px;"> [Sketcher Sketch](Sketcher_NewSketch.md) {#sketcher_newsketch.svg_sketcher_sketch}

-   Sólo se pueden editar los croquis que contengan una sola línea sin restricciones. Actualmente esto no funciona correctamente.
-   No hay menús contextuales para este objeto.

## Preferencias

Ver también: [Editor de preferencias](Preferences_Editor/es.md) y [Borrador Preferencias](Draft_Preferences/es.md).

-   El color de los nodos temporales es el mismo que el color de los símbolos atrapar. Este color se puede cambiar en las preferencias: {{MenuCommand|Edición → Preferencias... → Borrador → Ajustes visuales → Color}}. Tenga en cuenta que este color no se utiliza para los nodos temporales que se muestran para [Borrador BezCurvas](Borrador_BezCurve/es.md). Estos nodos utilizan el **Color de la línea** de la curva en su lugar.

## Guión

Ver también: [Documentación de la API autogenerada](https://freecad.github.io/SourceDoc/) y [Fundamentos de FreeCAD Guión](FreeCAD_Scripting_Basics/es.md).

No hay ningún método en Python para editar borradores de objetos. Para emular los resultados del comando hay que modificar las propiedades geométricas de los objetos.


<div class="mw-translate-fuzzy">





</div>


 