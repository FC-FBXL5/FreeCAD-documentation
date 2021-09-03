---
- GuiCommand:/fr
   Name:Path 3DSurface
   Name/fr:Path Surface 3D
   MenuLocation:Path → 3D Surface
   Workbenches:[Path](Path_Workbench/fr.md)
   Shortcut:
   Version:0.19
   SeeAlso:
---


</div>

## Description

Cet outil crée une nouvelle opération **<img src="images/Path_3DSurface.svg" width=24px> [Surface 3D](Path_3DSurface/fr.md)** qui est capable de générer des trajectoires G-Code pour toute la surface supérieure d\'un modèle 3D (ou est capable de travailler avec des faces sélectionnées) et permet d\'éviter les faces. Cette opération offre plusieurs motifs de coupe: ligne, zigzag, circulaire, zigzag circulaire, décalage et spirale (similaire à un motif adaptatif). Depuis la version 0.19, cette opération propose de nombreuses personnalisations pour permettre une plus grande productivité.

L\'opération **<img src="images/Path_3DSurface.svg" width=24px> [Surface 3D](Path_3DSurface/fr.md)** est également capable de générer des trajectoires de surfaçage 3D de base. Les capacités de rotation sont limitées à l\'ensemble du modèle et ne permettent pas d\'isoler des faces ou des régions spécifiques. Les trajectoires de rotation sont également limités aux motifs de coupe de ligne.

L\'outil 3D Surface s\'interface avec OCL.pyd, un module Open Source tiers intitulé [OpenCamLib](OpenCamLib/fr.md) qui génère des chemins d\'outil à partir d\'un modèle 3D. OpenCamLib n\'est pas directement intégré à FreeCAD.

**Remarque:** pour utiliser l\'opération Surface 3D, vous devez:

1.  Installer correctement [OpenCamLib](OpenCamLib/fr.md).
2.  Activez [Fonctions expérimentales](Path_experimental/fr.md) de l\'atelier Path.
3.  Vérifiez {{MenuCommand|Édition → Préférences... → Path → Advanced → Enable OCL dependent features}}.

## Utilisation

Les instructions d\'utilisation pour plusieurs variantes de [Surface 3D](Path_3DSurface/fr.md) sont présentées ici.

#### Opération de base {#opération_de_base}

1.  Appuyez sur l\'icône **<img src="images/Path_3DSurface.svg" width=24px> [3D Surface](Path_3DSurface/fr.md)** ou sélectionnez {{MenuCommand|Path → Surface 3D}} dans le menu déroulant.
2.  Sélectionnez le contrôleur d\'outil pour l\'opération dans la fenêtre contextuelle de la boîte de dialogue Contrôleur d\'outil, le cas échéant.
3.  Dans l\'onglet Géométrie de base, sélectionnez les faces spécifiques sur lesquelles vous souhaitez vous concentrer et/ou éviter pour l\'opération.
4.  Ajustez les profondeurs d\'opération selon vos besoins dans l\'onglet Profondeurs: Profondeur de départ, Profondeur de finition, Descente.
5.  Faites des ajustements dans l\'onglet Hauteurs si nécessaire.
6.  Configurez les paramètres dans l\'onglet Opérations si nécessaire:
    -   Choisissez votre mode de refroidissement.
    -   Choisissez la BoundBox: Stock ou BaseBoundBox
    -   Définissez le type de scan pour l\'opération: planaire ou rotationnel
    -   Sélectionnez le mode de calque pour l\'opération: passe unique ou passe multiple
        1.  Un seul passage est pour une passe finale
        2.  Multi-pass peut être utilisé pour le dégagement en combinaison avec l\'utilisation du décalage de profondeur pour laisser une couche de surface mince pour une passe de finition
    -   Ajoutez un décalage supplémentaire BoundBox supplémentaire à X et Y comme vous le souhaitez (*Rotational scans only*)
    -   Réglez la direction du Drop Cutter: X ou Y. Il s\'agit de la direction linéaire dans laquelle la fraise (broche) se déplacera. (*Rotational scans only*)
    -   Ajoutez une valeur de décalage de profondeur si vous souhaitez laisser une épaisseur de matériau spécifiée sur la surface, par exemple une passe de finition finale
    -   Définissez l\'intervalle d\'échantillonnage utilisé pour l\'analyse OCL.
    -   Définissez la valeur Step Over en pourcentage du diamètre de l\'outil.
    -   Cochez la case Utiliser le point de départ si vous souhaitez fournir un point de départ pour l\'opération dans la vue des propriétés de l\'onglet de données de l\'opération.
    -   L\'application des limites est activée par défaut. Cela force l\'outil de coupe à rester à l\'intérieur des limites de la géométrie de l\'entité pour l\'opération, comme une opération d\'empoquetage. Désactivez cette option pour permettre au couteau de s\'étendre vers l\'extérieur de la géométrie de l\'entité. La propriété Ajustement des limites remplace cette propriété.
    -   L\'optimisation des trajectoires linéaires est activée par défaut. La désactivation donnera un résultat gcode plus long et augmentera probablement le temps de découpe.
