# Part XOR/it
---
- GuiCommand:/it   Name:Part_XOR   Name/it:Booleana XOR   MenuLocation:Part → Dividi → Booleana XOR   Workbenches:[SeeAlso:[[Part_BooleanFragments/it|Frammenti booleani](Part_Workbench/it___Part]].md), [Affetta in composto](Part_Slice/it.md), [Congiungi](Part_CompJoinFeatures.md), [Booleane di Parte](Part_Boolean/it.md)---


</div>

## Descrizione

The <img alt="" src=images/Part_XOR.svg  style="width:24px;"> **Part XOR** command removes geometry shared by an even number of objects and leaves a void space between the involved objects. For two objects it represents a symmetric version of [Part Cut](Part_Cut.md).

<img alt="" src=images/Part_XOR-01.png  style="width:300px;"> <img alt="" src=images/Button_right.svg  style="width:16px;"> <img alt="" src=images/Part_XOR-02.png  style="width:300px;"> 
*Three overlapping objects → Result object*

## Utilizzo

1.  Select two or more objects. It is also possible to select a [Part Compound](Part_Compound.md) containing two or more objects.
2.  There are several ways to invoke the command:
    -   Select the **Part → Boolean → <img src="images/Part_XOR.svg" width=16px> Boolean XOR** option from the menu.
    -   Press the **<img src="images/Part_XOR.svg" width=16px> [Boolean XOR](Part_XOR.md)** button.

## Notes

-   Void spaces are hard to detect if the selected objects do not have co-planar faces. To verify the XOR result the [Std ToggleClipPlane](Std_ToggleClipPlane.md) can then be used.

## Proprietà

## Script


<div class="mw-translate-fuzzy">





</div>



---
![](images/Right_arrow.png) [documentation index](../README.md) > [Part](Part_Workbench.md) > Part XOR/it
