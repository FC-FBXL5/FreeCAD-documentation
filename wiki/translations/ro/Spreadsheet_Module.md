 

<img alt="Spreadsheet workbench icon" src=images/Workbench_Spreadsheet.svg  style="width:128px;">

## Introduction


<div class="mw-translate-fuzzy">


<small>(v0.15)</small> 

Atelierul lucru pentru foi de calcul vă permite să creați și să editați foi de calcul, să efectuați calcule și să preluați date dintr-un model și să exportați datele sale în alte aplicații de calcul tabelar, cum ar fi LibreOffice sau Microsoft Excel.


</div>


<div class="mw-translate-fuzzy">

![](images/Spreadsheet_screenshot.jpg )


</div>

<img alt="" src=images/Spreadsheet_screenshot.jpg  style="width:600px;"> 
*A spreadsheet with certain cells filled with text and quantities*

## Tools

-   <img alt="" src=images/Spreadsheet_CreateSheet.svg  style="width:24px;"> [Create sheet](Spreadsheet_CreateSheet.md): create a new spreadsheet.

-   <img alt="" src=images/Spreadsheet_Import.svg  style="width:24px;"> [Import](Spreadsheet_Import.md): import a tab-separated values file into a spreadsheet.
-   <img alt="" src=images/Spreadsheet_Export.svg  style="width:24px;"> [Export](Spreadsheet_Export.md): export a tab-separated values file from a spreadsheet.

-   <img alt="" src=images/Spreadsheet_MergeCells.svg  style="width:24px;"> [Merge cells](Spreadsheet_MergeCells.md): merge selected cells.
-   <img alt="" src=images/Spreadsheet_SplitCell.svg  style="width:24px;"> [Split cell](Spreadsheet_SplitCell.md): split previously merged cells.

-   <img alt="" src=images/Spreadsheet_AlignLeft.svg  style="width:24px;"> [Align left](Spreadsheet_AlignLeft.md): align the contents of selected cells to the left.
-   <img alt="" src=images/Spreadsheet_AlignCenter.svg  style="width:24px;"> [Align center](Spreadsheet_AlignCenter.md): align the contents of selected cells to the center horizontally.
-   <img alt="" src=images/Spreadsheet_AlignRight.svg  style="width:24px;"> [Align right](Spreadsheet_AlignRight.md): align the contents of selected cells to the right.
-   <img alt="" src=images/Spreadsheet_AlignTop.svg  style="width:24px;"> [Align top](Spreadsheet_AlignTop.md): align the contents of selected cells to the top.
-   <img alt="" src=images/Spreadsheet_AlignVCenter.svg  style="width:24px;"> [Align vertical center](Spreadsheet_AlignVCenter.md): align the contents of selected cells to the center vertically.
-   <img alt="" src=images/Spreadsheet_AlignBottom.svg  style="width:24px;"> [Align bottom](Spreadsheet_AlignBottom.md): top align the contents of selected cells to the bottom.

-   <img alt="" src=images/Spreadsheet_StyleBold.svg  style="width:24px;"> [Style bold](Spreadsheet_StyleBold.md): set the contents of selected cells to bold.
-   <img alt="" src=images/Spreadsheet_StyleItalic.svg  style="width:24px;"> [Style italic](Spreadsheet_StyleItalic.md): set the contents of selected cells to italic.
-   <img alt="" src=images/Spreadsheet_StyleUnderline.svg  style="width:24px;"> [Style underline](Spreadsheet_StyleUnderline.md): set the contents of selected cells to underlined.

-   <img alt="" src=images/Spreadsheet_SetAlias.svg  style="width:24px;"> [Set alias](Spreadsheet_SetAlias.md): set alias for selected cells.

-    **Black**and **White** set the foreground and the background colors of the selected cells.

-   Context-menu of the spreadsheet rows and columns: right-click onto the header of a row or column to insert a new row above or a new column at the left, or to delete the current row/column. You can also select several rows or columns to delete them.<small>(v0.20)</small>  You can also select where the the new rows/columns will be inserted. Furthermore, to insert for example 3 new columns at once, select 3 columns and use the context-menu that will now offer to insert 3 columns.


<div class="mw-translate-fuzzy">

