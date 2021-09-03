---
- GuiCommand:/ru
   Name:Part Boolean
   Name/ru:Part Boolean
   MenuLocation:Деталь → Булевы операции
   Workbenches:[Part](Part_Workbench/ru.md)
   SeeAlso:[Объединение](Part_Union/ru.md), [Пересечение](Part_Common/ru.md), [Обрезать](Part_Cut/ru.md) и [Part Section](Part_Section/ru.md)
---

## Описание


<div class="mw-translate-fuzzy">

Эта команда - общий инструмент для всех булевых операций. Она позволяет назначить исполняемые операции и их параметры через нижеследующий диалог.


</div>


<div class="mw-translate-fuzzy">

Для более быстрых булевых операций, смотрите [Объединение](Part_Union/ru.md), [Пересечение](Part_Common/ru.md) и [Обрезать](Part_Cut/ru.md).


</div>

![](images/PartBooleansDialog.png )


*Dialog to select objects and perform boolean operations with them.*

## Применение

See the individual commands:

-    **<img src="images/Part_Cut.svg" width=16px> [Part Cut](Part_Cut.md)
**
    

-    **<img src="images/Part_Fuse.svg" width=16px> [Part Fuse](Part_Fuse.md)
**
    

-    **<img src="images/Part_Common.svg" width=16px> [Part Common](Part_Common.md)
**
    

-    **<img src="images/Part_Section.svg" width=16px> [Part Section](Part_Section.md)
**
    


<div class="mw-translate-fuzzy">

Смотрите далее Деталь → [Уточнить форму](Part_RefineShape/ru.md)


</div>

## Coplanar problems {#coplanar_problems}

The boolean operations are performed by the internal geometry kernel, [OpenCASCADE Technology](OpenCASCADE.md) (OCCT). This library sometimes has problems producing boolean results when the input objects share an edge or a face. To be sure the boolean operation is successful the recommendation is that the shapes intersect each other clearly; this means that in most cases, one shape should protrude or be larger in size than the other shape.

In cases of coplanarity, even if the first boolean operation succeeds, subsequent boolean operations may fail. In this case, the problem may not be in the last operation done, but in the older ones, that is, in the nested operations as indicated in the <img src=images/Part_CheckGeometry.svg style="width:tree view](Tree_view.md). To troubleshoot these issues, it is recommended to use the **[16px"> [Part CheckGeometry](Part_CheckGeometry.md)** tool to inspect all objects for problems.

<img alt="" src=images/Part_Boolean_cut_coplanar_1.png  style="width:500px;">

<img alt="" src=images/Part_Boolean_cut_coplanar_2.png  style="width:500px;">


*Left: shapes that share a face, a boolean cut may produce incorrect results. Right: shapes that intersect each other clearly, the boolean cut will be successful in most cases.*

<img alt="" src=images/Part_Boolean_fusion_coplanar_1.png  style="width:500px;">

<img alt="" src=images/Part_Boolean_fusion_coplanar_2.png  style="width:500px;">


*Left: shapes that share a face, a boolean union may produce incorrect results. Right: shapes that intersect each other clearly, the boolean union will be successful in most cases.*





 