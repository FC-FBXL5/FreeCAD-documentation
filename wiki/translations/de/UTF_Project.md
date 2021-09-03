


{{VeryImportantMessage|
This roadmap is probably obsolete. For more information see [Development roadmap](Development_roadmap.md).<br>
If you are not involved with the development discussed here:<br>
!!! PLEASE DO NOT EDIT OR TRANSLATE !!!
}}


{{TOCright}}

Dies ist der Projektplan für den FreeCAD Teil der [Development roadmap/de](Development_roadmap/de.md).

## Zweck und Grundsätze {#zweck_und_grundsätze}

Verbesserung der Mehrsprachigkeit in FreeCAD durch die Implementierung der Unterstützung von UTF Zeichen innerhalb der Coin3D Schnittstelle.

Ungeachtet dessen, dass Coin3D nun auf eine offenere Entwicklungsplattform umzieht, ist es weiterhin sehr schwierig, etwas an das Projekt zurückzugeben.

(mrlukeparry) I have yet to receive a response on contributing back and for now it seems more appropriate to keep this within the FreeCAD project and would mean we can let users test without requiring development versions of Coin3D. I would aim to achieve this by 0.14 considering it\'s a big priority for increasing accessibility of FreeCAD to non-english users.

## Organisieren

-   Bereitstellen einer grundlegenden UTF-Zeichenketten-Behandlungsfunktionalität, die unabhängig von wichtigen Bibliotheken außer STL ist.
-   Implementieren der Coin3D-Felder und 3D-Text-Knoten zur Behandlung des neuen UTF-Datenspeichers.
-   Umstellen von Modulen auf die Nutzung der neuen textuellen Knoten
-   Gründliche Tests.

## Nächste Aktionen {#nächste_aktionen}

-   Implementieren der UTF-Zeichenketten-Behandlungsklassen **(in Arbeit)**
-   Behandlung von Schriftarten und Glyphen
-   Implementieren von Coin3D-Textfeldern und Knoten für Benutzung im Projekt
-   Umstellen von Modulen, die SoText2 und SoText3 nutzen, auf Verwendung neuer Knoten



[Category:Roadmap{{\#translation:}}](Category:Roadmap.md)