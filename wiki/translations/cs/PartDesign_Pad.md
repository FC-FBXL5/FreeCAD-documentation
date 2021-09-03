---
- GuiCommand:/cs
   Name:PartDesign_Pad
   Name/cs:Návrh dílu Deska
   Workbenches:[Návrh dílu](PartDesign_Workbench/cs.md)
   MenuLocation:Návrh dílu → Deska
---


</div>

## Úvod


<div class="mw-translate-fuzzy">

\'Vybraný náčrt do desky\' - Tento nástroj vezme vybraný náčrt (\'definující náčrt\') a vytvoří z něho \'desku\'. Pojem deska je zde obecně používán pro objekt vzniklý vysunutím náčrtu. Například, pokud je náčrt vytvořen ze dvou soustředných kružnic a následně je na ně aplikován nástroj Deska, bude výsledkem válec:


</div>

![](images/PartDesign_Pad_example.svg )

*Sketch (A) shown on the left; end result after pad operation (B) on the right.*

**Note:** {{VersionMinus|0.16}} If the selected sketch is mapped to the face of an existing solid or another Part Design feature, the pad will be fused to it.

## Usage

1.  Select the sketch to be padded. **Note:** As of <small>(v0.17)</small>  a face on the existing solid can alternatively be used.
2.  Press the **<img src="images/PartDesign_Pad.svg" width=16px> '''Pad'''** button.
3.  Set the Pad parameters, see the [Options](#Options.md) below.
4.  Click **OK**.

## Volby


<div class="mw-translate-fuzzy">

Při vytváření desky nabízí dialogové okno \'parametrů desky\' pět různých způsobů zadání výšky do jaké bude deska vysunuta


</div>

![](images/Pad_parameters_cropped_cs.png )

### Type

Typ nabízí pět různých způsobů určení délky, na kterou bude podložka protlačována.

#### Rozměr

Zadání číselné hodnoty pro výšku desky. Defaultní směr vysunutí je ven z podkladu, ale může to být změněno zakliknutím volby **Opačně**. Vysunutí je ve směru [kolmém](http://en.wikipedia.org/wiki/Surface_normal) k definující rovině náčrtu. S volbou **Symetricky s rovinou** bude deska vysunuta z poloviny na jedné straně roviny a z poloviny na druhé straně roviny. Záporný rozměr není povolen. Místo toho použijte volbu **Opačně**.

### Dva rozměry {#dva_rozměry}

Umožňuje zadat druhý rozměr. Pak se deska o tuto vzdálenost vysune na opačnou stranu (vzhledem k podkladové rovině). Opět lze využít volby **Opačně**.

### K poslední {#k_poslední}

Deska se vysune až k poslední ploše tělesa ve směru vysunutí. Není-li v daném směru žádná plocha, zobrazí se chybové hlášení.

### K první {#k_první}

Deska se vysune k první ploše tělesa ve směru vysunutí. Není-li v daném směru žádná plocha, zobrazí se chybové hlášení.

### Až k ploše {#až_k_ploše}

Deska se vysune až k ploše v objektu, která je vybrána kliknutím na ni. Není-li zde žádný objekt, nebude akceptován žádný výběr.

### Length

Defines the length of the pad. Multiple units can be used independently of the user\'s units preferences (m, cm, mm, nm, ft or \', in or \").

### Use custom direction {#use_custom_direction}


<small>(v0.19)</small> 

If checked, the pad direction will not be the normal vector of the sketch but the given vector. The pad length is however set according to the normal vector direction.

### Length along sketch normal {#length_along_sketch_normal}

If checked, the pad length is measured along the sketch normal, otherwise along the custom direction. <small>(v0.20)</small> 

### Offset to face {#offset_to_face}

Offset from face in which the pad will end. This option is only available when **Type** is either **To last**, **To first** or **Up to face**.

### Symmetric to plane {#symmetric_to_plane}

Tick the checkbox to extend half of the given length to either side of the sketch plane.

### Reversed

Reverses the direction of the pad.

## Properties

-    **Type**: Type of ways how the pad will be extruded, see [Options](#Options.md).

-    **Length**: Defines the length of the pad, see [Options](#Options.md).

-    **Length2**: Second pad length in case the **Type** option **TwoLengths** is used, see [Options](#Options.md).

-    **Use Custom Vector**: <small>(v0.19)</small>  If checked, the pad direction will not be the normal vector of the sketch but the given vector, see [Options](#Options.md).

-    **Direction**: <small>(v0.19)</small>  Vector of the pad direction if **Use Custom Vector** is used.

-    **Along Sketch Normal**: <small>(v0.20)</small>  If *true*, the pad length is measured along the sketch normal. Otherwise and if **Use Custom Vector** is used, it is measured along the custom direction.

-    **Up To Face**: A face the pad will extrude up to, see [Options](#Options.md).

-    **Offset**: Offset from face in which the pad will end. This is only taken into account if the **Type** option **UpToLast**, **UpToFirst** or **UpToFace** is used.

-    **Refine**: <small>(v0.17)</small>  true or false. Cleans up residual edges left after the operation. This property is initially set according to the user\'s settings (found in *Preferences → Part design → General → Model settings*). It can be manually changed afterwards. This property will be saved with the FreeCAD document.

## Omezení


<div class="mw-translate-fuzzy">

-   Stejně jako všechny funkce Návrh součástí, Pad také vytváří těleso, takže skica musí obsahovat uzavřený profil, jinak selže s chybou „Nepodařilo se ověřit zlomenou tvář". Uvnitř většího profilu může být více uzavřených profilů za předpokladu, že se žádné neprotínají (například obdélník se dvěma kruhy uvnitř).
-   Algoritmus používaný pro „To First" a „To Last" je:
    -   Vytvořte čáru přes těžiště náčrtu
    -   Najděte všechny plochy podpěry oříznuté touto čarou
    -   Vyberte plochu, kde je průsečík nejblíže / nejdále od náčrtu

:   To znamená, že nalezená tvář nemusí být vždy tím, co jste očekávali. Pokud se setkáte s tímto problémem, použijte místo toho typ „" „Nahoru do tváře" a vyberte požadovanou tvář.
:   Pro velmi zvláštní případ vytlačování na konkávní povrch, kde je náčrt větší než tento povrch, vytlačování selže. Toto je nevyřešená chyba.

-    v0.16 a nižší  Neexistuje žádné automatické čištění, např. sousedních rovinných povrchů do jednoho povrchu. Můžete to opravit ručně v pracovním stole součásti pomocí [ Zpřesnit tvar](Part_RefineShape/cs.md) (který vytvoří nepřipojený, neparametrický těleso) nebo pomocí [Zpřesnit tvarovou funkci](OpenSCAD_RefineShapeFeature/cs.md) z [OpenSCAD Workbench](OpenSCAD_Workbench/cs.md), který vytváří parametrickou funkci.


</div>


<div class="mw-translate-fuzzy">





</div>


{{PartDesign Tools navi

}} 