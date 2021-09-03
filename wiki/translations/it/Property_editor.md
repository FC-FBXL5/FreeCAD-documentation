


<div class="mw-translate-fuzzy">





</div>


{{TOCright}}

## Descrizione


<div class="mw-translate-fuzzy">

L\'[editore delle proprietà](property_editor/it.md) appare quando è attiva la scheda {{MenuCommand|Modello}} della vista combinata; consente di gestire le proprietà degli oggetti nel documento.


</div>


<div class="mw-translate-fuzzy">

Generalmente, l\'editore delle proprietà è destinato a gestire solo un oggetto alla volta. I valori mostrati nell\'editore appartengono all\'oggetto attivo del documento attivo. Alcune proprietà come i colori, possono però essere impostate per più oggetti selezionati. Se non ci sono elementi selezionati, l\'editore delle proprietà è vuoto.


</div>

Non tutte le proprietà possono sempre essere modificate; a seconda dello stato specifico della proprietà, alcune di esse possono essere invisibili (non elencate) o di sola lettura (non modificabili). {{TOCright}}


<div class="mw-translate-fuzzy">

![](images/FreeCAD_Properties_empty.png )


</div>


*Editore delle proprietà vuoto, quando nessun oggetto è selezionato.*

## Tipi di proprietà {#tipi_di_proprietà}

Una proprietà è un\'informazione come un numero o una stringa di testo allegata a un documento di FreeCAD o ad un oggetto del documento.

Gli oggetti creati con [script personalizzati](scripted_objects/it.md) possono utilizzare qualsiasi tipo di proprietà definita nel sistema di base. Vedere l\'elenco completo in [Proprietà degli oggetti](Property/it.md).

Alcuni dei tipi di proprietà più comunemente usati sono: 
```python
App::PropertyBool
App::PropertyFloat
App::PropertyAngle
App::PropertyDistance
App::PropertyInteger
App::PropertyString
App::PropertyMatrix
App::PropertyVector
App::PropertyPlacement
```

Oggetti diversi possono avere tipi di proprietà diverse. Tuttavia, molti oggetti hanno gli stessi tipi perché sono derivati dalla stessa classe interna. Ad esempio, la maggior parte degli oggetti che descrivono le forme geometriche (linee, cerchi, rettangoli, corpi solidi, parti importate, ecc.) hanno la proprietà \"Posizionamento\" che definisce la loro posizione nella [Vista 3D](3D_view/it.md).

## Proprietà Vista e Dati {#proprietà_vista_e_dati}

Ci sono due classi di proprietà delle funzioni accessibili tramite le schede nell\'editore delle proprietà:

-   Proprietà {{MenuCommand|Vista}} relative all\'aspetto \"visivo\" dell\'oggetto. Le proprietà {{MenuCommand|Vista}} sono legate all\'attributo **ViewProvider** (`ViewObject`) dell\'oggetto e sono accessibili solo quando viene caricata l\'interfaccia utente grafica (GUI). Non sono accessibili quando si utilizza FreeCAD in modalità console o come libreria senza testa.
-   Proprietà {{MenuCommand|Dati}} relative ai parametri \"fisici\" dell\'oggetto. Le proprietà {{MenuCommand|Dati}} definiscono le caratteristiche essenziali dell\'oggetto; esistono sempre, anche quando FreeCAD viene utilizzato in modalità console o come libreria. Ciò significa che se si carica un documento in modalità console, è possibile modificare il raggio di un cerchio o la lunghezza di una linea, anche se non è possibile visualizzare il risultato sullo schermo.


<div class="mw-translate-fuzzy">

Per questo motivo, le proprietà {{MenuCommand|Dati}} sono considerate più \"reali\", in quanto definiscono veramente la geometria di una forma. Invece le proprietà {{MenuCommand|Vista}} sono meno importanti perché influenzano solo l\'aspetto della geometria. Ad esempio, un cerchio di raggio di 10 mm è diverso da un cerchio di raggio di 5 mm; il colore del cerchio (proprietà vista) non influisce sulla sua forma, ma il raggio (proprietà dati) sì. In molti casi in questa documentazione, si intende che la parola \"proprietà\" si riferisce a una \"proprietà dati\".


