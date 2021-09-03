 

## Introduction

A [property](Property.md) is a piece of information like a number or a text string that is attached to a FreeCAD document or an object in a document. Public properties can be viewed and modified in the [Property editor](Property_editor.md).

Properties play a very important role in FreeCAD. As objects in FreeCAD are \"parametric\", this means that their behavior is defined by their properties, and how these properties are used as input for their class methods. See also [PropertyLink:\_InList\_and\_OutList](PropertyLink:_InList_and_OutList.md)

## All property types {#all_property_types}

Custom [scripted objects](scripted_objects.md) can use any of the property types defined in the base system:  
```python
Bool
Float
FloatList
FloatConstraint
Angle
Distance
ExpressionEngine
Integer
IntegerConstraint
Percent
Enumeration
IntegerList
String
StringList
Length
Link
LinkList
LinkSubList
Matrix
Vector
VectorList
VectorDistance
Placement
PlacementLink
PythonObject
Color
ColorList
Material
Path
File
FileIncluded
PartShape
FilletContour
Circle
```

Internally, the property name is prefixed with  
```python
App::PropertyBool
App::PropertyFloat
App::PropertyFloatList
...
```

Remember that these are property **types**. A single object may have many properties of the same type, but with different names.

For example:

 
```python
obj.addProperty("App::PropertyFloat", "Length")
obj.addProperty("App::PropertyFloat", "Width")
obj.addProperty("App::PropertyFloat", "Height")
```

This indicates an object with three properties of type \"Float\", named \"Length\", \"Width\", and \"Height\", respectively.

## Scripting


**See also:**

[FreeCAD scripting basics](FreeCAD_Scripting_Basics.md)

A [scripted object](scripted_objects.md) is created first, and then properties are assigned.  
```python
obj = App.ActiveDocument.addObject("Part::Feature", "CustomObject")

obj.addProperty("App::PropertyFloat", "Velocity", "Parameter", "Body speed")
obj.addProperty("App::PropertyBool", "VelocityEnabled", "Parameter", "Enable body speed")
```

In general, **Data** properties are assigned by using the object\'s `addProperty()` method. On the other hand, **View** properties are normally provided automatically by the parent object from which the scripted object is derived.

For example:

-   Deriving from `App::FeaturePython` provides only 4 **View** properties: \"Display Mode\", \"On Top When Selected\", \"Show In Tree\", and \"Visibility\".
-   Deriving from `Part::Feature` provides 17 **View** properties: the previous four, plus \"Angular Deflection\", \"Bounding Box\", \"Deviation\", \"Draw Style\", \"Lighting\", \"Line Color\", \"Line Width\", \"Point Color\", \"Point Size\", \"Selectable\", \"Selection Style\", \"Shape Color\", and \"Transparency\".

Nevertheless,  
```python
obj.ViewObject.addProperty("App::PropertyBool", "SuperVisibility", "Base", "Make the object glow")
```

## Source code {#source_code}

In the source code, properties are located in various {{FileName|src/App/Property*}} files.

They are imported and initialized in  {{Code|lang=cpp|code=
#include "Property.h"
#include "PropertyContainer.h"
#include "PropertyUnits.h"
#include "PropertyFile.h"
#include "PropertyLinks.h"
#include "PropertyPythonObject.h"
#include "PropertyExpressionEngine.h"
}}

 {{Powerdocnavi}} 

[Category:Developer Documentation{{\#translation:}}](Category:Developer_Documentation.md) [Category:Python Code{{\#translation:}}](Category:Python_Code.md)