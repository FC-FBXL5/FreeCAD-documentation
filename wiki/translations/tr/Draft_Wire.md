---
- GuiCommand:/tr
   Name:Draft Wire
   Name/tr:Tel
   Workbenches:[Taslak](Draft_Module/tr.md), [Yapı](Arch_Module/tr.md)
   Shortcut:W I
   MenuLocation:Taslak → Tel
   SeeAlso:[Çizgi](Draft_Line/tr.md), [BSpline](Draft_BSpline/tr.md)
   Version:0.17
---


</div>

## Description


<div class="mw-translate-fuzzy">

## Açıklama

Tel aracı bir çoklu çizgi (birkaç çizgi parçasının bir sırası) oluşturur. [Araç çubuğu](Draft_Tray/tr.md) \'nda ayarlanan [Çizgi stilini](Draft_Linestyle/tr.md) kullanır. Tel aracı, tam [Çizgi](Draft_Line/tr.md) aracı gibi davranır, ancak ikiden fazla nokta girmenize izin verir.


</div>

<img alt="" src=images/Draft_Polyline_example.jpg  style="width:400px;"> 
*Tel birçok noktayla tanımlanır*

## Create

### Usage

See also: [Draft Tray](Draft_Tray.md), [Draft Snap](Draft_Snap.md) and [Draft Constrain](Draft_Constrain.md).


<div class="mw-translate-fuzzy">

## Nasıl kullanılır {#nasıl_kullanılır}

1.  
    **<img src="images/_Draft_Wire.svg" width=16px> [Tel](Draft_Wire/tr.md)**düğmesine basın veya **W** ardından **I** tuşları.

2.  3D görünümde bir ilk noktaya tıklayın veya bir [koordinat](Draft_Coordinates/tr.md) yazın ve **<img src="images/_Draft_AddPoint.svg" width=16px> [add point](Draft_AddPoint/tr.md)** düğmesine basın.

3.  3D görünümünde ek noktalara tıklayın veya bir [ koordinat](Draft_Coordinates/tr.md) yazın ve **<img src="images/_Draft_AddPoint.svg" width=16px> [Nokta ekle](Draft_AddPoint/tr.md)** düğmesine basın.

4.  İşlemi tamamlamak için **Esc** veya **Kapat** tuşuna basınız.


</div>

### Options

The single character keyboard shortcuts available in the task panel can be changed. See [Draft Preferences](Draft_Preferences.md). The shortcuts mentioned here are the default shortcuts.


<div class="mw-translate-fuzzy">

## Seçenekler

-   Teli bitirmek için **A** veya **<img src="images/_Draft_FinishLine.png" width=12px> [Bitir](Draft_FinishLine/tr.md)** düğmesine basarak açık bırakın.
-   Teli kapatmak için **O** veya **<img src="images/_Draft_CloseLine.png" width=12px> [Kapat](Draft_CloseLine_/tr.md)** düğmesine basın, yani bir parça eklenecektir. Son noktadan ilkine bir yüz oluşturmak. Bir yüz oluşturmak için en az üç nokta gerekir.
-   Önceden yerleştirilmiş çizgi parçalarını kaldırmak için **W** veya **<img src="images/_Draft_Wipe.svg" width=12px> [Silme](Draft_Wipe/tr.md)** düğmesine basın, ancak teli düzenlemeye devam edin
-   Geçerli çalışma düzlemini en son yönde ayarlamak için **U** veya **<img src="images/_Draft_SelectPlane.svg" width=12px> [Çalışma düzlemi](Draft_SelectPlane/tr.md)** ayarla düğmesine basın puan.
-   Verilen eksendeki bir sonraki noktayı sınırlamak için bir noktadan sonra **X**, **Y** veya **Z** tuşlarına basın.
-   Koordinatları manuel olarak girmek için sayıları girin, ardından her bir X, Y ve Z bileşeni arasında **Enter** tuşuna basın. Noktayı yerleştirmek istediğiniz değerleri aldığınızda **<img src="images/_Draft_AddPoint.svg" width=16px> [Nokta ekle](Draft_AddPoint/tr.md)** düğmesine basabilirsiniz.
-   **Göreceli** moduna geçmek için **R** tuşuna basın veya onay kutusunu tıklayın. Göreceli mod açıksa, bir sonraki noktanın koordinatları sonuncusuna göre değişir; değilse, kesindir, kökenlerinden alınır (0,0,0).
-   **Devam**moduna geçmek için **T** tuşuna basın veya onay kutusunu tıklayın. Devam modu açıksa, Tel aracı teli bitirdikten sonra yeniden başlatılır ve araç düğmesine tekrar basmadan bir tane daha çizmenize olanak sağlar.
-   **Dolu** moduna geçmek için **L** tuşuna basın veya onay kutusunu tıklayın. Dolu modu açıksa, kapalı bir tel dolgulu bir yüz oluşturur ({{PropertyData/tr|Make Face}} `True`); değilse, kapalı tel bir yüz oluşturmaz ({{PropertyData/tr|Make Face}} `False`).

