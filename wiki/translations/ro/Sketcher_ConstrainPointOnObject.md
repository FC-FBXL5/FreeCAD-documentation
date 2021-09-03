---
- GuiCommand:
   Name:Sketcher ConstrainPointOnObject
   Workbenches:[Sketcher](Sketcher_Workbench.md)
   MenuLocation:Sketch → Sketcher constraints → Constrain point onto object
   Shortcut:Shift+O
   SeeAlso:[Constrain Coincident](Sketcher_ConstrainCoincident.md)
---


</div>

## Descriere

Aplică un punct pe un alt obiect, cum ar fi o linie, un arc sau o axă de schiță.


<div class="mw-translate-fuzzy">

## Cum se folosește {#cum_se_folosește}

1.  Selectați punctul pe care doriți să îl aplicați pe o linie/arc/etc. (Odată selectat punctul devine verde).
2.  Selectați linia pe care doriți să o atașați la punctul pe care tocmai l-ați selectat(Odată selecatată linia devine verde).
3.  Apăsați butonul **<img src=images/Constraint_PointOnObject.png style="width:24px"> '''Constrain point unto object'''**.


</div>

1.  Select the point you want to affix onto a line/arc/etc. (**Result:** Once selected the point will become green).
2.  Select the line you want affixed onto the point you have just selected (**Result:** Once selected the line becomes green).
3.  Invoke the **Constrain point onto object** tool using several methods:
    -   Press the **<img src=images/Sketcher_ConstrainPointOnObject.svg style="width:16px"> [Point on object](Sketcher_ConstrainPointOnObject.md)** button in the toolbar.
    -   Use the **Shift** + **O** keyboard shortcut.
    -   Use the {{MenuCommand|Sketch → Sketcher constraints → Constrain point onto object}} entry in the top menu.


<div class="mw-translate-fuzzy">

Notă : Ordinea în care alegeți linia și punctul nu contează. Punctul se va muta întotdeauna pe linie. Linia rămâne fixă.


</div>

### Script

Constrângerea poate fi creată din macrocomenzi și din consola Python folosind următoarea comandă:


`Sketch.addConstraint(Sketcher.Constraint('PointOnObject',LineMoving,PointOfLineMoving,LineFixed))`


<div class="mw-translate-fuzzy">

-   Sketch este un obiect sketch
-   LineMoving este numărul care desemnează linia, care conține punctul care trebuie mutat pe LineFixed (Linia care este fixă)
-   PointOfLineMoving este numărul vârfului liniei LineMoving, care trebuie mutat pe LineFixed
-   LinedFixed este numărul liniei care trebuie aplicată pe punctul PointOfLineMoving


</div>


<div class="mw-translate-fuzzy">

Pentru a identifica numărul care are indică liniile și punctele? Vă rog să vă referinți la parte de script a [Sketcher ConstrainCoincident](Sketcher_ConstrainCoincident.md).


</div>





{{Sketcher Tools navi

}}  