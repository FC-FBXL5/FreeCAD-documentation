 {{TOCright}}

## Descrizione

Ci sono state molte discussioni nel corso degli anni sulle differenze e le ramificazioni dell\'uso degli ambienti <img alt="" src=images/Workbench_Part.svg  style="width:24px;"> [Part](Part_Workbench/it.md) e <img alt="" src=images/Workbench_PartDesign.svg  style="width:24px;"> [PartDesign](PartDesign_Workbench/it.md).

È una buona idea usare l\'uno o l\'altro finché l\'utente non è a suo agio con uno, poi impara l\'altro. È anche tipicamente raccomandato che i nuovi utenti non li confondano finché non hanno capito le differenze.

Parliamo di queste differenze.

## Concetti dell\'ambiente Part {#concetti_dellambiente_part}

L\'ambiente Part è essenzialmente un modellatore di [Geometrie solide](Constructive_solid_geometry/it.md). L\'operatore combina varie primitive per finire con una rappresentazione della forma desiderata. (In effetti, l\'ambiente Part va un passo oltre le primitive e permette all\'operatore di usare un\'operazione di schizzo+estrusione (o schizzo+rivoluzione, loft, sweep\...) per creare anche forme casuali). Quando ogni primitiva o forma viene creata, non ha alcuna relazione con gli altri oggetti creati (tranne gli schizzi e i loro allegati), è un singolo solido isolato.

![centre\|Solidi isolati](images/Part_CSG_Prims.png )

Questa condizione rimane tale fino a quando l\'operatore usa delle operazioni per combinarli (tipicamente un booleano che li aggiunge o li sottrae). Ogni solido di partenza rimane accessibile separatamente e l\'operazione crea un nuovo oggetto.

Il risultato è la parte solida singola e la combinazione delle parti.

## Concetti dell\'ambiente PartDesign {#concetti_dellambiente_partdesign}

Nell\'ambiente PartDesign l\'oggetto Body è costruito direttamente come un singolo solido cumulativo isolato.

Il 1° passo di un corpo deve essere un blocco di materiale, creato da una primitiva additiva o un\'estrusione di uno schizzo, o una forma importata (poi chiamata Base Feature).

Questo blocco iniziale di materiale sarà cambiato in modo sequenziale fino ad ottenere la forma finale desiderata (solido).

È cumulativo nel senso che ogni operazione aggiunge o toglie materiale.

Per impostazione predefinita, il \"tip (Punta, Cima)\" del corpo - a meno che non ci sia un cambiamento volontario nella visualizzazione di una particolare caratteristica - è l\'ultima operazione eseguita sul corpo. Questo è lo stato attuale e visibile del corpo, pronto per essere cambiato di nuovo da una nuova funzione.

Qualsiasi funzione al di sotto del corpo rappresenta la forma cumulativa del solido dalla prima caratteristica alla caratteristica considerata.

Così **per avere il solido completo**, da un lato la caratteristica Tip deve essere l\'ultima tappa della costruzione di questo solido, e dall\'altro **è il corpo che deve essere selezionato** e non una fase della sua costruzione.

Questo permetterà, in caso di modifica, di *avere sempre l\'ultima versione del solido rappresentata*.

**Note e aggiunte :** In ogni momento della costruzione, l\'ultima funzione utilizzata è il \"Tip (Punta, Cima)\", che può essere definita anche come \"fase attiva nella costruzione dell\'oggetto\" o \"fase che precede l\'azione successiva nella costruzione dell\'oggetto\". Quando il disegno dell\'oggetto è completo, la punta è naturalmente l\'ultima fase o caratteristica della costruzione. Ma se lo si desidera, in caso di dimenticanza, qualsiasi caratteristica della costruzione può essere dichiarata provvisoriamente come Tip: essa diventa allora la tappa che precede l\'azione successiva nella costruzione dell\'oggetto, il che significa che una o più nuove caratteristiche possono essere inserite ovunque nella costruzione, **a condizione di non crearne nessuna incompatibile con la sequenza**.

