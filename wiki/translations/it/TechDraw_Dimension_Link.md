---
- GuiCommand:/it   Name:TechDraw  Dimension Link   Name/it:Link alla dimensione   Workbenches:[MenuLocation:TechDraw → Link alla geometria 3D   Shortcut:   SeeAlso:[[TechDraw NewView/it|Vista](TechDraw_Workbench/it___TechDraw]].md), [Proiezioni](TechDraw_NewProjGroup/it.md)---


</div>

## Descrizione

Lo strumento Link alla dimensione crea un collegamento tra la geometria 3D e una o più quote proiettate esistenti in una pagina. Questo collegamento permette alla dimensione di utilizzare i valori reali in 3D invece dei valori proiettati in 2D.

L\'uso più comune dello strumento Link alla geometria 3D è nel dimensionamento delle viste isometriche in un gruppo di proiezione. La lunghezza proiettata di un bordo in una vista isometrica, ovviamente, non sarà necessariamente uguale alla lunghezza effettiva del bordo. In una vista ortogonale le lunghezze proiettate e quelle effettive saranno uguali.

Il link alla geomtria 3D indica alla quota di calcolare il valore direttamente dalla geometria 3D.

## Utilizzo


<div class="mw-translate-fuzzy">

1.  Creare una dimensione appropriata nella pagina di disegno usando uno degli strumenti di [Lunghezza](TechDraw_Dimension_Length/it.md), [Dimensione orizzontale](TechDraw_Dimension_Horizontal/it.md), ecc. Questa dimensione sarà posizionata correttamente nella Pagina, ma mostrerà il valore della dimensione proiettata.
2.  Nella vista 3D selezionare la geometria, ad esempio un bordo, che corrisponde alla geometria della dimensione proiettata.
3.  Premere il pulsante **<img src="images/TechDraw_Dimension_Link.svg" width=16px> [Link alla geometria 3D](TechDraw_Dimension_Link/it.md)**.
4.  Si apre una finestra di dialogo. Selezionare una o più quote da collegare alla geometria 3D selezionata.
5.  Premere **OK**.


</div>

Al termine dell\'operazione di collegamento, la proprietà **MeasureType** della dimensione cambia da `Projected` a `True`.

## Limitazioni


<div class="mw-translate-fuzzy">

Gli oggetti dimensione sono vulnerabili ai problemi di \"denominazione topologica\". Per maggiori informazioni vedere le informazioni nello strumento [Lunghezza](TechDraw_Dimension_Length/it.md).


</div>

Lo strumento Link alla dimensione non impedisce di creare collegamenti errati, quindi bisogna scegliere il bordo corretto dalla vista 3D quando si crea il collegamento.

Al momento non c\'è modo di interrompere un link; si può però ripristinare la proprietà **MeasureType** in `Projected` in modo che la dimensione utilizzi il valore proiettato invece del valore collegato.


<div class="mw-translate-fuzzy">

Notare che se la dimensione da collegare si basa su due vertici, si devono selezionare due vertici nella vista 3D. Allo stesso modo se la dimensione si basa su un bordo, è necessario selezionare un bordo nella vista 3D.


</div>

## Proprietà

1.  La proprietà MeasureType di una dimensione collegata cambia da \"Projected\" a \"True\".

## Script


<div class="mw-translate-fuzzy">


**Vedere anche:**

[API TechDraw](TechDraw_API/it.md) e [Nozioni di base sugli script di FreeCAD](FreeCAD_Scripting_Basics/it.md).


</div>


<div class="mw-translate-fuzzy">

Lo strumento Link alla dimensione può essere utilizzato nelle [macro](macros/it.md) e dalla console [Python](Python/it.md) tramite la seguente funzione:


</div>


```python
to be defined
```


<div class="mw-translate-fuzzy">





</div>


{{TechDraw Tools navi

}}  