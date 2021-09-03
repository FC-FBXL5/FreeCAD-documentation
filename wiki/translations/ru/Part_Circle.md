---
- GuiCommand:/ru
   Name:Part Circle
   Name/ru:Окружность
   MenuLocation:Деталь → [Создать примитивы...](Part_Primitives/ru.md) → Окружность
   Workbenches:[Верстак Part](Part_Workbench/ru.md)
   SeeAlso:
---

## Описание

Эта команда создаёт ребро в форме круга. При значениях по умолчанию круговое изогнутое ребро будет замкнутым и, следовательно, будет кругом. Если свойства Угол0 или Угол1 изменить от их значений по умолчанию (0 и 360), ребро будет открытой кривой, то есть дугой.

В качестве альтернативы Окружность может быть первоначально определена (построена) по трём точкам. После создания круг будет содержать только стандартные свойства элемента Окружность и больше не будет содержать ссылки на точки указанные при её создании.

## Применение

Геометрический примитив Окружность доступен в диалоговом окне Создать Примитивы верстака Part(Деталь).

1.  Переключитесь на <img alt="" src=images/Workbench_Part.svg  style="width:24px;"> [верстак Part (Деталь)](Part_Workbench/ru.md)
2.  Есть несколько способов чтобы получить доступ к диалогу Создания Примитивов:
    -   Нажмите кнопку <img alt="" src=images/Part_Primitives.svg  style="width:24px;"> [Создать Примитивы\...](Part_Primitives/ru.md), расположенную на панели инструментов верстака Part
    -   Используйте меню {{MenuCommand|Деталь → [Создать Примитивы...](Part_Primitives/ru.md) → Окружность}}

## Свойства

-    {{Parameter|Радиус(Radius)}}: радиус изогнутого ребра (дуги или окружности)

-    {{Parameter|Угол(Angle) 0}}: начало изогнутого ребра (в градусах и в направлении против часовой стрелки), значение по умолчанию - 0

-    {{Parameter|Угол(Angle) 1}}: окончание изогнутого ребра (в градусах и в направлении против часовой стрелки), значение по умолчанию - 360





 