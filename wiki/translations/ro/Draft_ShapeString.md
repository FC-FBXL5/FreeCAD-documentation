---
- GuiCommand:/ro   Name:Draft ShapeString   Name/ro:Draft ShapeString   Workbenches:[Arch](Draft_Module/ro___Draft]],_[[Arch_Module/ro.md)|MenuLocation:Draft → Shape from text ...   Shortcut:S S   SeeAlso:[Draft Text](Draft_Text/ro.md), [Part Extrude](Part_Extrude/ro.md)---


</div>

## Descriere


<div class="mw-translate-fuzzy">

Instrumentul ShapeString introduce o formă compusă care reprezintă un șir de caractere(text) într-un punct dat în documentul curent. Pot fi definite atribute ca: Înălțimea textului, tipul fontul, etc. The resulting shape can be used with the [Part Extrude](Part_Extrude/ro.md) tool to create 3D letters.


</div>


<div class="mw-translate-fuzzy">

Cele [Draft Text](Draft_Text/ro.md) instrumentul este o alternativă mai simplă, care nu produce o formă închisă.


</div>

![](images/Draft_ShapeString_Example400.png )


<div class="mw-translate-fuzzy">

![](images/Draft_ShapeString_Example400.png )


</div>


<div class="mw-translate-fuzzy">

## Cum se folosește {#cum_se_folosește}


</div>

1.  There are several ways to invoke the command:
    -   Press the **<img src="images/Draft_ShapeString.svg" width=16px> [Draft ShapeString](Draft_ShapeString.md)** button.
    -   Select the {{MenuCommand|Drafting → <img src="images/Draft_ShapeString.svg" width=16px> Shape from text}} option from the menu.
    -   Use the keyboard shortcut: **S** then **S**.
2.  The {{MenuCommand|ShapeString}} task panel opens.
3.  Click a point in the [3D view](3D_view.md), or type coordinates.
4.  Optionally press the **Reset Point** button to reset the point to the origin.
5.  Enter a {{MenuCommand|String}}.
6.  Specify the {{MenuCommand|Height}}.
7.  To select a font do one of the following:
    -   Enter a file path in the {{MenuCommand|Font file}} input box.
    -   Press the **...** button and select a file.
8.  Press the **OK** button to finish the command.

## Opţiuni


<div class="mw-translate-fuzzy">

-   Pentru a introduce coordonatele manual, pur și simplu introduceți numerele, apoi apăsați **ENTER** între fiecare componenetă pe X, Y și Z.
-   Apăsați tasta **ESC**pentru a abandona operațiunea.
-   Puteți defini un fișier de font implicit în Draft/Prefences.


</div>

## Notes


<div class="mw-translate-fuzzy">

## Limitations

-   Acest instrumente nu este disponibil pentru versiunile anterioarea lui FreeCAD 0.14
-   Sunt suportatea următoareal tipuri de fișiere pentru fonturi: TrueType(\*.ttf), OpenType(\*.otf) și Type1(\*.pfb).
-   Înălțimile foarte mici ale textului pot cauza distorsionarea glifelor de caractere din cauza pierderii detaliilor la scalare.
-   Versiunea actuală este limitată la scrierile de la stânga la dreapta pe o linie de bază orizontală.
-   Pentru a crea texte de formă curbă puteți utiliza macrocomanda <img alt="" src=images/FCCircularTextButtom.png  style="width:24px;">[Circular Text](Macro_Circular_Text.md)


</div>


<div class="mw-translate-fuzzy">

## Tutorials

-   [Draft ShapeString tutorial](Draft_ShapeString_tutorial/ro.md)


</div>

-   [Draft ShapeString tutorial](Draft_ShapeString_tutorial.md): extrude a ShapeString, position it in 3D space, and create an engraving in another body.
-   [How to use ShapeStrings in PartDesign](https://forum.freecadweb.org/viewtopic.php?f=3&t=36623)

## Preferences

See also: [Preferences Editor](Preferences_Editor.md) and [Draft Preferences](Draft_Preferences.md).

-   The default font file can be changed in the preferences: {{MenuCommand|Edit → Preferences... → Draft → Texts and dimensions → Default ShapeString font file}}. See [Draft Preferences](Draft_Preferences.md).

## Proprietăți

See also: [Property editor](Property_editor.md).

A Draft ShapeString object is derived from a [Part Part2DObject](Part_Part2DObject.md) and inherits all its properties. It also has the following additional properties:

### Data


{{TitleProperty|Draft}}


<div class="mw-translate-fuzzy">

-    {{PropertyData/ro|Position}}: Punctul de bază a formei compuse

-    {{PropertyData/ro|String}}: Conținutul șirului tip text

-    {{PropertyData/ro|Size}}: Înălțimea literelor exprimată în unități FC

-    {{PropertyData/ro|Tracking}}: Spațierea dintre caractere exprimată în unități FC

-    {{PropertyData/ro|Font File}}: Definirea fișierului fontului utilizat pentru a desena șirul de caractere


</div>

### View


{{TitleProperty|Draft}}

-    **Pattern|Enumeration**: specifies the [Draft Pattern](Draft_Pattern.md) with which to fill the faces of the text. This property only works if **Display Mode** is {{value|Flat Lines}}.

-    **Pattern Size|Float**: specifies the size of the [Draft Pattern](Draft_Pattern.md).

## Scripting


<div class="mw-translate-fuzzy">

## Scripturi


</div>


<div class="mw-translate-fuzzy">

Instrumentul ShapeString poate fi utilizat în [macros](macros/ro.md) și de la consola Python folosind următoarele funcții:


</div>


```python
shapestring = make_shapestring(String, FontFile, Size=100, Tracking=0)
```


<div class="mw-translate-fuzzy">

-   Transformați un șir tip text într-o Compound Shape utilizând fontul specificat.
-   Creează o formă compusă ShapeString utilizând codul String specificat

  +

-   FontFile este obligatorie și trebuie să fie calea completă a unui fișier de fonturi acceptat

  +

-   Size este înălțimea textului rezultat în milimetri

  +

-   Tracking este distanța inter-caracter suplimentară în milimetri


</div>

The placement of the ShapeString can be changed by overwriting its `Placement` attribute, or by individually overwriting its `Placement.Base` and `Placement.Rotation` attributes.

Exempluː


```python
import FreeCAD as App
import Draft

doc = App.newDocument()

font1 = "/usr/share/fonts/truetype/msttcorefonts/Arial.ttf"
font2 = "/usr/share/fonts/truetype/dejavu/DejaVuSerif.ttf"
font3 = "/usr/share/fonts/truetype/freefont/FreeSerifItalic.ttf"

S1 = Draft.make_shapestring("This is a sample text", font1, 200)

S2 = Draft.make_shapestring("Inclined text", font2, 200, 10)

zaxis = App.Vector(0, 0, 1)
p2 = App.Vector(-1000, 500, 0)
place2 = App.Placement(p2, App.Rotation(zaxis, 45))
S2.Placement = place2

S3 = Draft.make_shapestring("Upside-down text", font3, 200, 10)
S3.Placement.Base = App.Vector(0, -1000, 0)
S3.Placement.Rotation = App.Rotation(zaxis, 180)

doc.recompute()
```





 