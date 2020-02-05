# Buchführung mit ledger

## Beispiele anhand des Buchungsjournals example/journal.dat

### Kontostände über alle Buchungen aus 2019
    ledger \
        -f example/journal.dat \
        -b 2019-01-01 \
        -e 2020-01-01 \
        balance

### Konten suchen

    bin/ktosuche example/journal.dat ideell versich

Sucht in allen Konten, die in journal.dat selbst oder in eingebundenen Dateien
definiert sind. Es werden die Konten angezeigt, die alle der genannten Stichworte
(`ideell` und `versich`) als Wortteile im Namen, der Beschreibung (`note`) oder
in einem der Aliase tragen. Die gefundenen Konten werden als Hierarchie angezeigt,
z. B.

    2 Erfolgskonten ideeller Bereich
        2500-2999 AUSGABEN
            2510 Übrige Ausgaben
                2753 Versicherungsbeiträge
            2550-2559 Personalkosten
                2555 Sozialversicherungsbeiträge

### 2018er Berichte
    bin/bericht-einnahmen-ausgaben-nach-bereichen example/journal.dat 2018
    bin/bericht-mittelverwendung example/journal.dat 2018
    bin/bericht-sbk example/journal.dat 2018

### 2019 abschließen
__Achtung:__ Die nachfolgend verwendeten Scripts fügen dem Buchungsjournal neue Buchungen hinzu!

    bin/1-buche-gewinnermittlung example/journal.dat 2019
    bin/2-buche-freie-ruecklagen example/journal.dat 2019
    bin/3-buche-ergebnisverwendung example/journal.dat 2019
    bin/4-buche-abschluss example/journal.dat 2019