</div>

### Proprietà di base {#proprietà_di_base}


**See also: [Object name](Object_name.md)**

L\'oggetto [script](scripted_objects/it.md) più semplice non mostra alcuna proprietà {{MenuCommand|Dati}} nell\'editore delle proprietà, ad eccezione dell\'attributo `Label`. {{Incode|Label}} è una stringa modificabile dall\'utente che identifica l\'oggetto nella [vista ad albero](tree_view/it.md). Invece, l\'attributo `Name` di un oggetto viene assegnato al momento della sua creazione e non può essere modificato; questo attributo è di sola lettura e non viene nemmeno visualizzato nell\'editor delle proprietà.

Un oggetto parametrico di base viene creato nel modo seguente:


```python
obj = App.ActiveDocument.addObject("App::FeaturePython", "App__FeaturePython")
obj.Label = "Plain_object"
print(obj.Name)
print(obj.Label)
```


<div class="mw-translate-fuzzy">

<img alt="" src=images/FreeCAD_Properties_View_basic.png  style="width:" height="264px;"> <img alt="" src=images/FreeCAD_Properties_Data_basic.png  style="width:" height="264px;">


</div>


*Schede Vista e Dati dell'editor delle proprietà, per un oggetto script di base "App::FeaturePython".*


<div class="mw-translate-fuzzy">

La maggior parte degli oggetti geometrici che possono essere creati e visualizzati nella [vista 3D](3D_view/it.md) sono derivati da una [`Part::Feature`](Part_Feature/it.md). Vedere [Part Feature](Part_Feature/it.md) per le proprietà più basilari di questi oggetti.


</div>


<div class="mw-translate-fuzzy">

Per la geometria 2D, la maggior parte degli oggetti deriva da [`Part::Part2DObject`](Part_Part2DObject/it.md) (essi stessi derivati da [`Part::Feature`](Part_Feature/it.md)) che sono la base di [Schizzi](Sketcher_Workbench/it.md), e di molti elementi di [Draft](Draft_Workbench/it.md). Vedere [Part Part2DObject](Part_Part2DObject/it.md) per le proprietà più basilari di questi oggetti.


</div>

## Azioni

Le azioni nelle proprietà vista sono state implementate nella versione 0.19.

Facendo clic con il tasto destro in uno spazio vuoto della vista o con una proprietà selezionata, viene visualizzato solo un comando:

-    {{MenuCommand|Mostra tutto}}: se attivo, oltre alle proprietà standard che appaiono già, mostra tutti i dati nascosti e visualizza le proprietà nelle rispettive schede.

    -   Dati: \"Proxy\", \"Label2\", \"Expression Engine\", and \"Visibility\".
    -   Vista: \"Proxy\".


<div class="mw-translate-fuzzy">

Quando l\'opzione {{MenuCommand|Mostra tutto}} è attiva e viene selezionata una proprietà, facendo un secondo clic con il tasto destro sono disponibili altre azioni:

-    {{MenuCommand|Mostra tutto}}: disattiva il comando {{MenuCommand|Mostra tutto}} e nasconde le proprietà aggiuntive di Dati e Vista.

-    {{MenuCommand|Add Property}}: aggiunge una proprietà dinamica all\'oggetto; funziona con oggetti di [script](scripted_objects/it.md) C++ e Python.

-    {{MenuCommand|Expression}}: visualizza l\'editor delle formule, che consente di utilizzare le [espressioni](Expressions/it.md) nel valore della proprietà.

-    {{MenuCommand|Hidden}}: se attivo, imposta la proprietà come nascosta, il che significa che verrà visualizzata solo se {{MenuCommand|Mostra tutto}} è attivo.

-    {{MenuCommand|Output}}: se attivo, imposta la proprietà come output.

-    {{MenuCommand|NoRecompute}}: se attivo, imposta la proprietà come non ricalcolata quandi il documento viene ricalcolato; è utile quando una proprietà non deve essere influenzata da altri aggiornamenti.

-    {{MenuCommand|ReadOnly}}: se attivo, imposta la proprietà in sola lettura; non sarà più modificabile fino a quando questo interruttore non viene disattivato.

