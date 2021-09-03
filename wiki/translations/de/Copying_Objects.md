 {{TOCright}}

## Übersicht

Wie viele andere Software hat auch FreeCAD die Möglichkeit, Objekte zu kopieren/auszuschneiden und einzufügen (Absätze, Tabellenzellen, Bilder, usw.). [Dokument](Document_structure/de.md) Objekte können innerhalb eines Dokuments oder zwischen Dokumenten frei kopiert werden, durch verwenden der **<img src="images/Std_Copy.svg" width=24px> [Kopieren](Std_Copy/de.md)**, **<img src="images/Std_Paste.svg" width=24px> [Einfügen](Std_Paste/de.md)** und **[Auswahl duplizieren](Std_DuplicateSelection/de.md)** Befehle.

![](images/Copy_past_duplicate.png )

Bitte beachte, dass die kopiert-eingefügten Objekte nicht vom Original abhängig sind. Wenn du abhängige Klone möchtest, verwende bitte <img alt="" src=images/Draft_Clone.svg  style="width:24px;"> [Arbeitsbereich Entwurf Klon](Draft_Clone/de.md) oder <img alt="" src=images/PartDesign_Clone.svg  style="width:24px;"> [PartDesign Arbeitsbereich Klon](PartDesign_Clone/de.md). Wenn du weder einen abhängigen Klon noch ein parametrisches Abbild brauchst, kannst du auch <img alt="" src=images/Part_SimpleCopy.svg  style="width:24px;"> [Formteil Arbeitsbereich Einfache Kopie](Part_SimpleCopy/de.md) verwenden. Für gemusterte Klone schaue bitte in den Abschnitt [Andere Methoden](Copying_Objects/de#Andere_Methoden.md) auf dieser Seite.

## Kopieren verknüpfter Objekte {#kopieren_verknüpfter_objekte}

[Dokument](Document_structure/de.md) Objekte können mit anderen Objekten verknüpft sein (z.B. ein Polster Formelement ist mit seiner Skizze, und ein Verschmelzungsformelement ist mit seinen Komponentenobjekten verknüpft). Dies bedeutet, dass bei der Auswahl der zu kopierenden Objekte eine gewisse Vorsicht geboten ist.

Wenn ein Objekt ohne seine Kinder ausgewählt wird, werden diese Kinder nicht automatisch durch Kopieren/Einfügen oder Auswahl duplizieren dupliziert. In diesem Fall kann das kopierte Objekt ein unerwartetes Verhalten zeigen, da die erwarteten Verknüpfungen nicht vorhanden sind.

Im Allgemeinen wird empfohlen, beim Kopieren eines übergeordneten Objekts alle abhängigen Objekte auszuwählen.

## Finden und Positionieren von eingefügten Objekt(en) {#finden_und_positionieren_von_eingefügten_objekten}

Nach dem Kopieren/Einfügen Vorgang ist es möglicherweise nicht offensichtlich, wo sich das/die neue(n) Objekt(e) im Dokumentfenster befinden. Das liegt daran, dass das neue Objekt die gleiche [Platzierungseigenschaft](Placement/de.md) wie das Original hat. Schalten die Eigenschaft Sichtbarkeit um (**Leertaste**), um das Original auszublenden. Verwende dann den Platzierungsdialog, um die Kopie an die richtige Position zu verschieben.

## Andere Methoden {#andere_methoden}

Wie bei den meisten Dingen in FreeCAD gibt es viele Möglichkeiten, eine Kopie zu erstellen. Für weitere Ideen schau unter:

-   PartDesign: [Gespiegelt](PartDesign_Mirrored/de.md), [Lineares Muster](PartDesign_LinearPattern/de.md), [Radiales Muster](PartDesign_PolarPattern/de.md), [Mehrfachtransformation](PartDesign_MultiTransform/de.md)
-   Part: [Spiegeln](Part_Mirror/de.md), [Einfache Kopie erstellen](Part_SimpleCopy/de.md)
-   Draft: [Versetzen](Draft_Offset/de.md), [Skalieren](Draft_Scale/de.md), [AnordnungRechtwinklig](Draft_OrthoArray/de.md), [PfadAnordnen](Draft_PathArray/de.md), [Klonen](Draft_Clone/de.md), [Spiegeln](Draft_Mirror/de.md)

## Hinweise

-   Wenn ein zu kopierendes Objekt Verweise auf Objekte(n) hat, die nicht in der Auswahl sind, fragt FreeCAD, ob die nicht ausgewählten Objekte in den Kopiervorgang einbezogen werden sollen. {{Version/de|0.14}}

## Mehr

-   [Kopieren](Std_Copy/de.md)
-   [Einfügen](Std_Paste/de.md)
-   [Auswahl duplizieren](Std_DuplicateSelection/de.md)


