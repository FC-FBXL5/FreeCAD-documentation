---
- GuiCommand:/de
   Name:TechDraw ExportPageDXF
   Name/de:TechDraw SeiteExportierenDXF
   MenuLocation:TechDraw → Seite als DXF-Datei exportieren 
   Workbenches:[TechDraw](TechDraw_Workbench/de.md)
   Version:0.18
   SeeAlso:[TechDraw SeiteExportierenSVG](TechDraw_ExportPageSVG/de.md), [Draft DXF](Draft_DXF/de.md)
---

# TechDraw ExportPageDXF/de

## Beschreibung

Das Werkzeug SeiteExportierenDXF speichert ein Zeichnungsblatt als [DXF](DXF/de.md)-Datei.

## Anwendung

1.  Eine Seite in der Baumansicht auswählen, wenn das Dokument mehrere Seiten enthält.
2.  Die Schaltfläche **<img src="images/TechDraw_ExportPageDXF.svg" width=16px> [Seite als DXF-Datei exportieren](TechDraw_ExportPageDXF/de.md)** drücken.
3.  Einen Speicherort und einen Dateinamen auswählen.

### Begrenzungen

-   Radien- und Durchmessermaße werden nur dann korrekt exportiert, wenn sie \"innerhalb\" des Bogens liegen.
-   Skalierung wird nicht unterstützt. Das DXF wird in der tatsächlichen Größe der TechDraw Seite gezeichnet.
-   Einheiten werden nicht unterstützt. Das DXF wird in Millimetern (mm) gezeichnet. Bemaßungstext wird genau wie in TechDraw angezeigt.
-   TechDraw kann keine [Draft-Ansicht](TechDraw_DraftView/de.md) oder [Arch-Ansicht](TechDraw_ArchView/de.md) nach DXF exportieren. Diese Ansichten sind [SVG](SVG/de.md)-Elemente, die intern vom Arbeitsbereich [Draft](Draft_Workbench/de.md) generiert werden, sodass es keine geometrische Form zum Exportieren gibt. Um eine Ansicht als DXF zu exportieren, muss sie mit [Ansicht](TechDraw_View/de.md) oder [Ansichtengruppe](TechDraw_ProjectionGroup/de.md) erstellt worden sein. Man wählt z. B. eine [Arch SchnittEbene](Arch_SectionPlane/de.md), danach verwendet man [Draft FormIn2DAnsicht](Draft_Shape2DView/de.md) um eine ebene Projektion zu erstellen, und wendet dann [Ansicht](TechDraw_View/de.md) auf dieses Objekt an. Alternativ wählt man die Objekte in der Baumansicht oder in der 3D-Ansicht aus und exportiert sie mit **Datei → [Exportieren...](Std_Export/de.md)**.
-   Das Schriftfeld einer Seite ist ebenfalls eine [SVG](SVG/de.md)-Vorlage, daher wird es auch nicht nach DXF exportiert.
-   Im Allgemeinen kann TechDraw nur die Elemente nach DXF exportieren, die von der Klasse `Import::ImpExpDxfWrite` des [Draft DXF](Draft_DXF/de.md)-Moduls unterstützt werden.

## Hinweise

-   Diese Funktion exportiert die Versionen R12 (AC1009) und R14 (AC1014) von [DXF](DXF/de.md).
    -   R12 ist eine ältere, einfachere Version des Standards, sollte aber für die meisten anderen Programme lesbar sein.
    -   R14 ist die Standardversion. Sie enthält unter anderem Unterstützung für Splines und Ellipsen.
-   Diese Parameter beeinflussen die Ausgabe:
    -   
        **Werkzeuge → Parameter Berabeiten → BasisApp/Einstellungen/Mod/Import → DxfVersionOut**
        
        . Dies ist ein ganzzahliger Wert. Gültige Einträge sind 12 oder 14. Der Standardwert ist 14.

    -   
        **Werkzeuge → Parameter Berabeiten → BasisApp/Einstellungen/Mod/Import → DiscretizeEllipses**
        
        . Dies ist ein boolescher Wert. Wenn `True`, werden Splines und Ellipsen in Polylinien umgewandelt; wenn `False`, werden Splines und Ellipsen als Splines- und Ellipsenobjekte geschrieben. Die Vorgabe ist `False`. Wenn der Parameter DxfVersionOut 12 ist, werden Splines und Ellipsen immer in Polylinien konvertiert.

    -   
        **Werkzeuge → Parameter Berabeiten → BasisApp/Einstellungen/Mod/Import → maxsegmentlength**
        
        . Dies ist ein Gleitkommawert. Wenn Splines und Ellipsen in Polylinien umgewandelt werden, bestimmt dieser Parameter die Segmentlänge.

## Skripten


**Siehe auch:**

[TechDrawGui API](TechDrawGui_API/de.md) und [FreeCAD Grundlagen Skripten](FreeCAD_Scripting_Basics/de.md).

Das Werkzeug SeiteExportierenDXF kann in [Makros](Macros/de.md) und von der [Python](Python/de.md)-Konsole aus mit den folgenden Funktionen benutzt werden:


```python
TechDraw.writeDXFPage(page,filename)
```





{{TechDraw Tools navi

}}



---
![](images/Right_arrow.png) [documentation index](../README.md) > [TechDraw](TechDraw_Workbench.md) > TechDraw ExportPageDXF/de
