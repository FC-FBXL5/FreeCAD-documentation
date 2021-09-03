---
- GuiCommand:/de
   Name:Draft Point
   Name/de:Entwurf Punkt
   MenuLocation:Entwurf → Punkt
   Workbenches:[Entwurf Arbeitsbereich](Draft_Workbench/de.md), [Architektur](Arch_Module/de.md)
   Version:0.7
---

## Beschreibung

Der <img alt="" src=images/Draft_Point.svg  style="width:24px;"> **Entwurf Punkt** Befehl erzeugt einen einfachen Punkt. Entwurf Punkte kann als eine Referenz für die Platzierung von Linien, Drähten oder anderen Objekten nützlich sein.

<img alt="" src=images/Draft_point_example.jpg  style="width:400px;">

## Anwendung

Siehe auch: [Entwurf Ablage](Draft_Tray/de.md), [Entwurf Fang](Draft_Snap/de.md) und [Entwurf beschränken](Draft_Constrain/de.md).

1.  Es gibt mehrere Möglichkeiten, den Befehl aufzurufen:
2.  Drücke die **<img src="images/Draft_Point.svg" width=16px> [Entwurf Punkt](Draft_Point/de.md)** Schaltfläche
    -   Wähle die Option {{MenuCommand|Entwerfen → <img src="images/Draft_Point.svg" width=16px> Punkt}} aus dem Menü.
    -   Das {{MenuCommand|Punkt}}-Aufgabenpaneel wird geöffnet. Siehe [Optionen](#Optionen.md) für weitere Informationen.
3.  Wähle einen Punkt in der [3D Ansicht](3D_view/de.md), oder gib Koordinaten ein und drücke die **<img src="images/Draft_AddPoint.svg" width=16px> Punkt eingeben**-Schaltfläche.

## Optionen

Die im Aufgabenpaneel verfügbaren Einzelzeichen Tastaturkürzel können geändert werden. Siehe [Entwurf Einstellungen](Draft_Preferences/de.md). Die hier genannten Tastenkürzel sind die Standardtastenkürzel.


<div class="mw-translate-fuzzy">

-   Um manuell Koordinaten einzugeben, trage einfach die Zahlen ein, drücke dann **Enter** zwischen jeder der X-, Y- und Z-Komponenten. Du kannst den **<img src="images/Draft_AddPoint.svg" width=16px> [Punkt hinzufügen](Draft_AddPoint/de.md)**-Button drücken, um den Punkt einzufügen, nachdem Du die gewünschten Werte eingeben hast.
-   Drücke **Alt**+**N** oder klicke das Ankreuzkästchen zur Umschaltung des *\'Nächstes*-Modus. Wenn der Fortsetzungsmodus eingeschaltet ist, wird das Punkt-Werkzeug nach der Eingabe des Punkts erneut starten, ohne dass Du den Werkzeug-Button nochmal drücken musst.
-   Drücke **Esc** oder den **'''Schließen'''**-Button zum Abbruch des aktuellen Befehls.


</div>

## Hinweise

-   Benutze <img alt="" src=images/Draft_Snap_Near.svg  style="width:16px;"> [Draft Fang Nächste](Draft_Snap_Near/de.md), um an Entwurfspunkten einzurasten.

## Einstellungen

Siehe auch: [Einstellungseditor](Preferences_Editor/de.md) und [Entwurf Einstellungen](Draft_Preferences/de.md).

-   To change the number of decimals used for the input of coordinates: {{MenuCommand|Edit → Preferences... → General → Units → Units settings → Number of decimals}}.

## Eigenschaften

Siehe auch: [Eigenschafteneditor](Property_editor/de.md).

Ein Entwurf Punkt Objekt wird von einem [Part Formelement](Part_Feature/de.md) abgeleitet und erbt alle seine Eigenschaften. Außerdem hat es die folgenden zusätzlichen Eigenschaften:

### Daten


{{TitleProperty|Draft}}

-    {{PropertyData/de|X|Abstand}}: gibt die X Koordinate des Punktes an.

-    {{PropertyData/de|Y|Abstand}}: gibt die Y Koordinate des Punktes an.

-    {{PropertyData/de|Z|Abstand}}: gibt die Z Koordinate des Punktes an.

### Ansicht


{{TitleProperty|Draft}}

-    **Pattern|Enumeration**: not used.

-    **Pattern Size|Float**: not used.

## Skripten

Siehe auch: [Autogenerated API documentation](https://freecad.github.io/SourceDoc/) und [FreeCAD Skripten Grundlagen](FreeCAD_Scripting_Basics/de.md).

Um einen Entwurfspunkt zu erstellen, verwende die Methode `make_point` ({{Version/de|0.19}}) des Entwurfsmoduls. Diese Methode ersetzt die veraltete Methode `makePoint`.


```python
point = make_point(X=0, Y=0, Z=0, color=None, name="Point", point_size=5)
point = make_point(point, Y=0, Z=0, color=None, name="Point", point_size=5)
```

-   Erstellt ein `Punkt`-Objekt an den angegebenen `X`-, `Y`- und `Z`-Koordinaten mit Einheiten in mm. Falls keine Koordinaten angegeben werden, wird der Punkt bei (0,0,0) angelegt.
    -   Falls `X` ein durch einen `FreeCAD.Vector` definierter `Punkt` ist, wird dieser verwendet.

-    `color`ist ein Tupel `(R, G, B)`, das die Farbe des Punktes in der RGB-Farbskala angibt; jeder Wert des Tupels sollte im Bereich von `0` bis `1` liegen.

-    `name`ist der Name des Objekts.

-    `point_size`ist die Größe des Objekt in Pixeln, falls die grafische Benutzeroberfläche geladen ist

Beispiel:


```python
import FreeCAD as App
import Draft

doc = App.newDocument()

point1 = Draft.make_point(1600, 1400, 0)

p2 = App.Vector(-3200, 1800, 0)
point2 = Draft.make_point(p2, color=(0.5, 0.3, 0.6), point_size=10)

doc.recompute()
```

Beispiel:

Dieser Code erzeugt `N` zufällige Punkte innerhalb eines Quadrats der Seitenlänge `2L`. Er macht eine Schleife, die `N` Punkte erzeugt, die überall von `-L` bis `+L` auf X und Y erscheinen können. Er wählt auch eine zufällige Farbe und Größe für jeden Punkt. Ändere `N`, um die Anzahl der Punkte zu ändern, und ändere `L`, um den von den Punkten abgedeckten Bereich zu ändern.


```python
import random
import FreeCAD as App
import Draft

doc = App.newDocument()

L = 1000
centered = App.Placement(App.Vector(-L, -L, 0), App.Rotation())
rectangle = Draft.make_rectangle(2*L, 2*L, placement=centered)

N = 10
for i in range(N):
    x = 2*L*random.random() - L
    y = 2*L*random.random() - L
    z = 0
    r = random.random()
    g = random.random()
    b = random.random()
    size = 15*random.random() + 5
    Draft.make_point(x, y, z, color=(r, g, b), point_size=size)

doc.recompute()
```





 