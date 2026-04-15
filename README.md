# dbs1-praktikum-p01
## Aufgabe 3 – Container im Hintergrund starten
Verwendeter Befehl:
docker run -d --name mydb bsalgert/postgres:v1 /demon.sh

Überprüfung:
docker ps

Ergebnis:
CONTAINER ID   IMAGE                  COMMAND                  CREATED          STATUS          PORTS      NAMES
cb4b34fb53fa   bsalgert/postgres:v1   "docker-entrypoint.s…"   42 seconds ago   Up 42 seconds   5432/tcp   mydb

Der Container wurde im Hintergrund gestartet.
Mit docker ps wurde überprüft, dass der Container läuft.
Der Container mydb wurde angezeigt.

## Aufgabe 4 
