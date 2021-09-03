





{{TOCright}}

## Вступление

This page will show you how to add a new workbench to the FreeCAD interface. [Workbenches](Workbenches.md) are containers for FreeCAD commands. They can be coded in Python, in C++, or in a mix of both, which has the advantage to ally the speed of C++ to the flexibility of Python. In all cases, though, your workbench will be launched by a set of two Python files.

## Структура Верстака {#структура_верстака}

You need a folder, with any name you like, placed in the user Mod directory, with an `Init.py` file, and, optionally an `InitGui.py` file. The Init file is executed when FreeCAD starts, and the `InitGui.py` file is executed immediately after, but only when FreeCAD starts in GUI mode. That\'s all it needs for FreeCAD to find your workbench at startup and add it to its interface.

The user Mod directory is a sub-directory of the user application data directory (you can find the latter by typing `App.getUserAppDataDir()` in the [Python console](Python_console.md)):

-   On Linux it is usually {{FileName|/home/<username>/.FreeCAD/Mod/}}.
-   On Windows it is {{FileName|%APPDATA%\FreeCAD\Macro\}}, which is usually {{FileName|C:\Users\<username>\Appdata\Roaming\FreeCAD\Mod\}}.
-   On macOS it is usually {{FileName|/Users/<username>/Library/Preferences/FreeCAD/Mod/}}.

Mod папка должна выглядеть так:


```python
/Mod/
 +-- MyWorkbench/
     +-- Init.py
     +-- InitGui.py
```

Внутри этих файлов вы можете делать все, что захотите. Обычно они используются таким образом:

-   В Init.py файл вы просто добавляете пару вещей, которые используются даже тогда, когда FreeCAD работает в консольном режиме, например таке как, импортеры и экспортеры файлов.


<div class="mw-translate-fuzzy">

-   В InitGui.py файле вы инициализируете Верстак, который содержит имя, значок и ряд команд FreeCAD (см. Ниже). Этот python файл также должен иметь определенные функции, первая выполняется при загрузке FreeCAD (стараетесь делать ее как можно меньше, чтобы не замедлять запуск), еще одну, которая выполняется при активации верстака (именно там выполняется большая часть работы), и третью, когда верстак деактивирован (чтобы при необходимости можно было осободить ненужные ресурсы).


</div>

The structure and file content for a workbench described here is the classic way of creating a new workbench. One can use a slight variation in the structure of files when making a new Python workbench, that alternative way is best described as a \"namespaced workbench\", opening up the possibility to use pip to install the workbench. Both structures work, so it is more a question of preference when creating a new workbench. The style and structure for workbenches presented here are available in the global namespace of FreeCAD, whereas for the alternative style and structure the workbench resides in a dedicated namespace. For further readings on the topic see [Related](Workbench_creation#Related.md).

### Структура Верстака на языке C++ {#структура_верстака_на_языке_c}

Если вы собираетесь писать свой Верстак на python, вам не нужно проявлять особую осторожность, и вы можете просто разместить другие файлы python в папке с Init.py и InitGui.py. Однако при работе с C++ вам следует проявлять большую осторожность и начинать соблюдюдать одно фундаментальное правило FreeCAD: Разделение вашего рабочего стола между частью приложения (которая может работать в режиме консоли, без какого-либо элемента графического интерфейса) и частью графического интерфейса, которая будет загружена только при запуске FreeCAD с полной графической средой. Поэтому при создании рабочей среды в C++ вы, скорее всего, будете использовать два модуля: модуль самого приложения и модуль графического интерфейса. Эти два модуля, конечно, должны быть вызываемы из python. Любой модуль FreeCAD (приложение или графический интерфейс) состоит, по крайней мере, из файла инициализации модуля. Это типичный AppMyModuleGui.cpp файл: 
```python
extern "C" {
    void MyModuleGuiExport initMyModuleGui()  
    {
         if (!Gui::Application::Instance) {
            PyErr_SetString(PyExc_ImportError, "Cannot load Gui module in console application.");
            return;
        }
        try {
            // import other modules this one depends on
            Base::Interpreter().runString("import PartGui");
            // run some python code in the console
            Base::Interpreter().runString("print('welcome to my module!')");
        }
        catch(const Base::Exception& e) {
            PyErr_SetString(PyExc_ImportError, e.what());
            return;
        }
        (void) Py_InitModule("MyModuleGui", MyModuleGui_Import_methods);   /* mod name, table ptr */
        Base::Console().Log("Loading GUI of MyModule... done\n");    // initializes the FreeCAD commands (in another cpp file)
        CreateMyModuleCommands();    // initializes workbench and object definitions
        MyModuleGui::Workbench::init();
        MyModuleGui::ViewProviderSomeCustomObject::init();     // add resources and reloads the translators
        loadMyModuleResource();
    }
}
```

