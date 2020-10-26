# Metasploit Cheat Sheet
Ein Cheat Sheet für diverse Linux Befehle

## Initalsierung
Kommandos um sich in Linux zurechtzufinden
 
### Datenbank initalsieren
Setz die Postgres Datenbank auf
    
    msfdb init

### Alle Startkommandos anzeigen
    msfconsole -h

### Metasploit starten
    msfconsole
    msfconsole -q

### Datenbankstatus prüfen
    db_status

## Basisbefehle

### Module finden
    search

### Module aktivieren
    use

### Informationen zu einem Modul anzeigen
    info

### Sich mit einem Host verbinden
Dient dazu um zu prüfen ob eine Verbindung mit einem Host möglich ist

    connect

### Eine Variable setzen
    set

### Eine globale Variable setzen
    setg

### Den Wert einer Variablen anzeigen
    get

### Den Wert einer Variable löschen
    unset

### Konsolenoutput in ein File schreiben
    spool

### Aktuelle Einstellung in ein Settings File speichern
    save

### Lade ein zusätliches Framework für Metasploit
    load

## Laufzeitbefehle

### Nmap laufen lassen und Resultate in DB speichern
    db_nmap -sV BOX-IP

### Gescannte Geräte in DB anzeigen
    hosts

### Erfasste Services in DB anzeigen
    services

### Erfasste Vulnerabilities in DB anzeigen
    vulns

### Payload setzen
    set PAYLOAD [Payload Name]

### Aktive jobs anzeigen
    jobs

### Aktuell aktive Sessions anzeigen
    sessions

### Aktuelle Session in den Hintergrund verschieben
    background

## Meterpreter Kommandos

### Den Server migrieren
Mit diesem Befehl kann der Zugangspunkt auf die Maschine in einen anderen, zuverlässigeren Prozess (welcher immer läuft) gewechselt werden

    migrate

### Userinformationen anzeigen
    getuid

### Informationen über das Remotesystem erhalten
    sysinfo

### Mimikatz laden
    load kiwi

### Berechtigungen des Users prüfen
    getprivs

### Dateien auf den Remote Computer hochladen
    upload

### Ein Metasploit Modul auführen
    run

### Prüfen ob das Ziel eine VM ist
    run post/windows/gather/checkvm

### Nach Exploits auf dem Ziel suchen um die Privilegien zu elevaten
    run post/multi/recon/local_exploit_suggester

### RDP einschalten (Administrator nötig)
    run post/windows/manage/enable_rdp

### Normale Shell starten
    shell


