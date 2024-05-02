
# Git auf Windows installieren
Git kann ganz einfach über die [.exe](https://git-scm.com/download/win) installiert werden oder über das winget tool
```bash
winget install --id Git.Git -e --source winget
```

Bei der Installation über die executable Datei, sind folgende Schritte im Installer notwendig:
1. Executable ausführen
2. Lizenz akzeptieren
3. Installationspfad angeben
4. Zu installierende Komponenten auswählen (Die Standard Auswahl ist meist vollkommen ausreichend)
5. Start Menü Order festlegen
6. Bei der Editor-Auswahl "Vim" auswählen
7. Den Standard Branch Namen durch das untere Auswahlmenü auf "main" setzen
8. Git erlauben durch die Befehlszeile und Drittanbietersoftware genutzt zu werden
9. "Use bundeled OpenSSH" auswählen
10. "Use the OpenSSL library" auswählen
11. "Checkout Windows-style, commit Unix style line endings" auswählen
12. "Use Windows' default console window" auswählen
13. "Fast-forward or merge" auswählen
14. "Git Credential Manager" auswählen
15. "Enable file system caching" auswählen
16. Installation abschließen

# Name und Email hinterlegen 
```bash
git config --global user.name "Name" 
git config --global user.email "Email"  
```
Diese Informationen werden genutzt um bei commits den Bearbeiter zu setzen.
 
# Account auf GitHub erstellen 
www.github.com 

# Login auf SSH umstellen 
## Schlüssel erzeugen
SSH-Key erzeugen und den Public key in GitHUB hochladen 
```bash
ssh-keygen –b 4096 
```
 
## SSH- key in der config hinterlegen 
In Datei: `.ssh/config` 
```bash
Host github.com 
  IdentityFile ~/.ssh/privatKeyForGitHub 
```

Wenn verschiedene keys verwendet werden sollen. Z.B. für Arbeitsrepos: 
Zusätzlich eintragen: 
```bash
Host github-work.com 
  Hostname   github.com 
  IdentityFile  ~/.ssh/privateKeyForGitHubWork 
```
Dann muss beim ersten `git clone` die Url github-work verwendet werden. Damit die Umleitung zum anderen Key funktioniert. 
```bash
git clone git@github-work.com:ACCOUNT/REPO.git 
```
 
# Repository auf SSH umstellen 
```bash
git remote set-url origin git@github.com:ACCOUNT/REPO.git 
```
 

 
