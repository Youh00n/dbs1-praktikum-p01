

 Aufgabe 1

Befehl:
docker run -it --rm bsalgert/postgres:v1

Ergebnis:
Die Abfrage wurde erfolgreich ausgeführt.
Es wurden 20 Datensätze angezeigt.


 Aufgabe 2

Befehl:
docker run --rm -v $(pwd)/script.sql:/script.sql -e SQL_FILE=/script.sql bsalgert/postgres:v1 > p01_ausgabe.log

Ergebnis:
Die SQL-Datei wurde im Container ausgeführt.
Die Ausgabe wurde in der Datei p01_ausgabe.log gespeichert.
Es wurden 20 Datensätze angezeigt.


 Aufgabe 3 

Befehl:
docker run -d --name mydb bsalgert/postgres:v1 /demon.sh

Überprüfung:
docker ps

Ergebnis:
CONTAINER ID   IMAGE                  COMMAND                  CREATED           STATUS             PORTS      NAMES
cb4b34fb53fa   bsalgert/postgres:v1   "docker-entrypoint.s…"   About an hour ago   Up About an hour   5432/tcp   mydb

Der Container wurde im Hintergrund gestartet.
Mit docker ps wurde überprüft, dass der Container läuft.
Der Container mit dem Namen "mydb" wird angezeigt.

 Aufgabe 4 

Befehle:
docker exec -it mydb bash
psql --help
psql -U postgres -d postgres

SQL:
SELECT * FROM Movies;

Ergebnis:
Die Verbindung zur PostgreSQL-Datenbank wurde erfolgreich hergestellt.
Die Tabelle Movies wurde angezeigt.

 Aufgabe 5 

Befehle:
docker stop mydb - container stoppen
docker ps        - status überprüfen 

Ergebnis:
Der Container wurde gestoppt.
Mit docker ps wurde überprüft, dass der Container nicht mehr läuft.
Der Container konnte mit docker start wieder gestartet werden.

Der Container kann mit  diesem Befehl neu erstellt werden:
docker run -d --name mydb bsalgert/postgres:v1 /demon.sh

-d docker läuft im hintergrund 
--name gibt container einen Namen
