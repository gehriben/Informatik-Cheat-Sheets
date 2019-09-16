Git Befehle
============

**Git Repository einrichten**

    #In das root Verzeichnis wechseln
    cd C:\Users\benig\Documents\_Benjamin\Studium\Semester 2\Programmieren 2\Übungen\PROG2-lab-IT17bWIN>
	
    #Neues Git Repository ziehen
    git clone https://github.engineering.zhaw.ch/widtmbri/TaskList.git
    
    #origin prüfen
    git remote -v

    #origin hinzufügen
    git remote add origin git@github.engineering.zhaw.ch:mustepet/PROG2-lab-ITxxx

    #upstream hinzufügen
    git remote add upstream git@github.engineering.zhaw.ch:mustepet/PROG2-lab-ITxxx

    #Branch wechseln
    git checkout gehriben


**Aktueller Repository Status**

    git status

**Git Commits**

    #Bisherige Commits ansehen
    git log

    #Statged oder unstaged files ansehen
    #git Status

    #Files statged (um zu commiten)
    git add .

    #Änderungen commiten
    git commit -a -m "Message"

    #Letze commit Message ändern
    git commit --amend -m "Message"

    #Commit pushen (ERST NACH COMMITEN!)
    git push -u origin gehriben

**Git Branches**

    #Branch wechseln
    git checkout [branchname]

    #Create branch on local Machine
    git checkout -b [branchname]

    #Einen Branch zurück in den oberen Branch mergen
    1. in den oberen Branch wechseln
    2. git merge [name unterbranch]

    #Branch löschen
    git branch -d [name]
