# Debian-Based-AI-Developer-Server

Testumgebung für OpenAI auf deinem Debian-System unter Windows Subsystem for Linux (WSL) zu erstellen, sind folgende Schritte erforderlich:

Installieren von Python: Debian kommt mit Python 3.7 vorinstalliert, aber es ist wahrscheinlich, dass du die neueste Version von Python möchtest. Hier sind die Schritte, um Python zu aktualisieren:

Zuerst aktualisiere deinen Paketmanager. Führe in der Befehlszeile aus:

```bash
sudo apt-get update
sudo apt-get upgrade
Als nächstes installiere die erforderlichen Abhängigkeiten. Führe aus:
```
```bash
sudo apt-get install -y make build-essential libssl-dev zlib1g-dev libbz2-dev \
libreadline-dev libsqlite3-dev wget curl llvm libncurses5-dev libncursesw5-dev \
xz-utils tk-dev libffi-dev liblzma-dev git openssh-server

```
Dann installiere pyenv, ein Tool zum Verwalten von Python-Versionen. Führe aus:

```bash
curl https://pyenv.run | bash
```
Füge pyenv zu deinem Shell-Startskript hinzu. Führe aus:

```bash
echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.bashrc
echo 'export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.bashrc
echo -e 'if command -v pyenv 1>/dev/null 2>&1; then\n  eval "$(pyenv init -)"\nfi' >> ~/.bashrc
exec "$SHELL"
```
Schließlich installiere die neueste Python-Version mit pyenv. Führe aus:

```bash

pyenv install 3.9.5
pyenv global 3.9.5
```
Überprüfe deine Python-Version mit:

```bash

python --version
```
Installieren von pip: pip ist der Paketmanager von Python, den du verwenden wirst, um die OpenAI-Bibliothek zu installieren. In der neuesten Version von Python sollte pip vorinstalliert sein. Du kannst dies überprüfen, indem du in der Befehlszeile ausführst:

```bash
pip --version
```
Wenn pip nicht installiert ist, kannst du es mit folgendem Befehl installieren:

```bash

sudo apt install python3-pip
```
Installieren der OpenAI-Bibliothek: Mit pip kannst du die OpenAI-Bibliothek installieren. Führe in der Befehlszeile aus:

```bash
pip install openai
```

## Optional (usefull)

`requests`: Dies ist eine grundlegende Bibliothek zum Senden von HTTP-Anfragen. Sie ist sehr nützlich, wenn du direkt mit der OpenAI API interagieren möchtest, anstatt die offizielle OpenAI-Bibliothek zu verwenden.

```bash
pip install requests
```
`click`: Diese Bibliothek hilft dir bei der Erstellung von schönen Command Line Interfaces. Sie hat viele Funktionen, die dir das Leben leichter machen, wie z.B. die automatische Erzeugung von Hilfeseiten und die Unterstützung für Befehlsgruppen und Argumente.

```bash
pip install click
```
`python-dotenv`: Damit kannst du Umgebungsvariablen aus einer .env-Datei in deinem Projekt laden. Das ist sehr nützlich, um sensible Informationen wie deinen OpenAI API-Schlüssel sicher zu speichern.

```bash
pip install python-dotenv
```
`pytest`: Dies ist eine Testbibliothek für Python, mit der du sicherstellen kannst, dass dein CLI-Tool wie erwartet funktioniert.

```bash
pip install pytest
```
Bitte beachte, dass du jedes dieser Pakete mit pip install --upgrade <paketname> aktualisieren kannst, um sicherzustellen, dass du die neueste Version hast.

Sobald du dein CLI-Tool erstellt hast, kannst du es in eine Python-Bibliothek umwandeln, die andere Entwickler als Plugin für ihre eigenen Projekte verwenden können. Es gibt verschiedene Möglichkeiten, dies zu tun, aber eine gängige Methode ist die Verwendung von setuptools, einer Bibliothek zur Erstellung von Python-Distributionen.

```bash
pip install setuptools
``` 
  
  
Verwende eine virtuelle Umgebung: Dies ist besonders wichtig, wenn du an mehreren Python-Projekten gleichzeitig arbeitest. Virtuelle Umgebungen erlauben es dir, die Paketabhängigkeiten für jedes Projekt getrennt zu halten, was zu weniger Konflikten und leichterer Fehlersuche führt. Du kannst das Paket virtualenv verwenden, um virtuelle Umgebungen in Python zu erstellen.

```bash
pip install virtualenv
  ```
Und dann eine neue virtuelle Umgebung erstellen mit:

```bash
virtualenv venv
  ```
Aktiviere die Umgebung mit:

```bash
source venv/bin/activate
  ```
Jetzt sind alle Python-Pakete, die du installierst, auf diese Umgebung beschränkt und beeinflussen nicht deine globale Python-Installation.

Verwende Versionskontrolle: Versionskontrolle ist ein Muss für jedes Softwareprojekt. Sie ermöglicht es dir, Änderungen an deinem Code im Laufe der Zeit zu verfolgen und zu älteren Versionen zurückzukehren, wenn etwas schief geht. Git ist das am häufigsten verwendete Versionskontrollsystem. Du kannst es auf Debian mit dem folgenden Befehl installieren:

### If you use Debain on WSL   
  
WSL starten: WSL wird automatisch gestartet, wenn du es öffnest. Du kannst dies tun, indem du einfach "wsl" in PowerShell eingibst:

```powershell
wsl
```
Dies öffnet eine neue WSL-Instanz mit der Standard-Distribution. Wenn du eine spezifische Distribution starten möchtest, kannst du deren Namen als Argument angeben, z.B.:

```powershell
wsl -d Ubuntu
```
Eine WSL-Distribution installieren: Du kannst eine neue WSL-Distribution aus dem Microsoft Store installieren. Der genaue Befehl hängt von der spezifischen Distribution ab, die du installieren möchtest. Zum Beispiel, um Ubuntu 20.04 zu installieren, könntest du ausführen:

```powershell
```
wsl --install -d Ubuntu-20.04
WSL stoppen: Du kannst eine laufende WSL-Instanz stoppen, indem du "exit" in der WSL-Befehlszeile eingibst. Um alle laufenden WSL-Instanzen zu stoppen, kannst du den folgenden Befehl in PowerShell ausführen:

```powershell
wsl --shutdown
```
Eine WSL-Distribution deinstallieren: Wenn du eine WSL-Distribution nicht mehr benötigst, kannst du sie mit dem folgenden Befehl deinstallieren:

```powershell
wsl --unregister <DistributionName>
```
Bitte beachte, dass dies alle Daten in der Distribution löscht.

Liste der installierten WSL-Distributionen anzeigen: Du kannst eine Liste aller installierten WSL-Distributionen anzeigen, indem du den folgenden Befehl in PowerShell ausführst:

```powershell
wsl --list --verbose
```
