---
- GuiCommand:/pl
   Name:Part Fillet
   Name/pl:Część: Zaokrąglenie
   MenuLocation:Część → Zaokrąglenie ...
   Workbenches:[Część](Part_Workbench/pl.md), [Complete](Complete_Workbench/pl.md)
   SeeAlso:[Fazka](Part_Chamfer/pl.md)
---

## Opis

Narzędzie to tworzy łuk *(zaokrąglenie)* na wybranych krawędziach obiektu. Okno dialogowe pozwala wybrać, na których obiektach i na których krawędziach należy pracować.

## Użycie

-   Uruchom narzędzie z paska narzędzi Part lub z menu. Możesz wybrać obiekt przed lub po uruchomieniu narzędzia.
-   Jeśli kształt nie został wybrany przed uruchomieniem narzędzia, wybierz go z rozwijanej listy kształt w [panelu zadań](Task_panel/pl.md).
-   Wybierz typ zaokrąglenia, albo stały promień *(domyślnie)*, albo zmienny promień.
-   Wybierz krawędzie albo w oknie [widoku 3D](3D_view/pl.md), albo zaznaczając je na liście krawędzi w [panelu zadań](Task_panel/pl.md).
-   Ustaw wartość promienia.
-   Kliknij przycisk **OK**, aby zatwierdzić.

![](images/Dialog-fillet.png )

## Zaokrąglenie w środowisku Część kontra Zaokrąglenie w środowisku Projekt Części {#zaokrąglenie_w_środowisku_część_kontra_zaokrąglenie_w_środowisku_projekt_części}

W środowisku pracy <img alt="" src=images/Workbench_PartDesign.svg  style="width:24px;"> [Projekt Części](PartDesign_Workbench/pl.md) znajduje się inne narzędzie do tworzenia zaokrągleń. Należy pamiętać, że ich działanie jest zupełnie inne. Sprawdź stronę <img alt="" src=images/PartDesign_Fillet.svg  style="width:24px;"> [Projekt Części: Zaokrąglenie](PartDesign_Fillet/pl.md) zawierającą więcej szczegółów na temat różnic między nimi.

## Uwagi dotyczące stosowania funkcji zaokrąglenia w Środowisku Part {#uwagi_dotyczące_stosowania_funkcji_zaokrąglenia_w_środowisku_part}

Part Filet może nie zrobić nic, jeśli wynikiem będzie dotknięcie lub przekroczenie następnej przyległej krawędzi. Jeśli więc nie otrzymasz oczekiwanego wyniku, spróbuj z mniejszą wartością. To samo dotyczy <img alt="" src=images/Part_Chamfer.svg  style="width:24px;"> [fazek](Part_Chamfer/pl.md).

Narzędzie do zaokrąglania czasem zawodzi przy próbie zaokrąglenia złożonych obiektów. Częstą przyczyną może być to, że kształt, który jest poddawany operacjom zaokrąglania nie jest geometrycznie poprawny. Może to wynikać z nieusunięcia linii/płaszczyzn itp. po wcześniejszych operacjach użytych do skonstruowania kształtu *(np. Wytnij/Przeciągnij/Fuzja)*. W celu zminimalizowania problemów można zastosować kilka kroków:

-   Tam, gdzie to możliwe, pozostawić wypełnianie części do czasu, aż część zostanie całkowicie wygenerowana. Zminimalizuje to interakcję pomiędzy operacjami zaokrąglania a kolejnymi operacjami logicznymi.
-   Użyj polecenia {{MenuCommand|Część → Sprawdź geometrię}}, aby sprawdzić, czy geometria kształtu nie zawiera błędów i skorygować ją.
-   Użyj polecenia {{MenuCommand|Część → Udoskonal kształt}} aby usunąć wszelkie artefakty wprowadzone przez poprzednie operacje logiczne przed wypełnieniem *(a w niektórych przypadkach pomiędzy kolejnymi operacjami wypełniania)*.
-   Rozważyć zastosowanie funkcji {{MenuCommand|Edycja → Preferencje → Projektowanie części → Automatycznie ...}}, aby umożliwić automatyczne sprawdzanie i udoskonalanie modelu po operacjach logicznych i szkicowych \'(wydajność może ulec zmianie, jeśli opcje te pozostaną włączone)\'\'.

Zwróć również uwagę, że na funkcję zaokrąglania części wpływa [Topologiczny problem nazewnictwa](Topological_naming_problem/pl.md), gdy jakakolwiek zmiana jest dokonywana na wcześniejszym etapie modelowania w łańcuchu, który wpływa na liczbę powierzchni lub wierzchołków. Może to spowodować nieprzewidywalny rezultat. Do czasu rozwiązania tego problemu *(prawdopodobnie z v0.19)* zaleca się stosowanie operacji Fazowania i [Zaokrąglania](Part_Fillet/pl.md) na ostatnich etapach łańcucha.





  