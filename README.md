AUFGABE 1
(container mit postgres datenbank starten) 
    docker run -it --rm bsalgert/postgres:v1 

AUFGABE 2
(SQL datei ausführen)
    docker run --rm -v $(pwd)/script.sql:/script.sql -e SQL_FILE=/script.sql bsalgert/postgres:v1 > result.log

AUFGABE 3
(container mydb mit Image bsalgert/postgres:v1 im Hintergrund starten)
    docker run -d --name mydb bsalgert/postgres:v1 /demon.sh
(alle laufenden Container anzeigen)
    docker ps

AUFGABE 4
(befehl in einen container starten + interaktives terminal starten (-it bash))
    docker exec -it mydb bash
(mit datenbankserver verbinden + database user -U + database name -d)
    psql -U postgres -d postgres
        (richtige parameter finden)
            psql --help

AUFGABE 5
(container stoppen)
    docker stop mydb
(container prüfen ob gestoppt)
    docker exec -it mydb bash -> error
(container neu erstellen)
    docker start mydb