### Файл Init.py {#файл_init.py}


{{code|code=
"""FreeCAD init script of XXX module"""

# ***************************************************************************
# *   Copyright (c) 2015 John Doe john@doe.com                              *   
# *                                                                         *
# *   This file is part of the FreeCAD CAx development system.              *
# *                                                                         *
# *   This program is free software; you can redistribute it and/or modify  *
# *   it under the terms of the GNU Lesser General Public License (LGPL)    *
# *   as published by the Free Software Foundation; either version 2 of     *
# *   the License, or (at your option) any later version.                   *
# *   for detail see the LICENCE text file.                                 *
# *                                                                         *
# *   FreeCAD is distributed in the hope that it will be useful,            *
# *   but WITHOUT ANY WARRANTY; without even the implied warranty of        *
# *   MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the         *
# *   GNU Lesser General Public License for more details.                   *
# *                                                                         *
# *   You should have received a copy of the GNU Library General Public     *
# *   License along with FreeCAD; if not, write to the Free Software        *
# *   Foundation, Inc., 59 Temple Place, Suite 330, Boston, MA  02111-1307  *
# *   USA                                                                   *
# *                                                                         *
# ***************************************************************************/

FreeCAD.addImportType("My own format (*.own)", "importOwn")
FreeCAD.addExportType("My own format (*.own)", "importOwn")
print("I am executing some stuff here when FreeCAD starts!")
}}

You can choose any license you like for your workbench, but be aware that if you wish to see your workbench integrated into and distributed with the FreeCAD source code at some point, it needs to be LGPL2+ like the example above. See [Licence](Licence.md).

The `FreeCAD.addImportType()` and `addEXportType()` functions allow you to give the name and extension of a file type, and a Python module responsible for its import. In the example above, an `importOwn.py` module will handle `.own` files. See [Code snippets](Code_snippets.md) for more examples.

### Python workbenches {#python_workbenches}

This is the InitGui.py file: 
```python
class MyWorkbench (Workbench):

    MenuText = "My Workbench"
    ToolTip = "A description of my workbench"
    Icon = """paste here the contents of a 16x16 xpm icon"""

    def Initialize(self):
        """This function is executed when FreeCAD starts"""
        import MyModuleA, MyModuleB # import here all the needed files that create your FreeCAD commands
        self.list = ["MyCommand1", "MyCommand2"] # A list of command names created in the line above
        self.appendToolbar("My Commands",self.list) # creates a new toolbar with your commands
        self.appendMenu("My New Menu",self.list) # creates a new menu
        self.appendMenu(["An existing Menu","My submenu"],self.list) # appends a submenu to an existing menu

    def Activated(self):
        """This function is executed when the workbench is activated"""
        return

    def Deactivated(self):
        """This function is executed when the workbench is deactivated"""
        return

    def ContextMenu(self, recipient):
        """This is executed whenever the user right-clicks on screen"""
        # "recipient" will be either "view" or "tree"
        self.appendContextMenu("My commands",self.list) # add commands to the context menu

    def GetClassName(self): 
        # This function is mandatory if this is a full Python workbench
        # This is not a template, the returned string should be exactly "Gui::PythonWorkbench"
        return "Gui::PythonWorkbench"
       
Gui.addWorkbench(MyWorkbench())
``` Other than that, you can do anything you want: you could put your whole workbench code inside the InitGui.py if you want, but it is usually more convenient to place the different functions of your workbench in separate files. So those files are smaller and easier to read. Then you import those files into your InitGui.py file. You can organize those files the way you want, a good example is one for each FreeCAD command you add.

