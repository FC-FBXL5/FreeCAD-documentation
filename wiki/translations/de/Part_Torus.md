---
- GuiCommand:/de
   Name:Part Torus   Name/de:Part Torus
   MenuLocation:Part → Torus
   Workbenches:[Part](Part_Workbench/de.md)
   SeeAlso:[[Part_CreatePrimitives/de
|Part CreatePrimitives]]
---


</div>

## Description


<div class="mw-translate-fuzzy">

## Zusammenfassung

Erstellt wird ein parametrisierter Torus: Parameter sind der mittlere Ring-Radius dieses \"Schwimmringes\" und der Radius seines Querschnitts.


</div>

<img alt="" src=images/SimpleTorus.jpg  style="width:400px;">


<div class="mw-translate-fuzzy">

## Anwendung


</div>


<div class="mw-translate-fuzzy">

Im Arbeitsbereich Körper (workbench Part) auf das Symbol <img alt="" src=images/Part_Torus.png  style="width:32px;"> klicken. Zunächst entsteht ein vollständiger Torus mit mittlerem Ring-Radius 10 mm und Querschnitt-Radius 2mm.


</div>

**Result:** The torus will be positioned at origin (point 0,0,0) on creation.
The angle parameters (angle1, angle2, angle3), as well as the radius parameters (radius1, radius2) permit to parametrize the torus, see next section.

## Werte wählen {#werte_wählen}

Die gewünschten geometrischen Größen (parametrische Werte) werden als \"Eigenschaften\" in der \"Combo-Ansicht\" eingestellt. Die Erst-Werte lassen sich in der Spalte \"Werte\" überschreiben.

![](images/TorusA.png )

Ein Torus-förmiger Raum wird von einer z.B. in der x-z-Ebene positionierten dünnen Scheibe durchfahren, wenn man diese auf einem Kreis um die z-Achse rotieren lässt.

-    {{Parameter|Radius1:}}Radius des Kreises, auf dem der Mittelpunkt der dünnen Scheibe rotiert bzw. mittlerer Radius des \"Schwimmringes\" (im abgebildeten Beispiel wurde der Erst-Wert 10 mm beibehalten).

-    {{Parameter|Radius2:}}Radius der dünnen Scheibe bzw. Radius der Torus-Querschnitts-Fläche (im abgebildeten Beispiel wurde der Erst-Wert 2 mm beibehalten).

-    {{Parameter|Angle3:}}Winkel eines Torus-Sektors (im abgebildeten Beispiel wurde der Erst-Wert 360° auf 270° verändert, 1/4-Sektor wurde entfernt). Die Winkelvermaßung beginnt bei der positiven x-Achse und erfolgt mathematisch positiv im Gegenuhrzeiger-Sinn.

### Die Winkel Angle2 und Angle3 {#die_winkel_angle2_und_angle3}

Ein Torus als Volumenkörper liegt nur vor, wenn die Erst-Werte dieser beiden Winkel beibehalten werden. Durch Verändern wird der Torus entlang seines größten Durchmessers aufgeschnitten und je ein mehr oder weniger breiter Gurt weggeschnitten. Übrig bleibt lediglich eine masselose Rest-Hülle.

![](images/TorusB.png )

Die Erst-Werte der beiden Winkel Angle2 und Angle3 ergeben in Summe 360°, was den vollständigen Umfang des Torus-Querschnitts-Kreises ausmacht. In der obigen Abbildung ist das xyz-Koordinatensystem in die Mitte des Querschnitts-Kreises verschoben. Der Kreis liegt in der xz-Ebene. Die Winkelvermaßungen beginnen bei der negativen x-Achse und zählen mathematisch positiv im Gegenuhrzeiger-Sinn (negative Werte bei Winkel 1, da im Uhrzeigersinn gezählt).

-    {{Parameter|Angle1:}}Winkel 1 kennzeichnet den Rest des halben Kreises, der sich unterhalb der xy-Ebene befindet. Sein Wert wurde vom Erst-Wert -180° auf -120° verkleinert. 1/6 Kreis wurde entfernt.


<div class="mw-translate-fuzzy">

![](images/TorusExampleAngle3.jpg )  Der Parameter Angle3 hat einen Wert von 90°.


</div>


<div class="mw-translate-fuzzy">





</div>


 