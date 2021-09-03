 <img alt="" src=images/preferences-techdraw.svg  style="width:64px;"> \_\_NOTOC\_\_

The [TechDraw Workbench](TechDraw_Workbench.md) was introduced officially as part of FreeCAD in version 0.17. It is relatively new and hasn\'t had the years of development that have benefited some other workbenches. Still, TechDraw now meets its original design goal and can now \"produce basic technical drawings based on the 3D model\".

Here is a rough roadmap of areas to be addressed in the future (in no particular order).

### Current Activity {#current_activity}

-   bug fixes in preparation for v0.19 release
-   usability issues in preparation for v0.19 release

### Upcoming

-   TBD

### Recent Changes {#recent_changes}

-   see below

## Changes for v0.19 {#changes_for_v0.19}

See also <https://forum.freecadweb.org/viewtopic.php?f=10&t=34586&hilit=release+notes#p290433>

### View Options {#view_options}

The ability to create a view from a 3D window or from existing 2D geometry.
\'\'\'- an experimental version of creating a view from the 3D window (Insert Active View) has been implemented. It works, but requires further development.

### Standards Compliance {#standards_compliance}

TechDraw does not fully conform with any standard. The ability to select a drawing standard and have the various idiosyncrasies respected is required.
\'\'\'- thanks to \@tpavlicek dimensions are formatted to a selected standard and style.

### GD&T, ControlFrames, Symbols {#gdt_controlframes_symbols}

This area of TD is weak and needs to be upgraded.
\'\'\'- thanks to \@fjullien, \@reox and others, the Balloon feature has been enhanced to provide base functionality in this area.

### Drawing Tools {#drawing_tools}

This includes the ability to add leaders, callouts and detail highlights to Views. It is a prerequisite to many enhancements, particularly in the drawing annotation area, such as feature control frames and reference highlights for detail views.
**- leaderlines, a rich text annotation, welding symbols, cosmetic vertices and edges and centerlines have been added.
**- individual lines can now be hidden, coloured or styled.

### 2D Geometry {#d_geometry}

A number of 2D geometry functions were recently added to the Part module. This needs to be reviewed with an eye towards replacing custom 2D geometry code in TechDraw with standard code from Part.
\'\'\'- these 2D functions are used in the new standard compliant dimensions.

### \"non-Vertex\" Dimensions {#non_vertex_dimensions}

There is a need for Dimensions that do not rely on specific vertex/edges, but on extrema of the figure - for example, overall width/height. Also the ability to create Dimensions based solely on the 3D model even if there is no corresponding projected geometry.
\'\'\'- Extent dimensions allow the creation of a dimension that covers the left/right or top/bottom extent of a collection of edges or faces.

## Futures

### Navigation Models {#navigation_models}

TechDraw does not support the various navigation model used in the rest of FreeCAD (CAD, Blender, etc).


<div class="mw-translate-fuzzy">


</div>

### Draft/Arch coexistence {#draftarch_coexistence}

There are inconsistencies between the way the Draft/Arch and TechDraw modules represent shapes. This limits the suitability of TechDraw for Draft/Arch users. One notable short-coming is that TechDraw is unable to apply Dimensions to the Svg images it receives from Draft/Arch.

### Templates

Making a template with editable text fields requires significant expertise with [SVG](SVG.md) and an SVG editor like Inkscape. Making the template creation process simpler will be a priority in the v0.18 development cycle.

### Bug Fixes/Feature Requests {#bug_fixesfeature_requests}

See the bug tracker for up to date information.


{{TechDraw Tools navi

}}  

[Category:User Documentation/it](Category:User_Documentation/it.md) [Category:User Documentation{{\#translation:}}](Category:User_Documentation.md) [Category:TechDraw{{\#translation:}}](Category:TechDraw.md)