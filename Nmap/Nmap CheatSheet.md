# Nmap CheatSheet

## Grundlegende Kommandos

### Service Versionen
    -sV

Versucht die Versionen der mit offenen Ports erkannten Services zu erkennen

### Portnummer festlegen
    -p <x> oder -p-

Port scan für den Port <x> oder für alle Ports bis <x>

### Hosterkennung deaktivieren
    -Pn

Zeigt nur die offenen Ports an und keine Informationen zum Service dahinter

### OS Erkennung
    -A

Aktiviert die OS und Versionserkennung

### Scan mit Standard Nmap Skripts
    -sc

Scant mit den Standard Skripts von Nmap

### Verbose Mode
    -v

### UDP Port Scan
    -sU

### TCP SYN Port Scan
    -sS

### Keine DNS Auflösung
    -n