# Mac Setup

## <span style="color:red">Ab hier musst du ADMIN sein</span>
## Homebrew
Homebrew ist ein Paketmanager
```shell
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
homebrew kann mit ```brew search something``` durchsucht werden
## <span style="color:red">ADMIN deaktivieren</span>
## iTerm2
Ein besseres Terminal
```shell
brew install --cask iterm2
```

## git
Ersetzt Apple Git mit einer neueren Version
```shell
brew install git
```

## Oh my zsh 
Eine bessere shell
```shell
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

## Oh my zsh plugins

Einige zsh Plugins
### zsh-syntax-highlighting
```shell
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```

### zsh-autosuggestions
```shell
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```

### Powerlevel10k
Installiert bessere Schriftart und git repos werden besser dargestellt.
```shell
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
```

### Plugins aktivieren
In der ```~/.zshrc``` wird folgendes hinzugefügt
```shell
ZSH_THEME="powerlevel10k/powerlevel10k"

...

plugins=(
    git
    osx
    bgnotify
    zsh-syntax-highlighting
    zsh-autosuggestions
)
```

## Python
Python ist bereits in einer alten Version in macOS enthalten.
Die Version kann über ```python --version```abgefragt werden.

Eine neue Version kann mit folgendem Befehl installiert werden.
```shell
brew install python@3.9
```
Die bestehende Installation wird über ```python``` und die neue Version über ```python3``` abgerufen

Anaconda ist sehr gut für ML Aufgaben
```shell
brew install --cask anaconda
```

Das Anaconda Verzeichnis muss global exportiert werden.
Dafür das folgende in die ```.zshrc``` einügen.
```shell
export PATH="/opt/homebrew/anaconda3/bin:$PATH"
```


## JAVA Entwicklung

### JDK
Bei SAP sollte das von SAP angepasste JDK verwendet werden. Eine aktuelle Version
der SAP Machine lässt sich über Homebrew isntallieren.
```shell
brew install sapmachine-jdk
```
Für weitere Versionen kann ein Tap hinzugefügt werden wie hier beschrieben:
https://github.com/SAP/homebrew-SapMachine
Neben der SAPmachine sind aber natürlich auch weitere JDKs über Homebrew
verfügbar und können mit ```brew search jdk``` gefunden werden.

## Editor
### VS Code von Microsoft
```shell
brew install --cask visual-studio-code
```
### Pycharm CE von Jetbrains
```shell
brew install --cask pycharm-ce
```
### IntelliJ IDEA CE von Jetbrains
```shell
brew install --cask intellij-idea-ce
```
Die profi Varianten der Jetbrains Tools können einfach durch das weglassen von ````ce````
installiert werden.

## GitHub Enterprise
### Create an Access Token
In your GitHub account, go to ```Settings / Developer settings / Personal access tokens``` and select ```Generate New Token```. Make a note of the token somewhere safe since this is the only chance you get to see it.

### Add the token to your local OSX Key Chain
When you now need to authenticate with GitHub on the command line you will need to use the token instead of your password (even though git will ask for your Github password).
```shell
git clone https://github.com/username/repo.git
Username: your_username
Password: your_token
```

### Confirme the setup
```shell
git config -l
```
## Ein paar hilfreiche Tools und Apps
### Mac Fenstermanagement
Rectangle ist open source und super schnell
```shell
brew install --cask rectangle
```

### Mac Menübar
Dozer ist ein kleines open source Tool
```shell
brew install --cask dozer
```

### REST Client
Das ist eine Glaubensfrage... Postman oder Insomnia...  
Ich bevorzuge Postman 
```shell
brew install --cask postman
```

### Github Desktop
Kann für das Reviewen von Pull Requests ganz nützlich sein.
```shell
brew install --cask github
```
