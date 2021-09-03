---
- GuiCommand:/sv   Name:Draft Scale   Name/sv:Draft Scale   Workbenches:[Arch](Draft_Workbench/sv___Draft]],_[[Arch_Workbench/sv.md)|MenuLocation:Draft → Scale   Shortcut:S C   SeeAlso:[Draft Clone](Draft_Clone/sv.md)---


</div>

## Beskrivning


<div class="mw-translate-fuzzy">

Detta verktyg skalar valda objekt runt en baspunkt. Om inga objekt är markerade, så kommer du ombes att välja ett.


</div>

The command can be used on 2D objects created with the [Draft Workbench](Draft_Workbench.md) or [Sketcher Workbench](Sketcher_Workbench.md), but also on many 3D objects such as those created with the [Part Workbench](Part_Workbench.md), [PartDesign Workbench](PartDesign_Workbench.md) or [Arch Workbench](Arch_Workbench.md).

<img alt="" src=images/Draft_Scale_example.png  style="width:400px;"> 
*Scaling an object around a base point*

## Bruk

See also: [Draft Snap](Draft_Snap.md) and [Draft Constrain](Draft_Constrain.md).

1.  Optionally select one or more objects, or one or more subelements of [Draft Lines](Draft_Line.md) or [Draft Wires](Draft_Wire.md).
2.  There are several ways to invoke the command:
    -   Press the **<img src="images/Draft_Scale.svg" width=16px> [Draft Scale](Draft_Scale.md)** button.
    -   Select the {{MenuCommand|Modification → <img src="images/Draft_Scale.svg" width=16px> Scale}} option from the menu.
    -   Use the keyboard shortcut: **S** then **C**.
3.  If you have not yet selected an object: select an object in the [3D view](3D_view.md).
4.  The {{MenuCommand|Scale}} task panel opens. See [Options](#Options.md) for more information.
5.  If subelements have been selected: check the {{MenuCommand|Modify subelements}} checkbox to switch on subelement mode.
6.  Pick the base point in the [3D view](3D_view.md), or type coordinates and press the **<img src="images/Draft_AddPoint.svg" width=16px> Enter point** button.
7.  Enter the X, Y and Z scale factors.
8.  Press **Enter** or the **OK** button to finish the command.

## Options

### First task panel {#first_task_panel}

The single character keyboard shortcuts mentioned here can be changed. See [Draft Preferences](Draft_Preferences.md).

-   To manually enter the coordinates for the base point enter the X, Y and Z component, and press **Enter** after each. Or you can press the **<img src="images/Draft_AddPoint.svg" width=16px> Enter point** button when you have the desired values. It is advisable to move the pointer out of the [3D view](3D_view.md) before entering coordinates.
-   The {{MenuCommand|Relative}} checkbox has no purpose for this command.
-   Press **G** or click the {{MenuCommand|Global}} checkbox to toggle global mode. If global mode is on, coordinates are relative to the global coordinate system, else they are relative to the [working plane](Draft_SelectPlane.md) coordinate system. <small>(v0.20)</small> 
-   The remaining checkboxes in this task panel are ignore by the command.
-   Press **S** to switch [Draft snapping](Draft_Snap.md) on or off.
-   Press the **Close** button to abort the command.

### Second task panel {#second_task_panel}


<div class="mw-translate-fuzzy">

-   Markera en punkt i ett tomt område i 3d vyn, eller på ett existerande objekt för baspunkten, sedan en annan punkt för skalfaktorn

-   x, y och z komponenterna av den andra punkten definierar skalfaktorn. Till exempel, (1,1,1) gör ingenting, (2,2,2) kommer att skala 2x i alla riktningar, (-1,1,1) kommer att spegla i x riktningen.

-   Nedtryckning av **CTRL** kommer att [snäppa](Draft_Snap/sv.md) din punkt till tillgängliga snäpp-punkter.

-   Nedtryckning av **SKIFT** kommer att koppla ihop x och y värdena, så att förhållandet inte ändras

-   Om du trycker på **ESC** så avbryts funktionen.

-   Skriv in siffror för att [manuellt mata in en koordinat](Draft_Coordinates/sv.md).

-    **C**växlar kopieringsläget på/av. Med kopiering på, så kommer objekt(en) att kopieras istället för att flyttas.

-   Nedtryckning av **ALT** kommer att skapa en kopia, även om kopieringsknappen är av.

-   Om **ALT** är nedtryckt, så kan du göra multipla kopior ända tills **ALT** släpps.


</div>

## Notes

-   The command can also scale [Image Planes](Image_CreateImagePlane.md), but not in clone mode.

## Preferences

See also: [Preferences Editor](Preferences_Editor.md) and [Draft Preferences](Draft_Preferences.md).

-   To change the number of decimals used for the input of coordinates: {{MenuCommand|Edit → Preferences... → General → Units → Units settings → Number of decimals}}.
-   To change the number of decimals used for the input of scale factors: {{MenuCommand|Edit → Preferences... → Draft → General settings → General Draft Settings → Internal precision level}}.
-   To store and reuse the same copy mode setting across commands: {{MenuCommand|Edit → Preferences... → Draft → General settings → Draft tools options → Global copy mode}}.
-   To reselect the base objects after copying objects: {{MenuCommand|Edit → Preferences... → Draft → General settings → Draft tools options → Select base objects after copying}}.

## Scripting

See also: [Autogenerated API documentation](https://freecad.github.io/SourceDoc/) and [FreeCAD Scripting Basics](FreeCAD_Scripting_Basics.md).

To scale objects use the `scale` method of the Draft module.


```python
scaled_list = scale(objectslist, scale=Vector(1,1,1), center=Vector(0,0,0), copy=False)
```

-    `objectslist`contains the objects to be scaled. It is either a single object or a list of objects.

-    `scale`is the vector that specifies by the X, Y and Z scale factors.

-    `center`is the center point of the scaling operation.

-   If `copy` is `True` copies are created instead of scaling the original objects.

-    `scaled_list`is returned with the original scaled objects, or with the new copies. It is either a single object or a list of objects, depending on `objectslist`.

Example:


```python
import FreeCAD as App
import Draft

doc = App.newDocument()

pts = [App.Vector(0, 0, 0), App.Vector(500, 500, 0), App.Vector(600, 0, 0)]
wire1 = Draft.make_wire(pts, closed=True)
doc.recompute()

scale1 = App.Vector(2.3, 0.75, 0)
wire2 = Draft.scale(wire1, scale1, copy=True)
doc.recompute()

scale2 = App.Vector(-2, -1.5, 0)
wires = Draft.scale([wire1, wire2], scale2, copy=True)
doc.recompute()
```





 