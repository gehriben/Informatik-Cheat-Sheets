# Linux Cheat Sheet
Ein Cheat Sheet für diverse Linux Befehle



## Basiskommandos
Kommandos um sich in Linux zurechtzufinden
 
### Aktueller Ordnerstandort
Zeigt an in welchem Ordner man gerade ist
    
    kali >pwd
    /root 

### Angemeldeter Benutzer
    kali >whoami
    root 

## Dateinavigation
Einige Kommandos um durch das Filesystem zu navigiern

### Ordner wechseln
In ein Ordner navigiern

    kali >cd /etc 
    root@kali: /etc#

Ein Ordner hoch navigieren

    kali >cd ..
    root@kali: /#

### Ordnerinhalt auflisten
Zeigt Dateinamen an

    kali >ls
    bin    initrd.img        media        run        var
    boot   initrd.img.old    mnt          sbin       vmlinuz
    dev    lib               opt          srv        vmlinuz.old
    etc    lib64             proc         tmp
    home   lost+found        root         usr

Zeigt zusätzliche Dateiinfos an

    kali >*ls -l**
    drw-r--r--    1    root     root    4096    Dec    5  11:15    bin 
    drw-r--r--    2    root     root    4096    Dec    5  11:15    boot 
    drw-r--r--    3    root     root    4096    Dec    9  13:10    dev 
    drw-r--r--    18   root     root    4096    Dec    9  13:43    etc 
    --snip--
    drw-r--r--    1    root     root    4096    Dec    5  11:15    var 

## Hilfe erhalten
    kali >aircrack-ng --help
    kali >nmap -h

### Referenz Manual
    kali >man nmap

## Suche

### locate - Befehl
    kali >locate aircrack-ng
    /usr/bin/aircrack-ng
    /usr/share/applications/kali-aircrack-ng.desktop
    /usr/share/desktop-directories/05-1-01-aircrack-ng.directory
    --snip--
    /var/lib/dpkg/info/aircrack-ng.mg5sums

### whereis - Befehl
Sucht Binary Files

    kali >whereis aircrack-ng
    aircarck-ng: /usr/bin/aircarck-ng /usr/share/man/man1/aircarck-ng.1.gz

### which - Befehl
Gibt nur jenes Binary File zurück dass in der PATH Variable ist

    kali >which aircrack-ng
    /usr/bin/aircrack-ng

### find - Befehl
Ist einiges mächtiger und bietet viele Parameter

    kali >find  / -type f -name apache2 
    /usr/lib/apache2/mpm-itk/apache2 
    /usr/lib/apache2/mpm-event/apache2 
    /usr/lib/apache2/mpm-worker/apache2 
    /usr/lib/apache2/mpm-prefork/apache2 
    /etc/cron.daily/apache2 
    /etc/logrotate.d/apache2 
    /etc/init.d/apache2 
    /etc/default/apache2 

### grep - Befehl
Filtert ein Textinput nach einem gewissen Suchbegriff
    kali >ps aux | grep apache2 
    root  4851 0.2 0.7 37548  7668 ?  Ss  10:14  0:00   /usr/sbin/apache2 -k start 
    root  4906 0.0 0.4 37572  4228 ?  S   10:14  0:00   /usr/sbin/apache2 -k start 
    root  4910 0.0 0.4 37572  4228 ?  Ss  10:14  0:00   /usr/sbin/apache2 -k start 
    --snip-- 

## Files und Ordner modifizieren

### File erstellen
> kali >cat > hackingskills 
Hacking is the most valuable skill set of the 21st century!

> kali >touch newfile

### File anschauen
kali >cat hackingskills 
Hacking is the most valuable skill set of the 21st century!

### Text zu Textfile hinzufügen
    kali >cat >> hackingskills 
    Everyone should learn hacking

### Ordner erstellen
    kali >mkdir newdirectory

### File kopieren 
    kali >cp oldfile  /root/newdirectory/newfile

### File umbenennen
    kali >mv newfile newfile2

### File löschen
    kali >rm newfile2

