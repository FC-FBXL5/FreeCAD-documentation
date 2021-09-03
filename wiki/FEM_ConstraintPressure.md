---
- GuiCommand:
   Name:FEM ConstraintPressure
   MenuLocation:Model → Mechanical Constraints → Constraint pressure
   Workbenches:[FEM](FEM_Workbench.md)
   SeeAlso:[FEM Constraint force](FEM_ConstraintForce.md)
---

## Description

Applies a pressure constraint to a face.

## Usage

1.  There are several ways to invoke the command:
    -   Press the **<img src="images/FEM_ConstraintPressure.svg" width=16px> [FEM ConstraintPressure](FEM_ConstraintPressure.md)** button.
    -   Select the {{MenuCommand|Model → Mechanical Constraints → <img src="images/FEM_ConstraintPressure.svg" width=16px> Constraint pressure}} option from the menu.
2.  Click on **Add reference** and select face in the [3D view](3D_view.md).
3.  Edit appropriate window to specify pressure load in MPa.
4.  Tick box to reverse direction if necessary.

## Notes

-   Distribution of pressure on face is always uniform and always perpendicular to face.

-   Pressure on faces: <https://tracker.freecadweb.org/view.php?id=3050>




 {{FEM Tools navi}}  