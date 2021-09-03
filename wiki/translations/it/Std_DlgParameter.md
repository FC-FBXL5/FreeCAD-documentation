---
- GuiCommand:/it
   Name:Std_DlgParameter
   Name/it:Modifica parametri
   MenuLocation:Strumenti → Modifica parametri...
   Workbenches:Tutti
   SeeAlso:[Editor delle preferenze](Preferences_Editor/it.md)
---

## Descrizione

Il comando **Modifica parametri** apre l\'editor dei parametri. Nell\'editor dei parametri i parametri che controllano il comportamento di FreeCAD e dei suoi ambienti di lavoro possono essere ispezionati e facoltativamente rimossi, aggiunti o modificati. I parametri sono memorizzati in un file chiamato {{FileName|user.cfg}}, la posizione di questo file dipende dal sistema operativo.

Lavorare con l\'editor dei parametri richiede una certa esperienza. Per i parametri più comuni conviene usare l\'[editor delle preferenze](Preferences_Editor/it.md).

![](images/Std_DlgParameter_dialog.png ) *La finestra di dialogo Editor dei parametri*

## Utilizzo

1.  Selezionare l\'opzione {{MenuCommand|Strumenti → <img src="images/Std_DlgParameter.svg" width=16px> Modifica parametri...}} dal menu.
2.  Viene visualizzata la finestra di dialogo Editor parametri. Per ulteriori informazioni, vedere le [Opzioni](Std_DlgParameter/it#Opzioni.md).
3.  Opzionalmente premere il pulsante **Salva nel disco** per aggiornare immediatamente il file {{FileName|user.cfg}}. Ciò non è indispensabile in quanto FreeCAD aggiornerà automaticamente quel file alla chiusura dell\'applicazione.
4.  Premere il pulsante **Chiudi** per chiudere l\'editor dei parametri.

## Opzioni

### Pannello di sinistra {#pannello_di_sinistra}

Il pannello di sinistra mostra un albero con gruppi di parametri e sottogruppi.

*Nel menu di scelta rapida del pannello sono disponibili le seguenti opzioni:*

#### Espandi/Riduci

1.  Se un gruppo selezionato ha uno o più sottogruppi, può essere espanso o compresso scegliendo questa opzione dal menu contestuale. Ma si può anche espandere e comprimere l\'albero nel solito modo.

#### Aggiungere un sottogruppo {#aggiungere_un_sottogruppo}

1.  Selezionare un gruppo.
2.  Selezionare l\'opzione {{MenuCommand|Aggiungi sottogruppo}} nel menu contestuale.
3.  Immettere un nome per il nuovo sottogruppo nella finestra di dialogo che si apre.
4.  Premere il pulsante **OK**.

#### Rimuovere un gruppo {#rimuovere_un_gruppo}

1.  Selezionare un gruppo.
2.  Selezionare l\'opzione {{MenuCommand|Rimuovi gruppo}} nel menu contestuale.
3.  Premere il pulsante **Sì** nella finestra di dialogo che si apre per confermare che si desidera rimuovere il gruppo (inclusi tutti i suoi sottogruppi e tutti i parametri del gruppo e dei suoi sottogruppi).

#### Rinominare un gruppo {#rinominare_un_gruppo}

1.  Selezionare un gruppo.
2.  Selezionare l\'opzione {{MenuCommand|Rinomina gruppo}} nel menu contestuale.
3.  Inserire un nuovo nome
4.  Un gruppo può anche essere rinominato facendo doppio clic su di esso.

#### Esportare un parametro {#esportare_un_parametro}

1.  Selezionare un gruppo.
2.  Selezionare l\'opzione {{MenuCommand|Esporta parametro}} nel menu contestuale.
3.  Immettere un nome file nella finestra di dialogo.
4.  Premere il pulsante **Salva**.

#### Importare un parametro {#importare_un_parametro}

1.  Selezionare un gruppo che non contiene alcun sottogruppo o rimuoverli prima. Tutti i parametri esistenti nel gruppo andranno persi.
2.  Selezionare l\'opzione {{MenuCommand|Importa parametro}} nel menu contestuale.
3.  Selezionare un file \*.FCParam nella finestra di dialogo.
4.  Premere il pulsante **Apri**.

### Pannello di destra {#pannello_di_destra}

Il pannello di destra mostra i parametri nel gruppo selezionato nel pannello di sinistra. Se questo gruppo contiene solo sottogruppi, il pannello di destra è vuoto.

*Nel menu di scelta rapida del pannello sono disponibili le seguenti opzioni:*

#### Cambia valore {#cambia_valore}

1.  Selezionare un parametro
2.  Selezionare l\'opzione {{MenuCommand|Cambia valore}} nel menu contestuale.
3.  Inserire un nuovo valore nella finestra di dialogo che si apre.
4.  Premere il pulsante **OK**.
5.  Il valore di un parametro può anche essere modificato facendo doppio clic sul suo campo \"Tipo\" o \"Valore\".

#### Rimuovere una chiave {#rimuovere_una_chiave}

1.  Selezionare un parametro.
2.  Selezionare l\'opzione {{MenuCommand|Rimuovi chiave}} nel menu contestuale.

#### Rinominare una chiave {#rinominare_una_chiave}

1.  Selezionare un gruppo.
2.  Selezionare l\'opzione {{MenuCommand|Rinomina gruppo}} nel menu contestuale.
3.  Inserire un nuovo nome
4.  Un gruppo può anche essere rinominato facendo doppio clic sul suo campo \"Nome\".

#### Nuovo elemento string {#nuovo_elemento_string}

1.  Selezionare l\'opzione {{MenuCommand|Nuovo elemento string}} o {{MenuCommand|Nuovo → Nuovo elemento string}} dal menu contestuale.
2.  Inserire un nome nella finestra di dialogo che si apre.
3.  Premere il pulsante **OK**.
4.  Immettere un valore nella finestra di dialogo successiva.
5.  Premere il pulsante **OK**.

#### Nuovo elemento float {#nuovo_elemento_float}

1.  Select the {{MenuCommand|New float item}} or {{MenuCommand|New → New float item}} option from the context menu.
2.  The next steps are similar to those for a [New string item](#New_string_item.md)

#### Nuovo elemento integer {#nuovo_elemento_integer}

1.  Select the {{MenuCommand|New integer item}} or {{MenuCommand|New → New integer item}} option from the context menu.
2.  The next steps are similar to those for a [New string item](#New_string_item.md)

#### New unsigned item {#new_unsigned_item}

1.  Select the {{MenuCommand|New unsigned item}} or {{MenuCommand|New → New unsigned item}} option from the context menu.
2.  The next steps are similar to those for a [New string item](#New_string_item.md)

#### New Boolean item {#new_boolean_item}

1.  Select the {{MenuCommand|New Boolean item}} or {{MenuCommand|New → New Boolean item}} option from the context menu.
2.  The next steps are similar to those for a [New string item](#New_string_item.md)

### Sorting

By default the groups in each tree level in the left panel are sorted alphabetically, and the parameters in the right panel are sorted alphabetically as well. But the order in each panel can be reversed by clicking the \'Group\' or \'Name\' header respectively.

### Quick search {#quick_search}

Typing a (partial) string in this input box will fully expand the tree in the left panel and highlight all groups with names that match the entered value. If no matches are found the background of the input box will turn red.

### Find

1.  In the left panel select the group where you want to start your search. The search direction is down. The search is not restricted to the group and its sub-groups, but rather the selected group and everything below it in the tree will be searched.
2.  Press the **Find...** button.
3.  Enter a string in the **Find what** input box. The search is case-insensitive.
4.  Check one or more of the {{CheckBox|TRUE|Groups}}, {{CheckBox|TRUE|Names}} and {{CheckBox|TRUE|Values}} checkboxes. Note that only string values will be searched.
5.  Optionally (un)check the {{CheckBox|TRUE|Match whole string only}} checkbox.
6.  Press the **Find Next** button to select the first group with a match. Matching parameters are not individually highlighted. Optionally repeat this until no further matches can be found.
7.  It is possible to start a new search without closing the dialog box. Again selecting the group from which to start searching is then usually required.
8.  Use the **Cancel** button to close the dialog box.

## Note


<div class="mw-translate-fuzzy">

-   La pagina [Ottimizzare l\'installazione](Fine-tuning/it.md) elenca una serie di parametri che potrebbero essere di interesse.


</div>

## Script


**Vedere anche:**

[Script di base per FreeCAD](FreeCAD_Scripting_Basics/it.md)

Per un esempio di scripting vedere [Box contenitore](Std_SelBoundingBox/it.md).


<div class="mw-translate-fuzzy">





</div>


{{Std Base navi

}}  