---
- GuiCommand:
   Name:Draft AutoGroup
   MenuLocation:Draft → Utilities → AutoGroup
   Workbenches:[Draft](Draft_Workbench.md), [Arch](Arch_Workbench.md)
   SeeAlso:[Std Group](Std_Group.md), [Entwurf VisGroup](Draft_VisGroup.md)
   Version:0.17
---


</div>

## Beschreibung


<div class="mw-translate-fuzzy">

Das Werkzeug \"Autogruppe\" legt eine ausgewählte [Std Gruppe](Std_Group.md) oder ein verwandtes Element wie [Entwurf VisGruppe](Draft_VisGroup.md), [Archbauwerk](Arch_Site.md), [Archbau](Arch_Building.md) oder [Archbauteil](Arch_BuildingPart.md) als aktive Autogruppe fest. Wenn eine Autogruppe festgelegt ist, werden neue Objekte beim Erstellen automatisch in die angegebene Gruppe verschoben.


</div>

This command was originally intended for groups, hence its name, but was redesigned in FreeCAD version 0.19 when a layer system was introduced. Because handling layers is now the default for the command the rest of this page will primarily focus on layers.

![](images/Draft_tray_menu.png )


<div class="mw-translate-fuzzy">


*Entwurfskassette, die die aktive Autogruppe durch Klicken auf das Ordnersymbol und Auswahl einer Gruppe einstellt*


</div>

## Anwendung

1.  To use this command in FreeCAD version 0.19 at least one [layer](Draft_Layer.md) must exist.
2.  Optionally select the layer you want to make active in the [Tree view](Tree_view.md).
3.  There are several ways to invoke the command:
    -   Press the **<img src="images/button_invalid.svg" width=16px> [None](Draft_AutoGroup.md)** button in the [Draft Tray](Draft_Tray.md). This button can look different. If there is an active layer it will show the name of the layer and a layer icon with the **Line Color** and **Shape Color** of the layer.
    -   Select the {{MenuCommand|Utilities → <img src="images/Draft_AutoGroup.svg" width=16px> AutoGroup}} option from the menu.
    -   If you have selected a layer: select the {{MenuCommand|<img src="images/button_right.svg" width=16px> Activate this layer}} option from the [Tree view](Tree_view.md) context menu.
4.  If you have not yet selected a layer the layer menu opens. Do one of the following:
    -   Select {{MenuCommand|None}} to work without an active layer.
    -   Select an existing layer to make active.
    -   Select {{MenuCommand|Add new Layer}} to create a new layer. Selecting this option will not change the active layer.
5.  If the active layer was changed the button in the [Draft Tray](Draft_Tray.md) is updated.

## Notes

-   A new [layer](Draft_Layer.md) can also be created by right-clicking the layer container in the [Tree view](Tree_view.md) and selecting the {{MenuCommand|<img src="images/Draft_NewLayer.svg" width=16px> Add new layer}} option from the context menu.
-   If [Draft construction mode](Draft_ToggleConstructionMode.md) is switched on the active [layer](Draft_Layer.md) is ignored.

## Preferences

See also: [Preferences Editor](Preferences_Editor.md) and [Draft Preferences](Draft_Preferences.md).

-   This command can optionally also handle groups: {{MenuCommand|Edit → Preferences... → Draft → General settings → General Draft Settings → Show groups in layers list drop-down button}}.

## Skripten


<div class="mw-translate-fuzzy">


**Siehe auch:**

[Draft API](Draft_API/de.md) und [FreeCAD Grundlagen Skripten](FreeCAD_Scripting_Basics/de.md).


</div>

If the [Draft Workbench](Draft_Workbench.md) is active the FreeCADGui application object has a `draftToolBar` property. This `draftToolBar` object has an `autogroup` property, which contains the name of the active autogroup, or is `None` if no autogroup is active. To change the active autogroup use the `setAutoGroup` method of the `draftToolBar` object. To put objects in the active autogroup use the `autogroup` method of the Draft module.


```python
# This code only works if the Draft Workbench is active!

import FreeCAD as App
import FreeCADGui as Gui
import Draft

doc = App.newDocument()

polygon1 = Draft.make_polygon(5, radius=1000)
polygon2 = Draft.make_polygon(3, radius=500)
polygon3 = Draft.make_polygon(6, radius=220)

layer = Draft.make_layer()
Gui.draftToolBar.setAutoGroup(layer.Name)

Draft.autogroup(polygon1)
Draft.autogroup(polygon2)
Draft.autogroup(polygon3)

doc.recompute()
```


<div class="mw-translate-fuzzy">





</div>


 