:   
    **Not:**uygun bir yüz oluşturmayacağından telin kendisiyle kesiştiği takdirde doldurulmaması gerekir. Kablo dolu ancak şekli görünmüyorsa, teli görmek için {{PropertyData/tr|Make Face}} \'i `False`\' e manuel olarak ayarlayın.

-   [Yakalama](Draft_Snap/tr.md) noktanızı mesafeden bağımsız olarak, en yakın çeki konumuna yönlendirmek için çizim yaparken **Ctrl** tuşunu basılı tutun.
-   Bir sonraki noktanızı yatay veya dikey olarak son noktaya göre [Kısıtlama](Draft_Constrain/tr.md) çizerken **Shift** tuşunu basılı tutun.
-   Son noktayı geri almak için **Ctrl** **Z** tuşuna basınız veya {{button|<img src="images/_Draft_UndoLine.png" width=12px> [Geri al](Draft_UndoLine/tr.md)}} düğmesine basınız. .
-   Geçerli komutu iptal etmek için **Esc** veya {{button|Kapat}} tuşuna basınız; Yerleştirilen çizgi bölümleri kalacaktır.


</div>

## Join

### Usage {#usage_1}

1.  The end points of the [Draft Lines](Draft_Line.md) and/or Draft Wires to be joined must be exactly coincident. If required first adjust points to ensure that this is the case.
2.  Select two or more [Draft Lines](Draft_Line.md) and/or Draft Wires.
3.  There are several ways to invoke the command:
    -   Press the **<img src="images/Draft_Wire.svg" width=16px> [Draft Wire](Draft_Wire.md)** button.
    -   Select the {{MenuCommand|Drafting → <img src="images/Draft_Wire.svg" width=16px> Polyline}} option from the menu.
    -   Use the keyboard shortcut: **P** then **L**.

## Notes


<div class="mw-translate-fuzzy">

Tel, ağaç görünümündeki öğeye çift tıklayarak veya {{Button | <img src="images/_Draft_Edit.svg_" width= 16px> [Düzenle](Draft_Edit/tr.md)}} düğmesine basılarak düzenlenebilir. Ardından noktaları yeni bir konuma taşıyabilir veya {{Button | <img src="images/_Draft_AddPoint.svg_" width= 16px> [Nokta ekle](Draft_AddPoint/tr_.md)}} veya {{Button | <img src="images/_Draft_DelPoint.svg_" width= 16px> öğesini tıklayabilirsiniz.[ Nokta kaldır](Draft_DelPoint/tr_.md)}} ve ardından noktaları eklemek veya kaldırmak için teli tıklatın.


</div>

## Preferences

See also: [Preferences Editor](Preferences_Editor.md) and [Draft Preferences](Draft_Preferences.md).

-   To change the number of decimals used for the input of coordinates: {{MenuCommand|Edit → Preferences... → General → Units → Units settings → Number of decimals}}.
-   To change the initial value of filled mode: {{MenuCommand|Edit → Preferences... → Draft → General settings → Draft tools options → Fill objects with faces whenever possible}}. Changing the filled mode in a task panel will override this preference for the current FreeCAD session.

## Properties

See also: [Property editor](Property_editor.md).

A Draft Wire object is derived from a [Part Part2DObject](Part_Part2DObject.md) and inherits all its properties. It also has the following additional properties:

### Data


{{TitleProperty|Draft}}


<div class="mw-translate-fuzzy">

### Veri

-    {{PropertyData/tr|Start}}: kablodaki ilk noktayı belirtir.

-    {{PropertyData/tr|End}}: kablo kapalıysa başlangıç ​​noktasını saymaz, kablodaki son noktayı belirtir.

