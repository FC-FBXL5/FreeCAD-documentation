---
- GuiCommand:/it
   Name:Std_SaveAs
   Name/it:Salva con nome
   MenuLocation:File → Salva con nome...
   Workbenches:Tutti
   SeeAlso:[Salva una copia](Std_SaveaCopy/it.md), [Salva](Std_Save/it.md)
---

# Std SaveAs/it


</div>

## Descrizione

Il comando **Salva con nome** salva il documento attivo con un nuovo nome di file.

## Utilizzo


<div class="mw-translate-fuzzy">

1.  Selezionare **File → Salva con nome...** nel menu.
2.  Immettere un nome per il file nella finestra di dialogo.
3.  Premere il pulsante **Salva**.


</div>

## Opzioni

-   Premere il tasto **Esc** o il pulsante **Annulla** per annullare il comando.

## Note

-   Questo comando può essere utilizzato anche per salvare i grafici delle dipendenze. Vedere [Grafico delle dipendenze](Std_DependencyGraph/it.md).

## Preferenze

-   L\'ultima posizione del file utilizzato viene memorizzata in: **Strumenti → Modifica parametri... → BaseApp → Preferences → General → FileOpenSavePath**.

## Script


**Vedere anche:**

[Script di base per FreeCAD](FreeCAD_Scripting_Basics/it.md)

Per salvare un documento con un nuovo nome, utilizzare il metodo `saveAs` dell\'oggetto documento. Per un esempio di scripting vedere [Nuovo](Std_New/it.md).


<div class="mw-translate-fuzzy">





</div>


{{Std Base navi

}}



---
![](images/Right_arrow.png) [documentation index](../README.md) > Std SaveAs/it
