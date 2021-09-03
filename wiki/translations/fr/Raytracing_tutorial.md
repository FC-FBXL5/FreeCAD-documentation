

## Atelier Raytracing {#atelier_raytracing}


<div class="mw-translate-fuzzy">


{{VeryImportantMessage|L'[atelier Raytracing](Raytracing_Workbench/fr.md) a été remplacé par le nouvel [https://github.com/FreeCAD/FreeCAD-render atelier Render], qui est destiné à le remplacer. Il ne doit pas être confondu avec [Le module de rendus](Render_project.md), arrêté et dépassé. Le Render Workbench peut être installé via le [Gestionnaire d'Addon](Std_AddonMgr/fr.md). L'information ici est fournie parce que par défaut FreeCAD est toujours livré (à partir de 0.19-24276) avec l'atelier Raytracing et parce que le nouveau module devrait fondamentalement fonctionner de la même manière}}

.


</div>


{{TutorialInfo/fr
|Topic= Raytracing
|Level= Débutant
|Time= 10 minutes + Render time
|Author=[http://freecadweb.org/wiki/index.php?title=User:Drei Drei]
|FCVersion=0.16 et plus
|Files=
}}

## Introduction

Ce tutoriel est destiné à présenter au lecteur le fonctionnement de base de l\'atelier Raytracing, ainsi que la plupart des outils disponibles pour créer une image rendue. Remarquez que l\'atelier Raytracing est progressivement écarté au profit du nouveau [module de rendus](Render_project/fr.md), disponible via le [gestionnaire d\'Addons](Std_AddonMgr.md).

<img alt="" src=images/Raytracing_tutorial_result.png  style="width:480px;">

## Exigences

-   FreeCAD la version 0.16 ou au-dessus.
-   [POV-Ray](http://www.povray.org/) et/ou [LuxRender](https://luxcorerender.org/) est installé sur le système.
-   Dans le cas de POV-Ray, il ne suffit pas d\'avoir l\'exécutable binaire en place, cela ***demande*** aussi l\'installation des ***fichiers de support***. Dans Ubuntu, ceux-ci sont fournis par le paquet Recommends-flagged [povray-includes](https://packages.ubuntu.com/search?keywords=povray-includes). Des problèmes potentiels ont également été constatés lors d\'installations de Linux nécessitant la création manuelle de fichiers de configuration locaux dans le dossier personnel de l\'utilisateur, comme nous l\'avons vu [ici](https://forum.freecadweb.org/viewtopic.php?f=3&t=27548&start=10#p224576).
-   Dans le cas de POV-Ray, l\'installation de [macro de psicofil](https://github.com/psicofil/Macros_FreeCAD) est recommandée.
-   Le lecteur a les connaissances de base pour utiliser les ateliers Part et PartDesign.

## Procédure

### Modélisation

Dans cet exemple un Cube est utilisé comme l\'objet d\'étude, mais les modèles créés dans la Partie ou les Établis PartDesign peuvent être utilisés au lieu de cela.

1.  Créez un nouveau document
2.  Activez l\'Atelier Part Workbench
3.  Créez un Cube. Vous pouvez changer ses propriétés .

Maintenant nous avons un modèle pour travailler.

### La préparation pour {#la_préparation_pour}

1.  Se rendre à l\'Atelier de Raytracing.
2.  Changer votre vue pour Perspective allez à **View** et choisissez **Perspective**
3.  Mettre sur l\'outil de rendu. Allez au menu **Édit** et choisir **Préférences**
4.  Cliquez sur **Raytracing** et mettre l\'emplacement sur l\'adresse de l'exécutable.
5.  Mettre la taille de l\'image rendue. Allez sur **Édit** et choisir **Préférences**. Cliquez sur **Raytracing** et réglez l\'image à la taille désirée

#### POV-Ray {#pov_ray}

1.  Choisir <img alt="" src=images/Raytrace_New.svg  style="width:32px;"> [New PovRay project](Raytracing_New/fr.md). Dans le menu déroulant, choisir **RadiosityNormal**.

#### LuxRender

1.  Choisir <img alt="" src=images/Raytrace_Lux.svg  style="width:32px;"> [New LuxRender projetc](Raytracing_Lux/fr.md). Dans le menu déroulant, choisir **LuxClassic**.

### Mettre l\'appareil photo place {#mettre_lappareil_photo_place}

1.  Placer la *3D view* à l\'emplacement désiré et à la distance du mode Dans ce cas nous utiliserons **Axonométrique view**
2.  Choisir le Dossier de **Project folder** de **Tree view**
3.  Sélectioner <img alt="" src=images/Raytrace_ResetCamera.svg  style="width:32px;"> [Reset camera](Raytracing_ResetCamera/fr.md)

### Importer le modèle {#importer_le_modèle}

1.  Choisir le modèle pour rendu.
2.  Choisir <img alt="" src=images/Raytrace_NewPartSegment.svg  style="width:32px;"> [Insert](Raytracing_InsertPart/fr.md)

### Démarrer l\'Outil Render {#démarrer_loutil_render}

1.  Choisir <img alt="" src=images/Raytrace_Render.svg  style="width:32px;"> [Render](Raytracing_Render/fr.md).
2.  Entrer le chemin ou l\'image sera stockée.
3.  Attendre le rendu pour finir. Ceci peut prendre quelque temps.

### Voir le résultat {#voir_le_résultat}

FreeCAD ouvrira immédiatement l\'image après que le rendu soit fini.


<div class="mw-translate-fuzzy">

Nous avons terminé avec le travail de base pour le [Module Raytracing](Raytracing_Workbench/fr.md).


</div>


{{Tutorials navi

}} {{Raytracing Tools navi}} 