---
- GuiCommand:
   Name:Mesh BuildRegularSolid
   MenuLocation:Meshes → Regular solid...
   Workbenches:[Mesh](Mesh_Workbench.md)
---

## Description

The **Mesh BuildRegularSolid** command creates a regular parametric solid mesh object.

## Usage

1.  There are several ways to invoke the command:
    -   Press the **<img src="images/Mesh_BuildRegularSolid.svg" width=16px> [Mesh BuildRegularSolid](Mesh_BuildRegularSolid.md)** button.
    -   Select the {{MenuCommand|Meshes → <img src="images/Mesh_BuildRegularSolid.svg" width=16px> Regular solid...}} option from the menu.
2.  The {{MenuCommand|Regular Solid}} dialog box opens.
3.  First select a mesh object type from the dropdown list:
    -   
        {{MenuCommand|<img src="images/Mesh_Cube.svg" width=16px> Cube}}
        

    -   
        {{MenuCommand|<img src="images/Mesh_Cylinder.svg" width=16px> Cylinder}}
        

    -   
        {{MenuCommand|<img src="images/Mesh_Cone.svg" width=16px> Cone}}
        

    -   
        {{MenuCommand|<img src="images/Mesh_Sphere.svg" width=16px> Sphere}}
        

    -   
        {{MenuCommand|<img src="images/Mesh_Ellipsoid.svg" width=16px> Ellipsoid}}
        

    -   
        {{MenuCommand|<img src="images/Mesh_Torus.svg" width=16px> Torus}}
        
4.  Specify the required settings. The available settings depend on the mesh object type. See [Properties](#Properties.md).
5.  For meshes with curved surfaces: a higher {{MenuCommand|Sampling}} value results in a finer mesh.
6.  Press the {{button|Create}} button to create the mesh object.
7.  Optionally create more mesh objects.
8.  Press the {{button|Close}} button to close the dialog box and finish the command.

## Notes

-   Mesh objects created with this command are parametric. Whenever they are recomputed, for example after changing one of their parameters, their mesh is reconstructed. This means that manipulating them with commands such as [Mesh RemeshGmsh](Mesh_RemeshGmsh.md), [Mesh Scale](Mesh_Scale.md) etc. usually does not make sense.

## Properties

Mesh objects created with this command inherit all [Mesh Feature](Mesh_Feature.md) properties. In addition each mesh object type has a number of properties to control its parametric behavior:

### <img alt="" src=images/Mesh_Cube.svg  style="width:32px;"> Cube {#mesh_cube.svg_cube}

#### Data


{{TitleProperty|Cube}}

-    **Height|FloatConstraint**: the height of the cube.

-    **Length|FloatConstraint**: the length of the cube.

-    **Width|FloatConstraint**: the width of the cube.

### <img alt="" src=images/Mesh_Cylinder.svg  style="width:32px;"> Cylinder {#mesh_cylinder.svg_cylinder}

#### Data {#data_1}


{{TitleProperty|Base}}

-    **Closed|Bool**: if set to `False`, the planar ends of the cylinder are left open.

-    **Edge Length|FloatConstraint**: the edge length of the faces in the mesh.

-    **Length|FloatConstraint**: the length of the cylinder.

-    **Radius|FloatConstraint**: the radius of the cylinder.

-    **Sampling|IntegerConstraint**: the number of faces along the curved surface.

### <img alt="" src=images/Mesh_Cone.svg  style="width:32px;"> Cone {#mesh_cone.svg_cone}

#### Data {#data_2}


{{TitleProperty|Base}}

-    **Closed|Bool**: if set to `False`, the planar end(s) of the cone are left open.

-    **Edge Length|FloatConstraint**: the edge length of the faces in the mesh.

-    **Length|FloatConstraint**: the length of the cone.

-    **Radius 1|FloatConstraint**: the first radius of the cone. Can be {{value|0}}.

-    **Radius 2|FloatConstraint**: the second radius of the cone. Can be {{value|0}}.

-    **Sampling|IntegerConstraint**: the number of faces along the curved surface.

### <img alt="" src=images/Mesh_Sphere.svg  style="width:32px;"> Sphere {#mesh_sphere.svg_sphere}

#### Data {#data_3}


{{TitleProperty|Base}}

-    **Radius|FloatConstraint**: the radius of the sphere.

-    **Sampling|IntegerConstraint**: the number of faces along both directions of the curved surface.

### <img alt="" src=images/Mesh_Ellipsoid.svg  style="width:32px;"> Ellipsoid {#mesh_ellipsoid.svg_ellipsoid}

#### Data {#data_4}


{{TitleProperty|Base}}

-    **Radius 1|FloatConstraint**: the first radius of the ellipsoid.

-    **Radius 2|FloatConstraint**: the second radius of the ellipsoid.

-    **Sampling|IntegerConstraint**: the number of faces along both directions of the curved surface.

### <img alt="" src=images/Mesh_Torus.svg  style="width:32px;"> Torus {#mesh_torus.svg_torus}

#### Data {#data_5}


{{TitleProperty|Base}}

-    **Radius 1|FloatConstraint**: the first (main) radius the torus.

-    **Radius 2|FloatConstraint**: the second radius of the torus.

-    **Sampling|IntegerConstraint**: the number of faces along both directions of the curved surface.




 {{Mesh Tools navi}}  