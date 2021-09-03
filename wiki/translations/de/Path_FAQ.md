

## Häufig gestellte Fragen Pfad Arbeitsbereich {#häufig_gestellte_fragen_pfad_arbeitsbereich}

## Wie viele Achsen kann der Pfad Arbeitsbereich handhaben? {#wie_viele_achsen_kann_der_pfad_arbeitsbereich_handhaben}

Zur Zeit kann die Version 0.18, Pfad Arbeitsbereich bis zu 3 Achsen Fräsen handhaben. Derzeit wird die 4. Achsen Fähigkeiten für die nächste offizielle Version entwickelt, wobei einige Pfad Arbeitsbereich Abläufe bereits auf den grundlegenden 4. Achsen Status aufgerüstet wurden.

[top](#top.md)

## Warum scheint es, dass der Pfad Arbeitsbereich in manchen Fällen mehr als einen Weg bietet, einen Ablauf festzulegen? {#warum_scheint_es_dass_der_pfad_arbeitsbereich_in_manchen_fällen_mehr_als_einen_weg_bietet_einen_ablauf_festzulegen}

Der Pfad Arbeitsbereich bietet vorhandene Werkzeuge für viele Fräsbearbeitungen, weitere sind in Arbeit, und da FreeCAD quelloffen ist, steht dem Anwender nichts im Wege, seine eigene Funktionalität zu erstellen.

Wie bei der 3D Modellierung stehen oft mehrere Methoden zur Verfügung, die für verschiedene Arbeitsabläufe vorteilhaft sein können. In einigen Fällen werden Kombinationen von Bearbeitungen verwendet, um ein vollständiges Fräsen des Rohteils zu ermöglichen.

Ein gängiges Beispiel ist, dass ein Konturschnitt aus Kanten oder Flächen erzeugt werden kann. In einigen Fällen ist eine geometrische Eingabe gegenüber einer anderen vorteilhaft.

[top](#top.md)

## Warum ändert das Aufbereiten eines Arbeitsvorgangswechsel die Position im Auftragsarbeitsablauf, angezeigt in der Liste der Arbeitsgänge? {#warum_ändert_das_aufbereiten_eines_arbeitsvorgangswechsel_die_position_im_auftragsarbeitsablauf_angezeigt_in_der_liste_der_arbeitsgänge}

Alle Ergänzungen zum Arbeitsauftrag\--einschließlich Änderungen und Arbeitsgangskopien\--werden am Ende des Auftrags Arbeitsablaufs angehängt. Wenn das die korrekte Arbeitsauftragsfolge zerreißt, muß sie im Arbeitsauftragseditor-\>Arbeitsablauf Reiter neu geordnet werden.

[top](#top.md)

## Was ist der Unterschied zwischen der lichten Höhe und der sicheren Höhe? {#was_ist_der_unterschied_zwischen_der_lichten_höhe_und_der_sicheren_höhe}

Genauere Informationen findest Du unter [Tiefen und Höhen](Template:Depths/Heights/de.md).

[top](#top.md)

## Was ist die typische Anwendung des EinrichtungsBlatts? {#was_ist_die_typische_anwendung_des_einrichtungsblatts}

Das EinrichtungsBlatt ist ein spezielles, in einem Arbeitsauftrag enthaltenes Tabellenblatt, das in der Eigenschaftsansicht modifiziert wurde und nur vom Pfad Arbeitsbereich aus zugänglich ist. Es bietet einen Mechanismus für erfahrenere Benutzer, um Aspekte ihres Arbeitsauftrags mit Hilfe von Werten und Ausdrücken, die im EinrichtungsBlatt enthalten sind, zu konfigurieren.

Die aktuellen Eingaben für Tiefen-, Höhen- und Werkzeugsteuerungen umfassen:

1.  Endtiefe Ausdruck \-- OpFinalDepth
2.  Anfangstiefe Ausdruck \-- OpStartDepth
3.  Step Down Ausdruck \-- Standardmäßig OpToolDiameter. Dieser Ausdruck wird für jeden Arbeitsgang verwendet, um den Standardabstiegswert zu berechnen, der auf dem Durchmesser des Werkzeugs basiert, der in der zugehörigen Werkzeugsteuerung definiert ist.
4.  Lichte Höhe Ausdruck \-- StartDepth+SetupSheet.ClearanceHeightOffset
5.  Lichte Höhe Versatz Wert \-- Enthält den in Ausdrücken verwendeten Wert.
6.  Sichere Höhe Ausdruck \-- StartDepth+SetupSheet.SafeHeightOffset
7.  Sichere Höhe Versatz Wert \-- Enthält den in den Ausdrücken verwendeten Wert.
8.  Horizontaler Eilwert\-- Stellt den Standardwert bereit, mit dem die horizontale Eilgeschwindigkeit für alle Werkzeugsteuerungen anfänglich ausgefüllt wird.
9.  Vertikaler Eilwert\-- Stellt den Standardwert bereit, mit dem der vertikale Eilvorschub für alle Werkzeug Steuerungen anfänglich gefüllt wird.

Dies bietet Flexibilität. So werden beispielsweise Standardausdrücke bereitgestellt, die jedoch vom Benutzer überschrieben werden können. Die Modifikation kann sogar die Standardgleichung auf einen Wert reduzieren, wenn dies dem Benutzer passt.

[top](#top.md)

## Was ist die typische Anwendung der Arbeitsauftragsvorlagen? {#was_ist_die_typische_anwendung_der_arbeitsauftragsvorlagen}

Auftragsvorlagen erlauben häufig verwendete Auftragsdefinitionen aus einem Auftrag zu speichern, um sie für nachfolgende, ähnlich konfigurierte Aufträge zu verwenden.

[top](#top.md)

## Wie viele Basisobjekte unterstützt der Pfad Arbeitsbereich? {#wie_viele_basisobjekte_unterstützt_der_pfad_arbeitsbereich}

Unterstützung gibt es nur für ein einziges Basisobjekt. Um Pfade für mehrere Festkörper in einem einzigen Auftrag zu erstellen, kkannst du diese zu einem Verbund zusammenfassen und diesen als Basisobjekt für den Auftrag verwenden.

[top](#top.md)

## Warum erzeugt eine Bearbeitung keine brauchbare Ausgabe? {#warum_erzeugt_eine_bearbeitung_keine_brauchbare_ausgabe}

Es gibt eine Vielzahl von Gründen, die dazu führen können, dass eine einzelne Bearbeitung kein Ergebnis erzeugt.

Ein häufiger Grund ist, dass die Werkzeuggeometrie, die in der für den Arbeitsgang ausgewählten Werkzeugsteuerung definiert ist, zu groß ist, um in die für den Arbeitsgang ausgewählte Geometrie des 3D Modells zu passen.

Beachte, dass dies in der Regel als eine Bewegung im Eiltempo zu dem Ort, an dem die Bearbeitung beginnt, erfolgt, ergänzt durch eine Bewegung im Eiltempo Z zu der Geometrie, die zur Definition der Bearbeitung ausgewählt wurde, und dann eine Rückkehr zur Eiltempo Zwischenhöhe.

Ein weiteres häufiges Missverständnis ist, dass ein Konturbearbeitung keine Pfade ausgibt, wenn die Kontureditorbearbeitung-\>Schnittseite auf \"Innen\" steht, die Standardeinstellung, und das Umschalten der 3D Modellierbarkeit es ermöglicht, sie zu sehen.

[top](#top.md)

## Kann der Pfad Arbeitsbereich 3D Oberflächen Fräsen? {#kann_der_pfad_arbeitsbereich_3d_oberflächen_fräsen}

Ja, Pfad ermöglicht 3D Oberflächenfräsbearbeitungen. Es erfordert die Installation von OpenCamLibrary\--einem quelloffenen Modul eines Drittanbieters, im Makro Dateipfad.

OpenCamLibrary ist nicht in FreeCAD eingebunden, um sicherzustellen, dass keine Lizenzverstöße auftreten.

[top](#top.md)

## Was kann ich tun, wenn die Standardbearbeitungsstrategien nicht meinen Anforderungen entsprechen? {#was_kann_ich_tun_wenn_die_standardbearbeitungsstrategien_nicht_meinen_anforderungen_entsprechen}

Bei Taschenbearbeitungen ist der Startpunkt standardmäßig auf XYZ = 000 eingestellt und immer aktiviert, aber auch er kann im Eigenschaftsansichtsfenster konfiguriert werden. Taschen- und Planfräsbearbeitungen bieten auf dem Bearbeitungsreiter eine explizite Angabe des Steig- und des konventionellen Schnittmodus.

Für Konturstil Bearbeitungen verfügt der Bearbeitungsreiter über einen \"Richtung\" Eingang , der als CW oder CCW konfiguriert werden kann und die Schnittrichtung definiert. Als Referenz:

1.  Cut Side = Außen, Schnittrichtung = CCW, Steigungsschnitt
2.  Cut Side = Außen, Schnittrichtung = CW, Konventioneller Schnitt
3.  Cut Side = Innen, Schnittrichtung = CW, konventioneller Schnitt

Cut Side = Innen, Schnittrichtung = CCW, Steigschnitt

Startpunkte können im Eigenschaften Fenster aktiviert und konfiguriert werden.

In Flächenfräsbearbeitungen können Materialzugaben festgelegt werden, die bei positiven Werten eine Überschneidung und bei negativen Werten eine Unterschneidung ermöglichen.

Bei Kontur- und Taschenoperationen dient der Extra Versatz demselben Zweck.

Diese Eingaben sind wertvoll und erlauben unter anderem folgende Funktionalität:

1.  Definition von Schruppdurchgängen, in Verbindung mit den Tiefen Eingabefeldern.
2.  Spezifizierung von Überschnitten für Plandreharbeiten.
3.  Formelemente kleiner als der Werkzeugdurchmesser, die es zu bewältigen gilt, können davon profitieren, dass ein Außenkonturschnitt mit einem negativen Zusatzversatzwert festgelegt wird.

Vorsicht ist geboten wenn Angabe von Materialzugaben und Versätzen angegeben werden, auf die Gefahr hin, dass unerwünschte Einschnitte in den Schaft vorgenommen werden.

[top](#top.md)

## Was mache ich, wenn ein Arbeitsgang mehr vertikale Bewegungen erzeugt, als mein Arbeitauftrag vertragen kann? {#was_mache_ich_wenn_ein_arbeitsgang_mehr_vertikale_bewegungen_erzeugt_als_mein_arbeitauftrag_vertragen_kann}

Bearbeitungen wie 3D\_Tasche, Taschen\_Form und FlächenFräsen aber nicht Konturbearbeitungen, haben eine Konfigurationsoption, um das Werkzeug unten zu halten, auf dem Datenreiter in der Eigenschaftsansicht.

[top](#top.md)

## Wie kann ich Laschen zum Spannen meiner Fräsarbeiten belassen? {#wie_kann_ich_laschen_zum_spannen_meiner_fräsarbeiten_belassen}

Pfad Arbeitsbereich bietet eine Aufbereitungskennzeichnung für genau diesen Zweck.

[top](#top.md)

## Was ist ein Postprozessor? {#was_ist_ein_postprozessor}

Der Postprozessor wird verwendet, um den Ausgabecode für CNC Steuerungen für verschiedene Maschinen in ihrem G-Code Dialekt anzupassen.

[top](#top.md)

## Kann ich einen bestehenden Postprozessor ändern oder einen eigenen Postprozessor erstellen? {#kann_ich_einen_bestehenden_postprozessor_ändern_oder_einen_eigenen_postprozessor_erstellen}

Postprozessoren sind Python Skripte, die im Makro Dateipfad gespeichert werden. Sie sind dazu gedacht, geändert zu werden oder als Vorlage für die weitere Entwicklung von Postprozessoren zu dienen.

[top](#top.md)

## Ich möchte nur einen Postprozessor verwenden\--kann ich ihn als Standard festlegen oder andere Optionen ausblenden? {#ich_möchte_nur_einen_postprozessor_verwenden__kann_ich_ihn_als_standard_festlegen_oder_andere_optionen_ausblenden}

Ja, in den Pfadeinstellungen gibt es einen Abschnitt für Postprozessoren, in dem du auswählen kannst, welche Postprozessoren angezeigt werden sollen, und einen Standardpostprozessor auswählen kannst.

[top](#top.md)

## Wie kann ich metrische/zöllige Einheiten für mein Pfadobjekt festlegen? {#wie_kann_ich_metrischezöllige_einheiten_für_mein_pfadobjekt_festlegen}

Die 3D Modell Einheiten werden im Bearbeiten-\>Einstellungen\...\>Allgemein-\>Einheiten Reiter des Aufklappmenü des Nutzersystems definiert.

Die Einheiten Einstellung, die festlegt, wie die Zielfräse den Auftrags G-Code interpretiert, wird im Ausgabe Postprozessor festgelegt, der einen G20 oder einen G21 G-Code Befehl einfügt, um Zoll bzw. Millimeter anzugeben.

Der Postprozessor kann auch für Einheiten/Sekunde oder Einheiten/Minute konfiguriert werden. Bei der Einstellung Einheiten/Minute wird die interne G-Code Dialekt Vorschubrate der Pfad Arbeitsbereich mit 60 multipliziert.

Unstimmigkeiten zwischen dem 3D Modell und den Postprozessor Einstellungen sind wahrscheinlich die Ursache für Fehler mit einem Faktor von 60 bei der Vorschubgeschwindigkeit und einem Faktor von 25,4 bei der Entfernung.

[top](#top.md)

## Wie kann ich meine Frässtrategien simulieren? {#wie_kann_ich_meine_frässtrategien_simulieren}

Ein volumetrischer Simulator wird bereitgestellt, um das Ergebnis des Schneidens der in den Auftragsbearbeitungen enthaltenen Werkzeuggeometrien gegen das Rohmaterial zu betrachten.

Wenn die Pfadlinien das Simulationsergebnis verdecken, sollte ihre Sichtbarkeit vor der Simulation ausgeschaltet werden.

[top](#top.md)

## Welche Bedeutung haben die Farben der Pfadlinien? {#welche_bedeutung_haben_die_farben_der_pfadlinien}

Die Farben der Pfadlinien werden in der Bearbeiten -\> Einstellungen -\> Pfad-\>Pfadfarben Reiter festgelegt. Die Standardfarben sind:

1.  Grün für normale Pfade.
2.  Rot für schnelle Pfade.
3.  Gelb für Sondierungspfade.

[top](#top.md)

## Wie kann ich die Sichtbarkeit von Pfadlinien aktivieren/deaktivieren? {#wie_kann_ich_die_sichtbarkeit_von_pfadlinien_aktivierendeaktivieren}

Der Pfad Arbeitsbereich ermöglicht die Kontrolle über die Anzeige von Pfadlinien, indem die Sichtbarkeit des Auftrags durch Auswahl in der Comboansicht umgeschaltet wird. Die Sichtbarkeit einzelner Vorgänge oder Gruppen von Vorgängen wird dann in der Comboansicht umgeschaltet.

[top](#top.md)

## Wie prüfe ich, ob meine G-Code Sequenz korrekt ist? {#wie_prüfe_ich_ob_meine_g_code_sequenz_korrekt_ist}

Standardmäßig wird die Postprozessorausgabe vor dem Speichern in einem Fenster angezeigt. Dies\--Zusammen mit dem Pfad CAM Simulator bietet eine Möglichkeit, den Auftrag zu prüfen, bevor er auf einer CNC Maschine verarbeitet wird. Das G-Code Inspektionswerkzeug erlaubt dir den internen Pfad G-Code für jede Bearbeitung prüfen, um festzustellen, ob die Ausgabe des Postprozessors dem entspricht, was in der Bearbeitung definiert ist.

Die Bearbeitungsliste in der Comboansicht zeigt die Reihenfolge an, in der die Bearbeitungen im Auftrag verarbeitet werden. Wenn die Bearbeitungen zwar korrekt sind, aber nicht in der gewünschten Reihenfolge, kann dies durch Doppelklicken auf die Bearbeitungsliste und Ziehen der Bearbeitungen an die richtige Stelle korrigiert werden, oder durch Doppelklicken auf den Auftragseditor und Auswählen des Arbeitsablauf Reiters und anschließendes Sortieren der ausgewählten Bearbeitungen mit den Pfeilen nach oben/unten.

[top](#top.md)

## Warum erhalte ich von meinem Postprozessor keine korrekte G-Code Ausgabe für Operationen, die mit dem Teilweise Befehl-\>Benutzerdefiniert Befehl eingefügt wurden? {#warum_erhalte_ich_von_meinem_postprozessor_keine_korrekte_g_code_ausgabe_für_operationen_die_mit_dem_teilweise_befehl_benutzerdefiniert_befehl_eingefügt_wurden}

Da das Format des benutzerdefinierten G-Code Befehls immer in Einheiten/Sekunde angegeben wird, kann er bei CNC Maschinen, die in Einheiten/Minute arbeiten, Fehler mit dem Faktor 60 verursachen.

[top](#top.md)

## Warum scheinen Änderungen an Positionierungswerten in der Eigenschaftsansicht im Pfad Arbeitsbereich nicht korrekt zu funktionieren? {#warum_scheinen_änderungen_an_positionierungswerten_in_der_eigenschaftsansicht_im_pfad_arbeitsbereich_nicht_korrekt_zu_funktionieren}

\"Die Pfad Funktion besitzt auch eine Eigenschaft Positionierung. Ändern des Wertes dieser Positionierung , ändert die Position der Funktion in der 3D Ansicht, obwohl die Pfadinformationen selbst nicht verändert werden. Die Transformation ist rein visuell. Auf diese Weise kannst du zum Beispiel einen Pfad um eine Fläche herum erstellen, die eine bestimmte Ausrichtung auf deinem Modell hat, die nicht die gleiche Ausrichtung ist, die dein Schneidmaterial auf der CNC Maschine haben wird.

Pfadverbünde können jedoch die Positionierung ihrer Kinder nutzen (siehe unten).\"

[https://www.freecadweb.org/wiki/Path\_scripting Pfad Skripten](https://www.freecadweb.org/wiki/Path_scripting_Pfad_Skripten.md)

[top](#top.md)

## Warum scheint die Pfad Arbeitsbereich auf meinem Computer Funktionalität zu vermissen, die ich in den Forenbeiträgen anderer Benutzer sehe? {#warum_scheint_die_pfad_arbeitsbereich_auf_meinem_computer_funktionalität_zu_vermissen_die_ich_in_den_forenbeiträgen_anderer_benutzer_sehe}

Standardmäßig ist Experimentelle Funktionalität im Pfad Arbeitsbereich ausgeblendet.

[top](#top.md)

## Warum erscheinen Youtube Videos, die von Pfad Arbeitsbereich Entwicklern veröffentlicht werden, nicht synchron mit dem Pfad Arbeitsbereich? {#warum_erscheinen_youtube_videos_die_von_pfad_arbeitsbereich_entwicklern_veröffentlicht_werden_nicht_synchron_mit_dem_pfad_arbeitsbereich}

Der Pfad Arbeitsbereich hat sich von FreeCAD v0.16 auf v0.17 drastisch verändert, und alle Videos, die vor dem 1. Januar 2018 veröffentlicht wurden, enthalten höchstwahrscheinlich Informationen, die nicht mehr mit der Version 0.17 des Pfad Arbeitsbereichs übereinstimmen.

[top](#top.md)

## Warum sind Bögen nicht rund, sondern bestehen aus einer Reihe von geraden Linien? {#warum_sind_bögen_nicht_rund_sondern_bestehen_aus_einer_reihe_von_geraden_linien}

Dabei geht es nur um die Anzeige des Pfades. Du kannst dies in den Einstellungen ändern: Lade Pfad Arbeitsbereich.

1.  Öffne Einstellungen -\>Pfad-\>Auftragseinstellungen
2.  Setze die Werte für *Standard Geometrietoleranz* und *Standard Kurvengenauigkeit* auf kleine Werte, aber nicht auf 0, z.B. auf 0.01mm.
3.  Bestätige die Änderung.
4.  Starte FreeCAD neu.

[top](#top.md)





{{Path_Tools_navi

}} 