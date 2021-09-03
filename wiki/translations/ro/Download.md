 {{TOCright}}


<div class="mw-translate-fuzzy">

## Varianta curentă stabilă {#varianta_curentă_stabilă}


</div>


<div class="mw-translate-fuzzy">

Versiunea 0,17 inițială de FreeCAD (0.17.13509) a fost publicată în 2018-04-06. Multe rezolvări de bug-uri au fost publicate de atunci, cea mai recentă versiune bug fix \"0.17.13541\" a fost publicată în 2018-08-16. Este posibil să nu fie disponibilă pentru toate sistemele de operare în acest moment. Pentru a afla noutățile, consultați [release notes](Release_notes_0.17.md).


</div>


<div class="mw-translate-fuzzy">

Veți găsi SHA256 checksums (pentru a verifica integritatea descărcării) și versiunea portabilă pe Windows la [0.17 Release page on GitHub](https://github.com/FreeCAD/FreeCAD/releases/tag/0.17). (Versiunile mai vechi au fost \"tunse\". Disponibilitatea va reveni în viitor)


</div>

Previous versions can be downloaded from the [releases](https://github.com/FreeCAD/FreeCAD/releases) page

+:----------------------------------------------------------------------------------------------------------------------------------------:+---+:------------------------------------------------------------------------------------------------------------------------------------------------------:+---+:-----------------------------------------------------------------------:+
| ![](images/Windows.png )                                                                                                           |   | ![](images/Mac.png )                                                                                                                                 |   | ![](images/AppImage-logo.png )                              |
|                                                                                                                                          |   |                                                                                                                                                        |   |                                                                         |
| Install on Windows                                                                                                                       |   | Install on Mac                                                                                                                                         |   | Install on Linux                                                        |
|                                                                                                                                          |   |                                                                                                                                                        |   |                                                                         |
| [64-bit](https://github.com/FreeCAD/FreeCAD/releases/download/0.19.2/FreeCAD-0.19.2.7b5e18a-WIN-x64-installer1.exe) (includes installer) |   | [macOS](https://github.com/FreeCAD/FreeCAD/releases/download/0.19.2/FreeCAD_0.19-24291-macOS-x86_64-conda.dmg) 64-bit |   | [AppImage](AppImage.md) 64-bit |
+------------------------------------------------------------------------------------------------------------------------------------------+---+--------------------------------------------------------------------------------------------------------------------------------------------------------+---+-------------------------------------------------------------------------+


<div class="mw-translate-fuzzy">

#### Note către utilizatorii de Windows {#note_către_utilizatorii_de_windows}

-   The 32-Bit installer (x86) suportă următoarele versiune de Windows: 7/8/10.
-   The 64-Bit installer (x64) suportă următoarele versiuni de Windows: 7/8/10.


</div>


<div class="mw-translate-fuzzy">

#### Note pentru utilizatorii de Mac OS X {#note_pentru_utilizatorii_de_mac_os_x}

Versiunea minim acceptată este Mac OS X 10.11 "El Capitan".


</div>


<div class="mw-translate-fuzzy">

#### Note către utilizatorii de GNU/Linux {#note_către_utilizatorii_de_gnulinux}


</div>


<div class="mw-translate-fuzzy">

FreeCAD poate fi instalat din depozitele oficiale ale majorității distribuțiilor Linux, dar versiunea pe care o oferă acestea poate fi destul de veche și poate să nu aibă multe caracteristici. În schimb, puteți descărca fișierul AppImage de la link-ul mai sus, marcați-l ca executabil și apoi executați-l fără nici o instalare. Vă rugăm să consultați pagina [Install on Linux](Install_on_Linux.md) pentru mai multe opțiuni de instalare, inclusiv cum să obțineți pachete actualizate pentru Ubuntu și derivatele sale.


</div>

Please see the [Installing on Linux](Installing_on_Linux.md) page for more installation options, including daily packages for Ubuntu and derivatives.

A portable version that doesn\'t need installation can be achieved by starting FreeCAD with these commands: <small>(v0.19)</small>  
```python
cd path/to/directory_containing_AppImage/
chmod +x ./FreeCAD_0.19-23756-Linux-Conda_glibc2.12-x86_64.AppImage
HOME="$PWD/Settings" FREECAD_USER_HOME="$PWD/Settings" ./FreeCAD_0.19-23756-Linux-Conda_glibc2.12-x86_64.AppImage
```

More information about FreeCAD\'s environment variables can be found on [the configuration page](Start_up_and_Configuration#Environment_variables.md).


<div class="mw-translate-fuzzy">

### Versiuni în dezvoltare {#versiuni_în_dezvoltare}

Dezvoltarea reeCAD-ului este întotdeauna activă! Doriți să verificați versiunea de dezvoltare 0.18? Pentru utilizatorii de Linux, verificați versiunea 0.18 [AppImage](AppImage.md).m Pentru MacOS, Windows și codul sursă, a se vedea pe pagina [FreeCAD releases](https://github.com/FreeCAD/FreeCAD/releases).


</div>


<div class="mw-translate-fuzzy">

### Module și macro-uri suplimentare {#module_și_macro_uri_suplimentare}


</div>


<div class="mw-translate-fuzzy">

Comunitatea FreeCAD oferă o multitudine de module și macrocomenzi suplimentare. Ele pot fi ușor accesate din interiorul FreeCAD folosind [Addon manager](Addon_Manager.md).


</div>


