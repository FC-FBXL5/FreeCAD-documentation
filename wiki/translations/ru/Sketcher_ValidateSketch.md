---
- GuiCommand:/ru
   Name:Sketcher Validate
   Name/ru:Проверить эскиз
   MenuLocation:Sketch/Part Design → Проверить эскиз...
   Workbenches:[Sketcher](Sketcher_Workbench/ru.md), [PartDesign](PartDesign_Workbench/ru.md)
---


</div>

## Описание


<div class="mw-translate-fuzzy">

Утилита **Проверить эскиз** может использоваться для анализа и восстановления эскиза, который больше не редактируется, имеет неверные ограничения, или для добавления утерянных [ограничений совпадения](Sketcher_ConstrainCoincident/ru.md) в эскизе, созданном из импортированной геометрии, такой как файлы DXF. Он также может быть полезен при поиске отсутствующих совпадений в собственных эскизах, которые генерирует ошибку «невозможно проверить сломанную грань» при попытке применить инструмент PartDesign-а.


</div>

![](images/Sketcher_ValidateSketch_taskpanel.png ) *The Sketcher validation task panel*

## Использование


<div class="mw-translate-fuzzy">

1.  Выберите эскиз для проверки, либо в [дереве модели](Tree_view/ru.md), либо щелкнув по одному из его ребер в [3D-виде](3D_view/ru.md).

    :   **Примечание:** эскиз не должен быть в режиме редактирования. Если вы находитесь в режиме редактирования эскиза, вам нужно использовать кнопку **<img src=images/Sketcher_LeaveSketch.svg style="width:16px"> [Покинуть эскиз](Sketcher_LeaveSketch/ru.md)**, или кнопку **Close** наверху панели задач.
2.  Откройте утилиту проверки эскиза либо:
    -   из ниспадающего меню {{MenuCommand|Sketch → Проверить набросок}}
    -   нажав кнопку <img alt="" src=images/Sketcher_ValidateSketch.svg  style="width:24px;"> в <img alt="Sketcher\_Workbench" src=images/Workbench_Sketcher.svg  style="width:16px;"> [верстаке Sketcher](Sketcher_Workbench/ru.md).
3.  Ознакомьтесь с [Параметрами](#Options/ru.md) для работы, ниже.
4.  Нажмите кнопку **Закрыть** когда закончите.


</div>

## Опции

### Пропавшие совпадения {#пропавшие_совпадения}

Обнаружение пропущенных совпадений для перекрывающихся вершин и добавление их. Нажмите кнопку **Найти**; появится всплывающее диалоговое окно, с сообщением, сколько пропущенных совпадений было найдено; они будут показаны в 3D виде желтыми крестиками. Нажмите кнопку **OK** что бы закрыть диалог, потом нажмите кнопку **Исправить** что бы добавить недостающие совпадения.

При необходимости определите большее значение допуска в выпадающем поле.

Press **Highlight open vertexes** to highlight vertexes that are outside this tolerance.

This tolerance is also used by the **Find**/**Fix** process.

Установите флажок \"Игнорировать вспомогательную геометрию\", чтобы игнорировать вспомогательную геометрию при анализе.

### Invalid constraints {#invalid_constraints}


<div class="mw-translate-fuzzy">

### Неверные ограничения {#неверные_ограничения}

Проверяет наличие некорректных ограничений.


</div>

For example, if there is a Circle-Line-Tangent constraint, but it references two lines, it is considered invalid.

(This sometimes happens due to the [Topological naming problem](Topological_naming_problem.md), i.e. the external geometry changes type).

It also does other checks, such as for empty links.

### Degenerated geometry {#degenerated_geometry}

Degenerated geometry can result from solver actions in a sketch.

For instance, if a line is forced to shorten to become almost a point.

Other examples: a zero length line or zero radius circle/arc.

### Reversed external geometry {#reversed_external_geometry}


<div class="mw-translate-fuzzy">

### Перевернутая внешняя геометрия {#перевернутая_внешняя_геометрия}

Перевернутая внешняя геометрия может произойти из-за того, что обработка перевернутой геометрии была изменена около версии 0.15.


</div>

This process might be helpful if sketches with external-geometry fail to solve because of these changes.

### Constraint orientation locking {#constraint_orientation_locking}


<div class="mw-translate-fuzzy">

### Блокировка ориентации ограничений {#блокировка_ориентации_ограничений}

Реализованы касательные и перпендикулярные ограничения (через точку).


</div>

Internally they work by constraining the angle between tangent vectors. With tangent constraint for example, the angle can be 0 or 180 degrees (co-directed or opposed vectors). The actual angle is remembered in the constraint data (\"constraint orientation is locked\"), it guards against flipping. But the angle can be erased (\"constraint orientation unlock\") or updated; these tools do exactly that.

The locking mechanism typically works well and this tool should not be needed. **It should only used after making a backup of the open document.**





{{Sketcher Tools navi

}}  