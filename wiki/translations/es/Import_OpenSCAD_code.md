


{{TutorialInfo/es
|Topic= Importar código OpenSCAD
|Level= Principiante
|Time= 30 minutos
|Author=r-frank
|FCVersion=0.16.6704
|Files=
}}

## Introducción

OpenSCAD, al igual que FreeCAD, es un programa de CAD 3D de código abierto. Pero mientras FreeCAD utiliza un enfoque visual, OpenSCAD utiliza una interfaz de programación para realizar operaciones 3D. El banco de trabajo de OpenSCAD puede utilizarse para importar el código de objetos de OpenSCAD y para tener acceso a algunas de las operaciones de malla posibles con OpenSCAD.

## Instalación de OpenSCAD {#instalación_de_openscad}

-   Los usuarios de Linux pueden instalar desde los repositorios de la distribución correspondiente, como Debian, openSUSE, Mint, Unbuntu, etc. o desde la página web [OpenSCAD página web](http://www.openscad.org/).
-   Los usuarios de Mac pueden descargar los binarios desde [OpenSCAD página web](http://www.openscad.org/).
-   Los usuarios de Windows pueden descargar el programa desde [OpenSCAD página web](http://www.openscad.org/). Dado que FreeCAD sólo necesita el ejecutable de OpenSCAD, los usuarios de Windows pueden instalar la versión portátil si lo desean.

## Configurar el ambiente de trabajo de OpenSCAD en FreeCAD {#configurar_el_ambiente_de_trabajo_de_openscad_en_freecad}


<div class="mw-translate-fuzzy">

-   Abre FreeCAD.
-   Cambia a [OpenSCAD Ambiente de trabajo](OpenSCAD_Workbench/es.md).
-   Elige Edición → Preferencias → OpenSCAD en el menú superior.
    -   Apunta FreeCAD al ejecutable de OpenSCAD (sección: Ajustes generales de OpenSCAD).
    -   Todos los demás valores de la página de configuración pueden dejarse por defecto.


</div>

## El modelo de muestra {#el_modelo_de_muestra}

Aquí usaremos el archivo example005.scad de los (antiguos) ejemplos de OpenSCAD, pero siéntase libre de usar cualquier archivo scad de su agrado.

<img alt="" src=images/TutorialOpenSCAD_SampleFile.jpg  style="width:800px;">

## Importar el modelo en FreeCAD {#importar_el_modelo_en_freecad}

-   En FreeCAD sólo tienes que elegir ** Archivo** → **Abrir** y elige el archivo .scad que quieras importar.
-   No es importante qué ambiente de trabajo está activado, el propio ambiente de trabajo de OpenSCAD sólo es necesario cuando se aplican características especiales a su modelo.
-   FreeCAD importará el archivo OpenSCAD y construirá un árbol con primitivas y operaciones booleanas
-   Tutorial terminado.

<img alt="" src=images/TutorialOpenSCAD_ImportFile.jpg  style="width:800px;">

## Relacionados

-   [FreeCAD Cómo Importar Exportar](FreeCAD_Howto_Import_Export/es.md)
-   \[\[Import\_Export\_Preference/es\|Preferencias de importación y exportación

\]\]

[Category:OpenSCAD{{\#translation:}}](Category:OpenSCAD.md)