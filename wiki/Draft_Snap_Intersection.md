---
- GuiCommand:
   Name:Draft Snap Intersection
   Workbenches:[Draft](Draft_Workbench.md), [Arch](Arch_Workbench.md)
   SeeAlso:[Draft Snap](Draft_Snap.md), [Draft Snap Lock](Draft_Snap_Lock.md)
---

## Description

The <img alt="" src=images/Draft_Snap_Intersection.svg  style="width:24px;"> **Draft Snap Intersection** option snaps to the intersection of two edges. The edges can belong to [Draft](Draft_Workbench.md) or [Arch](Arch_Workbench.md) objects but also to objects created with other [workbenches](Workbenches.md).

 ![](images/Draft_Snap_Intersection_example.png )  *Snapping the second point of a line to the intersection of two edges*

## Usage

For general information about snapping see [Draft Snap](Draft_Snap.md).

1.  Make sure snapping is enabled. See <img alt="" src=images/Draft_Snap_Lock.svg  style="width:16px;"> [Draft Snap Lock](Draft_Snap_Lock.md).
2.  If **Draft Snap Intersection** is not active do one of the following:
    -   Press the **<img src="images/Draft_Snap_Intersection.svg" width=16px>** button in the Draft Snap toolbar.
    -   Press the **<img src="images/Draft_Snap_Lock.svg" width=16px><img src="images/Toolbar_flyout_arrow.svg" width=8px>** button in the [Draft snap widget](Draft_snap_widget.md) and in the menu select the {{MenuCommand|<img src="images/Draft_Snap_Intersection.svg" width=16px> Snap Intersection}} option.
3.  Choose a [Draft](Draft_Workbench.md) or [Arch](Arch_Workbench.md) command to create your geometry.
4.  Note that you can also change snap options while a command is active.
5.  Move the cursor over one of the edges that intersect.
6.  The edge is highlighted.
7.  If an intersection is found the point is marked and the <img alt="" src=images/Draft_Snap_Intersection.svg  style="width:16px;"> icon is displayed near the cursor.
8.  If the edges have multiple intersections: optionally move the cursor closer to another intersection.
9.  Click to confirm the point.

## Preferences

See [Draft Snap](Draft_Snap#Preferences.md).




  