### Ordner löschen
Bei diesem Befehl muss der Ordner leer sein

    kali >rmdir newdirectory 
    rmdir:failed to remove 'newdirectory': Directory not empty

So werden auch gefüllte Ordner gelöscht
> kali >rm -r newdirectory

## Text Manipulation

### Kopfzeilen anschauen
Zeigt die 10 ersten Zeilen an

    kali >head /etc/snort/snort.conf 
    -------------------------------------------------------------- 
    VRT Rules Packages Snort.conf 
    
        For more information visit us at: 
    --snip-- 
    Snort bugs:bugs@snort.org 

Anzahl Zeilen können auch selbst definiert werden

    kali >head -20 /etc/snort/snort.conf

### Fusszeilen anzeigen
Zeigt die letzten 10 Zeilen an

    kali >tail /etc/snort/snort.conf 
    include $SO_RULE_PATH/smtp.rules 
    include $SO_RULE_PATH/specific-threats.rules 
    include $SO_RULE_PATH/web-activex.rules 
    include $SO_RULE_PATH/web-client.rules 
    include $SO_RULE_PATH/web-iis.rules 
    include $SO_RULE_PATH/web-miscp.rules 
    Event thresholding and suppression commands. See threshold.conf 

Kann auch hier wieder selbst definiert werden

    kali >tail -20 /etc/snort/snort.conf

### Zeilen nummerieren
    kali >nl /etc/snort/snort.conf 
    612 ################################################################# 
    613 #dynamic library rules 
    614 #include $SO_RULE_PATH/bad-traffic.rules 
    615 #include $SO_RULE_PATH/chat.rules 
    --snip-- 
    630 #include $SO_RULE_PATH/web-iis.rules 
    631 #include $SO_RULE_PATH/web-misc.rules 

### Text mit grep Filtern
    kali >cat /etc/snort/snort.conf | grep output

### Suchen und ersetzen
Sucht nach mysql und ersetzt es durch MySQL was wiederum in snort2.conf gespeichert wird¨

    kali >sed s/mysql/MySQL/g /etc/snort/snort.conf > snort2.conf

### Files mit more und less anschauen
More zeigt eine Seite gleichzeit eines Files an und lässt einen durchnavigieren

    kali >more /etc/snort/snort.conf 
    --snip-- 
         Snort build options: 
     Options: --enable-gre --enable-mpls --enable-targetbased 
    --enable-ppm --enable-perfprofiling enable-zlib --enable-active 
    -response --enable-normalizer --enable-reload --enable-react 
    --enable-flexresp3 
    
    --More--(2%)<br>

Less ist ähnlich wie more lässt einen aber noch filtern (hier nach `output`)

    kali >less /etc/snort/snort.conf 
        Snort build options: 
     Options: --enable-gre --enable-mpls --enable-targetbased 
       --enable-ppm --enable-perfprofiling enable-zlib --enable-active 
    -response --enable-normalizer --enable-reload --enable-react 
       /output 

## Netwerkanalyse

### Netzwerkinformationen anzeigen
    kali >ifconfig

### Wirelessgerät kontrollieren
    kali >iwconfig 
    wlan0 IEEE 802.11bg ESSID:off/any 
    Mode:Managed Access Point: Not Associated Tx-Power=20 dBm 
    --snip-- 
    lo    no wireless extensions 
    eth0  no wireless extensions 

### IP Adresse ändern
    kali >ifconfig eth0 192.168.181.115

### Netzwerkmaske und Broadcastadresse ändern
    kali >ifconfig eth0 192.168.181.115 netmask 255.255.0.0 broadcast 192.168.1.255

### MAC Adresse ändern (spoofen)
    kali >ifconfig eth0 down 
    kali >ifconfig eth0 hw ether 00:11:22:33:44:55 
    kali >ifconfig eth0 up 

### Neue IP vom DHCP anfordern
    kali >dhclient eth0

