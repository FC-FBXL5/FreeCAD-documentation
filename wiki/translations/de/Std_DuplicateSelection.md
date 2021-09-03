---
- GuiCommand:/de   Name:Std DuplicateSelection   Name/de:Std Auswahl duplizieren   MenuLocation:Bearbeiten → Auswahl duplizieren   Shortcut:    Workbenches:Alle   SeeAlso:[Kopieren](Std_Copy/de.md), [Einfügen](Std_Paste/de.md)---


</div>

## Description


<div class="mw-translate-fuzzy">

## Beschreibung

Der Auswahl duplizieren-Befehl ist eine \'Verkürzung\' von Kopieren + Einfügen (Copy + Paste). Er erstellt Kopien der aktuell ausgewählten Objekte in das aktuelle Dokument.


</div>

## Usage


<div class="mw-translate-fuzzy">

## Anwendung

1.  Wähle die zu duplizierenden Objekte.
2.  Benutze aus der Menüleiste **Bearbeiten** → **Auswahl** duplizieren.


</div>

## Notes


<div class="mw-translate-fuzzy">

## Mehr

Mehr Einzelheiten zum Replizieren von Objekten gibt es auf der [Objekte kopieren](Copying_Objects/de.md)-Seite.


</div>

## Preferences

-   Duplicate labels are allowed if {{MenuCommand|Tools → Edit parameters... → BaseApp → Preferences → Document → DuplicateLabels}} is set to `True`. This setting can also be changed in the [Preferences Editor](Preferences_Editor#Document.md).

## Scripting

The **Std DuplicateSelection** command can be applied after selecting one or more objects in the [Tree view](Tree_view.md):


```python
FreeCADGui.runCommand('Std_DuplicateSelection')
```

The selection can be manual (by using the mouse), or via the [Python console](Python_console.md).
To know more about selecting objects programmatically, refer to [Selection methods](Selection_methods.md).





{{Std Base navi

}}  