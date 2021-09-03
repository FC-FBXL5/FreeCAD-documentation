---
- GuiCommand:
   Name:Draft SetStyle
   MenuLocation:Utilities → Set style
   Workbenches:[Draft](Draft_Workbench.md), [Arch](Arch_Workbench.md)
   Version:0.19
   SeeAlso:[Draft AnnotationStyleEditor](Draft_AnnotationStyleEditor.md), [Draft ApplyStyle](Draft_ApplyStyle.md)
---

## Descrição

The <img alt="" src=images/Draft_SetStyle.svg  style="width:24px;"> **Draft SetStyle** command sets the default style for new objects.

This command is a work in progress and both the V0.19 version and the V0.20 version suffer from several bugs.

![](images/Draft_SetStyle_taskpanel.png ) *The Style settings task panel*

## Utilização

1.  There are several ways to invoke the command:
    -   Press the ![](images/Draft_tray_button_style.png ) button in the [Draft Tray](Draft_Tray.md). Depending on the current style settings this button can look different.
    -   Select the {{MenuCommand|Utilities → <img src="images/Draft_SetStyle.svg" width=16px> Set style}} option from the menu.
2.  The {{MenuCommand|Style settings}} task panel opens. See [Options](#Options.md) for more information.
3.  Optionally change one or more settings.
4.  Press the **OK** button.
5.  The button in the [Draft Tray](Draft_Tray.md) is updated.

## Opções

-   From the dropdown list at the top of the task panel an exiting style can be selected. <small>(v0.20)</small> 
-   Press the {{button|<img src="images/Document-save.svg" width=16px> Save style}} button to save the style settings. <small>(v0.20)</small> 
-   In the {{MenuCommand|Lines and faces}} section the following settings can be specified:
    -   
        {{MenuCommand|Line color}}
        
        . This is also used for [Draft Labels](Draft_Label.md) and for the **Point Color** of objects.

    -   
        {{MenuCommand|Line width}}
        
        . This is also used for [Draft Labels](Draft_Label.md).

    -   
        {{MenuCommand|Draw style}}
        
        . This feature currently does not work.

    -   
        {{MenuCommand|Display mode}}
        
        . This feature currently does not work.

    -   
        {{MenuCommand|Shape color}}
        
        .

    -   
        {{MenuCommand|Transparency}}
        
        . This feature currently does not work.
-   In the {{MenuCommand|Annotations}} section the following settings can be specified:
    -   
        {{MenuCommand|Text font}}
        
        .

    -   
        {{MenuCommand|Text size}}
        
        . This is in fact the line height, the letters are smaller.

    -   
        {{MenuCommand|Text spacing}}
        
        . This is used for [Draft Dimensions](Draft_Dimension.md). It is the distance between the text and the dimension line. <small>(v0.20)</small> 

    -   
        {{MenuCommand|Text color}}
        
        . This is also used for the **Line Color** of [Draft Dimensions](Draft_Dimension.md), which defines the color of the whole dimension including the text.

    -   
        {{MenuCommand|Line spacing}}
        
        . This scale factor is applied to the line height. This feature currently does not work. <small>(v0.20)</small> 

    -   
        {{MenuCommand|Arrow style}}
        
        .

    -   
        {{MenuCommand|Arrow size}}
        
        .

    -   
        {{MenuCommand|Show units}}
        
        .

    -   
        {{MenuCommand|Unit override}}
        
        .
-   Press the {{button|<img src="images/Draft_SetStyle.svg" width=16px> Selected}} button to apply the settings to selected objects or groups. <small>(v0.20)</small> 
-   Press the {{button|<img src="images/Draft_Text.svg" width=16px> Texts/dims}} button to apply the settings to all [Draft Texts](Draft_Text.md) and [Draft Dimensions](Draft_Dimension.md). <small>(v0.20)</small> 
-   Press the **Cancel** button to abort the command.

## Notas

-   The {{MenuCommand|Line color}}, {{MenuCommand|Line width}} and {{MenuCommand|Shape color}} settings are not only used for Draft objects, but also for objects created with other workbenches.
-   Styles are saved in a file with a fixed name: {{FileName|StylePresets.json}} which is stored in FreeCAD\'s user {{FileName|Draft}} folder:
    -   On Linux it is usually {{FileName|/home/<username>/.FreeCAD/Draft/}}.
    -   On Windows it is {{FileName|%APPDATA%\FreeCAD\Draft\}}, which is usually {{FileName|C:\Users\<username>\Appdata\Roaming\FreeCAD\Draft\}}.
    -   On macOS it is usually {{FileName|/Users/<username>/Library/Preferences/FreeCAD/Draft/}}.

## Preferências

See also: [Preferences Editor](Preferences_Editor.md) and [Draft Preferences](Draft_Preferences.md).

The following preferences are involved:

-   Line color: {{MenuCommand|Edit → Preferences... → Part design → Shape appearance → Default Shape view properties → Line color}}.
-   Line width: {{MenuCommand|Edit → Preferences... → Part design → Shape appearance → Default Shape view properties → Line width}}.
-   Draw style: {{MenuCommand|Tools → Edit parameters... → BaseApp → Preferences → Mod → Draft → DefaultDrawStyle}}.
-   Display mode: {{MenuCommand|Tools → Edit parameters... → BaseApp → Preferences → Mod → Draft → DefaultDisplayMode}}.
-   Shape color: {{MenuCommand|Edit → Preferences... → Part design → Shape appearance → Default Shape view properties → Shape color}}.
-   Transparency: {{MenuCommand|Tools → Edit parameters... → BaseApp → Preferences → Mod → Draft → DefaultTransparency}}.
-   Text font: {{MenuCommand|Edit → Preferences... → Draft → Texts and dimensions → Text settings → Font family}}.
-   Text size: {{MenuCommand|Edit → Preferences... → Draft → Texts and dimensions → Text settings → Font size}}.
-   Text spacing: {{MenuCommand|Edit → Preferences... → Draft → Texts and dimensions → Dimension settings → Text spacing}}.
-   Text color: {{MenuCommand|Tools → Edit parameters... → BaseApp → Preferences → Mod → Draft → DefaultTextColor}}.
-   Line spacing: {{MenuCommand|Tools → Edit parameters... → BaseApp → Preferences → Mod → Draft → LineSpacing}}.
-   Arrow style: {{MenuCommand|Edit → Preferences... → Draft → Texts and dimensions → Dimension settings → Arrow style}}.
-   Arrow size: {{MenuCommand|Edit → Preferences... → Draft → Texts and dimensions → Dimension settings → Arrow size}}.
-   Show units: {{MenuCommand|Edit → Preferences... → Draft → Texts and dimensions → Dimension settings → Show the unit suffix in dimensions}}.
-   Unit override: {{MenuCommand|Edit → Preferences... → Draft → Texts and dimensions → Dimension settings → Override unit}}.


<div class="mw-translate-fuzzy">





</div>


 