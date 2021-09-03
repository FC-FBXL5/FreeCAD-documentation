





{{TOCright}}


<div class="mw-translate-fuzzy">

Стилът на работа с мишката\" се състои от командите които се използват за навигация в 3D пространството и работа с обектите в него. FreeCAD подържа няколко стила на навигация с мишка. Стилът по-поразбиране се нарича \"CAD Навигация,\" и е доста прост и практичен. FreeCAD също предлага алтернативни стилове за навигация близки до интерфейсите на други програми.


</div>

## Навигация

Стилът на навигацията и работа с обектите е един и същ във всички работни плотове. Долуописаните жестове на мишката могат да се използват за да се контролира позицията на обекта и изгледа към обекта (в зависимост от кой стил на навигация е избран).

Има два начина да сменим стила на навигация:

-   В менюто [Preference Editor](Preferences_Editor/bg.md), скецията Display и в таба *3D View*;
-   Като натиснем десния бутон на мишката в празно място в 3D прозореца и изберем *Navigation style* от контекстното меню което се появява.

### Стил CAD Навигация (по-подразбиране) {#стил_cad_навигация_по_подразбиране}

Това е стилът на навигация по-подразбиране който позволява лесен контрол на изгелда без да изисква използването на клавиатурата, с изключението на бутона **SHIFT** за избиране на няколко обекта едновременно. {{CAD Navigation/bg}}


{{CAD Navigation
|Select_name=Select
|Pan_name=Pan
|Zoom_name=Zoom
|Rotate_view_name=Rotate view<br>First method
|Rotate_view_alt_name=Rotate view<br>Alternate method
|Ctrl=**Ctrl**
|Shift=**Shift**
|Select_text=Press the left mouse button over an object you want to select.

Holding down **Ctrl** allows the selection of multiple objects.
|Pan_text=Hold the middle mouse button, then move the pointer.
|Pan_mode_text=Pan mode: hold the **Ctrl** key, press the right mouse button once, then move the pointer. <small>(v0.17)</small> 
|Zoom_text=Use the mouse wheel to zoom in and out.

Clicking the middle mouse button re-centers the view on the location of the cursor.
|Zoom_mode_text=Zoom mode: hold the **Ctrl** and **Shift** keys, press the right mouse button once, then move the pointer. <small>(v0.17)</small> 
|Rotate_view_text=Hold the middle mouse button, then press and hold the left mouse button, then move the pointer.

The cursor location when the middle mouse button is pressed determines the center of rotation. Rotation works like spinning a ball which rotates around its center. If the buttons are released before you stop the mouse motion, the view continues [spinning](spinning.md), if this is enabled.

A double click with the middle mouse button sets a new center of rotation.
|Rotate_view_mode_text=Rotate mode: hold the **Shift** key, press the right mouse button once, then move the pointer. <small>(v0.17)</small> 
|Rotate_view_alt_text=Hold the middle mouse button, then press and hold the right mouse button, then move the pointer.

With this method the middle mouse button may be released after the right mouse button is held pressed.

Users who use the mouse with their right hand may find this method easier than the first method.
}}

### Стил на навгиация Inventor {#стил_на_навгиация_inventor}

Този стил на навигация е наподобява програмата [Open Inventor](http://en.wikipedia.org/wiki/Open_Inventor) (която не бива да се бърка с Autodesk Inventor). В този стил не можете да избирате обекти само с мишката. За да избирате обекти трябва да задържите натиснат бутонът **CTRL**. {{Inventor Navigation/bg}}

This mode is not based on Autodesk Inventor.


{{OpenInventor Navigation
|Select_name=Select
|Pan_name=Pan
|Zoom_name=Zoom
|Rotate_view_name=Rotate view
|Ctrl=**Ctrl**
|Select_text=Hold **Ctrl**, then press the left mouse button over an object you want to select.
|Pan_text=Hold the middle mouse button, then move the pointer.
|Zoom_text=Use the mouse wheel to zoom in and out.

Alternatively, hold the middle mouse button, then press and hold the left mouse button, then move the pointer. 
|Rotate_view_text=Hold the left mouse button, then move the pointer.
}}

### Стил навигация Blender {#стил_навигация_blender}

Този стил навигация е подобен на навигацията в програмата [Blender](http://www.blender.org). Не може да се движви обект в четерите посоки(pan) само с мишката. За да движите обект в четирите посоки трябва да задържите бутонът **SHIFT**. {{Blender Navigation/bg}}

Alternatively, hold both left and right mouse buttons, and then move the pointer. \|Zoom\_text=Use the mouse wheel to zoom in and out. \|Rotate\_view\_text=Hold the middle mouse button, then move the pointer. }}

### Навигация с тъчпад {#навигация_с_тъчпад}

