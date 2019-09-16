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