# <img alt="El icono del Ambiente de trabajo Imagen" src=images/Workbench_Image.svg  style="width:64px;"> Image Workbench/es


{{TOCright}}

## Introducción

El <img alt="" src=images/Workbench_Image.svg  style="width:24px;"> [Ambiente de trabajo Imagen](Image_Workbench/es.md) gestiona diferentes tipos de imágenes [bitmap](bitmap/es.md), y te permite abrirlas en FreeCAD.

## Herramientas


<div class="mw-translate-fuzzy">

-   <img alt="" src=images/Image_Open.svg  style="width:32px;"> [Abrir](Image_Open/es.md): abrir una imagen en un nuevo viewport.
-   <img alt="" src=images/Image-import-to-plane.svg  style="width:32px;"> [Importar al plano](Image_CreateImagePlane/es.md): importar una imagen a un plano en la vista 3D.
-   <img alt="" src=images/Image-scale.svg  style="width:32px;"> [Escalar](Image_Scaling/es.md): escalar una imagen importada a un plano.


</div>

## Características

-   Como un [Boceto](Sketcher_Workbench/es.md), una imagen importada puede ser adjuntada a uno de los planos principales XY, XZ, o YZ, y se le da un desplazamiento positivo o negativo.
-   La imagen se importa con relación de 1 píxel a 1 milímetro.
-   La recomendación es que la imagen importada tenga una resolución razonable.

## Workflow


<div class="mw-translate-fuzzy">

## Flujo de trabajo 

Un uso principal de este ambientes de trabajo es trazar sobre la imagen, con las herramientas [Borrador](Draft_Workbench/es.md) o [Croquizador](Sketcher_Workbench/es.md), para generar un cuerpo sólido basado en los contornos de la imagen.


</div>

Trazar sobre una imagen funciona mejor si la imagen tiene un pequeño relleno negativo, por ejemplo, -0,1 mm, desde el plano de trabajo. Esto significa que la imagen estará ligeramente por detrás del plano donde dibujas tu geometría 2D, por lo que no dibujarás sobre la propia imagen.

El relleno de la imagen puede establecerse durante la importación, o modificarse posteriormente a través de sus propiedades.





{{Image Tools navi

}}



---
![](images/Right_arrow.png) [documentation index](../README.md) > [Workbenches](Category_Workbenches.md) > [Image](Category_Image.md) > Image Workbench/es