-    {{PropertyData/tr|Closed}}: kablonun kapalı olup olmadığını belirtir. Kablo başlangıçta açıksa, bu değer `False`; `True` olarak ayarlamak, teli kapatmak için bir çizgi kesimi çizer. Kablo başlangıçta kapalıysa, bu değer `True`; `False` olarak ayarlamak, son satır parçasını kaldıracak ve teli açacaktır.

-    {{PropertyData/tr|Chamfer Size}}: telin köşelerinde oluşturulan olukların (düz segmentler) boyutunu belirtir.

-    {{PropertyData/tr|Fillet Radius}}: telin köşelerinde oluşturulan filetoların (yay parçaları) yarıçapını belirtir.

-    {{PropertyData/tr|Make Face}}: Teli bir yüz yapıp yapmamayı belirtir. `True` ise bir yüz yaratılır, aksi takdirde sadece kenarlar nesnenin bir parçası olarak kabul edilir. Bu özellik yalnızca {{PropertyData/tr|Closed}} `True` ise çalışır.

:   
    **Not:**, tel uygun bir yüz oluşturmayacağından kendisiyle kesiştiğinde {{PropertyData/tr|Make Face}} ayarını `True` olarak ayarlamayın.

-    {{PropertyData/tr|Subdivisions}}: telin her bir bölümündeki iç düğümlerin sayısını belirtir. {{version/tr|0.16}}

-    {{PropertyData/tr|Length}}: (salt okunur) tüm kablonun uzunluğunu belirtir.


</div>

### View


{{TitleProperty|Draft}}


<div class="mw-translate-fuzzy">

### Görünüm

-    {{PropertyView/tr|End Arrow}}: `True` ise kablonun son noktasında bir sembol gösterecektir, böylece bir açıklama satırı olarak kullanılabilir.

-    {{PropertyView/tr|Arrow Size}}: telin sonunda görüntülenen sembolün boyutunu belirtir.

-    {{PropertyView/tr|Arrow Type}}: telin sonunda görüntülenen, \"Nokta\", \"Daire\", \"Ok\" veya \"Tik\" olabilen sembol tipini belirtir.

-    {{PropertyView/tr|Pattern}}: kapalı telin yüzünü doldurmak için bir [Desen](Draft_Pattern/tr.md) belirtir. Bu özellik yalnızca {{PropertyData/tr|Make Face}} `True` ise ve {{PropertyView/tr|Display Mode}} \"Düz Çizgiler\" ise çalışır.

-    {{PropertyView/tr|Pattern Size}}: [Desen](Draft_Desen/tr.md) \'in boyutunu belirtir.


</div>

## Betik


<div class="mw-translate-fuzzy">


**Ayrıca bkz.:**

[Taslak API](Draft_API/tr.md) ve [FreeCAD Betik esasları](FreeCAD_Scripting_Basics/tr.md).


</div>


<div class="mw-translate-fuzzy">

Tel aracı, aşağıdaki işlevi kullanarak [makrolar](macros/tr.md) ve [Python](Python/tr.md) konsolundan kullanılabilir:


</div>


```python
wire = make_wire(pointslist, closed=False, placement=None, face=None, support=None)
wire = make_wire(Part.Wire, closed=False, placement=None, face=None, support=None)
```


<div class="mw-translate-fuzzy">

-   Belirtilen nokta listesiyle `Wire` nesnesini yaratır, `pointslist`.
    -   Listedeki her nokta, `FreeCAD.Vector` ile tanımlanır ve birim milimetre cinsinden tanımlanır.
    -   Alternatif olarak, giriş, noktaların çıkarıldığı bir `Part.Wire` olabilir.

-    `closed``True` ise veya ilk ve son noktalar aynıysa, tel kapanır.

-   Bir `placement` verilirse kullanılır; Aksi halde, şekil başlangıçta oluşturulur.

-    `face``True` ise ve tel kapalıysa, tel bir yüz yapacaktır, yani dolgulu görünecektir.


</div>

Örnek:


```python
import FreeCAD as App
import Draft

doc = App.newDocument()

p1 = App.Vector(0, 0, 0)
p2 = App.Vector(1000, 1000, 0)
p3 = App.Vector(2000, 0, 0)

wire1 = Draft.make_wire([p1, p2, p3], closed=True)
wire2 = Draft.make_wire([p1, 2*p3, 1.3*p2], closed=True)
wire3 = Draft.make_wire([1.3*p3, p1, -1.7*p2], closed=True)

doc.recompute()
```


<div class="mw-translate-fuzzy">


{{Draft Tools navi/tr}}


{{Userdocnavi/tr}}


</div>


 