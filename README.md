# Buchführung mit ledger

## Beispiele anhand des Buchungsjournals example/journal.dat

### Kontostände über alle Buchungen aus 2019
    ledger \
        -f example/journal.dat \
        -b 2019-01-01 \
        -e 2020-01-01 \
        balance

### 2018er Berichte
    bin/bericht-einnahmen-ausgaben-nach-bereichen example/journal.dat 2018
    bin/bericht-mittelverwendung example/journal.dat 2018
    bin/bericht-sbk example/journal.dat 2018

### 2019 abschließen
    bin/1-buche-gewinnermittlung example/journal.dat 2019
    bin/2-buche-freie-ruecklagen example/journal.dat 2019
    bin/3-buche-ergebnisverwendung example/journal.dat 2019
    bin/4-buche-abschluss example/journal.dat 2019