7.  Si vous souhaitez prévisualiser le résultat avant d\'accepter les paramètres, cliquez sur **Apply**
8.  Cliquez sur le bouton **OK** pour confirmer et générer des chemins.

Pour obtenir des effets différents ou plus complexes, définissez des propriétés d\'opération supplémentaires dans l\'onglet Données de la vue Propriétés pour l\'opération.

#### Balayages rotationnels (4ème axe) {#balayages_rotationnels_4ème_axe}

1.  Lancez une [Opération de base](#Op.C3.A9ration_de_base.md) comme décrit ci-dessus et définissez le **Scan Type** à **Rotational**.
2.  **Remarque:** La sélection de face n\'est pas disponible pour les scans rotationnels, les modifications apportées à la géométrie de base sont donc ignorées.
3.  Localisez l\'onglet Données et la vue Propriétés pour la nouvelle opération [Surface 3D](Path_3DSurface/fr.md). Une section **Rotation** devrait être disponible avec des propriétés supplémentaires à ajuster, listées ci-dessous.
    Il est recommandé de définir toutes les propriétés de rotation souhaitées en une seule fois avant de recalculer. Pour ce faire, cliquez sur la touche ENTRÉE immédiatement après avoir modifié un paramètre de propriété. Ce processus vous permettra de modifier et d\'enregistrer plusieurs propriétés avant de recalculer l\'opération.
4.  Ajustez les paramètres suivants selon vos besoins:
    -   Définissez {{PropertyData/fr|Cutter Tilt}} sur l\'index de décalage (angle) \[0-90\]. (Utilisé pour les fraises à boulets)
    -   Remplacez {{PropertyData/fr|Drop Cutter Dir}} par l\'axe de déplacement de la fraise (broche).
    -   Modifiez {{PropertyData/fr|Drop Cutter Extra Offset}} pour étendre le BoundBox dans les directions X et Y.
    -   Définissez {{PropertyData/fr|Rotation Axis}} sur l\'axe souhaité.
    -   Ajustez {{PropertyData/fr|Start Index}} pour démarrer l\'index (angle) \[0-360\].
    -   Ajustez {{PropertyData/fr|Stop Index}} pour arrêter l\'index (angle) \[0-360\].
5.  Cliquez sur l\'icône **<img src=images/_View-refresh.svg style="width:16px"> Recompute** dans la barre d\'outils.
6.  Attendez les résultats \...

##### Notes About Rotational Scans {#notes_about_rotational_scans}


<div class="mw-translate-fuzzy">

##### Remarques sur les balayages rotationnels {#remarques_sur_les_balayages_rotationnels}

-   Les balayages **Rotationnels** nécessitent beaucoup plus de temps et de traitement que les balayages **Planaires**. Les facteurs ayant une incidence sur le temps de traitement comprennent: l\'intervalle d\'échantillonnage, l\'interpolation, le diamètre de l\'outil et la taille du modèle. Encore une fois, les analyses en rotation peuvent prendre beaucoup de temps. Certains peuvent prendre 3, 5 ou 10 minutes ou plus.
-   Pour des raisons de temps, il est préférable de ne pas recalculer un balayage rotationnel après chaque changement de propriété. considérez plutôt l'un des éléments suivants:
    -   utilisez la technique **pour modifier tous les paramètres avec la touche ENTREE** mentionnée à l\'étape 2 ci-dessus puis l\'opération **<img src=images/View-refresh.svg style="width:16px"> Recompute**.
    -   désactiver l\'opération avec l\'outil **<img src="images/Path_OpActiveToggle.svg" width=16px> [Activation d'opération](Path_OpActiveToggle/fr.md)**, apportez vos modifications aux propriétés de l\'opération, puis cliquez sur le **<img src="images/Path_OpActiveToggle.svg" width=16px> [Activation d'opération](Path_OpActiveToggle/fr.md)** à nouveau pour réactiver l\'opération, ce qui déclenche un recalcul en interne.
