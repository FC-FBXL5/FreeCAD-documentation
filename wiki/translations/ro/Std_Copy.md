---
- GuiCommand:   Name:Std Copy   MenuLocation:[Shortcut:Ctrl+C   Workbenches:All   SeeAlso:[[Std_Paste|Paste](Std_Edit_Menu___Edit]]_→_Copy.md), [Duplicate Selection](Std_DuplicateSelection.md)---


</div>

## Description


<div class="mw-translate-fuzzy">

## Descriere

Comanda **[16px|text-top=Std Copy|link=Std Copy/fr](File:Std_Copy.png.md) [copie](Std_Copy/fr.md)** este implicată în replicarea obiectelor [Document](Document_structure.md). It places the currently selected objects into the \"clipboard\" for later use by the [Paste](Std_Paste.md) command. Obiectele pot fi copiate între Documente.


</div>

## Usage


<div class="mw-translate-fuzzy">

## Cum se folosește {#cum_se_folosește}

1.  Selectați Object(ul)ele de replicat.
2.  Press the **[16px|Copy](File:Std_Copy.png.md)** icon, **ctrl** + **C** keys or use menu choices Edit → Copy.


</div>

## Notes

-   When you are working in a FreeCAD text window, an input box or a spreadsheet, the standard keyboard shortcut **Ctrl**+**C**, in almost all cases, does not call the **Std Copy** command but uses the Copy function from the OS instead.
-   It is not possible to copy-paste native objects between FreeCAD and other applications.

## Scripting

The **Std Copy** command can be applied after selecting one or more objects in the [Tree view](Tree_view.md):


```python
FreeCADGui.runCommand('Std_Copy')
FreeCADGui.runCommand('Std_Paste')
```

The selection can be manual (by using the mouse), or via the [Python console](Python_console.md).
To know more about selecting objects programmatically, refer to [Selection methods](Selection_methods.md).





{{Std Base navi

}}  