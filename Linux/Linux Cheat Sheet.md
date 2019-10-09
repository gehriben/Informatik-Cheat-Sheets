# Linux Cheat Sheet
Ein Cheat Sheet für diverse Linux Befehle

## Inhaltsverzeichnis

* 1. [Basiskommandos](#Basiskommandos)
	* 1.1. [Aktueller Ordnerstandort](#AktuellerOrdnerstandort)
	* 1.2. [Angemeldeter Benutzer](#AngemeldeterBenutzer)
* 2. [Dateinavigation](#Dateinavigation)
	* 2.1. [Ordner wechseln](#Ordnerwechseln)
	* 2.2. [Ordnerinhalt auflisten](#Ordnerinhaltauflisten)
* 3. [Hilfe erhalten](#Hilfeerhalten)
	* 3.1. [Referenz Manual](#ReferenzManual)
* 4. [Suche](#Suche)
	* 4.1. [locate - Befehl](#locate-Befehl)
	* 4.2. [whereis - Befehl](#whereis-Befehl)
	* 4.3. [which - Befehl](#which-Befehl)
	* 4.4. [find - Befehl](#find-Befehl)
	* 4.5. [grep - Befehl](#grep-Befehl)
* 5. [Files und Ordner modifizieren](#FilesundOrdnermodifizieren)
	* 5.1. [File erstellen](#Fileerstellen)
	* 5.2. [File anschauen](#Fileanschauen)
	* 5.3. [Text zu Textfile hinzufügen](#TextzuTextfilehinzufgen)
	* 5.4. [Ordner erstellen](#Ordnererstellen)
	* 5.5. [File kopieren](#Filekopieren)
	* 5.6. [File umbenennen](#Fileumbenennen)
	* 5.7. [File löschen](#Filelschen)
	* 5.8. [Ordner löschen](#Ordnerlschen)
* 6. [Text Manipulation](#TextManipulation)
	* 6.1. [Kopfzeilen anschauen](#Kopfzeilenanschauen)
	* 6.2. [Fusszeilen anzeigen](#Fusszeilenanzeigen)
	* 6.3. [Zeilen nummerieren](#Zeilennummerieren)
	* 6.4. [Text mit grep Filtern](#TextmitgrepFiltern)
	* 6.5. [Suchen und ersetzen](#Suchenundersetzen)
	* 6.6. [Files mit more und less anschauen](#Filesmitmoreundlessanschauen)
* 7. [Netwerkanalyse](#Netwerkanalyse)
	* 7.1. [Netzwerkinformationen anzeigen](#Netzwerkinformationenanzeigen)
	* 7.2. [Wirelessgerät kontrollieren](#Wirelessgertkontrollieren)
	* 7.3. [IP Adresse ändern](#IPAdressendern)
	* 7.4. [Netzwerkmaske und Broadcastadresse ändern](#NetzwerkmaskeundBroadcastadressendern)
	* 7.5. [MAC Adresse ändern (spoofen)](#MACAdressendernspoofen)
	* 7.6. [Neue IP vom DHCP anfordern](#NeueIPvomDHCPanfordern)
	* 7.7. [DNS Informationen erhalten](#DNSInformationenerhalten)
	* 7.8. [Eigener DNS Server ändern](#EigenerDNSServerndern)
* 8. [Software installieren und löschen](#Softwareinstallierenundlschen)
	* 8.1. [Ein Paket suchen](#EinPaketsuchen)
	* 8.2. [Software hinzufügen](#Softwarehinzufgen)
	* 8.3. [Software löschen](#Softwarelschen)
	* 8.4. [Softwareliste aktualisiern](#Softwarelisteaktualisiern)
	* 8.5. [Software aktualisiern](#Softwareaktualisiern)
	* 8.6. [Weiter Repositorys hinzufügen](#WeiterRepositoryshinzufgen)
* 9. [Berechtigungen kontrollieren](#Berechtigungenkontrollieren)
	* 9.1. [Besitzerrechte an User vergeben](#BesitzerrechteanUservergeben)
	* 9.2. [Besitzerrechte an Gruppe vergeben](#BesitzerrechteanGruppevergeben)
	* 9.3. [Berechtigungen prüfen](#Berechtigungenprfen)
	* 9.4. [Berechtigungen ändern](#Berechtigungenndern)
* 10. [Prozess Management](#ProzessManagement)
	* 10.1. [Prozesse anzeigen](#Prozesseanzeigen)
	* 10.2. [Nach Prozessnamen filtern](#NachProzessnamenfiltern)
	* 10.3. [Nach Ressourcenverbrauch sortieren](#NachRessourcenverbrauchsortieren)
	* 10.4. [Prozesspriorität verwalten](#Prozesspriorittverwalten)
	* 10.5. [Prozess töten](#Prozesstten)
	* 10.6. [Prozess im Hintergrund laufen lassen](#ProzessimHintergrundlaufenlassen)
	* 10.7. [Prozess wieder in Vordergrund bringen](#ProzesswiederinVordergrundbringen)
	* 10.8. [Prozess schedulen](#Prozessschedulen)
* 11. [Userumgebungsvariablen verwalten](#Userumgebungsvariablenverwalten)
	* 11.1. [Variablen ansehen und modifizieren](#Variablenansehenundmodifizieren)
	* 11.2. [Terminal Fenster ändern](#TerminalFensterndern)
	* 11.3. [PATH Variable ändern](#PATHVariablendern)
	* 11.4. [Eine Userdefinierte Variable erstellen](#EineUserdefinierteVariableerstellen)
* 12. [Bash Scripting](#BashScripting)
	* 12.1. [Beispielskripte](#Beispielskripte)
	* 12.2. [Skripte ausführen](#Skripteausfhren)
	* 12.3. [Nützliche Kommandos für bash](#NtzlicheKommandosfrbash)
* 13. [Kompression](#Kompression)
	* 13.1. [Files zu einem Archiv zusammenfügen](#FileszueinemArchivzusammenfgen)
	* 13.2. [Filearchiv ansehen](#Filearchivansehen)
	* 13.3. [Filearchiv extrahieren](#Filearchivextrahieren)
	* 13.4. [Kompression mit gzip](#Kompressionmitgzip)
	* 13.5. [Kompression mit bzip2](#Kompressionmitbzip2)
	* 13.6. [Kompression mit compress](#Kompressionmitcompress)
	* 13.7. [Bit-by-Bit Kopie einer Harddisk](#Bit-by-BitKopieeinerHarddisk)
* 14. [Filesystem und Speichermanagement](#FilesystemundSpeichermanagement)
	* 14.1. [Gerätepartitionen](#Gertepartitionen)
	* 14.2. [Geräte ans Filesystem mounten](#GerteansFilesystemmounten)
	* 14.3. [Geräte unmounten](#Gerteunmounten)
	* 14.4. [Gemountete Geräte anzeigen](#GemounteteGerteanzeigen)
	* 14.5. [Filesystem auf Fehler prüfen](#FilesystemaufFehlerprfen)
* 15. [Logging System](#LoggingSystem)
	* 15.1. [rsyslog](#rsyslog)
	* 15.2. [logrotate](#logrotate)
	* 15.3. [Unsichtbar bleiben](#Unsichtbarbleiben)
* 16. [Services nutzen und missbrauchen](#Servicesnutzenundmissbrauchen)
	* 16.1. [Services starten, stoppen und neustarten](#Servicesstartenstoppenundneustarten)
	* 16.2. [MySQL](#MySQL)
	* 16.3. [PostgreSQL](#PostgreSQL)
* 17. [Anonym und sicher werden](#Anonymundsicherwerden)
	* 17.1. [IP Pakete verfolgen](#IPPaketeverfolgen)
	* 17.2. [Proxy verwenden](#Proxyverwenden)
* 18. [Wireless Netzwerke untersuchen](#WirelessNetzwerkeuntersuchen)
	* 18.1. [Grundlegende Befehle](#GrundlegendeBefehle)
	* 18.2. [Aircrack-ng](#Aircrack-ng)
	* 18.3. [BlueZ (Bluetooth)](#BlueZBluetooth)
* 19. [Kernel verstehen und Module laden](#KernelverstehenundModuleladen)
	* 19.1. [Grundlegende Kommandos](#GrundlegendeKommandos)
	* 19.2. [Kernel konfigurieren](#Kernelkonfigurieren)
	* 19.3. [Kernel Module verwalten](#KernelModuleverwalten)
* 20. [Jop Scheduling](#JopScheduling)
	* 20.1. [Jops automatisch starten](#Jopsautomatischstarten)
	* 20.2. [Jops bei Betriebssystemstart ausführen](#JopsbeiBetriebssystemstartausfhren)

##  1. <a name='Basiskommandos'></a>Basiskommandos
Kommandos um sich in Linux zurechtzufinden
 
###  1.1. <a name='AktuellerOrdnerstandort'></a>Aktueller Ordnerstandort
Zeigt an in welchem Ordner man gerade ist
    
    kali >pwd
    /root 

###  1.2. <a name='AngemeldeterBenutzer'></a>Angemeldeter Benutzer
    kali >whoami
    root 

##  2. <a name='Dateinavigation'></a>Dateinavigation
Einige Kommandos um durch das Filesystem zu navigiern

###  2.1. <a name='Ordnerwechseln'></a>Ordner wechseln
In ein Ordner navigiern

    kali >cd /etc 
    root@kali: /etc#

Ein Ordner hoch navigieren

    kali >cd ..
    root@kali: /#

###  2.2. <a name='Ordnerinhaltauflisten'></a>Ordnerinhalt auflisten
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

##  3. <a name='Hilfeerhalten'></a>Hilfe erhalten
    kali >aircrack-ng --help
    kali >nmap -h

###  3.1. <a name='ReferenzManual'></a>Referenz Manual
    kali >man nmap

##  4. <a name='Suche'></a>Suche

###  4.1. <a name='locate-Befehl'></a>locate - Befehl
    kali >locate aircrack-ng
    /usr/bin/aircrack-ng
    /usr/share/applications/kali-aircrack-ng.desktop
    /usr/share/desktop-directories/05-1-01-aircrack-ng.directory
    --snip--
    /var/lib/dpkg/info/aircrack-ng.mg5sums

###  4.2. <a name='whereis-Befehl'></a>whereis - Befehl
Sucht Binary Files

    kali >whereis aircrack-ng
    aircarck-ng: /usr/bin/aircarck-ng /usr/share/man/man1/aircarck-ng.1.gz

###  4.3. <a name='which-Befehl'></a>which - Befehl
Gibt nur jenes Binary File zurück dass in der PATH Variable ist

    kali >which aircrack-ng
    /usr/bin/aircrack-ng

###  4.4. <a name='find-Befehl'></a>find - Befehl
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

###  4.5. <a name='grep-Befehl'></a>grep - Befehl
Filtert ein Textinput nach einem gewissen Suchbegriff
    kali >ps aux | grep apache2 
    root  4851 0.2 0.7 37548  7668 ?  Ss  10:14  0:00   /usr/sbin/apache2 -k start 
    root  4906 0.0 0.4 37572  4228 ?  S   10:14  0:00   /usr/sbin/apache2 -k start 
    root  4910 0.0 0.4 37572  4228 ?  Ss  10:14  0:00   /usr/sbin/apache2 -k start 
    --snip-- 

##  5. <a name='FilesundOrdnermodifizieren'></a>Files und Ordner modifizieren

###  5.1. <a name='Fileerstellen'></a>File erstellen
> kali >cat > hackingskills 
Hacking is the most valuable skill set of the 21st century!

> kali >touch newfile

###  5.2. <a name='Fileanschauen'></a>File anschauen
kali >cat hackingskills 
Hacking is the most valuable skill set of the 21st century!

###  5.3. <a name='TextzuTextfilehinzufgen'></a>Text zu Textfile hinzufügen
    kali >cat >> hackingskills 
    Everyone should learn hacking

###  5.4. <a name='Ordnererstellen'></a>Ordner erstellen
    kali >mkdir newdirectory

###  5.5. <a name='Filekopieren'></a>File kopieren 
    kali >cp oldfile  /root/newdirectory/newfile

###  5.6. <a name='Fileumbenennen'></a>File umbenennen
    kali >mv newfile newfile2

###  5.7. <a name='Filelschen'></a>File löschen
    kali >rm newfile2

###  5.8. <a name='Ordnerlschen'></a>Ordner löschen
Bei diesem Befehl muss der Ordner leer sein

    kali >rmdir newdirectory 
    rmdir:failed to remove 'newdirectory': Directory not empty

So werden auch gefüllte Ordner gelöscht
> kali >rm -r newdirectory

##  6. <a name='TextManipulation'></a>Text Manipulation

###  6.1. <a name='Kopfzeilenanschauen'></a>Kopfzeilen anschauen
Zeigt die 10 ersten Zeilen an

    kali >head /etc/snort/snort.conf 
    -------------------------------------------------------------- 
    VRT Rules Packages Snort.conf 
    
        For more information visit us at: 
    --snip-- 
    Snort bugs:bugs@snort.org 

Anzahl Zeilen können auch selbst definiert werden

    kali >head -20 /etc/snort/snort.conf

###  6.2. <a name='Fusszeilenanzeigen'></a>Fusszeilen anzeigen
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

###  6.3. <a name='Zeilennummerieren'></a>Zeilen nummerieren
    kali >nl /etc/snort/snort.conf 
    612 ################################################################# 
    613 #dynamic library rules 
    614 #include $SO_RULE_PATH/bad-traffic.rules 
    615 #include $SO_RULE_PATH/chat.rules 
    --snip-- 
    630 #include $SO_RULE_PATH/web-iis.rules 
    631 #include $SO_RULE_PATH/web-misc.rules 

###  6.4. <a name='TextmitgrepFiltern'></a>Text mit grep Filtern
    kali >cat /etc/snort/snort.conf | grep output

###  6.5. <a name='Suchenundersetzen'></a>Suchen und ersetzen
Sucht nach mysql und ersetzt es durch MySQL was wiederum in snort2.conf gespeichert wird¨

    kali >sed s/mysql/MySQL/g /etc/snort/snort.conf > snort2.conf

###  6.6. <a name='Filesmitmoreundlessanschauen'></a>Files mit more und less anschauen
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

##  7. <a name='Netwerkanalyse'></a>Netwerkanalyse

###  7.1. <a name='Netzwerkinformationenanzeigen'></a>Netzwerkinformationen anzeigen
    kali >ifconfig

###  7.2. <a name='Wirelessgertkontrollieren'></a>Wirelessgerät kontrollieren
    kali >iwconfig 
    wlan0 IEEE 802.11bg ESSID:off/any 
    Mode:Managed Access Point: Not Associated Tx-Power=20 dBm 
    --snip-- 
    lo    no wireless extensions 
    eth0  no wireless extensions 

###  7.3. <a name='IPAdressendern'></a>IP Adresse ändern
    kali >ifconfig eth0 192.168.181.115

###  7.4. <a name='NetzwerkmaskeundBroadcastadressendern'></a>Netzwerkmaske und Broadcastadresse ändern
    kali >ifconfig eth0 192.168.181.115 netmask 255.255.0.0 broadcast 192.168.1.255

###  7.5. <a name='MACAdressendernspoofen'></a>MAC Adresse ändern (spoofen)
    kali >ifconfig eth0 down 
    kali >ifconfig eth0 hw ether 00:11:22:33:44:55 
    kali >ifconfig eth0 up 

###  7.6. <a name='NeueIPvomDHCPanfordern'></a>Neue IP vom DHCP anfordern
    kali >dhclient eth0

###  7.7. <a name='DNSInformationenerhalten'></a>DNS Informationen erhalten
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

###  7.8. <a name='EigenerDNSServerndern'></a>Eigener DNS Server ändern
    kali >echo "nameserver 8.8.8.8"> /etc/resolv.conf

##  8. <a name='Softwareinstallierenundlschen'></a>Software installieren und löschen

###  8.1. <a name='EinPaketsuchen'></a>Ein Paket suchen

    apt-cache search keyword

###  8.2. <a name='Softwarehinzufgen'></a>Software hinzufügen

    apt-get install packagename

###  8.3. <a name='Softwarelschen'></a>Software löschen

    kali >apt-get remove snort

Der obige Befehl löscht das Paket nicht komplett sondern behält dessen Konfigurationsfiles. Um ein Paket komplett zu löschen kann folgender Befehl verwendet werden:

    kali >apt-get purge  snort

###  8.4. <a name='Softwarelisteaktualisiern'></a>Softwareliste aktualisiern
Folgender Befehl updatet die Softwarerepositorys und prüft ob neue Software hinzugefügt wurde:

    kali >apt-get update

###  8.5. <a name='Softwareaktualisiern'></a>Software aktualisiern
Folgender Befehl aktualisiert effektiv Software auf die neuste Version

    kali >apt-get upgrade   

###  8.6. <a name='WeiterRepositoryshinzufgen'></a>Weiter Repositorys hinzufügen
Die obigen Befehle suchen die angegeben Software aus Repositorys. Diese werden in folgender Date verlinkt und können dort ergänzt werden:

    kali >leafpad /etc/apt/sources.list

Es gibt dabei verschiedene Arten von Repositorys:

**main** Contains supported open source software <br>
**universe** Contains community-maintained open source <br>
**multiverse** Contains software restricted by copyright issues <br>
**restricted** Contains proprietary device drivers <br>
**backports** Contains packages from later releases <br>

##  9. <a name='Berechtigungenkontrollieren'></a>Berechtigungen kontrollieren

###  9.1. <a name='BesitzerrechteanUservergeben'></a>Besitzerrechte an User vergeben

    kali >chown ubob v/tmp/bobsfile

###  9.2. <a name='BesitzerrechteanGruppevergeben'></a>Besitzerrechte an Gruppe vergeben

    kali >chgrp usecurity /etct/vnewIDS

###  9.3. <a name='Berechtigungenprfen'></a>Berechtigungen prüfen

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

###  9.4. <a name='Berechtigungenndern'></a>Berechtigungen ändern

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

##  10. <a name='ProzessManagement'></a>Prozess Management

###  10.1. <a name='Prozesseanzeigen'></a>Prozesse anzeigen

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

###  10.2. <a name='NachProzessnamenfiltern'></a>Nach Prozessnamen filtern

    kali >ps aux | grep msfconsole
    root 39756  0.0  0.0  4304  716  pts/2 Ss+  15:13  0:00 sh -c service 
    postgresql start && msfdb init & msfconsole
    root 39759  35.1  15.2  4304  227888  pts/2 Sl+  15:13  1:36 ruby /usr/bin/
    msfconsole
    root 39892  0.0  0.0  4304  940  pts/2 S+  15:18  0:00 grep msfconsole

###  10.3. <a name='NachRessourcenverbrauchsortieren'></a>Nach Ressourcenverbrauch sortieren

    kali >top

###  10.4. <a name='Prozesspriorittverwalten'></a>Prozesspriorität verwalten
Die Prioritäten gehen von **-20** bis **19**, wobei -20 am **höchtsten** und **19** am tiefsten priorisiert ist

Mit folgendem Befehl wird ein Prozess mit entsprechender Priorität gestartet. Dies erhöht die Priorität der Prozesses um 10 (Setzt es **nicht** auf -10!!!)

    kali >nice  -n -10 /bin/slowprocess

Folgender Befehl ändert die Priorität eines laufenden Prozesses. Die Priorität wird fix gesetzt nicht wie oben addiert oder subtrahiert!

    kali >renice 15 6996

###  10.5. <a name='Prozesstten'></a>Prozess töten
Folgender Befehl beendet und startet den Prozess neu:

    kali >kill -1 6996

Folgender Befhel beendet den Prozess sofort:

    kali >kill -9 6996

    kali >killall -9 zombieprocess

###  10.6. <a name='ProzessimHintergrundlaufenlassen'></a>Prozess im Hintergrund laufen lassen

    kali >leafpad newscript &

Nun kann die Konsole weiterhin benutzt werden während leafpad geöffnet ist.

###  10.7. <a name='ProzesswiederinVordergrundbringen'></a>Prozess wieder in Vordergrund bringen

    kali >fg 1234

###  10.8. <a name='Prozessschedulen'></a>Prozess schedulen

    kali >at 7:20am
    at >/root/myscanningscript

##  11. <a name='Userumgebungsvariablenverwalten'></a>Userumgebungsvariablen verwalten

###  11.1. <a name='Variablenansehenundmodifizieren'></a>Variablen ansehen und modifizieren
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

###  11.2. <a name='TerminalFensterndern'></a>Terminal Fenster ändern

    kali >PS1="World's Best Hacker
    World's Best Hacker: #
    kali >export PS1

    kali >export PS1='C:\w> '
    C:/tmp>

###  11.3. <a name='PATHVariablendern'></a>PATH Variable ändern
PATH Variable ansehen:

    kali >echo $PATH
    /usr/local/sbin:usr/local/bin:/usr/sbin:/sbin/bin

Der PATH Variable etwas hinzufügen

    kali >PATH=$PATH:/root/newhackingtool

###  11.4. <a name='EineUserdefinierteVariableerstellen'></a>Eine Userdefinierte Variable erstellen

    kali >MYNEWVARIABLE="Hacking is the most valuable skill set in the 21st century"

    kali >echo $MYNEWVARIABLE
    Hacking is the most valuable skill set in the 21st century

Diese Variable kann wie folgt wieder gelöscht werden:

    kali >unset MYNEWVARIABLE

##  12. <a name='BashScripting'></a>Bash Scripting

###  12.1. <a name='Beispielskripte'></a>Beispielskripte
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

###  12.2. <a name='Skripteausfhren'></a>Skripte ausführen

    kali >./MySQLscannerAdvanced.sh 

###  12.3. <a name='NtzlicheKommandosfrbash'></a>Nützliche Kommandos für bash

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

##  13. <a name='Kompression'></a>Kompression

###  13.1. <a name='FileszueinemArchivzusammenfgen'></a>Files zu einem Archiv zusammenfügen 
    kali >tar -cvf HackersArise.tar hackersarise1 hackersarise2 hackersarise3

Die 3 Files wurden nun zu einem Archiv zusammengefügt. <br>

###  13.2. <a name='Filearchivansehen'></a>Filearchiv ansehen
Über folgenden Befehl kann das Archiv nun angesehn werden

    kali >tar -tvf HackersArise.tar

###  13.3. <a name='Filearchivextrahieren'></a>Filearchiv extrahieren
    kali >tar -xvf HackersArise.tar 
---
    kali >tar -xf HackersArise.tar 
(Zeigt die extrahieren Files nicht an)

###  13.4. <a name='Kompressionmitgzip'></a>Kompression mit gzip
Mit gzip wird ein Archiv komprimiert und braucht so weniger Speicherplatz

    kali >gzip HackersArise.*

Um es wieder zu entpacken gibt es folgenden Befehl:

    gunzip HackersArise.*

###  13.5. <a name='Kompressionmitbzip2'></a>Kompression mit bzip2
bzip2 funktioniert gleich wie gzip hat allerdings eine bessere Kompressionsrate, ist dafür aber langsamer.

    kali >bzip2 HackersArise.*

Um es wieder zu entpacken kann folgender Befehl verwendet werden: 

    kali >bunzip2 HackersArise.*

###  13.6. <a name='Kompressionmitcompress'></a>Kompression mit compress
Hat die tiefste Kompressionsrate ist dafür aber auch am schnellsten

    kali >compress HackersArise.*

Um es zu entpacken kann folgender Befehl verwendet werden (gunzip Befehl würde auch gehen):

    kali >uncompress HackersArise.*

###  13.7. <a name='Bit-by-BitKopieeinerHarddisk'></a>Bit-by-Bit Kopie einer Harddisk
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

##  14. <a name='FilesystemundSpeichermanagement'></a>Filesystem und Speichermanagement

###  14.1. <a name='Gertepartitionen'></a>Gerätepartitionen
Um eine Speichergerät mit dessen partitionen und Kapazitäten anzeigen zu lassen kann folgender Befehl genutzt werden:

    kali >kali >fdisk -l

Folgender Befehl hat die gleiche Funktion wie der obige zeigt aber die Partitionen als eine Art Baum an:

    kali >lsblk

###  14.2. <a name='GerteansFilesystemmounten'></a>Geräte ans Filesystem mounten
Folgender Befehl mountet ein Gerät an ein Ordner (dieser sollte leer sein!):

    kali >mount /dev/sdb1 /mnt

###  14.3. <a name='Gerteunmounten'></a>Geräte unmounten
Nachfolgender Befehl unmountet ein Gerät wieder;

    kali >umount /dev/sdb1

###  14.4. <a name='GemounteteGerteanzeigen'></a>Gemountete Geräte anzeigen
    kali >df 
    Filesystem          1K-Blocks      Used  Available Use%     Mounted on 
    rootfs               19620732  17096196    1504788  92%     / 
    udev                    10240         0      10240   0%     /dev 
    --snip--<br>
    /dev/sdb1            29823024  29712544     110480  99%     /media/USB3.0 

###  14.5. <a name='FilesystemaufFehlerprfen'></a>Filesystem auf Fehler prüfen
    kali >fsck 

Dieser Befehl prüft das Filesystem auf Fehler. Dazu muss aber zuerst das Gerätun unmountet werden.

    kali >umount /dev/sdb1

Nun kann fsck ausgeführt werden:

    kali >fsck -p /dev/sdb1

Das `-p` Flag repariert automatisch auftauchende Probleme.

##  15. <a name='LoggingSystem'></a>Logging System

###  15.1. <a name='rsyslog'></a>rsyslog
Das Rsyslog File beinhaltet einige Logging Informationen und kann wie folgt geöffnet werden:

    kali >leafpad /etc/rsyslog.conf

Ab Zeile 50 können logging Regeln definiert werden

    mail.* /var/log/mail (=> loggt alles mail Nachrichten in /var/log/mail) 
    kern.crit /var/log/kernel (=> loggt alle kritischen Kernel Nachrichten in /var/log/kern) 
    *.emerg * (=> loggt alle Emergency Nachrichten des Systems)

###  15.2. <a name='logrotate'></a>logrotate
Innerhalb des logrotate.conf Files kann spezifiziert werden zu welchem Zeitpunkt logs archiviert werden sollen.
Logrotate kann wie folg geöffnet werden:

    kali >leafpad /etc/logrotate.conf

###  15.3. <a name='Unsichtbarbleiben'></a>Unsichtbar bleiben
Mit dem `shred` Befehl werden logfiles gelöscht und mehrere male überschrieben um sich nicht wiederherstellen zu können

    shred -f -n 10 /var/log/auth.log.*
(Überschreibt 10 mal)

Ebenfalls kann das Logging auch einfach **augeschaltet** werden. Dies geht über folgenden Befehl:

    kali >service rsyslog stop

##  16. <a name='Servicesnutzenundmissbrauchen'></a>Services nutzen und missbrauchen

###  16.1. <a name='Servicesstartenstoppenundneustarten'></a>Services starten, stoppen und neustarten
    kali >service apache2 start
---
    kali >service apache2 stop
---
    kali >service apache2 restart 

###  16.2. <a name='MySQL'></a>MySQL
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

###  16.3. <a name='PostgreSQL'></a>PostgreSQL
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

##  17. <a name='Anonymundsicherwerden'></a>Anonym und sicher werden

###  17.1. <a name='IPPaketeverfolgen'></a>IP Pakete verfolgen
Die einzelnen Hops einsehen die ein Paket passiert:

    kali >traceroute google.com 
    traceroute to google.com (172.217.1.78), 30 hops max, 60 bytes packets 
    1   192.168.1.1 (192.168.1.1)   4.152 ms 3.834 ms 32.964 ms 
    2   10.0.0.1 (10.0.0.1)  5.797 ms 6.995 ms 7.679 ms 
    3   96.120.96.45 (96.120.96.45)  27.952 ms 30.377 ms 32.964 ms 
    --snip-- 
    18 lgal15s44-in-f14.le100.net (172.217.1.78)  94.666 ms 42.990 ms 41.564 ms 

###  17.2. <a name='Proxyverwenden'></a>Proxy verwenden
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

##  18. <a name='WirelessNetzwerkeuntersuchen'></a>Wireless Netzwerke untersuchen

###  18.1. <a name='GrundlegendeBefehle'></a>Grundlegende Befehle
Wireless Interfaces und dessen Einstellungen anzeigen lassen.

    kali >iwconfig

Wireless Access Points in der Nähe scannen (zeigt alle Infos an)

    kali >iwlist wlan0 scan

Wireless Access Points in der Nähe scannen (Nur Keyinfos)

    kali >nmcli dev wifi

Mit einem WLAN verbinden

    kali >nmcli dev wifi connect Hackers-Arise password 12345678

###  18.2. <a name='Aircrack-ng'></a>Aircrack-ng
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

###  18.3. <a name='BlueZBluetooth'></a>BlueZ (Bluetooth)
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

##  19. <a name='KernelverstehenundModuleladen'></a>Kernel verstehen und Module laden

###  19.1. <a name='GrundlegendeKommandos'></a>Grundlegende Kommandos
Die Kernel Version einsehen

    kali >uname -a

Kernel log ansehen

    kali >dmesg

###  19.2. <a name='Kernelkonfigurieren'></a>Kernel konfigurieren
In der Datei *sysctl* lassen sich diverse Kernel Einstellungen anpassen

    kali >sysctl -a | less
    dev.cdrom.autoclose = 1
    dev.cdrom.autoeject = 0
    dev.cdrom.check_media = 0
    dev.cdrom.debug = 0
    --snip--

###  19.3. <a name='KernelModuleverwalten'></a>Kernel Module verwalten
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

##  20. <a name='JopScheduling'></a>Jop Scheduling

###  20.1. <a name='Jopsautomatischstarten'></a>Jops automatisch starten
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

###  20.2. <a name='JopsbeiBetriebssystemstartausfhren'></a>Jops bei Betriebssystemstart ausführen
Services können mithilfe des rc.d Skript bei Betriebssystemstart mitgestartet werden. Dafür ist das update-rc.d Kommando gedacht:

    kali >update-rc.d <name of the script or service> <remove|defaults|disable|enable>