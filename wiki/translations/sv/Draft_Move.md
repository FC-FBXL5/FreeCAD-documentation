---
- GuiCommand:/sv   Name:Draft Move   Name/sv:Draft Move   Workbenches:[Arch](Draft_Workbench/sv___Draft]],_[[Arch_Workbench/sv.md)|MenuLocation:Draft -> Move   Shortcut:M V---


</div>

## Beskrivning


<div class="mw-translate-fuzzy">

Detta verktyg flyttar de markerade objekten från en punkt till en annan. Om inget objekt är valt, så kommer du ombes att välja ett.


</div>

The command can be used on 2D objects created with the [Draft Workbench](Draft_Workbench.md) or [Sketcher Workbench](Sketcher_Workbench.md), but also on many 3D objects such as those created with the [Part Workbench](Part_Workbench.md), [PartDesign Workbench](PartDesign_Workbench.md) or [Arch Workbench](Arch_Workbench.md).

<img alt="" src=images/Draft_Move_example.jpg  style="width:400px;"> 
*Moving an object from one point to another*

## Bruk

See also: [Draft Snap](Draft_Snap.md) and [Draft Constrain](Draft_Constrain.md).


<div class="mw-translate-fuzzy">

-   Markera punkter i ett tomt område i 3d vyn, eller på ett existerande objekt.

-   Nedtryckning av **CTRL** kommer att [snäppa](Draft_Snap/sv.md) din punkt till tillgängliga snäpp-punkter.

-   Nedtryckning av **SKIFT** kommer att [begränsa](Draft_Constrain/sv.md) dig vertikalt eller horisontellt i relation till startpunkten.

-   Om du trycker på **ESC** så avbryts funktionen.

-   Skriv in siffror för att [manuellt mata in en koordinat](Draft_Coordinates/sv.md).

-    **C**växlar kopieringsläget på/av. Med kopiering på, så kommer objekt(en) att kopieras istället för att flyttas.

-   Nedtryckning av **ALT** kommer att skapa en kopia, även om kopieringsknappen är av.

-   Om **ALT** är nedtryckt, så kan du göra multipla kopior ända tills **ALT** släpps.


</div>

## Options

The single character keyboard shortcuts mentioned here can be changed. See [Draft Preferences](Draft_Preferences.md).

-   To manually enter coordinates enter the X, Y and Z component, and press **Enter** after each. Or you can press the **<img src="images/Draft_AddPoint.svg" width=16px> Enter point** button when you have the desired values. It is advisable to move the pointer out of the [3D view](3D_view.md) before entering coordinates.
-   To use polar coordinates enter a value for the {{MenuCommand|Length}} and a value for the {{MenuCommand|Angle}}, and press **Enter** after each.
-   Check the {{MenuCommand|Angle}} checkbox to constrain the pointer to the specified angle.
-   Press **H** to change the focus from the {{MenuCommand|X}} input box to the {{MenuCommand|Length}} input box and back. Depending on the input box that receives the focus the {{MenuCommand|Angle}} checkbox is checked or unchecked.
-   Press **R** or click the {{MenuCommand|Relative}} checkbox to toggle relative mode. If relative mode is on, the coordinates of the second point are relative to the first point, else they are relative to the coordinate system origin.
-   Press **G** or click the {{MenuCommand|Global}} checkbox to toggle global mode. If global mode is on, coordinates are relative to the global coordinate system, else they are relative to the [working plane](Draft_SelectPlane.md) coordinate system. <small>(v0.20)</small> 
-   Press **T** or click the {{MenuCommand|Continue}} checkbox to toggle continue mode. If continue mode is on, the command will restart after finishing. This mode really only makes sense if copy mode is switched on. Depending on the {{MenuCommand|Select base objects after copying}} preference, either the original objects are selected for the next command call or the copies that were created last. See [Preferences](#Preferences.md).
-   Press **P** or click the {{MenuCommand|Copy}} checkbox to toggle copy mode. If copy mode is on, the command will create moved copies instead of moving the original objects.
-   Press **D** or click the {{MenuCommand|Modify subelements}} checkbox to toggle subelement mode. If subelement mode is on, the command will use the selected subelements instead of the whole objects. The subelements must belong to [Draft Lines](Draft_Line.md) or [Draft Wires](Draft_Wire.md).
-   If copy mode and subelement mode are both on, and edges of [Draft Wires](Draft_Wire.md) are selected, new wires will be created from those edges.
-   Press **S** to switch [Draft snapping](Draft_Snap.md) on or off.
-   Press **Esc** or the **Close** button to abort the command.

## Notes

-   An Object that is [attached](Part_Attachment.md) cannot be moved with the Draft Move command. To move it either its **Support** object has to be moved, or its **Attachment Offset** has to be changed.

## Preferences

See also: [Preferences Editor](Preferences_Editor.md) and [Draft Preferences](Draft_Preferences.md).

-   To change the number of decimals used for the input of coordinates, lengths and angles: {{MenuCommand|Edit → Preferences... → General → Units → Units settings → Number of decimals}}.
-   To change the initial focus of the task panel to the {{MenuCommand|Length}} input box: {{MenuCommand|Edit → Preferences... → Draft → General settings → Draft tools options → Set focus on Length instead of X coordinate}}. Note that you must move the pointer in the [3D view](3D_view.md) for the change to take effect.
-   To store and reuse the same copy mode setting across commands: {{MenuCommand|Edit → Preferences... → Draft → General settings → Draft tools options → Global copy mode}}.
-   To reselect the base objects after copying objects: {{MenuCommand|Edit → Preferences... → Draft → General settings → Draft tools options → Select base objects after copying}}.

## Scripting

See also: [Autogenerated API documentation](https://freecad.github.io/SourceDoc/) and [FreeCAD Scripting Basics](FreeCAD_Scripting_Basics.md).

To move objects use the `move` method of the Draft module.


```python
moved_list = move(objectslist, vector, copy=False)
```

-    `objectslist`contains the objects to be moved. It is either a single object or a list of objects.

-    `vector`is the displacement.

-   If `copy` is `True` copies are created instead of moving the original objects.

-    `moved_list`is returned with the original moved objects, or with the new copies. It is either a single object or a list of objects, depending on `objectslist`.

Example:


```python
import FreeCAD as App
import Draft

doc = App.newDocument()

polygon1 = Draft.make_polygon(5, radius=1000)
polygon2 = Draft.make_polygon(3, radius=500)
polygon3 = Draft.make_polygon(6, radius=220)

Draft.move(polygon1, App.Vector(500, 500, 0))
Draft.move(polygon1, App.Vector(500, 500, 0))
Draft.move(polygon2, App.Vector(1000, -1000, 0))
Draft.move(polygon3, App.Vector(-500, -500, 0))

list1 = [polygon1, polygon2, polygon3]

vector = App.Vector(-2000, -2000, 0)
list2 = Draft.move(list1, vector, copy=True)
list3 = Draft.move(list1, -2*vector, copy=True)

doc.recompute()
```





 