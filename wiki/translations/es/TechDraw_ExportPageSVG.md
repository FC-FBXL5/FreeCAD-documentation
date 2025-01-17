---
- GuiCommand:
   Name:TechDraw ExportPageSVG
   MenuLocation:TechDraw → Export Page as SVG
   Workbenches:[TechDraw](TechDraw_Workbench.md)
   SeeAlso:[TechDraw Templates](TechDraw_Templates.md), [Draft SVG](Draft_SVG.md)
---

# TechDraw ExportPageSVG/es

## Descripción

The ExportPageSVG tool saves the current drawing page as an [SVG](SVG.md) file.

## Utilización

1.  Press the **<img src="images/TechDraw_ExportPageSVG.svg" width=16px> [Export Page as SVG](TechDraw_ExportPageSVG.md)** button.
2.  A File Save dialog will open. Select a location and file name.

## Notas

-   [TechDraw Hatch](TechDraw_Hatch.md) patterns are not exported to [SVG](SVG.md) due to a limitation in Qt4\'s SVG support.
-   Text positions and sizes are not correct in the exported file. Using the \"system\" default font in the drawing improves the size problem considerably.

## Guión


**Ver también:**

[DibujoTécnico API](TechDrawGui_API/es.md), y [Fundamentos de scripting de FreeCAD](FreeCAD_Scripting_Basics/es.md).

The SaveSVG tool can be used in [macros](Macros.md) and from the [Python](Python.md) console by using the following functions:


```python
TechDrawGui.exportPageAsSvg(DrawPageObject,FilePath)
```

Note that the FreeCADGui module must be active to use this function.


<div class="mw-translate-fuzzy">





</div>


{{TechDraw Tools navi

}}



---
![](images/Right_arrow.png) [documentation index](../README.md) > [TechDraw](TechDraw_Workbench.md) > TechDraw ExportPageSVG/es
