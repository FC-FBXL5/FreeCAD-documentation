---
- GuiCommand:/es   Name:Arch Git‏‎   Name/es:Arch Git   Workbenches:[[Arch Module/es   Arch]]|MenuLocation:Arch → Utilities → Git   Shortcut:‏‎   SeeAlso:---


</div>


{{VeryImportantMessage|Starting from FreeCAD v0.17, this tool has been removed from the Arch Workbench and is now part of the external [[WebTools Workbench]] that you can install via menu Tools → <img src="images/AddonManager.svg" width=24px> [[Addon manager]].
}}

## Description

Este comando permite administrar el actual documento con [GIT](https://en.wikipedia.org/wiki/Git_%28software%29). GIT es un sistema de control de versiones de archivos y mantiene seguimiento de los cambios.

GIT es una herramienta compleja, considera aprender lo basico de el antes de usar esta herramienta, para evitar operaciones erroneas que pueden causar perdida de datos.Un literatura abundante acerca de GIT esta disponible y facil de encontrar en internet.


<div class="mw-translate-fuzzy">

**Nota:** para ser capaz de usar esta herramienta, el paquete [gitpython](https://github.com/gitpython-developers/GitPython) debe ser instalado en tu sistema. En la mayoria de las distribuciones linux, gitpython esta disponible de los repositorios de software estandar como *gitpython* o *python-git*.


</div>

## Utilización


<div class="mw-translate-fuzzy">

1.  Guardar el documento activo actual
2.  Asegurarse que el archivo guardado esta dentro de un repositorio git existente
3.  Seleccionar el menu Arquitectura -\> Utilidades -\> **<img src="images/Arch_CommitGit.png" width=16px> [Git](Arch_Git.md)
**


</div>

## Opciones

![Tasks tab showing Git interface](images/Arch_Git_panel.jpg )

-   The **Log** button will pop up a dialog showing the most recent log entries. The output corresponds to git log.
-   The **Refresh** button will re-scan the repository for changed files. After saving your work you have to do a manual refresh.
-   The **Diff** button will show the differences between the current version of a selected file and the most recent version stored in the repository. The output corresponds to git diff.
    -   By default a binary diff is made, you have to set up the fcinfo tool for textual diffing.
-   The **Select all** button will select all files to be committed.
-   The **Commit** button will commit the selected files. Be sure to write a commit message that describes the changes you are committing.
-   The **Pull** button will **download** any new changes to the repository from the selected remote. If the file currently opened in FreeCAD is being modified by a pull, a warning message will inform you so you can either save the file again or save it elsewhere.
-   The **Push** button will **upload** your latest commit(s) to the selected remote.


<div class="mw-translate-fuzzy">

-   La herramienta todavia no puede crear nuevos repositorios. tu tienes que tener un repositorio ya creado (FreeCAD revisara si el actual archivo de documento esta dentro de un repositorio Git)
-   La herramienta no puede cambiar o crear derivaciones. tu debes hacer eso manualmente con herramientas regulares de Git.


</div>

## Enabling human-readable diffs for FCStd files with the fcinfo utility {#enabling_human_readable_diffs_for_fcstd_files_with_the_fcinfo_utility}

FreeCAD\'s [Fcstd file format](File_Format_FCStd.md) is a zip-based binary format, for which Git cannot produce proper diffs. This means that you cannot see what has changed between one version and another, and also that each new version stored in the Git repository is a full copy of the file.

Although the second problem currently has no solution, the first one can be solved with a little tool available from the FreeCAD source code, called [fcinfo](https://github.com/FreeCAD/FreeCAD/blob/master/src/Tools/fcinfo). Git can be told to use the fcinfo utility to print a human-friendly report of a FCStd file, and, when asked to produce a diff between two FCStd files, will produce a diff between the two fcinfo reports instead. Please note that this is only visual feedback, a full copy of the file will still be stored internally.

Example of a diff produced with fcinfo:


```python
diff --git a/testhouse.FcStd b/testhouse.FcStd
index 08077b6..985b1d8 100644
--- a/testhouse.FcStd
+++ b/testhouse.FcStd
@@ -1,26 +1,25 @@
-Document: /tmp/43un09_testhouse.FcStd (442K)
-   SHA1: 67c1985a45d93cba57d5bf44490897aba460100d
+Document: /tmp/zfXoDd_testhouse.FcStd (370K)
+   SHA1: db1cb5fca18af7bfdca849028f40550df4d845cb
    Comment : This is a test house to showcase FreeCAD's BIM worflow and IFC export capabilities
    Company : uncreated.net
    CreatedBy : Yorik van Havre
    CreationDate : Fri May  9 12:05:54 2014 
    FileVersion : 1
    Id : 
-   Label : testhouse
-   LastModifiedBy : Yorik van Havre
-   LastModifiedDate : 2016-06-28T17:05:57-03:00
+   Label : testhouse2
+   LastModifiedBy : Yorik van Havre
+   LastModifiedDate : Sat Sep 13 20:46:36 2014
+
    License : CC-BY 3.0
    LicenseURL : http://creativecommons.org/licenses/by/3.0/
-   ProgramVersion : 0.17R7800 (Git)
-   TipName : 
+   ProgramVersion : 0.15R3989 (Git)
    Uid : 67e62d8a-6674-4358-92fe-615443be887a
-   Objects: (231)
+   Objects: (221)
        Annotation : Drawing::FeatureViewAnnotation
        Annotation001 : Drawing::FeatureViewAnnotation
        Annotation002 : Drawing::FeatureViewAnnotation
        Annotation003 : Drawing::FeatureViewAnnotation
-       Annotation004 : Drawing::FeatureViewAnnotation
-       Annotation005 : Drawing::FeatureViewAnnotation
        Array : Part::FeaturePython (9K)
        Box : Part::Box (2K)
        Building : App::DocumentObjectGroupPython
@@ -110,7 +109,7 @@ Document: /tmp/43un09_testhouse.FcStd (442K)
        Floor : App::DocumentObjectGroupPython
        Floor001 : App::DocumentObjectGroupPython
        Floor002 : App::DocumentObjectGroupPython
-       Frame : Part::FeaturePython (89K)
```

Each FreeCAD file contains a SHA1 checksum number, which will change each time the file is saved, even if no contents was changed. So fcinfo will always print something, no matter of the contents changes.

To enable the use of fcinfo (Linux and Mac only - TODO: add Windows instructions)

1.  Save the fcinfo file somewhere in your system path
2.  Make it executable
3.  Create a .gitattributes file in your Git repository and add the following line in it:

*.FCStd diff=fcinfo

Add the following lines to the .gitconfig file in your home directory:

[diff "fcinfo"]
textconv = /path/to/fcinfo

Alternatively, if you want to invoke fcinfo with arguments (e.g., --gui) use this approach [1](https://stackoverflow.com/questions/55601430/how-to-pass-a-filename-argument-gitconfig-diff-textconv):

[diff "fcinfo"]
textconv = sh -c '/path/to/fcinfo --gui "$0"'