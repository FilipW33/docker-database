#Docker dla baz danych

##Krok 1 

Upewnij się, że plik docker-compose.yaml oraz Twój plik .sql (np. world.sql) znajdują się w tym samym folderze.

*Otwórz terminal (CMD, PowerShell lub Terminal) w tym folderze.

*Uruchom serwer w tle za pomocą komendy:

```docker-compose up -d


Przy pierwszym uruchomieniu Docker pobierze obraz mysql:8.0 i automatycznie załaduje dane z pliku .sql. Może to potrwać kilka minut.


##Krok 2

Ważne jest IP urządzenia by się podłączyć zdalnie 

```ipconfig - windows
ifconfig / ip addr - linux 

##Krok 3

Przykładowe podłączenie do bazy z innego komputera 

```mysql -h 192.168.1.10 -P 3307 -u student -p

Następnie zostaniesz poproszony o hasło 

##Krok 4 

Aby zatrzymać serwer wystarczy wpisć 

```docker-compose down

dane zostaną zachowane w (databes_data)

ewentualnie pełny restart z usunięciem volumenu (wszystkie dane zostaną wymazane)

```docker-compose down -v

!Uwaga co ze zmianą na inne dystrybucje np. PostgreSQL:
 MySQL używa portu 3306 a PostgreSQL 5432
by zmienić obraz z MySQL wystarczyt zmienić image w docker-compose.yaml np. na postgres:15
oraz MySQL używa /var/lib/mysql a PostgreSQL /var/lib/postgresql/data - też to trzeba zmienić 