#### Preferences

You can add a Preferences page for your Python workbench. The Preferences pages look for a preference icon with a specific name in the Qt Resource system. If your icon isn\'t in the resource system or doesn\'t have the correct name, your icon won\'t appear on the Preferences page.

Adding your workbench icon:

-   the preferences icon needs to be named \"preferences-\" + \"modulename\" + \".svg\" (all lowercase)
-   make a qrc file containing all icon names
-   in the main \*.py directory, run pyside-rcc -o myResources.py myqrc.qrc
-   in InitGui.py, add import myResource(.py)
-   update your repository(git) with myResources.py and myqrc.qrc

You\'ll need to redo the steps if you add/change icons.

\@kbwbe has created a nice script to compile resources for the A2Plus workbench. See below.

Adding your preference page(s):

-   You need to compile the Qt designer plugin that allows you to add preference settings with [Qt Designer](Compile_on_Linux#Qt_designer_plugin.md)
-   Create a blank widget in Qt Designer (no buttons or anything)
-   Design your preference page, any setting that must be saved (preferences) must be one of the Gui::Pref\* widgets that were added by the plugin)
-   In any of those, make sure you fill the PrefName (the name of your preference value) and PrefPath (ex: Mod/MyWorkbenchName), which will save your value under BaseApp/Preferences/Mod/MyWorkbenchName
-   Save the ui file in your workbench, make sure it\'s handled by cmake
-   In your workbench, for ex. inside the InitGui file, inside the Initialize method (but any other place works too), add: FreeCADGui.addPreferencePage(\"/path/to/myUiFile.ui\",\"MyGroup\"), \"MyGroup\" being one of the preferences groups on the left. FreeCAD will automatically look for a \"preferences-mygroup.svg\" file in its known locations (which you can extend with FreeCADGui.addIconPath())
-   Make sure the addPreferencePage() method is called only once, otherwise your pref page will be added several times

### C++ workbenches {#c_workbenches}

If you are going to code your workbench in C++, you will probably want to code the workbench definition itself in C++ too (although it is not necessary: you could also code only the tools in C++, and leave the workbench definition in Python). In that case, the InitGui.py file becomes very simple: It might contain just one line: 
```pythonimport MyModuleGui``` where MyModule is your complete C++ workbench, including the commands and workbench definition.

Coding C++ workbenches works in a pretty similar way. This is a typical Workbench.cpp file to include in the Gui part of your module: 
```python
namespace MyModuleGui {
    class MyModuleGuiExport Workbench : public Gui::StdWorkbench
    {
        TYPESYSTEM_HEADER();

    public:
        Workbench();
        virtual ~Workbench();

        virtual void activated();
        virtual void deactivated();

    protected:
        Gui::ToolBarItem* setupToolBars() const;
        Gui::MenuItem*    setupMenuBar() const;
    };
}
```

#### Preferences {#preferences_1}

You can add a Preferences page for C++ workbenches too. The steps are similar to those for Python.

## FreeCAD commands {#freecad_commands}

FreeCAD commands are the basic building block of the FreeCAD interface. They can appear as a button on toolbars, and as a menu entry in menus. But it is the same command. A command is a simple Python class, that must contain a couple of predefined attributes and functions, that define the name of the command, its icon, and what to do when the command is activated.

### Python command definition {#python_command_definition}


```python
class My_Command_Class():
    """My new command"""

    def GetResources(self):
        return {'Pixmap'  : 'My_Command_Icon', # the name of a svg file available in the resources
                'Accel' : "Shift+S", # a default shortcut (optional)
                'MenuText': "My New Command",
                'ToolTip' : "What my new command does"}

    def Activated(self):
        """Do something here"""
        return

    def IsActive(self):
        """Here you can define if the command must be active or not (greyed) if certain conditions
        are met or not. This function is optional."""
        return True

FreeCADGui.addCommand('My_Command',My_Command_Class())
```

### C++ command definition {#c_command_definition}

Similarly, you can code your commands in C++, typically have a Commands.cpp file in your Gui module. This is a typical Commands.cpp file: 
```pythonDEF_STD_CMD_A(CmdMyCommand);

CmdMyCommand::CmdMyCommand()
  :Command("My_Command")
{
  sAppModule    = "MyModule";
  sGroup        = QT_TR_NOOP("MyModule");
  sMenuText     = QT_TR_NOOP("Runs my command...");
  sToolTipText  = QT_TR_NOOP("Describes what my command does");
  sWhatsThis    = QT_TR_NOOP("Describes what my command does");
  sStatusTip    = QT_TR_NOOP("Describes what my command does");
  sPixmap       = "some_svg_icon_from_my_resource";
}

void CmdMyCommand::activated(int iMsg)
{
    openCommand("My Command");
    doCommand(Doc,"print('Hello, world!')");
    commitCommand();
    updateActive();
}

bool CmdMyCommand::isActive(void)
{
  if( getActiveGuiDocument() )
    return true;
  else
    return false;
}

void CreateMyModuleCommands(void)
{
    Gui::CommandManager &rcCmdMgr = Gui::Application::Instance->commandManager();
    rcCmdMgr.addCommand(new CmdMyCommand());
}
```

## \"Compiling\" your resource file {#compiling_your_resource_file}

compileA2pResources.py from the A2Plus workbench:


```python#!/usr/bin/env python
# -*- coding: utf-8 -*-
#***************************************************************************
#*                                                                         *
#*   Copyright (c) 2019 kbwbe                                              *
#*                                                                         *
#*   Portions of code based on hamish's assembly 2                         *
#*                                                                         *
#*   This program is free software; you can redistribute it and/or modify  *
#*   it under the terms of the GNU Lesser General Public License (LGPL)    *
#*   as published by the Free Software Foundation; either version 2 of     *
#*   the License, or (at your option) any later version.                   *
#*   for detail see the LICENCE text file.                                 *
#*                                                                         *
#*   This program is distributed in the hope that it will be useful,       *
#*   but WITHOUT ANY WARRANTY; without even the implied warranty of        *
#*   MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the         *
#*   GNU Library General Public License for more details.                  *
#*                                                                         *
#*   You should have received a copy of the GNU Library General Public     *
#*   License along with this program; if not, write to the Free Software   *
#*   Foundation, Inc., 59 Temple Place, Suite 330, Boston, MA  02111-1307  *
#*   USA                                                                   *
#*                                                                         *
#***************************************************************************

# This script compiles the A2plus icons for py2 and py3
# For Linux only
# Start this file in A2plus main directory
# Make sure pyside-rcc is installed

import os, glob

qrc_filename = 'temp.qrc'
if os.path.exists(qrc_filename):
    os.remove(qrc_filename)

qrc = '''<RCC>
\t<qresource prefix="/">'''
for fn in glob.glob('./icons/*.svg'):
    qrc = qrc + '\n\t\t<file>%s</file>' % fn
qrc = qrc + '''\n\t</qresource>
</RCC>'''

print(qrc)

f = open(qrc_filename,'w')
f.write(qrc)
f.close()

os.system(
    'pyside-rcc -o a2p_Resources2.py {}'.format(qrc_filename))
os.system(
    'pyside-rcc -py3 -o a2p_Resources3.py {}'.format(qrc_filename))

os.remove(qrc_filename)
```

## Related

-   [Translating an external workbench](Translating_an_external_workbench.md)
-   [Namespaced Workbenches - discussion](https://forum.freecadweb.org/viewtopic.php?t=47460)
-   [freecad.workbench\_starterkit](https://github.com/FreeCAD/freecad.workbench_starterkit)





{{Powerdocnavi

}} 

[Category:Developer Documentation{{\#translation:}}](Category:Developer_Documentation.md) [Category:Python Code{{\#translation:}}](Category:Python_Code.md)