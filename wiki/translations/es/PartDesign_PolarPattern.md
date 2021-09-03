---
- GuiCommand:/es
   Name:PartDesign PolarPattern
   Name/es:DiseñoPieza PatrónPolar
   MenuLocation:DiseñoPieza → Aplicar un patrón → PatrónPolar
   Workbenches:[DiseñoPieza](PartDesign_Workbench/es.md)
---

## Descripción

La herramienta **Patrón polar** crea copias de una operación girando alrededor de un eje seleccionado. A partir de la versión v0.17, se puede crear un patrón polar de múltiples operaciones.

![](images/PartDesign_PolarPattern_example.png )

*Arriba: Un vaciado de una ranura (B) creada sobre un sólido base (A, también referido como soporte) es usada para crear un patrón polar. El resultado (C) se muestra a la derecha.*

## Uso

#### Para crear un patrón {#para_crear_un_patrón}

1.  (Opcional) Seleccionar la operación (u operaciones {{Version/es|0.19}}) que se han de repetir.
2.  Presionar el botón **<img src=images/PartDesign_PolarPattern.svg style="width:24px">** **PatrónPolar** .
    -   Si no hay ninguna operación seleccionada previamente, se puede seleccionar una operación *de una sola pieza* como base.
3.  Definir el **Eje**. Ver [Opciones](#Options/es.md).
4.  Definir el **Ángulo** entre la que será la última copia y la figura original.
5.  Introducir el número de **Apariciones** o copias deseadas.
6.  Si hay varias operaciones en el patrón, su orden puede ser importante, ver la imagen inferior.
7.  Aceptar con **OK**.

#### Ordenar operaciones {#ordenar_operaciones}

![](images/PartDesign_feature-order.gif ) *Efecto del orden de operaciones*


{{Version/es|0.19}}

Se puede cambiar el orden arrastrando la forma deseada en la lista e inmediatamente se puede apreciar el resultado como vista previa.

#### Añadir operaciones {#añadir_operaciones}

###### v0.18

1.  Pulsar el botón **Añadir una operación** para añadir una operación a repetir, la cual debe ser visible en la [vista 3D](3D_view/es.md).
    1.  Ir al árbol de dependencias de la pestaña Modelo.
    2.  Seleccionar en el árbol la operación a añadir y presionar la **barra espaciadora** para hacerla visible en la [vista 3D](3D_view/es.md).
    3.  Volver al panel de tareas.
    4.  Seleccionar la operación en la vista 3D; será añadida a la lista.
    5.  Repetir para añadir más operaciones.

###### v0.19

1.  Pulsar el botón **Añadir una operación** para añadir una operación a repetir.
    1.  Ir al árbol de dependencias de la pestaña Modelo.
    2.  Seleccionar en el árbol la operación que se tiene que añadir.
    3.  Repetir para añadir más operaciones.

#### Eliminar operaciones {#eliminar_operaciones}

-   Pinchar con botón derecho del ratón sobre la operación en la lista y seleccionar *Eliminar*.

o

###### v0.18 {#v0.18_1}

1.  Pulsar el botón **Eliminar operación** para eliminar una operación de la lista, la cual debe ser visible en la [vista 3D](3D_view/es.md).
    1.  Ir al árbol de dependencias de la pestaña Modelo.
    2.  Seleccionar en el árbol la operación que se tiene que eliminar y presionar la **barra espaciadora** para hacerla visible en la [vista 3D](3D_view/es.md).
    3.  Volver al panel de tareas.
    4.  Seleccionar la operación en la vista 3D; habrá sido eliminada la lista.
    5.  Repetir para eliminar más operaciones.

###### v0.19 {#v0.19_1}

1.  Presionar **Eliminar operación** para eliminar una operación de la lista.
2.  Ir al árbol de dependencias de la pestaña Modelo.
3.  Seleccionar en el árbol la operación a eliminar.
4.  Repetir para eliminar más operaciones.

## Opciones

![](images/Polarpattern_parameters.png )

### Eje

Cuando se crea una operación de patrón polar, la ventana de diálogo *PolarPattern parameters* ofrece diferentes maneras de especificar el eje de rotación del patrón.

#### Eje normal del boceto {#eje_normal_del_boceto}

Se toma como eje para el patrón polar un eje que es normal al boceto y que comienza en el origen del boceto de la operación.
La dirección del patrón puede invertirse pinchando la casilla \'Reverse direction\'.

#### Eje horizontal del boceto {#eje_horizontal_del_boceto}

Usa el eje horizontal del boceto como eje.

#### Eje vertical del boceto {#eje_vertical_del_boceto}

Usa el eje vertical del boceto como eje.

#### Eje del boceto personalizado {#eje_del_boceto_personalizado}

Si el boceto que define la operación a copiar contiene también una línea o líneas de construcción, la lista desplegable contendrá un eje de boceto personalizado por cada línea de construcción. La primera línea de construcción se llamará \'Línea de construcción 1\'.

#### Eje base (X/Y/Z) {#eje_base_xyz}


{{Version/es|0.17 o posteriores}}

Seleccionar uno de los ejes estándar de Origen del Body (cuerpo) (X, Y o Z) como eje.

#### Seleccione referencia\... {#seleccione_referencia...}

Permite al usuario seleccionar una Línea de referencia o una arista de un objeto, o una línea de un boceto para usarla como eje.

### Ángulo y repeticiones {#ángulo_y_repeticiones}

Especifica el ángulo a ser cubierto por el patrón, y el número total de formas repetidas (incluyendo la operación original). Por ejemplo, cuatro repeticiones en un ángulo de 280 grados dará un espaciado de 60 grados entre repeticiones. Excepción: Si el ángulo es de 360 grados, como la primera y la última repetición son idénticas, 4 repeticiones quedarán separadas 90 grados. {{Clear}}

## Limitaciones

-   Ver [Patrón lineal Limitaciones](PartDesign_LinearPattern/es#Limitations.md).








{{PartDesign Tools navi

}} 