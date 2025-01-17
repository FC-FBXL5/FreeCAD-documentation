---
- GuiCommand:/fr
   Name:Draft Fillet
   Name/fr:Draft Congé
   MenuLocation:Draft → Congé
   Workbenches:[Draft](Draft_Workbench/fr.md), [Arch](Arch_Workbench/fr.md)
   Shortcut:**F** **I**
   Version:0.19
   SeeAlso:[Draft Ligne](Draft_Line/fr.md), [Draft Polyligne](Draft_Wire/fr.md)
---

# Draft Fillet/fr

## Description

La commande <img alt="" src=images/Draft_Fillet.svg  style="width:24px;"> **Draft Congé** crée un congé, un coin arrondi ou un chanfrein, un bord droit entre deux [Draft Lignes](Draft_Line/fr.md).

<img alt="" src=images/Draft_Fillet_example.png  style="width:400px;"> 
*Plusieurs congés et chanfreins créés entre deux lignes*

## Utilisation

1.  Sélectionnez deux [Draft Lignes](Draft_Line/fr.md) qui se rejoignent en un seul point.
2.  Il y a plusieurs façons de lancer la commande :
    -   Appuyez sur le **<img src="images/Draft_Fillet.svg" width=16px> [Congé](Draft_Fillet/fr.md)**.
    -   Sélectionnez l\'option **Draft → <img src="images/Draft_Fillet.svg" width=16px> Congé** dans le menu.
    -   Utilisez le raccourci clavier : **F** puis **I**.
3.  Saisissez le **Rayon du congé**. Si l\'option **Créer un chanfrein** est sélectionnée, ce sera la taille du chanfrein (la longueur de la règle). Notez que la commande n\'aboutira pas si le rayon ou la taille du chanfrein est trop grand pour les lignes sélectionnées.
4.  Vérifiez éventuellement l\'option **Supprimer les objets originaux**.
5.  Vérifiez éventuellement l\'option **Créer un chanfrein**.
6.  Si vous avez sélectionné l\'une des deux options précédentes : Cliquez dans le champ de saisie **Rayon du congé**.
7.  Appuyez sur **Entrée**.

## Options

-   Appuyez sur **Echap** ou sur le bouton **Fermer** pour annuler la commande.

## Remarques

-   Un Draft Congé ne peut pas être édité et n\'est pas lié aux lignes qui ont été utilisées pour le créer.
-   Seules les Draft Lignes, c\'est-à-dire les [Draft Polylignes](Draft_Wire/fr.md) avec seulement deux points sont supportés pour le moment.
-   Une [Draft Polyligne](Draft_Wire/fr.md) qui a au moins trois points peut recevoir un congé ou être chanfreinée en modifiant respectivement sa **Fillet Radius** ou **Chamfer Size**. Le fait que les [Draft Lignes](Draft_Line/fr.md) et [Draft Polylignes](Draft_Wire/fr.md) puissent être jointes avec les commandes [Draft Polylignes](Draft_Wire/fr.md), [Draft Joindre](Draft_Join/fr.md) ou [Draft Agréger](Draft_Upgrade/fr.md), nous avons ici une méthode alternative pour créer des filets et des chanfreins.

## Propriétés

Voir aussi : [Éditeur de propriétés](Property_editor/fr.md)

Un objet Draft Congé est dérivé d\'un [Part Part2DObject](Part_Part2DObject/fr.md) et hérite de toutes ses propriétés. Il possède également les propriétés supplémentaires suivantes :

### Données


{{TitleProperty|Draft}}

-    **End|VectorDistance**: (en lecture seule) spécifie le dernier point du congé.

-    **Fillet Radius|Length**: (en lecture seule) rayon avec lequel le congé a été créé.

-    **Length|Length**: (en lecture seule) spécifie la longueur totale du congé.

-    **Start|VectorDistance**: (lecture seule) spécifie le point de départ du congé.

### Vue


{{TitleProperty|Draft}}

-    **Arrow Size|Length**: spécifie la taille du symbole affiché à la fin du filet.

-    **Arrow Type|Enumeration**: spécifie le type de symbole affiché à la fin du filet qui peut être {{value|Dot}}, {{value|Circle}}, {{value|Arrow}}, {{value|Tick}} ou {{value|Tick-2}}.

-    **End Arrow|Bool**: spécifie s\'il faut afficher un symbole à la fin du congé, afin qu\'il puisse être utilisé comme ligne d\'annotation.

-    **Pattern|Enumeration**: non utilisé.

-    **Pattern Size|Float**: non utilisé.

## Script

Voir aussi : [Autogenerated API documentation](https://freecad.github.io/SourceDoc/) et [FreeCAD Débuter avec les scripts](FreeCAD_Scripting_Basics/fr.md).

Pour créer un Draft Congé, utilisez la méthode `make_fillet` du module Draft :


```python
fillet = make_fillet([line1, line2], radius=100, chamfer=False, delete=False)
```

-   Crée un objet `Congé` entre les lignes `ligne1` et `ligne2`, en utilisant le `rayon` pour la courbure.
-   Si le `chanfrein` est `True`, il créera une arête droite de la longueur du `rayon`, au lieu d\'un arête arrondie.
-   Si `delete` est `True`, il supprimera les `ligne1` et `ligne2` données, et ne laissera que le nouvel objet.

Exemple :


```python
import FreeCAD as App
import Draft

doc = App.newDocument()

p1 = App.Vector(0, 0, 0)
p2 = App.Vector(1000, 1000, 0)
p3 = App.Vector(2000, 0, 0)

line1 = Draft.make_line(p1, p2)
line2 = Draft.make_line(p2, p3)

doc.recompute()

fillet = Draft.make_fillet([line1, line2], radius=500)

doc.recompute()
```



---
![](images/Right_arrow.png) [documentation index](../README.md) > [Draft](Draft_Workbench.md) > Draft Fillet/fr
