

![150](images/Crystal_Clear_app_tutorials.png )

Toto je místo kam jít, jestliže se chcete zúčastnit vývoje software FreeCADu.

Tyto stránky jsou zatím v ranném vývoji. Nemůžete-li najít informace, které hledáte nebo jste našli informace, na které zatím nemáme odkazy, přidejte prosím komentář na [forum](http://forum.freecadweb.org/index.php?sid=5f84150e79db8842e277b042077097ff) a někdo se na to podívá (nebo jste-li dost smělí, můžete upravit tyto stránky přímo sami!).

## Developer Documentation {#developer_documentation}


<div class="mw-translate-fuzzy">

## Dokumentace pro vývojáře {#dokumentace_pro_vývojáře}

Dokumentace pro vývojáře zahrnuje následující sekce:


</div>

### Compiling FreeCAD {#compiling_freecad}


<div class="mw-translate-fuzzy">

### Udělejte sami: Kompilace FreeCADu {#udělejte_sami_kompilace_freecadu}

-   [Správa zdrojového kódu](Source_code_management.md)
-   [Vyledání podpory](Tracker.md) máte-li problém nebo si myslíte, že jste odhalili chybu
-   [Kompilace na Windows](CompileOnWindows.md)
-   [Kompilace na Unixu](CompileOnUnix.md)
-   [Kompilace na Mac OS X](CompileOnMac.md)
-   [Detaily licence](Licence.md) - o licenci FreeCADu
-   [Knihovny třetích stran](Third_Party_Libraries.md)
-   [Nástroje třetích stran](Third_Party_Tools.md)
-   [Spuštění a konfigurace](Start_up_and_Configuration.md)
-   [Zdrojová dokumentace](Source_documentation.md)


</div>

### Packaging

[Packaging](Packaging.md) consists in taking the compiled binaries and Python source files of FreeCAD, and distributing them for use in a particular system.

-   [Linux packaging](Linux_packaging.md)
    -   [Debian development](Debian_development.md)
    -   [Debian Unstable](Debian_Unstable.md)
    -   [Git buildpackage](Git_buildpackage.md)
-   [Windows packaging](Windows_packaging.md)
-   [MacOS packaging](MacOS_packaging.md)

### Build Support Tools {#build_support_tools}


<div class="mw-translate-fuzzy">

### Nástroje pro podporu buildu {#nástroje_pro_podporu_buildu}

-   [Nástroj pro build FreeCADu](FreeCAD_Build_Tool.md)
    -   [Přidávání aplikačního modulu](Module_Creation.md) do FreeCADu
-   [Ladění](Debugging.md) FreeCADu
-   [Testování](Testing.md) FreeCADu


</div>

### Modifying FreeCAD {#modifying_freecad}


<div class="mw-translate-fuzzy">

### Modifikace FreeCADu {#modifikace_freecadu}

-   Vylepšování [vzhledu](Gui_Command.md) FreeCADu nebo pracovní plochy
-   [Branding](Branding.md) aneb *jak dát FreeCADu unikátní vzhled*
-   [Předloha](Artwork.md) - směrujeme FreeCAD k tomu aby mohl být opakovaně využitelný
-   [Překlad FreeCADu](Localisation.md)
-   [Dodatečné moduly Pythonu](Extra_python_modules.md), aneb *jak rozšířit funkcionalitu Pythonu ve FreeCADu*


</div>

-   [Translating an external workbench](Translating_an_external_workbench.md)

### Module developer\'s guide {#module_developers_guide}

[FreeCAD Mod Dev Guide](https://github.com/qingfengxia/FreeCAD_Mod_Dev_Guide): This is an ebook under writing on github, please fork and send pull request to contribute.

Chapters:

-   Overview and Software Architecture
-   Source code structure
-   Base and App module
-   Gui module
-   Python wrapping
-   Modular design
-   Fem module source analysis (mixed C++ and Python)
-   Development of CFD Module (pure Python)
-   Module testing and debugging
-   Contribute code with git

Latest pdf preview can be downoaded from [pdf folder](https://github.com/qingfengxia/FreeCAD_Mod_Dev_Guide/tree/master/pdf) of this git repo

### Internals


<div class="mw-translate-fuzzy">

### Dokumentace OpenCascade {#dokumentace_opencascade}

-   [Roman Lygin\'s tutorials](http://opencascade.wikidot.com/romansarticles)
-   [Online class reference](http://opencascade.sourcearchive.com/documentation/6.3.0.dfsg.1-1/classes.html). Poslední verze online nápovědy která je dostupná tímto způsobem, je sice už trochu zastaralá, ale stále ještě odpovídající. Je to asi výhodnější než muset stahovat jeden veliký soubor, což byste museli udělat, pokud byste chtěli nejnovější verzi.
-   [The openCascade wiki](http://opencascade.wikidot.com)


</div>

OpenCascade is a software development platform for 3D surface and solid modeling, CAD data exchange, and visualization, mostly in the form of C++ libraries.

-   [Roman Lygin\'s tutorials](http://opencascade.wikidot.com/romansarticles)
-   [Full Online Documentation](https://dev.opencascade.org/cdoc/overview/html/index.html)
-   [Reference Manual](https://dev.opencascade.org/doc/refman/html/index.html)
-   [The openCascade wiki](http://opencascade.wikidot.com) (currently containing ?? Chinese spam)

#### File format {#file_format}

[File Format FCStd](File_Format_FCStd.md). The files created with FreeCAD are `.zip` files that include the [BREP](https://en.wikipedia.org/wiki/Boundary_representation) geometry, as well as XML data that describes the document.

#### Sketcher solver {#sketcher_solver}

-   [Sketcher Solver Architecture Booklet](https://forum.freecadweb.org/viewtopic.php?f=10&t=36355) (forum thread), [source](https://github.com/abdullahtahiriyo/FreeCADBooks/tree/master/FreeCAD_Solver_Architecture) in GitHub.
-   [PlaneGCS solver](https://github.com/FreeCAD/FreeCAD/blob/master/src/Mod/Sketcher/App/planegcs/) in the FreeCAD source code; important files are [GCS.cpp](https://github.com/FreeCAD/FreeCAD/blob/master/src/Mod/Sketcher/App/planegcs/GCS.cpp) and [SubSystem.cpp](https://github.com/FreeCAD/FreeCAD/blob/master/src/Mod/Sketcher/App/planegcs/SubSystem.cpp).
-   [Recent Several Sketcher improvements](https://forum.freecadweb.org/viewtopic.php?f=9&t=29192).

The sketcher solver isn\'t perfect, as there are some issues with numerical precision when using large values, see [Adventure of fixing sketcher solver for large sketches](https://forum.freecadweb.org/viewtopic.php?f=10&t=40502).

The development of a new solver architecture could improve the way the solver is used both in the [Sketcher Workbench](Sketcher_Workbench.md), and for assembly of 3D bodies. See [Reimplementing constraint solver](https://forum.freecadweb.org/viewtopic.php?f=20&t=40525).

## Roadmap


<div class="mw-translate-fuzzy">

## Plány FreeCADu {#plány_freecadu}

FreeCAD, ačkoli už je použitelný v určité oblasti, je na začátku dlouhé cesty mezi významné CADy. Je toho potřeba ještě mnoho udělat pro dosažení stavu kdy bychom se mohli srovnávat s komerčními softwary.


</div>

[0.20 Development Cycle](0.20_Development_Cycle.md)

## Community

-   [IRC channel](irc://chat.freenode.net/freecad) ,synchronized with [gitter channel](https://gitter.im/FreeCAD/FreeCAD)
-   [Development forum](https://forum.freecadweb.org/viewforum.php?f=6)


<div class="mw-translate-fuzzy">

-   [Vývojářské plány](Development_roadmap.md)


</div>


<div class="mw-translate-fuzzy">

## Příspěvky

[Přispěvatelé](Contributors.md)


</div>




[Category:Hubs{{\#translation:}}](Category:Hubs.md) [Category:Developer Documentation{{\#translation:}}](Category:Developer_Documentation.md)