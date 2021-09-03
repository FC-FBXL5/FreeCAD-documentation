


<div class="mw-translate-fuzzy">


{{VeryImportantMessage|(November 2018) Diese Information kann unvollständig und veraltet sein. Für die letzte API siehe die (engl.) [https://www.freecadweb.org/api autogenerierte API-Dokumentation].}}


</div>

In FreeCAD, Placement defines an object\'s position and rotation. The Placement concept is explained in detail here: [Placement](Placement.md).

Example of setting a document object\'s Placement: 
```python
myObj = FreeCAD.ActiveDocument.ActiveObject
pl = FreeCAD.Placement()
pl.move(FreeCAD.Vector(2,0,0))
myObj.Placement = pl
```


{{APIClass|Placement| ) or (Placement) or (Matrix) or (Base, Rotation) or (Base,Rotation,Center) or (Base,Axis,Angle|Constructs a placement, empty or with the given arguments, or as a copy of the given placement.}}


{{APIProperty|Base|a vector representing the Placement's position.}}


{{APIProperty|Rotation|a quaternion representing the Placement's rotation.}}


{{APIFunction|inverse| |computes the inverse placement|a placement.}}


{{APIFunction|move|Vector|moves the Placement along the given vector|nothing}}


{{APIFunction|multVec|Vector|applies the Placement to the given vector|the resulting vector.}}


{{APIFunction|multiply|Placement|multiplies this placement with another one|the resulting placement.}}


{{APIFunction|toMatrix| | |a matrix representing the Placement's transformation.}}


 

[Category:API{{\#translation:}}](Category:API.md) [Category:Poweruser Documentation{{\#translation:}}](Category:Poweruser_Documentation.md)