---
- GuiCommand:/de
   Name:PartDesign_PolarPattern
   Name/de:PartDesign Polares Muster
   MenuLocation:PartDesign → Ein Muster anwenden → PolaresMuster
   Workbenches:[PartDesign](PartDesign_Workbench/de.md)
---

## Beschreibung

Das **Polarmuster** Werkzeug nimmt ein ausgewähltes Formelement und erstellt eine Reihe von Kopien, die um eine ausgewählte Achse gedreht sind. Ab Version 0.17 kann es mehrere Formelemente mustern.

![](images/PartDesign_PolarPattern_example.png )

*Oben: Eine schlitzförmige Tasche (B), die auf einem Grundkörper (A, auch als Träger bezeichnet) angebracht ist, wird für ein Polarmuster verwendet. Das Ergebnis (C) ist rechts dargestellt.*

## Anwendung

#### Ein Muster erstellen {#ein_muster_erstellen}

1.  Wähle (Optional) das Formelement ({{Version/de|0.19}} oder mehrere Formelemente), die gemustert werden sollen.
2.  Drücke die **<img src=images/PartDesign_PolarPattern.svg style="width:24px">** **PolarMuster** Schaltfläche.
    -   Falls du kein Element ausgewählt haben solltest kannst du ein *einziges* Grundelement auswählen.
3.  Definiere die **Achse**. Siehe [Optionen](#Options/de.md).
4.  Definiere den **Winkel** zwischen dem letzten kopierten Auftreten und dem Original Formelement.
5.  Lege die Anzahl der **Häufigkeiten** fest.
6.  Wenn du mehrere Formelemente im Muster hast, kann deren Reihenfolge wichtig sein, siehe Abbildung unten.
7.  Drücke **OK**.

#### Formelemente ordnen {#formelemente_ordnen}

![](images/PartDesign_feature-order.gif ) *Auswirkung der Formelementreihenfolge*


{{Version/de|0.19}}

Du kannst durch Ziehen des Formelements in der Liste die Reihenfolge ändern, und du wirst das Ergebnis sofort als Vorschau sehen.

#### Formelemente hinzufügen {#formelemente_hinzufügen}

###### v0.18

1.  Drücke **Formelement hinzufügen**, um ein Formelement hinzuzufügen, das gemustert werden soll. Das Formelement muss in der [3D Ansicht](3D_view/de.md) sichtbar sein:
    1.  Wechsle in den Modellbaum;
    2.  Wähle in der Struktur das hinzuzufügende Formelement aus und drücke die **Leertaste**, um es in der [3D Ansicht](3D_view/de.md) sichtbar zu machen;
    3.  Wechsle zurück zum Aufgabenpaneel;
    4.  Wähle das Formelement in der 3D Ansicht; es wird der Liste hinzugefügt.
    5.  Wiederhole dies um weitere Formelemente hinzuzufügen.

###### v0.19

1.  Drücke **Formelement hinzufügen**, um ein zu bemusterndes Formelement hinzuzufügen.
2.  Wechsle zum Modellbaum;
3.  Wähle in der Baumstruktur das hinzuzufügende Formelement.
4.  Wiederhole den Vorgang, um weitere Formelemente hinzuzufügen.

#### Formelemente entfernen {#formelemente_entfernen}

-   Rechtsklicke auf das Formelement in der Liste und wähle *Entfernen*.

oder

1.  Drücke **Formelement entfernen** um ein Formelement aus der Liste zu entfernen. Das Formelement muss in der [3D Ansicht](3D_view/de.md) sichtbar sein:
    1.  Wechsle in den Modellbaum;
    2.  Wähle im Baum das zu entfernende Formelement aus und drücke die **Leertaste**, um es in der [3D Ansicht](3D_view/de.md) sichtbar zu machen;
    3.  Wechsle zurück zum Aufgabenpaneel;
    4.  Wähle das Formelement in der 3D Ansicht; es sollte aus der Liste entfernt worden sein.
    5.  Wiederhole dies um weitere Formelemente zu entfernen.

###### v0.19 {#v0.19_1}

1.  Drücke **Formelement entfernen**, um ein Formelement aus der Liste zu entfernen.
2.  Wechsle zum Modellbaum;
3.  Wähle im Baum das zu entfernende Formelement.
4.  Wiederhole den Vorgang, um andere Formelemente zu entfernen.

## Optionen

![](images/Polarpattern_parameters.png )

### Achse

Beim Erstellen eines Polaren Form-Musters bietet der Dialog \"Polardiagramm-Parameter\" verschiedene Möglichkeiten zum Festlegen der Pattern-Rotationsachse.

#### Normale Skizzenachse {#normale_skizzenachse}

Eine Achse, die normal zur Skizze ist und im Ursprung der Skizze des verwendeten Merkmals beginnt, wird als Achse für das polare Muster genommen.
Die Drehrichtung des Musters kann umgekehrt werden, indem Sie auf \"Richtung umkehren\" klicken.

#### Horizontale Skizzenachse {#horizontale_skizzenachse}

Benutzt die horizontale Achse der Skizze als Achse.

#### Vertikale Skizzenachse {#vertikale_skizzenachse}

Benutzt die vertikale Achse der Skizze als Achse.

#### Individuelle Achse in der Skizze {#individuelle_achse_in_der_skizze}

Wenn die Skizze für das zu wiederholende Muster Konstruktionsliniem besitzen, werden diese Konstruktionslinien in dem Dropdown-MenüI als jeweils spezielle Achsen aufgelistet. Die erste Konstruktionslinie wird im Menü als *Konstruktionslinie 1* aufgelistet.

#### Basis (X/Y/Z) Achse {#basis_xyz_achse}


<small>(v0.17)</small> 

Die Standardachsen des Koordinatensystems des Körpers (Body) stehen als Basis X, Y oder Z-Richtung zur Verfügung. 

#### Referenz auswählen\... {#referenz_auswählen...}

Erlaubt Dir, entweder eine Bezugslinie oder eine Kante eines Objekts oder eine Linie einer Skizze als Achse zu benutzen.

### Winkel und Häufigkeiten {#winkel_und_häufigkeiten}

Gibt den Winkel an, der vom Muster abgedeckt werden soll, sowie die Gesamtzahl der Musterformen (einschließlich des ursprünglichen Formelements). Zum Beispiel würden vier Vorkommen in einem Winkel von 180 Grad einen Abstand von 60 Grad zwischen Mustern ergeben. Es gibt eine Ausnahme: Wenn der Winkel 360 Grad beträgt werden z.b vier Vorkommen um 90 Grad voneinander getrennt, weil das erste und das letzte Vorkommen identisch sind. {{Clear}}

## Begrenzungen

-   Siehe [Begrenzungen der linearen Musterformelemente](PartDesign_LinearPattern/de#Begrenzungen.md)








{{PartDesign Tools navi

}} 