### DNS Informationen erhalten
    kali >dig hackers-arise.com ns 
    --snip-- 
    ;; QUESTION SECTION: 
    ;hackers-arise.com.    IN   NS 
    ;; ANSWER SECTION: 
    hackers-arise.com.  5  IN   NS   ns7.wixdns.net. 
    hackers-arise.com.  5  IN   NS   ns6.wixdns.net. 
    ;; ADDITIONAL SECTION: 
    ns6.wixdns.net.     5  IN   A   216.239.32.100 
    --snip-- 

### Eigener DNS Server ändern
    kali >echo "nameserver 8.8.8.8"> /etc/resolv.conf

## Software installieren und löschen

### Ein Paket suchen

    apt-cache search keyword

### Software hinzufügen

    apt-get install packagename

### Software löschen

    kali >apt-get remove snort

Der obige Befehl löscht das Paket nicht komplett sondern behält dessen Konfigurationsfiles. Um ein Paket komplett zu löschen kann folgender Befehl verwendet werden:

    kali >apt-get purge  snort

### Softwareliste aktualisiern
Folgender Befehl updatet die Softwarerepositorys und prüft ob neue Software hinzugefügt wurde:

    kali >apt-get update

### Software aktualisiern
Folgender Befehl aktualisiert effektiv Software auf die neuste Version

    kali >apt-get upgrade   

### Weiter Repositorys hinzufügen
Die obigen Befehle suchen die angegeben Software aus Repositorys. Diese werden in folgender Date verlinkt und können dort ergänzt werden:

    kali >leafpad /etc/apt/sources.list

Es gibt dabei verschiedene Arten von Repositorys:

**main** Contains supported open source software <br>
**universe** Contains community-maintained open source <br>
**multiverse** Contains software restricted by copyright issues <br>
**restricted** Contains proprietary device drivers <br>
**backports** Contains packages from later releases <br>

## Berechtigungen kontrollieren

### Besitzerrechte an User vergeben

    kali >chown ubob v/tmp/bobsfile

### Besitzerrechte an Gruppe vergeben

    kali >chgrp usecurity /etct/vnewIDS

