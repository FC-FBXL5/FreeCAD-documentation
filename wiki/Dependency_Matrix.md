Future home of the FreeCAD Dependency Matrix: Current preparation work happening in: <https://docs.google.com/spreadsheets/d/1ar6FyCoRdxFBgx5huSU9Zl655AHlbZpe8z9XLgtRMUE/edit#gid=0>

## About Dependency Matrix {#about_dependency_matrix}

FreeCAD relies on many 3rd party libraries and applications. Integrating them and packaging them is a feat in itself. This page tries to ascertain which 3rd party versions work with specific versions of FC. This page right now is only relevant for FreeCAD 0.17 and higher

### FreeCAD 0.17dev {#freecad_0.17dev}

+------------------------+--------------------------------------+----------------------------------------+----------------------------------------+--------------------------------------+--------------------------------------+
|                        | \'\'\'                               | \'\'\'                                 | \'\'\'                                 | \'\'\'                               | \'\'\'                               |
|                        |                                      |                                        |                                        |                                      |                                      |
|                        | ### Windows 7 X86 {#windows_7_x86}   | ### Windows 8.1 X86 {#windows_8.1_x86} | ### Windows 8.1 X64 {#windows_8.1_x64} | ### Windows 10 X86 {#windows_10_x86} | ### Windows 10 X64 {#windows_10_x64} |
|                        |                                      |                                        |                                        |                                      |                                      |
|                        | \'\'\'                               | \'\'\'                                 | \'\'\'                                 | \'\'\'                               | \'\'\'                               |
+------------------------+--------------------------------------+----------------------------------------+----------------------------------------+--------------------------------------+--------------------------------------+
| **cmake**              | 3.6.2                                | 3.6.2                                  | 3.6.2                                  | 3.6.2                                | 3.6.2                                |
+------------------------+--------------------------------------+----------------------------------------+----------------------------------------+--------------------------------------+--------------------------------------+
| **Qt5**                | \-                                   | \-                                     | \-                                     | \-                                   | \-                                   |
+------------------------+--------------------------------------+----------------------------------------+----------------------------------------+--------------------------------------+--------------------------------------+
| **VS2013 SP3**         | \-                                   | X                                      | X                                      | \-                                   | \-                                   |
+------------------------+--------------------------------------+----------------------------------------+----------------------------------------+--------------------------------------+--------------------------------------+
| **VS2013 SP4**         | \-                                   | X                                      | X                                      | \-                                   | \-                                   |
+------------------------+--------------------------------------+----------------------------------------+----------------------------------------+--------------------------------------+--------------------------------------+
| **VS2013 SP5**         | \-                                   | X                                      |                                        | \-                                   | \-                                   |
+------------------------+--------------------------------------+----------------------------------------+----------------------------------------+--------------------------------------+--------------------------------------+
| **VS2015**             | \-                                   | \-                                     | \-                                     | X                                    | X                                    |
+------------------------+--------------------------------------+----------------------------------------+----------------------------------------+--------------------------------------+--------------------------------------+
| **VS2015 SP2**         | \-                                   | \-                                     | \-                                     | X                                    | X                                    |
+------------------------+--------------------------------------+----------------------------------------+----------------------------------------+--------------------------------------+--------------------------------------+
| **Windows 7 SDK**      | X                                    | \-                                     | \-                                     | \-                                   | \-                                   |
+------------------------+--------------------------------------+----------------------------------------+----------------------------------------+--------------------------------------+--------------------------------------+
| **Windows 8 SDK**      | \-                                   | \-                                     | \-                                     | \-                                   | \-                                   |
+------------------------+--------------------------------------+----------------------------------------+----------------------------------------+--------------------------------------+--------------------------------------+
| **Windows 10 SDK**     | \-                                   | \-                                     | \-                                     | \-                                   | \-                                   |
+------------------------+--------------------------------------+----------------------------------------+----------------------------------------+--------------------------------------+--------------------------------------+
| **DXSDK**              | X                                    | \-                                     | \-                                     | \-                                   | \-                                   |
+------------------------+--------------------------------------+----------------------------------------+----------------------------------------+--------------------------------------+--------------------------------------+
| **PSQL**               | 9.1.9                                | 9.1.9                                  | 9.1.9                                  | 9.1.9                                | 9.1.9                                |
+------------------------+--------------------------------------+----------------------------------------+----------------------------------------+--------------------------------------+--------------------------------------+
| **MinGW**              | 5.3.0                                | \-                                     | \-                                     | \-                                   | \-                                   |
+------------------------+--------------------------------------+----------------------------------------+----------------------------------------+--------------------------------------+--------------------------------------+
|                        |                                      |                                        |                                        |                                      |                                      |
+------------------------+--------------------------------------+----------------------------------------+----------------------------------------+--------------------------------------+--------------------------------------+
|                        | \'\'\'                               | \'\'\'                                 | \'\'\'                                 |                                      |                                      |
|                        |                                      |                                        |                                        |                                      |                                      |
|                        | ### OSX 10.10 {#osx_10.10}           | ### OSX 10.11 {#osx_10.11}             | ### macOS 10.12 {#macos_10.12}         |                                      |                                      |
|                        |                                      |                                        |                                        |                                      |                                      |
|                        | \'\'\'                               | \'\'\'                                 | \'\'\'                                 |                                      |                                      |
+------------------------+--------------------------------------+----------------------------------------+----------------------------------------+--------------------------------------+--------------------------------------+
| **Qt5**                | \-                                   | \-                                     | \-                                     |                                      |                                      |
+------------------------+--------------------------------------+----------------------------------------+----------------------------------------+--------------------------------------+--------------------------------------+
| **Python**             | \-                                   | \-                                     | \-                                     |                                      |                                      |
+------------------------+--------------------------------------+----------------------------------------+----------------------------------------+--------------------------------------+--------------------------------------+
| **Cmake**              | 3.0.2                                | 3.6.2                                  | 3.6.2                                  |                                      |                                      |
+------------------------+--------------------------------------+----------------------------------------+----------------------------------------+--------------------------------------+--------------------------------------+
| **Clang**              | 7.0.2                                | 8.0.0                                  | 8.0.0                                  |                                      |                                      |
+------------------------+--------------------------------------+----------------------------------------+----------------------------------------+--------------------------------------+--------------------------------------+
| **Xcode**              | 7.2.1                                | 8.2                                    | 8.2.1                                  |                                      |                                      |
+------------------------+--------------------------------------+----------------------------------------+----------------------------------------+--------------------------------------+--------------------------------------+
| **OCC**                | ≥7.0                                 | ≥7.0                                   | ≥7.0                                   |                                      |                                      |
+------------------------+--------------------------------------+----------------------------------------+----------------------------------------+--------------------------------------+--------------------------------------+
| **Smesh**              | \-                                   | \-                                     | \-                                     |                                      |                                      |
+------------------------+--------------------------------------+----------------------------------------+----------------------------------------+--------------------------------------+--------------------------------------+
| **VTK**                | \-                                   | \-                                     | \-                                     |                                      |                                      |
+------------------------+--------------------------------------+----------------------------------------+----------------------------------------+--------------------------------------+--------------------------------------+
| **Command line tools** | \-                                   | \-                                     | \-                                     |                                      |                                      |
+------------------------+--------------------------------------+----------------------------------------+----------------------------------------+--------------------------------------+--------------------------------------+
|                        | \'\'\'                               | \'\'\'                                 | \'\'\'                                 | \'\'\'                               | \'\'\'                               |
|                        |                                      |                                        |                                        |                                      |                                      |
|                        | ### RedHat 6.6 x64 {#redhat_6.6_x64} | ### OpenSuse 42.1 {#opensuse_42.1}     | ### Ubuntu 14.04 {#ubuntu_14.04}       | ### RedHat 7.2 x64 {#redhat_7.2_x64} | ### Ubuntu 16.04 {#ubuntu_16.04}     |
|                        |                                      |                                        |                                        |                                      |                                      |
|                        | \'\'\'                               | \'\'\'                                 | \'\'\'                                 | \'\'\'                               | \'\'\'                               |
+------------------------+--------------------------------------+----------------------------------------+----------------------------------------+--------------------------------------+--------------------------------------+
| **Qt5**                | \-                                   | \-                                     | \-                                     | \-                                   | \-                                   |
+------------------------+--------------------------------------+----------------------------------------+----------------------------------------+--------------------------------------+--------------------------------------+
| **Python**             | \-                                   | \-                                     | \-                                     | \-                                   | \-                                   |
+------------------------+--------------------------------------+----------------------------------------+----------------------------------------+--------------------------------------+--------------------------------------+
| **Cmake**              | \-                                   | 3.6.2                                  | 2.8.12.2                               | \-                                   | 3.5.1                                |
+------------------------+--------------------------------------+----------------------------------------+----------------------------------------+--------------------------------------+--------------------------------------+
| **Gcc**                | ≥4.7                                 | ≥4.7                                   | ≥4.7                                   | ≥4.7                                 |                                      |
+------------------------+--------------------------------------+----------------------------------------+----------------------------------------+--------------------------------------+--------------------------------------+
| **OCC**                | ≥7.0                                 | ≥7.0                                   | ≥7.0                                   | ≥7.0                                 |                                      |
+------------------------+--------------------------------------+----------------------------------------+----------------------------------------+--------------------------------------+--------------------------------------+
| **VTK**                | \-                                   | \-                                     | \-                                     | \-                                   |                                      |
+------------------------+--------------------------------------+----------------------------------------+----------------------------------------+--------------------------------------+--------------------------------------+
|                        |                                      |                                        |                                        |                                      |                                      |
+------------------------+--------------------------------------+----------------------------------------+----------------------------------------+--------------------------------------+--------------------------------------+

## List of dependencies {#list_of_dependencies}

-   [CMake](https://gitlab.kitware.com/cmake/cmake) - a cross-platform, open-source build system.

[OCCT](http://git.dev.opencascade.org/gitweb/?p=occt.git) - Open CASCADE Technology, The Open Source 3D Modeling Libraries

[VTK](https://gitlab.kitware.com/vtk/vtk) - Visualization Toolkit for 3D computer graphics, image processing and visualization. VTK consists of a C++ class library and several interpreted interface layers including Tcl/Tk, Java, and Python.

Coin3d -

pivy

graphviz

OpenCamlib

[Category:3rd Party](Category:3rd_Party.md) [Category:Sandbox](Category:Sandbox.md)