-   L\'opération **<img src="images/Path_3DSurface.png" width=16px> [Surface 3D](Path_3DSurface/fr.md)** est toujours considérée comme une \"fonctionnalité expérimentale\" au 25/06/2019. En tant que tel, elle peut contenir quelques bugs qui doivent encore être clairement identifiés. Veuillez signaler les bogues et les problèmes sur le [FreeCAD Path/CAM Forum](https://forum.freecadweb.org/viewforum.php?f=15).
-   Le **<img src="images/Path_Simulator.svg" width=16px> [Path Simulateur d'usinage](Path_Simulator/fr.md)** intégré ne prend pas en charge la simulation du 4ème axe. Vous devrez utiliser un simulateur tiers pour inspecter ou vérifier visuellement les chemins. Voir la section [Ressources](#Ressources.md) ci-dessous pour des suggestions.
-   Vous verrez probablement des lignes de rotation rouges autour de votre modèle dans la fenêtre. C\'est normal dans FreeCAD pour le moment.

#### Outils de découpe disponibles {#outils_de_découpe_disponibles}

Cette opération 3D Surface utilise actuellement \[OCL/fr\|OCL\] de [OpenCamLib](OpenCamLib/fr.md) pour extraire les chemins de la base de la pièce. En tant que tel, une traduction des paramètres d'outil est nécessaire entre le contrôleur d'outil FreeCAD et OCL afin de compléter l'analyse avec la forme de l'outil (outil de coupe) choisi.


</div>

##### Notes About Scans of complex models {#notes_about_scans_of_complex_models}

Excessively long processing times (longer than 10 minutes) can occur when processing large complex models. In addition to the factors already mentioned the following steps could help identify potential causes and solutions.

***Low Memory***
Check how much memory is available while the scan is running using a tool such as the Windows **Task Manager, Memory tab**. If more than 90% of memory is consistently being used then a small **Linear Deflection** parameter could be generating a mesh that is too large for the available memory.
To confirm this \...

1.  Create a new **<img src="images/Path_3DSurface.svg" width=24px> [3D Surface](Path_3DSurface.md)** operation.
2.  Switch to the Model tab and increase the **Linear Deflection** value. For example change from 2.5um to 20um
3.  Switch back to the Tasks tab to complete setting up the operation.
4.  Click **OK** button to confirm and generate paths.

To make this value the default for all new **<img src="images/Path_3DSurface.svg" width=24px> [3D Surface](Path_3DSurface.md)** operations, change the **GeometryTolerance** parameter.
{{MenuCommand|Tools → Edit Parameters ... → Preferences → Mod → Path → GeometryTolerance }}.
Note as of version 0.19 the **Linear Deflection** default = GeometryTolerance / 4

***Invalid Geometry***
If a model contains invalid geometry the scanning time can increase significantly. A model can be checked using the **Check Geometry** function in <img alt="" src=images/Workbench_Part.svg  style="width:24px;">**Part Workbench**.
To run the tool:

1.  Switch to the <img alt="" src=images/Workbench_Part.svg  style="width:24px;">**Part Workbench** and select the model to check
2.  Click on the **<img src="images/Part_CheckGeometry.svg" width=16px>** button available in the Part workbench toolbar OR use the {{MenuCommand|Part → <img src="images/Part_CheckGeometry.svg" width=16px> Check geometry}} entry from the top menu.
3.  Click the **Run Check** button and review the results.

If the results includes items like *BOPAlgo SelfIntersect* then the geometry is invalid and should be corrected by adjusting the model.
(Hint: Boolean operations and Loft commands can sometimes introduce *Self Intersections*)

#### Available Tool (Cutter) Shapes {#available_tool_cutter_shapes}

This 3D Surface op currently uses [OpenCamLib](OpenCamLib.md) \[OCL\|OCL\] to extract paths from the part base. As such, a tool setting translation is required between the FreeCAD tool controller and OCL in order to complete the scan with your chosen tool(cutter) shape.

Ces formes d'outils sont respectées et disponibles pour cette opération 3D Surface:


<div class="mw-translate-fuzzy">

-   Fraise à queue
-   Fraise hémisphérique
-   Fraise à tête cylindrique
-   Fraise à chanfreiner
-   Graveur


</div>


<div class="mw-translate-fuzzy">

Si vous choisissez d\'exécuter le simulateur de trajectoire dans l\'atelier Path, il utilise uniquement la fraise de bout standard pour simuler des trajectoires. Par conséquent, vous ne verrez pas l'enlèvement de matière spécifique à une forme d'outil. L\'enlèvement de matière est illustré à l\'aide de la forme de la fraise.

REMARQUE: à compter de mai 2019, seule la fraise en bout dispose d\'un type de test permettant de déterminer l\'exactitude de la traduction des paramètres de l\'outil FreeCAD-OCL. Veuillez poster tout commentaire concernant une utilisation autre que l'usine finale dans la section [Path/CAM](https://forum.freecadweb.org/viewforum.php?f=15) des forums FreeCAD.


</div>

NOTE: As of May 2019, only the End Mill has any type of testing to determine accuracy of the FreeCAD-to-OCL tool settings translation. Please post any feedback for non-end-mill usage to the [Path/CAM](https://forum.freecadweb.org/viewforum.php?f=15) section in the FreeCAD forums.

## Propriétés: Version 0.19 {#propriétés_version_0.19}

\'\'\' *Remarque* \'\'\': toutes ces propriétés ne sont pas disponibles dans l\'éditeur de fenêtre de tâches. Certaines ne sont accessibles que dans l\'onglet Données du panneau Vue de propriétés pour cette opération.

#### Base

Remarque: il est conseillé de ne pas modifier la propriété Placement des opérations de chemin. Déplacez ou faites pivoter le modèle de tâche de chemin selon vos besoins.

-    {{PropertyData/fr|Placement}}: emplacement global \[position et rotation\] de l\'objet - par rapport à l\'origine (ou à l\'origine du conteneur de l\'objet parent).

    -   
        {{PropertyData/fr|Angle}}
        
        : angle en degrés appliqué à la rotation de l\'objet autour de la valeur de la propriété Axis.

    -   
        {{PropertyData/fr|Axis}}
        
        : axe (un ou plusieurs) autour duquel faire pivoter l\'objet, défini dans les sous-propriétés: x, y, z.

        -   
            {{PropertyData/fr|X}}
            
            : valeur de l\'axe x.

        -   
            {{PropertyData/fr|Y}}
            
            : valeur de l\'axe y.

        -   
            {{PropertyData/fr|Z}}
            
            : valeur de l\'axe z.

    -   
        {{PropertyData/fr|Position}}
        
        : position de l\'objet, définie dans les sous-propriétés: x, y, z - par rapport à l\'origine (ou à l\'origine du conteneur de l\'objet parent).

        -   
            {{PropertyData/fr|X}}
            
            : valeur de distance x.

        -   
            {{PropertyData/fr|Y}}
            
            : valeur de distance y.

        -   
            {{PropertyData/fr|Z}}
            
            : valeur de distance z.

-    {{PropertyData/fr|Label}}: nom de l\'objet fourni par l\'utilisateur (UTF-8).

#### Options d\'évitement {#options_dévitement}

-    {{PropertyData/fr|Bound Box}}: si l\'opération est limitée par l\'objet stock ou par le cadre englobant de l\'objet de base

-    {{PropertyData/fr|Cut Mode}}: la direction dans laquelle le parcours d\'outil doit aller autour de la pièce: Climb (sens horaire) ou Conventionnel (anti sens horaire)

-    {{PropertyData/fr|Cut Pattern}}: motif d\'effacement à utiliser

-    {{PropertyData/fr|Cut Pattern Reversed}}: inverse l\'ordre de coupe des trajectoires pas à pas. Pour les motifs de coupe circulaire, commencez par l\'extérieur et travaillez vers le centre

-    {{PropertyData/fr|Depth Offset}}: décalage de l\'axe Z par rapport à la surface de l\'objet

-    {{PropertyData/fr|Layer Mode}}: le mode de complétion de l\'opération: simple ou multi-passes

-    {{PropertyData/fr|Pattern Center At}}: choisissez l\'emplacement du point central pour commencer le motif de coupe

-    {{PropertyData/fr|Pattern Center Custom}}: définit le point de départ du motif de coupe

-    {{PropertyData/fr|Profile Edges}}: profiler les bords de la sélection

-    {{PropertyData/fr|Sample Interval}}: l\'intervalle d\'échantillonnage. Les petites valeurs entraînent de longs temps d\'attente

-    {{PropertyData/fr|Step Over}}: pourcentage de dépassement du chemin de coupe-goutte

#### Profondeur

-    {{PropertyData/fr|Clearance Height}}: hauteur nécessaire pour éviter les pinces et les obstructions.

-    {{PropertyData/fr|Final Depth}}: profondeur finale de l\'outil - valeur la plus basse de Z.

-    {{PropertyData/fr|Safe Height}}: seuil supérieur duquel les mouvements rapides sont autorisés.

-    {{PropertyData/fr|Start Depth}}: profondeur initiale de l\'outil - première profondeur de coupe en Z.

-    {{PropertyData/fr|Step Down}}: abaissement incrémentiel de l\'outil.

#### Conversion en maillage {#conversion_en_maillage}


<div class="mw-translate-fuzzy">

-    {{PropertyData/fr|Angular Deflection}}: des valeurs plus petites donnent un maillage plus fin et plus précis. Des valeurs plus petites augmentent beaucoup le temps de traitement

-    {{PropertyData/fr|Linear Deflection}}: des valeurs plus petites donnent un maillage plus fin et plus précis. Des valeurs plus petites n\'augmentent pas beaucoup le temps de traitement


</div>

#### Optimisation

-    {{PropertyData/fr|Circular Use G2 G3}}: Convertissez les arcs coplanaires en commandes gcode G2/G3 pour les motifs de coupe \Circular\ et\ CircularZigZag\

-    {{PropertyData/fr|Gap Sizes}}: Commentaires: trois plus petites lacunes identifiées dans la géométrie de la trajectoire

-    {{PropertyData/fr|Gap Threshold}}: les espaces d\'artefacts colinéaires et co-radiaux qui sont plus petits que ce seuil sont fermés dans la trajectoire

-    {{PropertyData/fr|Optimiser les chemins linéaires}}: active l\'optimisation des trajectoires linéaires (points colinéaires). Supprime les points colinéaires inutiles de la sortie G-Code

-    {{PropertyData/fr|Optimize Step Over Transitions}}: permet une optimisation distincte des transitions entre chaque étape sur la trajectoire

#### Tracé

-    {{PropertyData/fr|Active}}: mettre à False pour empêcher l\'opération de générer du code.

-    {{PropertyData/fr|Base}}: géométrie de base pour cette opération.

-    {{PropertyData/fr|Comment}}: commentaire facultatif pour cette opération.

-    {{PropertyData/fr|Coolant Mode}}: mode de refroidissement pour cette opération.

-    **Cycle Time**: estimation du temps de cycle pour cette opération.

-    {{PropertyData/fr|Tool Controller}}: définit le contrôleur d\'outil utilisé dans l\'opération.

-    {{PropertyData/fr|User Label}}: étiquette attribuée par l\'utilisateur.

#### Rotation

-    {{PropertyData/fr|Cutter Tilt}}: définit l\'angle d\'inclinaison de la fraise (broche).

-    {{PropertyData/fr|Drop Cutter Dir}}: direction le long de laquelle les lignes de dropcutter sont créées

-    {{PropertyData/fr|Drop Cutter Extra Offset}}: décalage supplémentaire par rapport au cadre de sélection sélectionné - utilisez des sous-propriétés pour définir les valeurs

    -   
        {{PropertyData/fr|X}}
        
        : valeur de distance x

    -   
        {{PropertyData/fr|Y}}
        
        : valeur de distance y

    -   
        {{PropertyData/fr|Z}}
        
        : valeur de distance z

-    {{PropertyData/fr|Rotation Axis}}: définit l\'axe de rotation du modèle.

-    {{PropertyData/fr|Start Index}}: index de départ (angle) pour la rotation

-    {{PropertyData/fr|Stop Index}}: index d\'arrêt (angle) pour la rotation

#### Paramètres de géométrie sélectionnés {#paramètres_de_géométrie_sélectionnés}

-    {{PropertyData/fr|Avoid Last X Faces}}: évite de couper les \"N\" dernières faces dans la liste Géométrie de base des faces sélectionnées

-    {{PropertyData/fr|Avoid Last X Internal Features}}: ne pas couper les fonctionnalités internes sur les faces évitées

-    {{PropertyData/fr|Boundary Adjustment}}: des valeurs positives poussent l\'outil de coupe vers ou au-delà de la limite. Les valeurs négatives éloignent la fraise de la limite

-    {{PropertyData/fr|Boundary Enforcement}}: si true, l\'outil de découpe restera à l\'intérieur des limites du modèle ou des faces sélectionnées

-    {{PropertyData/fr|Handle Multiple Features}}: choisissez comment traiter plusieurs entités de géométrie de base

-    {{PropertyData/fr|Internal Features Adjustment}}: les valeurs positives poussent l\'outil de coupe vers ou dans l\'entité. Les valeurs négatives retirent l\'outil de coupe de la fonction

-    {{PropertyData/fr|Internal Features Cut}}: coupe des zones de fonction internes dans une face sélectionnée plus grande

#### Point de départ {#point_de_départ}

-    {{PropertyData/fr|Start Point}}: point de départ personnalisé pour la trajectoire de cette opération, défini dans les sous-propriétés: x, y, z

    -   
        {{PropertyData/fr|X}}
        
        : valeur de l\'axe x

    -   
        {{PropertyData/fr|Y}}
        
        : valeur de l\'axe y

    -   
        {{PropertyData/fr|Z}}
        
        : valeur de l\'axe z

-    {{PropertyData/fr|Use Start Point}}: mis à True, si vous spécifiez un point de départ

#### Surface

-    {{PropertyData/fr|Scan Type}}: Planaire: scan de surface plane en 3D. Rotationnel: balayage rotationnel 4ème axe.

#### Déchets

-    {{PropertyData/fr|Ignore Waste}}: ignore les zones situées en dessous de la profondeur spécifiée.

-    {{PropertyData/fr|Ignore Waste Depth}}: profondeur utilisée pour identifier les zones de déchets à ignorer.

-    {{PropertyData/fr|Release From Waste}}: coupe les déchets jusqu\'à la profondeur sur le bord du modèle, ce qui libère le modèle.

## Tasks Window Editor Layout {#tasks_window_editor_layout}


<div class="mw-translate-fuzzy">

## Disposition de l\'éditeur de fenêtre de tâches {#disposition_de_léditeur_de_fenêtre_de_tâches}

*Les descriptions des paramètres sont fournies dans la liste des propriétés ci-dessus.* Cette section est simplement une représentation des paramètres de l'éditeur de fenêtres pour l'opération.


</div>

##### Localisation de la base {#localisation_de_la_base}

-   **Base Geometry import selection**: utilisez cette liste pour sélectionner la géométrie de base à importer à partir de l\'opération existante sélectionnée
-   **Import**: importe la géométrie de base de l\'opération sélectionnée dans la liste des géométries de base des opérations courantes
-   **Base Geometry list for current operation**: liste des géométries de base pour l\'opération en cours, le cas échéant
-   **Add**: ajoute le ou les éléments sélectionnés qui devraient être la (les) base(s) du (des) trajectoire(s)
-   **Remove**: supprimez les éléments sélectionnés dans la liste Base Location
-   **Edit**: efface tous les éléments de la liste Base Location

#### Profondeur {#profondeur_1}

-    {{PropertyData/fr|Start Depth}}
    

-    {{PropertyData/fr|Final Depth}}
    

-    {{PropertyData/fr|Step Down}}
    

#### Hauteur

-    {{PropertyData/fr|Safe Height}}
    

-    {{PropertyData/fr|Clearance Height}}
    

#### Opération

-    {{PropertyData/fr|Tool Controller}}
    

-    {{PropertyData/fr|Coolant Mode}}
    

-    {{PropertyData/fr|BoundBox}}
    

-    {{PropertyData/fr|Scan Type}}
    

-    {{PropertyData/fr|Layer Mode}}
    

-    {{PropertyData/fr|BoundBox extra offset X}}
    

-    {{PropertyData/fr|BoundBox extra offset Y}}
    

-    {{PropertyData/fr|Drop Cutter Direction}}
    

-    {{PropertyData/fr|Depth Offset}}
    

-    {{PropertyData/fr|Step Over}}
    

-    {{PropertyData/fr|Sample Interval}}
    

-    {{PropertyData/fr|Optimize Output Enabled}}
    

-    {{PropertyData/fr|Use Start Point}}
    

-    {{PropertyData/fr|Boundary Enforcement}}
    

-    {{PropertyData/fr|Optimize Linear Paths}}
    

## Ressources

-   simulateur G-code(tracé): [NCViewer](https://ncviewer.com/)
-   simulateur G-code(tracé): [CAMotics](https://www.camotics.org/)


<div class="mw-translate-fuzzy">





</div>


{{Path Tools navi

}} 