## Proprietățile celulei {#proprietățile_celulei}


</div>

Proprietățile unei celule de calcul tabelar pot fi editate cu un clic dreapta pe o celulă. Următoarele dialoguri apar:

![](images/SpreadsheetCellPropDialog.png )


<div class="mw-translate-fuzzy">

Are câteva tab-uri. Următoarele proprietăți pot fi modificate:


</div>


<div class="mw-translate-fuzzy">

-   Culoarea textului și culoarea de fundal
-   Aliniere text orizontală și verticală
-   Stil text: bold, italic, subliniat
-   Unitate de afișare pentru această celulă. Citiți secțiunea de mai jos.
-   Definiți un nume alias pentru această celulă. Acest alias-nume poate fi folosit în formulele de celule și, de asemenea, în FreeCADExpressions <small>(v0.16)</small> 


</div>

## Cell expressions {#cell_expressions}

A spreadsheet cell may contain arbitrary text or an expression. Technically, expressions must start with an equals \'=\' sign. However, the spreadsheet attempts to be intelligent; if you enter what looks like an expression without the leading \'=\', one will be added automatically.

Cell expressions may contain numbers, functions, references to other cells, and references to properties of the model (But see [Current limitations](#Current_limitations.md) below). Cells are referenced by their column (CAPITAL letter) and row (number). A cell may also be referenced by its [alias-name](#alias_name.md) (below). Example: B4 + A6

**Note:** Cell expressions are treated by FreeCAD as programming code. Therefore, when you edit a cell the content you see that it is not following your display settings:

-   the decimal separator is always a dot
-   the number of displayed decimals can differ from your [preferences settings](Preferences_Editor#Units.md)

References to objects in the model are explained under [References to CAD-data](#References_to_CAD-data.md) below. Using spreadsheet cell values to define model properties are explained under [Spreadsheet data in expressions](#Spreadsheet_data_in_expressions.md) below. For more information on expressions and the available functions, see [Expressions](Expressions.md).

## Interaction between spreadsheets and the CAD model {#interaction_between_spreadsheets_and_the_cad_model}

Data in the cells of a spreadsheet may be used in CAD model parameter expressions. Thus, a spreadsheet may be used as the source for parameter values used throughout a model, effectively gathering the values in one place. When values are changed in the spreadsheet, they are propagated throughout the model.

Similarly, properties from CAD model objects may be used in expressions in spreadsheet cells. This allows use of object properties like volume or area in the spreadsheet. If the name of an object in the CAD model is changed, the change will automatically be propagated to any references in spreadsheet expressions using the name which was changed.

More than one spreadsheet may be used in a document. A spreadsheet can be identified using either its name or its label.

FreeCAD will automatically assign a unique name to a spreadsheet when it is created. These names follow the pattern `Spreadsheet`, `Spreadsheet001`, `Spreadsheet002` and so on. The name can not be changed manually, and it is not visible in the properties of the spreadsheet. It can be used to refer to the spreadsheet in an [Expression](Expressions.md) (see [Spreadsheet data in expressions](#Spreadsheet_data_in_expressions.md) below.)

The label of a spreadsheet is automatically set to the name of the spreadsheet upon creation. Unlike the name, the label can be changed, for example in the properties panel or using the context menu action Rename. Note that the label of a spreadsheet within a document has to be unique; if you try to change the label to a label already used by another spreadsheet, FreeCAD will not accept the new label.

FreeCAD checks for cyclic dependencies. See [Current limitations](Spreadsheet_Workbench#Current_limitations.md).


<div class="mw-translate-fuzzy">

## Referință To CAD-Data {#referință_to_cad_data}


</div>


<div class="mw-translate-fuzzy">

Este posibil să utilizați datele din construcție în foaia de calcul. Următorul tabel prezintă câteva exemple, presupunând că modelul are o caracteristică numită \"Cube\" (rețineți că acesta este numele intern al caracteristicii, și nu numele utilizatorului atribuit etichetei):

  CAD-Data                                     Call in Spreadsheet          Result
  -------------------------------------------- ---------------------------- ----------------------------------
  Parametric Length of a Part-Workbench Cube   =Cube.Length                 Length with units mm
  Volume of the Cube                           =Cube.Shape.Volume           Volume in mm³ without units
  Type of the Cube-shape                       =Cube.Shape.ShapeType        String: Solid
  Label of the Cube                            =Cube.Label                  String: Cube
  x-coordinate of center of mass of the Cube   =Cube.Shape.CenterOfMass.x   x-coordinate in mm without units


</div>

Computed expressions in spreadsheet cells start with an equals (\'=\') sign. However, the spreadsheet entry mechanism attempts to be smart. An expression may be entered without the leading \'=\'; if the string entered is a valid expression, an \'=\' is automatically added when the final **Enter** is typed. If the string entered is not a valid expression (often the result of entering something with the wrong case, e.g. \"MyCube.length\" instead of \"MyCube.Length\"), no leading \'=\' is added and it is treated as simply a text string.

**Note:** The above behavior (auto insert of \'=\') has some unpleasant ramifications:

-   If you want to keep a column of names corresponding to the [alias-names](#alias_name.md) in an adjacent column of values, you must enter the name in the label column *before* giving the cell in the value column its alias-name. Otherwise, when you enter the alias-name in the label column the spreadsheet will assume it is an expression and change it to \"=\"; and the displayed text will be the value from the  cell.
-   If you make an error when entering the name in the label column and wish to correct it, you cannot simply change it to the alias-name. Instead, you must first change the alias-name to something else, then fix the text name in the label column, then change the alias-name in the value column back to its original.

One way to side-step these issues is to prefix text labels corresponding to alias-names with a fixed string, thereby making them different. Note that \"\_\" will not work, as it is converted to \"=\". However, a blank, while invisible, will work.

The following table shows some examples assuming the model has a feature named \"MyCube\":

  CAD-Data                                     Cell in Spreadsheet            Result
  -------------------------------------------- ------------------------------ ----------------------------------
  Parametric Length of a Part-Workbench Cube   =MyCube.Length                 Length with units mm
  Volume of the Cube                           =MyCube.Shape.Volume           Volume in mm³ without units
  Type of the Cube-shape                       =MyCube.Shape.ShapeType        String: Solid
  Label of the Cube                            =MyCube.Label                  String: MyCube
  x-coordinate of center of mass of the Cube   =MyCube.Shape.CenterOfMass.x   x-coordinate in mm without units


<div class="mw-translate-fuzzy">

## Spreadsheet Data în Expresii {#spreadsheet_data_în_expresii}


</div>

In order to use spreadsheet data in other parts of FreeCAD, you will usually create an [Expression](Expressions.md) that refers to the spreadsheet and the cell that contains the data you want to use. You can identify spreadsheets by name or by label, and you can identify the cells by position or by alias. Autocompletion is available for all forms of referencing.

+------------------+-----------------------------------------------------+--------------------------------------------------------+
|                  | Spreadsheet by Name                                 | Spreadsheet by Label                                   |
+==================+=====================================================+========================================================+
| Cell by Position |                                      |                                         |
|                  | `<nowiki>=Spreadsheet042.B5</nowiki>`      | `<nowiki>=<<MySpreadsheet>>.B5</nowiki>`      |
|                  |                                                  |                                                     |
+------------------+-----------------------------------------------------+--------------------------------------------------------+
| Cell by Alias    |                                      |                                         |
|                  | `<nowiki>=Spreadsheet042.MyAlias</nowiki>` | `<nowiki>=<<MySpreadsheet>>.MyAlias</nowiki>` |
|                  |                                                  |                                                     |
+------------------+-----------------------------------------------------+--------------------------------------------------------+


<div class="mw-collapsible mw-collapsed">

The recommended way to refer to spreadsheet data is to use the spreadsheet label and cell alias name. For a more in-depth explanation of the pros and cons of the addressing modes, see the expanded section below.


<div class="mw-collapsible-content">

Using the spreadsheet label has the advantage that it can be freely changed to describe the contents of the spreadsheet. It is also easier to identify the spreadsheet that is being used since the text in the expression matches the label shown in the model and property views. If you decide to change the label of a spreadsheet, existing references to the contents of the spreadsheet will be updated, so you won\'t break your expressions by renaming the spreadsheet. The internal name of the spreadsheet is not readily available anywhere except within the expression editor, so if you use the internal name and later decide to rename the spreadsheets, you might have a hard time tracing your expression data back to its source.

Be aware that when you create a new spreadsheet, the name and the label are the same, so it is easy to accidentally use the spreadsheet name instead of the label. A simple way to avoid this is to give the spreadsheet a meaningful name before starting to use it in expressions.

While you may use the row and column number in an expression to reference a cell, best practice is to give the cell an alias name and use that. See [Cell Properties](#Cell_Properties.md) above on how to set the alias. For example, if the data in cell B1 contained the length parameter for an object, an alias name of `MyObject_Length` would allow the value to be referred to as `<<MyParams>>.MyObject_Length` instead of `Spreadsheet.B1`. Besides being much easier to read and understand, alias names are also much easier to change if you decide to adjust the structure of your spreadsheet. Using an alias also has the advantage that it is reasier to see which cells are used to control other parts of the document. Note that FreeCAD will automatically adjust the positional references in expressions if you insert or remove rows and columns in the spreadsheet, so even if you use row and column numbers in an expression, you can insert rows and columns without breaking the references to the surrounding cells.


</div>


</div>

### Complex models and recomputes {#complex_models_and_recomputes}

Editing a spreadsheet will trigger a recompute of the 3D model, even if the changes do not affect the model. For a complex model a recompute can take a long time, and having to wait after every single edit is of course quite annoying.

There are three solutions to deal with this:

1.  Temporarily skip recomputes:
    -   In the [Tree view](Tree_view.md) right-click the <img alt="" src=images/Document.svg  style="width:24px;"> document that contains the spreadsheet.
    -   Select the {{MenuCommand|Skip recomputes}} option from the context menu.
    -   There is a big disadvantage to this solution. New values entered in the spreadsheet will not be displayed until the document is recomputed. Instead `#PENDING` is shown.
    -   You can either recompute manually, using the [Std Refresh](Std_Refresh.md) command, or disable {{MenuCommand|Skip recomputes}} when you are done editing.
2.  Use a macro to automatically skip recomputes while editing a spreadsheet:
    -   Download and run [skipSheet.FCMacro](https://forum.freecadweb.org/viewtopic.php?f=8&t=48600#p419301).
    -   This solution saves a few steps compared to the first solution, but also has the mentioned disadvantage.
3.  Put the spreadsheet in a separate file:
    -   You can reference spreadsheet data from an external file with this syntax: `<nowiki>=NameOfFile#<<MySpreadsheet>>.MyAlias</nowiki>`.
    -   The advantage of having the spreadsheet in another file over switching off recomputes is that the spreadsheet itself does get recomputed.
    -   The disadvantage is that the model won\'t automatically recompute after changes to the spreadsheet.
    -   In the scenario where you first open the \'spreadsheet\' file, change one or more values and then open the \'model\' file, there won\'t be any indication that the model needs to be recomputed. But if both files are open the [Std Refresh](Std_Refresh.md) icon will update correctly for the \'model\' file after changes to the \'spreadsheet\' file.

## Unități de măsură {#unități_de_măsură}


<div class="mw-translate-fuzzy">

Foaia de calcul utilizează unități. Dacă un număr are o unitate, această unitate va fi utilizată în toate calculele. Înmulțirea a două lungimi cu unitatea în mm dă o suprafață cu unitatea mm pătrați-mm & sup2 ;.


</div>

If a cell contains a value which represents a dimension, it should be entered with its associated unit. While in many simple cases one can get by with a dimensionless value, it is unwise to not enter the unit. If a value representing a dimension is entered without its associated unit, there are some sequences of operations which cause FreeCAD to complain of incompatible units in an expression when it appears the expression should be valid. (This may be better understood by viewing [this thread](https://forum.freecadweb.org/viewtopic.php?f=3&t=34713&p=292455#p292438) in the FreeCAD forums.)


<div class="mw-translate-fuzzy">

Puteți schimba unitatea de lungime de la mm la inch prin dialog, veți obține cu un clic dreapta pe o celulă. Celula va arăta acum lungimea în centimetri. Valoarea utilizată pentru calcule nu se modifică. Rezultatele unei formule care utilizează această valoare nu se modifică atunci când unitatea indicată a unei intrări a fost modificată. Rezultatul se calculează încă din lungimea în mm.


</div>


<div class="mw-translate-fuzzy">

Un număr fără o unitate de măsură nu poate fi modificat într-un număr cu unitate de măsură prin dialogul proprietăților celulare. Se poate introduce un șir de unități, care va fi afișat, dar celula conține încă un număr fără unitate de măsură.


</div>


<div class="mw-translate-fuzzy">

Uneori este de dorit să scapi de o unitate. Acest lucru se poate face numai prin înmulțirea cu 1 cu o unitate reciprocă.


</div>

## Import și export {#import_și_export}


<div class="mw-translate-fuzzy">

Foiile de calcul pot fi importate și exportate în formatul [csv](https://en.wikipedia.org/wiki/Comma-separated_values), care poate fi, de asemenea, citit și scris de majoritatea altor aplicații de calcul tabelar, cum ar fi Microsoft Excel sau LibreOffice Calc. Când importați fișiere în FreeCAD, separatorul/delimitatorul (caracterul care este utilizat pentru a separa coloanele) trebuie să fie caracterul TAB (acest lucru poate fi setat când exportați din alte aplicații). Importul unui fișier CSV este disponibil prin intermediul foii de calcul Spreadsheet / Import sau prin apăsarea pe pictograma ![ 24px](images/_SpreadsheetImport.svg ). Această funcție de import nu deschide fișiere Excel sau orice alt format de foaie de calcul.


</div>


<div class="mw-translate-fuzzy">

Foile de calcul în format Excel \"xlsx\" pot fi importate prin meniul File / Import \... într-un document FreeCAD. Foile de calcul Excel pot fi deschise de FreeCAD făcând clic pe meniul File / Open \... sau făcând clic pe pictograma ![ 24px](images/_Document-open.svg ). În acest caz se creează un nou document cu o foaie de calcul în interior. Sunt acceptate următoarele caracteristici:


</div>


<div class="mw-translate-fuzzy">

-   toate funcțiile disponibile și în foaia de calcul FreeCAD. Alte funcții dau o eroare în celula corespunzătoare după import.
-   Alias nume pentru celule
-   Mai mult de un tabel din foaia Excel. În acest caz, sunt create mai multe foi de calcul FreeCAD.


</div>


<div class="mw-translate-fuzzy">

Alte funcționalități nu sunt importate în foaia de calcul FreeCAD. Importul Excel este {{Version | 0.17}} al FreeCAD.


</div>

## Printing

To handle the page setup necessary for printing, FreeCAD spreadsheets are printed by inserting them into a [TechDraw Spreadsheet View](TechDraw_SpreadsheetView.md).


<div class="mw-translate-fuzzy">

## Limitări curente {#limitări_curente}


</div>


<div class="mw-translate-fuzzy">

Nu este posibilă furnizarea de date pentru o geometrie, de exemplu o lungime, într-o foaie de calcul și extragerea în aceeași foaie de calcul a volumului forma rezultată. Aceasta va crea o referință circulară. Aceasta este o decizie de proiectare. Cu toate acestea, este posibil să utilizați două foi de calcul diferite: una ca sursă de date pentru geometrie și altul pentru raportarea datelor geometrice.


</div>


<div class="mw-translate-fuzzy">

Nu este posibilă selectarea și copierea mai multor celule. Numai conținutul unei celule din câmpul de introducere poate fi copiat și inserat în câmpul de intrare al unei alte celule.


</div>


<div class="mw-translate-fuzzy">

## Bazele script programări {#bazele_script_programări}


</div>


```python
import Spreadsheet
sheet = App.ActiveDocument.addObject("Spreadsheet::Sheet","MySpreadsheet")
sheet.Label = "Dimensions"

sheet.set('A1','10mm')
sheet.recompute()
sheet.get('A1')

sheet.setAlias('B1','Diameter')
sheet.set('Diameter','20mm')
sheet.recompute()
sheet.get('Diameter')
```


<div class="mw-translate-fuzzy">





</div>


{{Spreadsheet_Tools_navi

}} 

[Category:Workbenches{{\#translation:}}](Category:Workbenches.md)