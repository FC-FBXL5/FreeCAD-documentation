---
- GuiCommand:/tr   Name:Part Shapebuilder   Name/tr:Part Shapebuilder   MenuLocation:Part -> Shapebuilder...   |Workbenches:[SeeAlso:[[Part_CreatePrimitives/tr|Part CreatePrimitives](Part_Workbench/tr___Part]].md)---


</div>

## Description

A tool to create more complex shapes from various parametric geometric primitives.

## Usage

This tool can create the following objects:

### Edge from two vertices {#edge_from_two_vertices}

1.  Select two vertices
2.  Click on **Create**

![](images/Edge_from_verts-1.gif )

### Wire from edges {#wire_from_edges}

1.  Select a set of adjacent edges in the [3D view](3D_view.md)
2.  Click on **Create**

![](images/Wire_from_edges-1.gif )

### Face from vertices {#face_from_vertices}

1.  Select vertices bounding the face in the [3D view](3D_view.md)
2.  Select if face should be planar
3.  Click on **Create**
4.  Object will be created in [3D view](3D_view.md) and will be listed in [tree view](Tree_view.md)

![](images/Face_from_verts.gif )

### Face from edges {#face_from_edges}

1.  Select a closed set of edges bounding the face in the [3D view](3D_view.md)
2.  Select if face should be planar
3.  Click on **Create**
4.  Object will be created in [3D view](3D_view.md) and will be listed in [tree view](Tree_view.md)

![](images/Face_from_edges.gif )

### Shell from faces {#shell_from_faces}

1.  Select faces in the [3D view](3D_view.md)
2.  Select if the shape should be refined
3.  Select if all faces should be included in shell
4.  Click on **Create**
5.  Object will be created in [3D view](3D_view.md) and will be listed in [tree view](Tree_view.md)

### Solid from shell {#solid_from_shell}

1.  Select if the shape should be refined
2.  Click on **Create**
3.  Object will be created in [3D view](3D_view.md) and will be listed in [tree view](Tree_view.md)

## Notes

A possible workflow could be:

-   Draw a wireframe-model of your shape using the tools in the <img alt="" src=images/Workbench_Draft.svg  style="width:24px;"> [Draft Workbench](Draft_Workbench.md) (for example line and dwire)
-   Create all faces with \"face from edges\"
-   Create a \"shell from faces\"
-   Create a \"solid from shell\"





 