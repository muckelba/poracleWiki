---
title: Poracle für Gruppen
nav_order: 1
layout: default
parent: German
grand_parent: v3 Userguide
---

# Poracle für Gruppen
Dieser Abschnitt richtet sich vor allem Scan-Administratoren.

## Gruppe/Kanal einrichten
**Discord**: Bei der Erstellung eines Discord-Bots kann dieser einem Server zugewiesen werden.
Anschließend kann er dort dann jeder Untergruppe hinzugefügt werden und ist dann einsatzbereit.

**Telegram**: In Telegram kann man den Bot beliebig vielen Gruppen/Kanälen hinzufügen.
Sowohl der Bot selbst, als auch einer der zuvor eingetragenen Bot-Admins müssen als Gruppen/Kanal-Admin eingetragen werden.
Entsprechend also die Telegram-Einstellungen dahingehend anpassen. Der Bot wird ansonsten im folgenden nicht antworten (können).

Telegram und Discord haben nun einen großen Unterschied bei der Befehl-Anwendung für den Poracle-Bot: Telegram startet einen Befehl mit “/” (Slash), Discord startet mit “!” (Ausrufezeichen).
Die restliche Befehlsstruktur ist in beiden Anwendungen gleich. (Für Discord nachfolgend also immer / durch ! ersetzen)
Um jetzt eine Gruppe für bestimmte Meldungen einzustellen, muss folgendes getan werden:

**`/channel add`**  
Schaltet eine Gruppe/ einen Kanal für die Botnutzung frei.

**`/area add name`**  
Fügt eine Area für die der Bot Benachrichtigungen sammeln soll hinzu. Es können mehrere Areas gleichzeitig ausgewählt sein.

**`/area list`**  
Ist optional und zeigt alle für diesen Poracle-Bot verfügbaren Areas an. Sobald wir mit der Einrichtung fertig sind, sollte hier also mindestens ein Name eures Gebiets auftauchen.
Ab jetzt können Filtereinstellungen eingetragen werden. Eine erweiterte Übersicht in Kapitel [Filter-Optionen](#filter-optionen), hier nur ein kurzes Beispiel:

**`/track everything IV97`**  
Gemeldet werden ab jetzt alle Pokémon im ausgewählten Gebiet mit einer IV von mindestens 97,00%.

**`/tracked`**  
Dient zur Überprüfung. Es wird eine Übersicht aller getrackten Dinge gezeigt, ist diese zu lang wird sie als File bereitgestellt.
Wir empfehlen diesen Befehl immer abschließend zu verwenden, um zu überprüfen, ob auch alles richtig funktioniert hat.
Des weiteren ist es sinnvoll, die hier gesendete Antwort (incl. Datei) bei einer Supportanfrage mit zusenden.

**`/help`**  
Zeigt eine Auswahl an Befehlen, die der Bot verarbeiten kann und einige Beispiele dazu. Eine ausführlichere Liste findet man hier. 

Der Bot sollte auf jede Eingabe, die für ihn bestimmt ist, antworten. Antwortet der Bot gar nicht, liegt in jedem Fall noch ein Fehler vor. In diesem Fall prüfen, ob die bisher genannten Schritte vollständig abgeschlossen wurden und ansonsten eine Supportanfrage stellen. Hat der Bot einen Befehl erfolgreich verarbeitet sendet er ein ein :white_check_mark: - Emoji. Ist ein Befehl als solcher eine Doppelung bekommt man ein :ok_hand: - Emoji zurück. Gab es einen Fehler in der Eingabe und der Bot kann den Befehl nicht vollständig verarbeiten, gibt es in den meisten Fällen eine Fehlermeldung.