-    {{MenuCommand|Transient}}: se attivo, imposta la proprietà come transitoria.

-    {{MenuCommand|Touched}}: se attivo, viene toccato e pronto per il ricalcolo.

-    {{MenuCommand|EvalOnRestore}}: se attivo, viene valutato al ripristino del documento.


</div>

## Esempio di proprietà di un oggetto PartDesign {#esempio_di_proprietà_di_un_oggetto_partdesign}

In this section we show some common properties that are visible for a [PartDesign Body](PartDesign_Body.md), and one [PartDesign Feature](PartDesign_Feature.md). The specific properties of an object can found in the specific documentation page of that object.

### Vista

Most of these properties are inherited from the [Part Feature](Part_Feature.md) basic object.


<div class="mw-translate-fuzzy">

<img alt="" src=images/FreeCAD_Properties_View.png  style="width:490px;"> {{TitleProperty|Base}}


</div>


<div class="mw-translate-fuzzy">

-    **Bounding Box**: Indica se deve essere visualizzata una casella (riquadro di delimitazione) che mostra l\'ingombro complessivo dell\'oggetto. Valore Falso o Vero (predefinito, Falso).

-    **Control Point**: Indica se i punti di controllo delle funzioni devono essere visualizzati. Valore Falso o Vero (predefinito, Falso).

-    **Deviation**: Imposta la precisione della rappresentazione poligonale del modello nella vista 3D (tassellatura). Valori più bassi = migliore qualità. Il valore è in percentuale della dimensione dell\'oggetto (deviazione in mm = (w+h+d)/3\* valore in Percentuale /100, dove w, h, d sono le dimensioni del riquadro di delimitazione).

-    **Display Mode**:Modalità di visualizzazione della funzione, **Flat lines, Shaded, Wireframe, Points** [96px](IMAGE:Vue_DisplayModePartDesign_fr_00.png.md). (Default, **Flat lines**).

-    **Lighting**: Illuminazione **One side, Two side** [96px](IMAGE:Vue_Lighting_fr_00.png.md). (Default, **Two side**).

-    **Line Color**: Dà il colore della linea (bordi) (Default, **25, 25, 25**).

-    **Line Width**: Dà lo spessore della linea (bordi) (Default, **2**).

-    **Point Color**: Fornisce il colore dei punti (estremità della funzione) (Default, **25, 25, 25**).

-    **Point Size**: Dà la dimensione dei punti (Default, **2**).

-    **Selectable**: Consente la selezione della funzione. Valore Falso o Vero (predefinito, Vero).

-    **Shape Color**: Dà il colore della forma (default, **204, 204, 204**).

-    **Transparency**: Imposta il grado di trasparenza nella funzione da **0** a **100** (Default, **0**).

-    **Visibility**: Determina la visibilità della funzione (come la barra **SPACE**). Valore Falso o Vero (predefinito, Vero).





</div>

### Dati

In this case we observe the properties of the [PartDesign Revolution](PartDesign_Revolution.md) feature.


<div class="mw-translate-fuzzy">

<img alt="" src=images/FreeCAD_Properties_Data.png  style="width:490px;"> {{TitleProperty|Base}}


</div>


<div class="mw-translate-fuzzy">

-    {{ProprietaDati|Label}}:

Label è il nome attribuito all\'operazione, questo nome può essere modificato a discrezione.


</div>


{{TitleProperty|Part Design}}

-    **Refine**: whether to refine the fusion done with other objects.


<div class="mw-translate-fuzzy">

-    **Placement**:

Ogni funzione ha un posizionamento che può essere controllato tramite la tabella delle proprietà dei dati. Placement controlla il posizionamento della parte rispetto al sistema di coordinate. NOTA: le proprietà di posizionamento non influenzano le dimensioni fisiche della funzione, ma semplicemente la sua posizione nello spazio!
Se si seleziona il titolo **Placement** <img alt="Options Placement" src=images/Tache_Placement_01_fr_00.png  style="width:256px;">, alla sua destra appare un pulsante con **tre puntini**. Cliccando su questi ** '''...'''**, si apre la finestra delle opzioni per il **[Posizionamento](Tasks_Placement/it.md)**.