В случай че разполагате само с тъчпад (например на лаптоп) може да използвате този стил. При навигацията с тъчпад за всяка операция (движение, ротация, промяна на мащаб) се използва и клавиатурата.


{{Touchpad Navigation/bg}}

### Навигация с жестове (v0.16) {#навигация_с_жестове_v0.16}

Този стил на навигация е основно предназначен за работа с тъчскрийн или с електронна писалка/таблет. Може да се използва и само с мишка. {{Gesture Navigation/bg}}

Alternatively, tap and hold, then drag. This simulates the pan with the right mouse button. \|Zoom\_text=Use the mouse wheel to zoom in and out. \|Zoom\_gesture\_text=Drag two fingers (pinch) closer or farther apart. \|Rotate\_view\_text=Hold the left mouse button, then move the pointer. In [Sketcher](Sketcher_Workbench.md) and other edit modes, this behavior is disabled. Hold **Alt** when pressing the mouse button to enter rotation mode.

To set the camera\'s focus point for rotation, click a point with the middle mouse button. Alternatively, aim the cursor at a point and press **H** on the keyboard. \|Rotate\_view\_gesture\_text=Drag with one finger to rotate.

Hold **Alt** when in the [Sketcher](Sketcher_Workbench.md). \|Tilt\_view\_text=Hold both left and right mouse buttons, then move the pointer sideways. \|Tilt\_view\_gesture\_text=Rotate the imaginary line formed by two touch points.

On v0.18 this method is disabled by default. To enable, go to {{MenuCommand|Edit → Preferences → Display}}, and untick \"Disable touchscreen tilt gesture\" checkbox. }}

### Навигация с жестове стил Maya {#навигация_с_жестове_стил_maya}


<div class="mw-translate-fuzzy">

При навигация в стил Maya+жестове всички промени на изгледа се извършват като се задържи клавишът **ALT** и бутон на мишката. Поради това е нужна мишка с 3 бутона за използването на този стил. Ако нямате такава, е възможно и да се използват жестовете описани по-горе. {{MayaGesture Navigation/bg}}


</div>

Alternatively, use the mouse wheel to zoom in and out. \|Rotate\_view\_text=Hold **Alt** and the left mouse button, then move the pointer. }}

### Revit Navigation {#revit_navigation}

This style was introduced in version 0.18.


{{Revit Navigation
|Select_name=Select
|Pan_name=Pan
|Zoom_name=Zoom
|Rotate_view_name=Rotate view
|Shift=**Shift**
|Select_text=Press the left mouse button over an object you want to select.
|Pan_text=Hold the middle mouse button, then move the pointer.

Alternatively, hold both left and right mouse buttons, then move the pointer.

|Zoom_text=Use the mouse wheel to zoom in and out.
|Rotate_view_text=Hold **Shift** and the middle mouse button, then move the pointer.

Alternatively, hold the middle mouse button, then press and hold the right mouse button, then move the pointer.
}}

### OpenCascade

This style was introduced in version 0.18.


{{OpenCascade Navigation
|Select_name=Select
|Pan_name=Pan
|Zoom_name=Zoom
|Rotate_view_name=Rotate view
|Ctrl=**Ctrl**
|Select_text=Press the left mouse button over an object you want to select.
|Pan_text=Hold the middle mouse button, then move the pointer.
|Zoom_text=Use the mouse wheel to zoom in and out.

Alternatively, hold **Ctrl** and the left mouse button, then move the pointer.
|Rotate_view_text=Hold **Ctrl** and the right mouse button, then move the pointer.
}}

## Избиране на обекти {#избиране_на_обекти}

### Проста селекция {#проста_селекция}

Обект може да се избере като се натисне левия бутон на мишката върху него или в 3D прозореца, или върху неговото име в дървото на обектите.

### Пре-селекция {#пре_селекция}

Ако режим \"Пре-селекция\" е включен (настройката за него може да намерите в менюто Preferences), то когато курсора на мишката е върху някой обект в 3D прозореца ще видите информация за него дори и без да го избирате.

## Manipulating Objects {#manipulating_objects}

FreeCAD offers [*manipulators*](Manipulator.md) that are handles that can be used to modify an object\'s appearance, shape, or other parameters.

## Поддържан хардуер {#поддържан_хардуер}

FreeCAD също поддържа някои [3D input devices](3D_input_devices.md).

## Mac OS X Issues {#mac_os_x_issues}

Recently we got reports [on the forum](http://forum.freecadweb.org/viewtopic.php?f=3&t=3592&start=0) from Mac users that those mouse button and key combination do not work as expected. Unfortunately, none of the developers owns a Mac, neither do the other regular contributors. We need your help to determine which mouse buttons and key combination work so we can update this wiki.


{{docnav|Getting started/bg|Document structure/bg}}


