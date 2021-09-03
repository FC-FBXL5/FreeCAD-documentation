---
- GuiCommand:
   Name:Part SimpleCopy‎
   MenuLocation:Part → Create a copy → Create simple copy
   Workbenches:[Part](Part_Workbench.md)
   SeeAlso:[Std Copy](Std_Copy.md), [Std Duplicate Selection](Std_DuplicateSelection.md), [Part TransformedCopy](Part_TransformedCopy.md), [Part ElementCopy](Part_ElementCopy.md), [Part RefineShape](Part_RefineShape.md)
---

## Description


**![](images/)_[Part_SimpleCopy‎](Part_SimpleCopy‎.md)**

produces a copy that has no parametric history; the steps and operations needed to create it aren\'t accessible any more.

**Alternatively**, to produce other non-parametric copies use <img alt="" src=images/Part_TransformedCopy.svg  style="width:16px;">[Transformed Copy](Part_TransformedCopy.md), <img alt="" src=images/Part_ElementCopy.svg  style="width:16px;"> [Element Copy](Part_ElementCopy.md), and <img alt="" src=images/Part_RefineShape.svg  style="width:16px;"> [RefineShape](Part_RefineShape.md)

## Usage

1.  Select an object for which you wish to make a copy.
2.  Go to the menu {{MenuCommand|Part → Create a copy → ![](images/)_[Create_simple_copy](Part_SimpleCopy.md)}}.

## Properties

### Data

The copy has a simple **Placement** property like any other [Part Feature](Part_Feature.md).

### View

The copy has simple view properties like any other [Part Feature](Part_Feature.md).

## Scripting

The **Part SimpleCopy**‎ command can be applied after selecting one or more objects in the [Tree view](Tree_view.md):

 
```python
FreeCADGui.runCommand('Part_SimpleCopy')
```

The selection can be manual (by using the mouse), or via the [Python console](Python_console.md).
To know more about selecting objects programmatically, refer to [Selection methods](Selection_methods.md).




   