</div>


<div class="mw-translate-fuzzy">

-    {{ProprietaDati|Axis}}:

Questa opzione specifica l\'asse o gli assi su cui l\'operazione creata deve essere ruotata. Il valore di rotazione esatto viene dalla opzione angolo (sopra). Questa opzione ha tre argomenti, che vengono passati come numeri alle rispettive caselle di testo X, Y, Z dello strumento. Inserendo un valore in più di uno degli assi si causa la rotazione della parte del corrispondente angolo per ogni asse. Per esempio, con un angolo impostato pari a 15°, specificando un valore di 1,0 per X, e di 2,0 per Y causa una rotazione finale del pezzo di 15° sull\'asse X e di 30° sull\'asse Y.


</div>


<div class="mw-translate-fuzzy">

-    {{ProprietaDati|Angle}}:

L\'argomento Angolo specifica l\'angolo da utilizzare con l\'opzione Axis. In questa opzione si stabilisce un angolo, poi sotto, con l\'opzione Axis, si imposta l\'asse sul quale si vuole utilizzare questo angolo. L\'operazione viene ruotata dell\'angolo specificato, attorno all\'asse specificato. Un esempio di utilizzo potrebbe essere quando si crea una operazione rivoluzione, ma poi serve ruotare l\'intera operazione di un certo valore, per allinearla con una diversa operazione preesistente.


</div>


{{TitleProperty|Sketch Based}}


<div class="mw-translate-fuzzy">

-    {{ProprietaDati|Position}}:

Questa opzione specifica il punto base, ovvero, il punto a cui tutte le dimensioni si riferiscono. Questa opzione ha tre argomenti, che vengono passati come numeri alle rispettive caselle di testo X, Y, Z dello strumento. Inserendo un valore in una o più caselle si produce una traslazione della parte sull\'asse corrispondente, pari al numero di unità indicate.


</div>




## Scripting


**See also:**

[FreeCAD Scripting Basics](FreeCAD_Scripting_Basics.md).

See [scripted objects](scripted_objects.md) for the full information on adding properties to objects defined through [Python](Python.md).

Most properties that are visible in the property editor can be accessed from the [Python console](Python_console.md). These properties are just attributes of the class that defines the selected object. For example, if the property editor shows the **Group** property, this means that the object has the `Group` attribute. 
```python
print(obj.Group)
```

These attributes (properties) are added with the `addProperty` method of the base object. At least it is necessary to specify the type of [property](property.md), and its name. 
```python
obj.addProperty("App::PropertyFloat", "Custom")
print(obj.Custom)
```

Properties follow the `CapitalCamelCase` or `PascalCase` convention, meaning that each word starts with a capital letter, and there are no underscores. When the property editor displays such names, it leaves a space between each capital letter, making it easier to read.


```python
obj.addProperty("App::PropertyDistance", "CustomCamelProperty")
obj.CustomCamelProperty = 1000
print(obj.CustomCamelProperty)
```

![](images/FreeCAD_Property_editor_Custom.png ) *Property editor showing the Data properties of a [PartDesign Body](PartDesign_Body.md), with two additional properties, "Custom" and "Custom Camel Property".*

In similar way the {{MenuCommand|View}} properties are added, not to the base object, but to its `ViewObject`. Then, it follows that properties like **Angular Deflection**, **Bounding Box**, **Display Mode**, **Display Mode Body**, **Line Color**, and others, can be examined and changed from the [Python console](Python_console.md).


```python
print(obj.ViewObject.AngularDeflection)
print(obj.ViewObject.BoundingBox)
print(obj.ViewObject.DisplayMode)
print(obj.ViewObject.DisplayModeBody)
print(obj.ViewObject.LineColor)
```

All public properties of the object, and of its view provider, are contained in the corresponding `PropertiesList` attribute. 
```python
print(obj.PropertiesList)
print(obj.ViewObject.PropertiesList)
```


<div class="mw-translate-fuzzy">


{{docnav/it|[Personalizzare l'interfaccia](Interface_Customization/it.md)|[Ambienti di lavoro](Workbenches/it.md)}}


</div>


{{Interface navi

}} {{Std Base navi}} 