### Berechtigungen prüfen

    kali >ls –l /usr/share/hashcat
    total 32952
    u v       w  x            y         z           {
    drwxr-xr-x  5  root  root    4096     Dec 5 10:47  charsets
    -rw-r--r--  1  root  root    33685504 June 28 2018 hashcat
    -rw-r--r--  1  root  root    33685504 June 28 2018 hashcat
    drwxr -xr-x 2  root  root    4096     Dec 5 10:47  masks
    drwxr -xr-x 2  root  root    4096     Dec 5 10:47  OpenCL
    drwxr -xr-x 3  root  root    4096     Dec 5 10:47  rules

1. Das **d** am Anfang sagt aus ob es ein Ordner oder ein File ist
2. Das erste **rwx** bestimmt die Rechte des **Besitzers**
3. Das zweite **rwx** bestimmt die Rechte der **Gruppe**
4. Das dritte **rwx** bestimmte die Rechte **aller anderen**

### Berechtigungen ändern

    kali >chmod 774 hashcat.hcstat

| Binary | Octal | rwx |
|-------|-------|------| 
| 000 | 0 | --- |
| 001 | 1 | --x |
| 010 | 2 | -w- |
| 011 | 3 | -wx |
| 100 | 4 | r-- |
| 101 | 5 | r-x |
| 110 | 6 | rw- |
| 111 | 7 | rwx |

## Prozess Management

### Prozesse anzeigen

    kali >ps
    PID    TTY      TIME      CMD
    39659  pts/0    00:00:01  bash
    39665  pts/0    00:00:00  ps

Folgender Befehl zeigt weitere Details zu den Prozessen an:

    kali >ps aux
    USER  PID   %CPU  %MEM    VSZ    RSS TTY    STAT START   TIME   COMMAND
    Root    1    0.0   0.4    202540  6396 ?    Ss   Apr24    0:46  /sbin/init
    Root    2    0.0   0.0         0     0 ?    S    Apr24    0:00  [kthreadd
    Root    3    0.0   0.0         0     0 ?    S    Apr24    0:26  [ksoftirqd
    --snip--
    root  39706  0.0  0.2  36096  3204 pts/0    R+ 15:05  0:00    ps aux

### Nach Prozessnamen filtern

    kali >ps aux | grep msfconsole
    root 39756  0.0  0.0  4304  716  pts/2 Ss+  15:13  0:00 sh -c service 
    postgresql start && msfdb init & msfconsole
    root 39759  35.1  15.2  4304  227888  pts/2 Sl+  15:13  1:36 ruby /usr/bin/
    msfconsole
    root 39892  0.0  0.0  4304  940  pts/2 S+  15:18  0:00 grep msfconsole

### Nach Ressourcenverbrauch sortieren

    kali >top

### Prozesspriorität verwalten
Die Prioritäten gehen von **-20** bis **19**, wobei -20 am **höchtsten** und **19** am tiefsten priorisiert ist

Mit folgendem Befehl wird ein Prozess mit entsprechender Priorität gestartet. Dies erhöht die Priorität der Prozesses um 10 (Setzt es **nicht** auf -10!!!)

    kali >nice  -n -10 /bin/slowprocess

Folgender Befehl ändert die Priorität eines laufenden Prozesses. Die Priorität wird fix gesetzt nicht wie oben addiert oder subtrahiert!

    kali >renice 15 6996

### Prozess töten
Folgender Befehl beendet und startet den Prozess neu:

    kali >kill -1 6996

Folgender Befhel beendet den Prozess sofort:

    kali >kill -9 6996

    kali >killall -9 zombieprocess

### Prozess im Hintergrund laufen lassen

    kali >leafpad newscript &

Nun kann die Konsole weiterhin benutzt werden während leafpad geöffnet ist.

### Prozess wieder in Vordergrund bringen

    kali >fg 1234

### Prozess schedulen

    kali >at 7:20am
    at >/root/myscanningscript

## Userumgebungsvariablen verwalten

### Variablen ansehen und modifizieren
Alle **Standard** Variablen ansehen:

    kali >env
    XDG_VTNR=7
    SSHAGENT_PID=922
    XDG_SESSION_ID=2
    XDG_GREETER_DATA_DIR=/var/lib/lightdm/data/root
    GLADE_PIXMAP_PATH=:echo
    TERM=xterm
    SHELL=/bin/bash
    --snip--
    USER=root
    --snip--
    PATH=/usr/local/sbin :usr/local/bin:/usr/sbin:/sbin/bin
    --snip--
    HOME=/root
    --snip--

Alle Variablen ansehen:

    kali >set | more
    BASH=/bin/bash
    BASHOPTS=checkwinsize:cmdlist:complete_fullquote:expand_aliases:extglob.....


    Managing User Environment Variables   73

    BASH_ALIASES=()
    BASH_ARGC=()
    BASH_ARGV=()
    --snip--

Für bestimmte Variablen filtern:

    kali >set | grep
    HISTSIZE=1000

Variable für eine Session ändern:

    kali >HISTSIZE=0

Variable permanent ändern:

    kali >HISTSIZE=1000
    kali >export HISTSIZE

### Terminal Fenster ändern

    kali >PS1="World's Best Hacker
    World's Best Hacker: #
    kali >export PS1

    kali >export PS1='C:\w> '
    C:/tmp>

### PATH Variable ändern
PATH Variable ansehen:

    kali >echo $PATH
    /usr/local/sbin:usr/local/bin:/usr/sbin:/sbin/bin

Der PATH Variable etwas hinzufügen

    kali >PATH=$PATH:/root/newhackingtool

### Eine Userdefinierte Variable erstellen

    kali >MYNEWVARIABLE="Hacking is the most valuable skill set in the 21st century"

    kali >echo $MYNEWVARIABLE
    Hacking is the most valuable skill set in the 21st century

Diese Variable kann wie folgt wieder gelöscht werden:

    kali >unset MYNEWVARIABLE

## Bash Scripting

### Beispielskripte
Skript mit User Input:

    #! /bin/bash
    # This is your second bash script. In this one, you prompt /
    # the user for input, place the input in a variable, and /
    # display the variable contents in a string.
    echo "What is your name?"
    read name
    echo "What chapter are you on in Linux Basics for Hackers?"
    read chapter
    echo "Welcome" $name "to Chapter" $chapter "of Linux Basics for Hackers!"

Einfaches Port-Scanner Skript:

    #! /bin/bash
    # This script is designed to find hosts with MySQL installed
    nmap w-sT 192.168.181.0/24 x-p 3306 y>/dev/null z-oG MySQLscan
    cat MySQLscan | grep open > MySQLscan2 |
    cat MySQLscan2   

Verbessertes Scanner Skript:

    #! /bin/bash
    echo "Enter the starting IP address : "
    read FirstIP
    echo "Enter the last octet of the last IP address : "
    read LastOctetIP
    echo "Enter the port number you want to scan for : "
    read port
    nmap -sT $FirstIP-$LastOctetIP -p $port >/dev/null -oG MySQLscan
    cat MySQLscan | grep open > MySQLscan2
    cat MySQLscan2

### Skripte ausführen

    kali >./MySQLscannerAdvanced.sh 

### Nützliche Kommandos für bash

| Command | Function |
|---------|----------|
| : | Returns 0 or true
| . | Executes a shell script
| bg | Puts a job in the background
| break | Exits the current loop
| cd | Changes directory
| continue | Resumes the current loop
| echo | Displays the command arguments
| eval | Evaluates the following expression 
| exec | Executes the following command without creating a new process
| exit | Quits the shell
| export | Makes a variable or function available to other programs 
| fg | Brings a job to the foreground
| getopts | Parses arguments to the shell script
| jobs | Lists background (bg) jobs
| pwd | Displays the current directory
| read | Reads a line from standard input
| readonly | Declares as variable as read-only
| set | Lists all variables
| shift | Moves the parameters to the left
| test | Evaluates arguments
| [ | Performs a conditional test
| times | Prints the user and system times
| trap | Traps a signal
| type | Displays how each argument would be interpreted as a command
| umask | Changes the default permissions for a new file
| unset | Deletes values from a variable or function
| wait | Waits for a background process to complete

## Kompression

### Files zu einem Archiv zusammenfügen 
    kali >tar -cvf HackersArise.tar hackersarise1 hackersarise2 hackersarise3

Die 3 Files wurden nun zu einem Archiv zusammengefügt. <br>

### Filearchiv ansehen
Über folgenden Befehl kann das Archiv nun angesehn werden

    kali >tar -tvf HackersArise.tar

### Filearchiv extrahieren
    kali >tar -xvf HackersArise.tar 
---
    kali >tar -xf HackersArise.tar 
(Zeigt die extrahieren Files nicht an)

### Kompression mit gzip
Mit gzip wird ein Archiv komprimiert und braucht so weniger Speicherplatz

    kali >gzip HackersArise.*

Um es wieder zu entpacken gibt es folgenden Befehl:

    gunzip HackersArise.*

### Kompression mit bzip2
bzip2 funktioniert gleich wie gzip hat allerdings eine bessere Kompressionsrate, ist dafür aber langsamer.

    kali >bzip2 HackersArise.*

Um es wieder zu entpacken kann folgender Befehl verwendet werden: 

    kali >bunzip2 HackersArise.*

### Kompression mit compress
Hat die tiefste Kompressionsrate ist dafür aber auch am schnellsten

    kali >compress HackersArise.*

Um es zu entpacken kann folgender Befehl verwendet werden (gunzip Befehl würde auch gehen):

    kali >uncompress HackersArise.*

### Bit-by-Bit Kopie einer Harddisk
Folgender Befehl ermöglicht es die gesamte Festplatte zu kopieren mitsamt den gelöschten Files (Achtung! Sehr langsam):

    dd if=inputfile of=outputfile

Beispiel:

    kali >dd if=/dev/sdb of=/root/flashcopy 
    1257441=0 records in 
    1257440+0 records out 
    7643809280 bytes (7.6 GB) copied, 1220.729 s, 5.2 MB/s 
---
    kali >dd if=/dev/media of=/root/flashcopy bs=4096 conv:noerror 

(Kopiert auch bei Errors weiter mit einer Blocksize von 4096 Bytes was schneller geht)

## Filesystem und Speichermanagement

### Gerätepartitionen
Um eine Speichergerät mit dessen partitionen und Kapazitäten anzeigen zu lassen kann folgender Befehl genutzt werden:

    kali >kali >fdisk -l

Folgender Befehl hat die gleiche Funktion wie der obige zeigt aber die Partitionen als eine Art Baum an:

    kali >lsblk

### Geräte ans Filesystem mounten
Folgender Befehl mountet ein Gerät an ein Ordner (dieser sollte leer sein!):

    kali >mount /dev/sdb1 /mnt

### Geräte unmounten
Nachfolgender Befehl unmountet ein Gerät wieder;

    kali >umount /dev/sdb1

### Gemountete Geräte anzeigen
    kali >df 
    Filesystem          1K-Blocks      Used  Available Use%     Mounted on 
    rootfs               19620732  17096196    1504788  92%     / 
    udev                    10240         0      10240   0%     /dev 
    --snip--<br>
    /dev/sdb1            29823024  29712544     110480  99%     /media/USB3.0 

### Filesystem auf Fehler prüfen
    kali >fsck 

Dieser Befehl prüft das Filesystem auf Fehler. Dazu muss aber zuerst das Gerätun unmountet werden.

    kali >umount /dev/sdb1

Nun kann fsck ausgeführt werden:

    kali >fsck -p /dev/sdb1

Das `-p` Flag repariert automatisch auftauchende Probleme.

## Logging System

### rsyslog
Das Rsyslog File beinhaltet einige Logging Informationen und kann wie folgt geöffnet werden:

    kali >leafpad /etc/rsyslog.conf

Ab Zeile 50 können logging Regeln definiert werden

    mail.* /var/log/mail (=> loggt alles mail Nachrichten in /var/log/mail) 
    kern.crit /var/log/kernel (=> loggt alle kritischen Kernel Nachrichten in /var/log/kern) 
    *.emerg * (=> loggt alle Emergency Nachrichten des Systems)

### logrotate
Innerhalb des logrotate.conf Files kann spezifiziert werden zu welchem Zeitpunkt logs archiviert werden sollen.
Logrotate kann wie folg geöffnet werden:

    kali >leafpad /etc/logrotate.conf

### Unsichtbar bleiben
Mit dem `shred` Befehl werden logfiles gelöscht und mehrere male überschrieben um sich nicht wiederherstellen zu können

    shred -f -n 10 /var/log/auth.log.*
(Überschreibt 10 mal)

Ebenfalls kann das Logging auch einfach **augeschaltet** werden. Dies geht über folgenden Befehl:

    kali >service rsyslog stop

## Services nutzen und missbrauchen

### Services starten, stoppen und neustarten
    kali >service apache2 start
---
    kali >service apache2 stop
---
    kali >service apache2 restart 

### MySQL
MySQL Services starten

    kali >service mysql start

Sich als User einloggen (z.B. root)

    kali >mysql -u root -p

Datenbanken anzeigen lassen

    mysql >show databases;

Datenbank auswählen

    mysql >use mysql;

Passwort setzen

    mysql >update user set password = PASSWORD("hackers-arise") where user = 'root';

Auf eine Remote Datenbank anmelden (z.B. als root)

    kali >mysql -u root -p 192.168.1.101

Tabellen einer Datenbank anzeigen

    show tables;

Struktur einer Tabelle anzeigen
    
    mysql >describe cardnumbers;

Bestimmter Inhalt aus Tabelle anzeigen lassen

    SELECT columns FROM table

(mysql >SELECT * FROM cardnumbers;)

### PostgreSQL
Postgres starten

    kali >service postgresql start

Metasploit mit Postgre verbinden
    
    kali >msfconsole
    msf >msfdb init

Als root einloggen

    msf >su postgres

User und Passwort erstellen

    postgres@kali:/root$ createuser msf_user -P

Neue Datenbank erstellen mit und Berechtigungen vergeben

    postgres@kali:/root$ createdb
    postgres@kali:/root$ exit

Metasploit Konsole mit PostgreSQL Datenbank verbinden

    msf >db_connect msf_user:password@127.0.0.1/hackers_arise_db

Status der Datenbank prüfen
    
    msf >db_status

## Anonym und sicher werden

### IP Pakete verfolgen
Die einzelnen Hops einsehen die ein Paket passiert:

    kali >traceroute google.com 
    traceroute to google.com (172.217.1.78), 30 hops max, 60 bytes packets 
    1   192.168.1.1 (192.168.1.1)   4.152 ms 3.834 ms 32.964 ms 
    2   10.0.0.1 (10.0.0.1)  5.797 ms 6.995 ms 7.679 ms 
    3   96.120.96.45 (96.120.96.45)  27.952 ms 30.377 ms 32.964 ms 
    --snip-- 
    18 lgal15s44-in-f14.le100.net (172.217.1.78)  94.666 ms 42.990 ms 41.564 ms 

### Proxy verwenden
Komando über eine Kette von Proxys verwenden

    kali >proxychains firefox www.hackers-arise.com 
    (Öffnet die URL in Firefox über eine Kette von hinterlegten Proxys)

Proxys für Kette hinterlegen

    kali >leafpad /etc/proxychains.conf 
    [ProxyList] 
    # add proxy here... 
    socks4 114.134.186.12 22020 
    #meanwhile 
    #defaults set to "tor" 
    #socks4 127.0.0.1 9050 

Dynamic Chaining (Es werden mehrere Proxys verwendet) aktivieren (strict_chain und random_chain müssen auskommentiert sein!!)

    kali >leafpad /etc/proxychains.conf 
    dynamic_chain (<= ENTKOMMENTIEREN!!!)<br>
    # 
    # Dynamic – Each connection will be done via chained proxies 
    # all proxies chained in the order as they appear in the list 
    # at least one proxy must be online to play in chain 
    --snip-- 

Random Chaining (Es werden mehrere Proxys in zufälliger Reihenfolge verwendet) aktivieren (strict_chain und dynamic_chain müssen auskommentiert sein!!)

    kali >leafpad /etc/proxychains.conf 
    random_chain (<= ENTKOMMENTIEREN!!!)<br>
    # Random - Each connection will be done via random proxy 
    # (or proxy chain, see chain_len) from the list. 
    # this option is good to test your IDS :) 
    # Makes sense only if random_chain 
    chain_len = 3 (<= Anzahl Proxys anpassen!!!)

## Wireless Netzwerke untersuchen

### Grundlegende Befehle
Wireless Interfaces und dessen Einstellungen anzeigen lassen.

    kali >iwconfig

Wireless Access Points in der Nähe scannen (zeigt alle Infos an)

    kali >iwlist wlan0 scan

Wireless Access Points in der Nähe scannen (Nur Keyinfos)

    kali >nmcli dev wifi

Mit einem WLAN verbinden

    kali >nmcli dev wifi connect Hackers-Arise password 12345678

### Aircrack-ng
WiFi Karte in Monitor Modus schalten (Um Traffic mitlesen zu können)

    airmon-ng start|stop|restart interface <br>
    (kali >airmon-ng start wlan0)

Broadcast Meldungen von WLANs mitlesen

    kali >airodump-ng wlan0mon

Mit Infos aus obigen Befehelen können nun die Daten die zwischen einem Client und dessen AP, mitgelesen werden.

    airodump-ng -c 10 --bssid 01:01:AA:BB:CC:22 -w Hackers-ArisePSK wlan0mon

Nun können alle Clients gezwungen werden sich zu reauthentifizieren

    aireplay-ng --deauth 100 -a 01:01:AA:BB:CC:22-c A0:A3:E2:44:7C:E5 wlan0mon

Die ausgelesenen Hashes können nun mit einer Wörterliste versucht werden zu knacken

    aircrack-ng -w wordlist.dic -b 01:01:AA:BB:CC:22 Hacker-ArisePSK.cap

### BlueZ (Bluetooth)
Ist eine Implementierung des Bluetooth Protokoll Stack und wird zum scannen von Bluetooth Geräten verwendet.

Bluetooth Adapter Informationen und Einstellungen anzeigen

    kali >hciconfig

Adapter aktivieren

    kali >hciconfig hci0 up

Nach anderen Bluetooth Geräten scannen

    kali >hcitool scan

Weitere Informationen von Bluetooth Geräten erhalten

    kali >hcitool inq

Nach den Services auf einem Bluetooth Gerät scannen
    
    kali >sdptool browse 76:6E:46:63:72:66

Ein Bluetooth Gerät anpingen
    
    kali >l2ping 76:6E:46:63:72:66 -c 4

## Kernel verstehen und Module laden

### Grundlegende Kommandos
Die Kernel Version einsehen

    kali >uname -a

Kernel log ansehen

    kali >dmesg

### Kernel konfigurieren
In der Datei *sysctl* lassen sich diverse Kernel Einstellungen anpassen

    kali >sysctl -a | less
    dev.cdrom.autoclose = 1
    dev.cdrom.autoeject = 0
    dev.cdrom.check_media = 0
    dev.cdrom.debug = 0
    --snip--

### Kernel Module verwalten
Alle aktuelle Module im Kernel auflisten:

    kali >lsmod
    Module                        Size       Used by
    nfnetlink_queue               20480      0
    nfnetlink_log                 201480     0
    nfnetlink                     16384      2 nfnetlink_log, nfnetlink_queue
    bluetooth                     516096     0
    rfkill                        0          2 bluetooth
    --snip--

Folgender Befehl zeigt mehr Informationen über ein Modul an (hier Bluetooth):

    kali >modinfo bluetooth
    filename:   /lib/modules/4.6.0-kali-amd64/kernel/net/bluetooth/bluetooth.ko
    alias:      net-pf-31
    license:    GPL
    version:    2.21
    description:Bluetooth Core ver 2.21
    author:     Marcel Holtman <marcel@holtmann.org>
    srcversion: FCFDE98577FEA911A3DAFA9
    depends:    rfkill, crc16
    intree:     Y
    vermagic:   4.6.0-kali1-amd64  SMP mod_unload modversions
    parm:       disable_esco: Disable eSCO connection creation (bool)
    parm:       disable_ertm: Disable enhanced retransmission mode (bool)

Ein Modul zum Kernel hinzufügen:

    kali >modprobe -a <module name>

Ein Modul aus dem Kernel entfernen:

    kali >modprobe -r <module to be removed>

## Jop Scheduling

### Jops automatisch starten
Jops müssen innerhalbt eines Files angegeben werden. Diese File kann wie folg geöffnet werden:

    kali >crontab -e
    Select an editor. To change later, run 'select-editor'.
    1. /bin/nano   <----easiest
    2. /usr/bin/mcedit
    3. /usr/bin/vim.basic
    4. /usr/bin/vim.gtk
    5. /usr/bin/vim.tiny
    Choose 1-5 [1]:

Besser wäre ein bevorzugter editor zu nutzuen mit:

    kali >leafpad /etc/crontab

Die Jops müssen anschliessen wie folg in diesem File eingetragen werden:

    # m h dom mon dow user command
    17 * * * * root cd / && run-parts --report /etc/cron.hourly
    25 6 * * * root test -x /usr/sbin/anacron II ( cd / && run-parts
    47 6 15,30 * 7 root test -x /usr/sbin/anacron II ( cd / && run-parts
    52 6 1 * 0,6 root test -x /usr/sbin/anacron II ( cd / && run-parts
    #

* Unter m kommt die Start Minute (Bei 2:30 = 30)
* Unter h kommt die Start Stunde (Bei 2:30 = 2)
* Unter dow die Wochentage (0-6 = Sonntag bis Samstag)
* dom = Day of Month (bestimmter Tag im Monat)
* Mon = Month (bestimmter Monat 0-11)
* Ein * bedeutet **any**

### Jops bei Betriebssystemstart ausführen
Services können mithilfe des rc.d Skript bei Betriebssystemstart mitgestartet werden. Dafür ist das update-rc.d Kommando gedacht:

    kali >update-rc.d <name of the script or service> <remove|defaults|disable|enable>