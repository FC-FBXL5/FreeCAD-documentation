---
- GuiCommand:/pl
   Name:Sketcher ConstrainVertical
   Name/pl:Wiązanie pionowe
   MenuLocation:Szkic → Wiązania szkicownika → Wiązanie pionowe
   Workbenches:[Szkicownik](Sketcher_Workbench/pl.md)
   Shortcut:**V**
   SeeAlso:[Szkicownik: Wiązanie poziome](Sketcher_ConstrainHorizontal/pl.md)
---

# Sketcher ConstrainVertical/pl

## Opis

Tworzy wiązanie pionowe dla wybranych linii lub elementów polilinii. Zaczynając od wersji {{VersionPlus/pl|0.17}} może również ograniczać wierzchołki w pionie. Można wybrać więcej niż jeden obiekt.

## Użycie

1.  Wybierz linie lub wierzchołki, które mają być związane w pionie
2.  Aby uruchomić komendę wiązania pionowego:
    -   Naciśnij przycisk **[<img src=images/Sketcher_ConstrainVertical.svg style="width:16px"> [Wiązanie pionowe](Sketcher_ConstrainVertical/pl.md)**.
    -   Użyj skrótu na klawiaturze **V**.
    -   Użyj pozycji **Sketch → Wiązania szkicownika → [<img src=images/Sketcher_ConstrainVertical.svg style="width:16px"> Wiązanie pionowe** , znajdującej się w menu rozwijanym Szkicu
3.  Alternatywnie, narzędzie może być uruchomione bez wcześniejszego zaznaczenia i będzie oczekiwało zaznaczenia.
4.  Kliknij prawym przyciskiem myszy, lub wciśnij raz klawisz **Esc** aby zakończyć działanie narzędzia.

## Tworzenie skryptów 


```pythonSketch.addConstraint(Sketcher.Constraint('Vertical', Line))```

Strona [skrypty szkicownika](Sketcher_scripting/pl.md) wyjaśnia wartości, których można użyć dla `Line` oraz zawiera dalsze przykłady tworzenia wiązań przy użyciu skryptów języka Python.





{{Sketcher_Tools_navi

}}



---
![](images/Right_arrow.png) [documentation index](../README.md) > [Sketcher](Sketcher_Workbench.md) > Sketcher ConstrainVertical/pl
