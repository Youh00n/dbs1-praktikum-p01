# DBS1 Praktikum 01
Hier sind  alle verwendeten Befehle aus den Aufgaben 1–6 des ersten Praktikums.  

Aufgabe 1: Container starten & SELECT ausführen
    Container starten : docker run -it --rm bsalgert/postgres:v1
    SQL-Befehl ausführen : SELECT * FROM Movies; (12 Datensätze)
    Verlassen des Datenbank Prompt: \q 

Aufgabe 2: SQL-Datei ausführen
    SQL-Datei erstellen : touch script.sql
    Befehl in Datei geben: echo "SELECT * FROM Movies;" > script.sql
    QL-Datei ausführen und Ausgabe in result.log speichern: docker run --rm -v $(pwd)/script.sql:/script.sql -e SQL_FILE=/script.sql bsalgert/postgres:v1 > result.log

Aufgabe 3: Container im Hintergrund starten 
    Container mydb im Hintergrund starten: docker run -d --name mydb bsalgert/postgres:v1 /demon.sh
    (Zum Öffnen des bestehtenden Container: docker start mydb)
    Laufende Container anzeigen: docker ps

Aufgabe 4: psql im laufenden Container verwenden
    Shell im Container öffnen: docker exec -it mydb bash
    Mit psql verbinden: psql -U postgres -d postgres
    SQL ausführen: SELECT * FROM Movies;
    psql & Shell verlassen: \q , exit

Aufgabe 5: Container verwalten
    Container stoppen: docker stop mydb
    Status prüfen:  docker ps -a
    Container neu erstellen:  docker run -d --name mydb bsalgert/postgres:v1 /demon.sh

Aufgabe 6: Git Repository
    ReadMe erstellen: echo "# DBS1 Praktikum 01" > README.md
    Git Repository erstellen: git init
    Datei hinzufügen: git add .
    Comitten: git commit -m "Praktikum 01 – vollständige Lösung"
    

