

## Introducción


{{TOCright}}

En FreeCAD la palabra \"[Croquis](Sketch/es.md)\" se usa normalmente para referirse a un [Croquizador CroquisObjeto](Sketcher_SketchObject/es.md) (`Sketcher::SketchObject` clase) que es definida por el [Ambiente de trabajo Croquizador](Sketcher_Workbench/es.md). Este es un dibujo 2D que utiliza restricciones matemáticas para describir la geometría 2D con precisión.

Ver [Coquizador CroquisObjeto](Sketcher_SketchObject/es.md) para más información sobre este tipo de objeto.

## Utilización

Hay dos maneras comunes de crear un Croquis: usando el [Ambiente de trabajo Croquizador](Sketcher_Workbench/es.md) directamente, o a través del [Ambiente de trabajo DiseñoPieza](PartDesign_Workbench/es.md).

### Ambiente de Trabajo Croquizador {#ambiente_de_trabajo_croquizador}

1.  Cambia al <img alt="" src=images/Workbench_Sketcher.svg  style="width:16px;"> [Ambiente de Trabajo Croquizador](Sketcher_Workbench/es.md).
2.  Pulsa **<img src=images/Sketcher_NewSketch.svg style="width:16px"> [Croquizador NuevoCroquis](Sketcher_NewSketch/es.md)**.

### Ambiente de Trabajo DiseñoPieza {#ambiente_de_trabajo_diseñopieza}

1.  Cambiar a la <img alt="" src=images/Workbench_PartDesign.svg  style="width:16px;"> [Ambiente de Trabajo DiseñoPieza](PartDesign_Workbench/es.md).
2.  Press **<img src=images/PartDesign_Body.svg style="width:16px"> [Cuerpo DiseñoPieza](PartDesign_Body/es.md)**.
3.  Press **<img src=images/PartDesign_NewSketch.svg style="width:16px"> [DiseñoPieza NuevoBoceto](PartDesign_NewSketch/es.md)**.

Cuando termines de editar el boceto, ciérralo para salir del modo de edición. Haz doble clic en él para volver a entrar en el modo de edición.

## Notas

Un Croquis se utiliza muy normalmente junto con el <img alt="" src=images/Workbench_PartDesign.svg  style="width:16px;"> <img src=images/PartDesign_Pad.svg style="width:Ambiente de trabajo DiseñoPiezas](PartDesign_Workbench/es.md) para crear sólidos por extrusión, utilizando el **[16px"> [PartDesign Pastilla](PartDesign_Pad/es.md)**.

Sin embargo, un Croquis siempre puede ser creado por sí mismo para cualquier otro propósito; no tiene que estar ligado a un <img src=images/Arch_Window.svg style="width:DiseñoPieza Cuerpo](PartDesign_Body/es.md). Por ejemplo, el **[16px"> <img src=images/Arch_Wall.svg style="width:Arquitectura Ventana](Arch_Window/es.md)** de la herramienta <img alt="" src=images/Workbench_Arch.svg  style="width:16px;"> [Ambiente de trabajo Arquitectura](Arch_Workbench/es.md) utiliza los Croquis para definir las formas de las ventanas y las puertas; del mismo modo, pueden utilizarse para definir la forma de **[16px"> [Arquitectura Muros](Arch_Wall/es.md)**.


{{Sketcher Tools navi

}} {{Document objects navi}} 

[Category:Glossary{{\#translation:}}](Category:Glossary.md)