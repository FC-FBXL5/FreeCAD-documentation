
{{Page in progress}}







{{TOCright}}


<div class="mw-translate-fuzzy">

Skissmodulens alternativskärm hittas i [Alternativfönstret](Preferences_Editor/sv.md) (Meny Redigera -\> Alternativ).


</div>


<div class="mw-translate-fuzzy">

Den har **General settings**, där du kan specificera färgen på [snäpp](Draft_Snap/sv.md) symbolerna, standard bredd och färg på nya objekt. Genaom att kryssa i \"Save current color and linewidth across sessions\" rutan, så kommer alla ändringar som du gör i Skissmodulens **Kommandolåda** att sparas här, så att du kan starta din nästa FreeCAD session med samma färg och bredd som du använde förra gången.


</div>


<div class="mw-translate-fuzzy">

![](images/Draft_Preferences.jpg )


</div>

General settings allows you to set certain basic properties like the default [working plane](Draft_SelectPlane.md), the name and color of the [construction group](Draft_ToggleConstructionMode.md), a prefix to use for the [Draft Clones](Draft_Clone.md), and the internal precision of the calculations.

![](images/Preference_Draft_Tab_01.png )

## Grid and snapping {#grid_and_snapping}

Grid and snapping allows you to set properties of the **<img src="images/Draft_ToggleGrid.svg" width=16px> [visible grid](Draft_ToggleGrid.md)**, which can be used with the [Draft Snap](Draft_Snap.md) methods.

By default the option \"Always snap (disable snap mod)\" is active, which means that you don\'t need to press a modifier key to activate the snapping tools. If this option is not active, you must press a modifier key to activate snapping.

You can set three modifiers:

-    **Shift**constraint modifier, to [constraint](Draft_Constrain.md) the movement of the cursor along the X, Y, or Z axis.

-    **Ctrl**snap modifier, to snap the cursor to specific modes given by [Draft Snap](Draft_Snap.md).

-    **Alt**alternative modifier, to activate an alternative function for a Draft tool.

You can specify the space between each grid line, between each major line, and the total number of lines displayed in the working plane.

![](images/Preference_Draft_Tab_02.png )

## Visual settings {#visual_settings}

Visual settings allows you to specify the default line color and width for new objects, and the color of the [Draft Snap](Draft_Snap.md) symbols. By clicking the \"Save current color and linewidth across sessions\" checkbox, changes made in the [Draft Tray](Draft_Tray.md) will be saved and restored the next time you open FreeCAD.

![](images/Preference_Draft_Tab_03.png )

## Texts and dimensions {#texts_and_dimensions}

Texts and dimensions allows you to set default properties for the [Draft Text](Draft_Text.md), [Draft Dimension](Draft_Dimension.md), and [Draft ShapeString](Draft_ShapeString.md) tools, including default font and size, and style and size of the dimension lines. These properties can be changed in the individual text objects as well.

![](images/Preference_Draft_Tab_04.png )





 

[Category:Preferences{{\#translation:}}](Category:Preferences.md)