Quando tutto è finito, bisogna ridichiarare l\'ultima caratteristica come Tip, che corrisponde all\'oggetto finito.

![centre\|Corpo solido cumulativo](images/Part_Design_Cumulativ.png )

Questa immagine mostra un Corpo. È un solido cumulativo che consiste in uno schizzo estruso e in una primitiva conica. Questo è un solido singolo.

Se Tip su *Pad*, il solido estruso può esistere separatamente, ma se Tip su *Cono*, il cono non può esistere separatamente (Tip su cono = solido estruso + cono).

(Un\'altra cosa menzionata spesso è che un Corpo **\'\' DEVE**\'\' essere un singolo solido contiguo. Questo significa che tutta la geometria creata da una caratteristica nel Corpo *deve* toccare il suo predecessore).

## Le conseguenze {#le_conseguenze}

Anche se non è raccomandato ai nuovi utenti, è possibile combinare gli strumenti di Part WB e PartDesign WB, purché si sappia cosa si sta facendo. Per esempio :

Le persone vengono colte di sorpresa quando tentano di usare qualche caratteristica sotto il corpo (piuttosto che il corpo stesso) come una selezione di un\'operazione booleana nell\'ambiente Part. Questo è un problema, perché la caratteristica selezionata non rappresenta **IL** solido completo.

In un certo senso, dal punto di vista dell\'ambiente Part, il corpo rappresenta un\'altra primitiva. Quindi, si puoò usare un corpo (ricordate che è un proxy per la punta) e un oggetto Part per fare un operazione booleana. Ma l\'oggetto risultante è un oggetto dell\'ambiente Part. E quindi gli strumenti dell\'ambiente PartDesign non possono più essere usati.

E può diventare ancora più complicato. Se si crea un nuovo corpo e vi si trascina il risultato del paragrafo precedente, si crea un BaseObject. E su questo si può andare ad usare gli strumenti dell\'ambiente PartDesign.

## Le avvertenze {#le_avvertenze}

C\'è un\'avvertenza con la Punta (ultima funzione sul solido) e la sua rappresentazione del singolo solido nel Corpo. Se la punta è una caratteristica sottrattiva ed è usata in un\'operazione estetica, per esempio uno Specchio, lo Specchio sta operando sulla caratteristica sottostante (una tasca per esempio). Così il solido cumulativo non viene specchiato, ma la caratteristica sottrattiva sì. Il risultato di questo deve creare un unico solido.

In questo esempio, uno specchio della punta (che è la tasca della cavità) intorno a uno qualsiasi dei piani di base, o anche una faccia del solido non produrrà un solido specchiato dell\'intero modello. (Infatti, produrrà una funzione speculare nell\'albero che è essenzialmente vuota).

![centre\|Solidi isolati](images/PhantomMirror.png )

In questo esempio, uno specchio della punta (che è la tasca della cavità) viene eseguito intorno al piano di riferimento e produce una cavità speculare:

![centre\|Solidi isolati](images/MirroredSlot.png )

Vedere la pagina <img alt="" src=images/PartDesign_Mirrored.svg  style="width:24px;"> [PartDesign Simmetria](PartDesign_Mirrored/it.md) wiki dello strumento per maggiori informazioni.

## Comparison

You can see below the same example built with each of the two workbenches. Of course, there are always several possible construction timelines with each workbench. ![Compare constructions with Part WB and PartDesign WB](images/PartWBvsPartDesignWBexample.jpg )

  In <img alt="" src=images/Workbench_PartDesign.svg  style="width:24px;"> PartDesign WB                                                                                    In <img alt="" src=images/Workbench_Part.svg  style="width:24px;"> Part WB
  ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  01- <img alt="" src=images/PartDesign_Body.svg  style="width:32px;"> New body \> <img alt="" src=images/Sketcher_NewSketch.svg  style="width:32px;"> New Sketch in XZ plane   01- <img alt="" src=images/Workbench_Sketcher.svg  style="width:24px;"> Sketcher WB \> <img alt="" src=images/Sketcher_NewSketch.svg‎‎  style="width:32px;"> Sketch in XZ plane
  ![](images/01sketchXZ_PartWBvsPartDesignWBn.jpg )                                                                                             ![](images/01Psketch_PartWBvsPartDesignWBn.jpg )
                                                                                                                                                                               

  ----------------------------------------------------------------------------------------------- ----------------------------------------------------------------------------------
  02- <img alt="" src=images/PartDesign_Revolution.svg  style="width:32px;"> Revolution / Z   02- <img alt="" src=images/Part_Revolve.svg  style="width:32px;"> Revolve / Z
  ![](images/02revolutionZ_PartWBvsPartDesignWBn.jpg )          ![](images/02revolveZ_PartWBvsPartDesignWBn.jpg )
                                                                                                  
  ----------------------------------------------------------------------------------------------- ----------------------------------------------------------------------------------

  ------------------------------------------------------------------------------------------------- -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  03- <img alt="" src=images/Sketcher_NewSketch.svg  style="width:32px;"> New Sketch in XY plane   03- <img alt="" src=images/Workbench_Sketcher.svg  style="width:24px;"> Sketcher WB \> <img alt="" src=images/Sketcher_NewSketch.svg‎‎  style="width:32px;"> New Sketch in XY plane
  ![](images/03sketchXY_PartWBvsPartDesignWBn.jpg )                  ![](images/03sketchXY_PartWBvsPartDesignWBn.jpg )
                                                                                                    
  ------------------------------------------------------------------------------------------------- -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

  ------------------------------------------------------------------------------- --------------------------------------------------------------------------------
  04- <img alt="" src=images/PartDesign_Pocket.svg  style="width:32px;"> Pocket   04a- <img alt="" src=images/Part_Extrude.svg  style="width:32px;"> Extrude
  ![](images/04pocket_PartWBvsPartDesignWBn.jpg )    ![](images/04aExtrude_PartWBvsPartDesignWB.jpg )
                                                                                  
  ------------------------------------------------------------------------------- --------------------------------------------------------------------------------

  ------------------------------------------------------------------------------ ------------------------------------------------------------------------
                                                                                 04b- <img alt="" src=images/Part_Cut.svg  style="width:32px;"> Cut
  ![](images/00nothing_PartWBvsPartDesignWB.jpg )   ![](images/04bCut_PartWBvsPartDesignWB.jpg )
                                                                                 
  ------------------------------------------------------------------------------ ------------------------------------------------------------------------

  ------------------------------------------------------------------------------------------------- -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  05- <img alt="" src=images/Sketcher_NewSketch.svg  style="width:32px;"> New Sketch in XZ plane   05- <img alt="" src=images/Workbench_Sketcher.svg  style="width:24px;"> Sketcher WB \> <img alt="" src=images/Sketcher_NewSketch.svg‎‎  style="width:32px;"> New Sketch in XZ plane
  ![](images/05sketchXZ_PartWBvsPartDesignWB.jpg )                    ![](images/05PsketchXZ_PartWBvsPartDesignWB.jpg )
                                                                                                    
  ------------------------------------------------------------------------------------------------- -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

  -------------------------------------------------------------------------------- --------------------------------------------------------------------------------
  06- <img alt="" src=images/PartDesign_Pad.svg  style="width:32px;"> Pad sym/XZ      06a- <img alt="" src=images/Part_Extrude.svg  style="width:32px;"> Extrude sym/XZ
  ![](images/06padSymXZ_PartWBvsPartDesignWB.jpg )   ![](images/06aExtrude_PartWBvsPartDesignWB.jpg )
                                                                                   
  -------------------------------------------------------------------------------- --------------------------------------------------------------------------------

  ------------------------------------------------------------------------------ ----------------------------------------------------------------------------------------------------------------------------------------------------------
                                                                                 06b- <img alt="" src=images/Workbench_Draft.svg  style="width:24px;"> Draft <img alt="" src=images/Draft_PolarArray.svg  style="width:32px;"> Polar Pattern
  ![](images/00nothing_PartWBvsPartDesignWB.jpg )   ![](images/06bDraftPolarPattern_PartWBvsPartDesignWB.jpg )
                                                                                 
  ------------------------------------------------------------------------------ ----------------------------------------------------------------------------------------------------------------------------------------------------------

  ------------------------------------------------------------------------------ ------------------------------------------------------------------------------
                                                                                 06c- <img alt="" src=images/Part_Fuse.svg  style="width:32px;"> Fusion
  ![](images/00nothing_PartWBvsPartDesignWB.jpg )   ![](images/06cFusion_PartWBvsPartDesignWB.jpg )
                                                                                 
  ------------------------------------------------------------------------------ ------------------------------------------------------------------------------

  --------------------------------------------------------------------------------------------------------- -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  07- <img alt="" src=images/Sketcher_NewSketch.svg  style="width:32px;"> New Sketch on base planar face   07- <img alt="" src=images/Workbench_Sketcher.svg  style="width:24px;"> Sketcher WB \> <img alt="" src=images/Sketcher_NewSketch.svg‎‎  style="width:32px;"> New Sketch in XZ plane
  ![](images/07sketchBaseSupFace_PartWBvsPartDesignWB.jpg )          ![](images/07PsketchXZ_PartWBvsPartDesignWB.jpg )
                                                                                                            
  --------------------------------------------------------------------------------------------------------- -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

  ------------------------------------------------------------------------------------------------ --------------------------------------------------------------------------------
  08- <img alt="" src=images/PartDesign_Hole.svg  style="width:32px;"> Hole - counterbore            08a- <img alt="" src=images/Part_Revolve.svg  style="width:32px;"> Revolve
  ![](images/08hole-counterbore_PartWBvsPartDesignWB.jpg )   ![](images/08aRevolve_PartWBvsPartDesignWB.jpg )
                                                                                                   
  ------------------------------------------------------------------------------------------------ --------------------------------------------------------------------------------

  ------------------------------------------------------------------------------ ----------------------------------------------------------------------------------------------------------------------------------------------------------
                                                                                 08b- <img alt="" src=images/Workbench_Draft.svg  style="width:24px;"> Draft <img alt="" src=images/Draft_PolarArray.svg  style="width:32px;"> Polar Pattern
  ![](images/00nothing_PartWBvsPartDesignWB.jpg )   ![](images/08bDraftPolarPattern_PartWBvsPartDesignWB.jpg )
                                                                                 
  ------------------------------------------------------------------------------ ----------------------------------------------------------------------------------------------------------------------------------------------------------

  ------------------------------------------------------------------------------------------------------------------ ----------------------------------------------------------------------
  09- <img alt="" src=images/PartDesign_PolarPattern.svg  style="width:32px;"> Polar Pattern of Hole and Pad   09- <img alt="" src=images/Part_Cut.svg  style="width:32px;"> Cut
  ![](images/09polarPatternHoleAndPad_PartWBvsPartDesignWB.jpg )         ![](images/09Cut_PartWBvsPartDesignWB.jpg )
                                                                                                                     
  ------------------------------------------------------------------------------------------------------------------ ----------------------------------------------------------------------

Compare the construction trees in the two workbenches as well as their organization and reading timeline :

  ------------------------------------------------------------------------------------ ------------------------------------------------------------------------
  10- Construction tree in PartDesign WB                                               10- Construction tree in Part WB
  ![](images/PartvsPartDesign_TreePartDesignWB.jpg )   ![](images/PartvsPartDesign_TreePartWB.jpg )
                                                                                       
  ------------------------------------------------------------------------------------ ------------------------------------------------------------------------

## Conclusion

Part and PartDesign workbenches can be used together with some care, creating quite complex models.

[Top](#Top.md)


{{Tutorials navi

}}  {{PartDesign Tools navi}} {{Sketcher Tools navi}} 