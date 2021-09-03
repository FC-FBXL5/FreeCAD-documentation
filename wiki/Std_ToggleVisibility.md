---
- GuiCommand:
   Name:Std ToggleVisibility
   MenuLocation:View → Toggle visibility
   Workbenches:All
   Shortcut:**Space**
   SeeAlso:[Std ShowSelection](Std_ShowSelection.md), [Std HideSelection](Std_HideSelection.md), [Std ToggleObjects](Std_ToggleObjects.md), [Std ShowObjects](Std_ShowObjects.md), [Std HideObjects](Std_HideObjects.md)
---

## Description

The **Std ToggleVisibility** command toggles the visibility of selected objects in [3D views](3D_view.md).

## Usage

1.  Select one or more objects.
    -   Invisible objects can be selected in the [Tree view](Tree_view.md).
    -   Be careful when you use **Ctrl**+**A** to select all objects in the Tree view. This will also selects sub-elements of [PartDesign bodies](PartDesign_Body.md) and objects used for [Part Booleans](Part_Boolean.md). In most cases these should stay invisible.
    -   Objects used for [Part Booleans](Part_Boolean.md) are also selected when you use **Ctrl**+**A** in a 3D view.
2.  There are several ways to invoke the command:
    -   Select the {{MenuCommand|View → <img src="images/Std_ToggleVisibility.svg" width=16px> Toggle visibility}} option from the menu.
    -   Select the {{MenuCommand|View → Visibility → <img src="images/Std_ToggleVisibility.svg" width=16px> Toggle visibility}} option from the menu.
    -   Select the {{MenuCommand|<img src="images/Std_ToggleVisibility.svg" width=16px> Toggle visibility}} option from the Tree view context menu. This option is not available in the [PartDesign Workbench](PartDesign_Workbench.md).
    -   Select the {{MenuCommand|<img src="images/Std_ToggleVisibility.svg" width=16px> Toggle visibility}} option from the 3D view context menu.
    -   Use the keyboard shortcut: **Space**.

## Notes

-   Invisible objects are displayed with a greyed out label and a greyed out icon in the [Tree view](Tree_view.md).
-   Objects nested in a [Std Part](Std_Part.md), or a [Std Link](Std_LinkMake.md) to a [Std Group](Std_Group.md), or a LinkGroup, and [features](PartDesign_Feature.md) of a [PartDesign Body](PartDesign_Body.md) will only be visible in [3D views](3D_view.md) if their parent is visible as well. This means that a feature in a PartDesign Body that is nested in a Std Part will only be visible in 3D views if the feature itself, the PartDesign Body, and the Std Part are all visible. And if the Std Part is in turn nested in another Std Part, then that last object must also be visible.
-   If the visibility of a [Std Group](Std_Group.md) (or an object derived from it such as an [Arch BuildingPart](Arch_BuildingPart.md)) is changed, the visibility of its nested objects will change accordingly. But their visibility can be changed independently as well.
-   The action of this command cannot be undone with [Std Undo](Std_Undo.md).
-   The visibility of an object can also be changed through its related **Visibility** property in the [Property editor](Property_editor.md) or the [Combo view](Combo_view.md).

## Scripting


**See also:**

[FreeCAD Scripting Basics](FreeCAD_Scripting_Basics.md).

Use the `show` and `hide` methods of an object to change its visibility.

 
```python
import FreeCADGui

obj = FreeCADGui.ActiveDocument.myObjectName

if obj.Visibility == True:
  obj.hide()
else:
  obj.show()
```




 {{Std Base navi}}  