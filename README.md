# Le BABA de la programmation

## Généralités

### Quel éditeur de code utiliser ?
[VSCode](https://code.visualstudio.com/) est un éditeur de code compatible avec tous les languages. Il est facile à prendre en main pour les actions git.

### Pimper le terminal pour travailler avec git
Lorsqu'on travaille avec git, on doit pouvoir repérer facilement dans quelle branche on se trouve.
Pour cela, on peut configurer le terminal avec [Oh My Zsh (OMZ)](https://ohmyz.sh/).

<img width="378" alt="Capture d’écran 2025-03-06 à 5 06 54 PM" src="https://github.com/user-attachments/assets/fefdae0b-7bd0-44a9-bef2-e6aebe9a0e4c" />

### Où mettre ses repos git ?
Un repo git peut être mis n'importe où. Il n'est pas obligatoire de l'avoir sous la main via l'interface graphique donc un dossier à la racine fera très bien l'affaire sachant que tous les repos sont référencés dans github : https://github.com/associationbloom

### Commandes bash à connaitre
Le bash est l'interpréteur en ligne de commande de base dans le terminal. Il permet de communiquer avec l'ordinateur sans passer par l'interface graphique. Il est notamment très utile pour naviguer partout dans la machine, gérer des fichiers et des dossiers et lancer des scripts.

_Exemple : j'ai un dossier avec 1453 photos à trier par format portrait ou paysage : en quelques lignes de commandes, je peux trier les photos sans avoir à le faire manuellement._

#### Références
Le cours de Jacques Lefrère est extrèmement complet. Vous pouvez vous y référer pour creuser l'ensemble des commandes bash : http://wwwens.aero.jussieu.fr/lefrere/master/mni/mni/unix/cours-unix.pdf

#### Cheatsheet
Afficher le chemin absolu du répertoire courant
```
pwd
```

Afficher l'arborescence du dossier
```
tree
```

Afficher les fichiers et les dossiers
```
ls
ls toto* (affiche les fichiers commençant par toto)
ls -l (affiche le format long : types + droits + Nbre de liens + ....)
ls -a (affiche tous les fichiers y compris les fichiers cachés commençant par '.')
```

Changer de dossier
```
cd chemin (vers le dossier dont le chemin absolu est donné)
cd .. (répertoire parent)
cd ~ (répertoire de base)
cd - (répertoire précedent)
cd / (répertoire racine)
```

Copier des fichiers / dossiers
```
cp * dossier (crée une copie de tous les fichiers vers le répertoire 'dossier')
cp toto.txt dossier (crée une copie du fichier toto.txt vers le répertoire 'dossier')
```

Déplacer ou renommer un fichier / dossier
```
mv source destination (déplacer tous les fichiers de dossier 'source' vers le dossier 'destination')
mv toto.txt destination (déplacer le fichier toto.txt vers le dossier 'destination')
mv toto.txt tata.txt (renommer le fichier toto.txt en tata.txt)
```

Créer un dossier
```
mkdir data (créer un dossier 'data' dans le dossier courant)
mkdire data/bathymetry (créer un dossier 'data' puis un dossier 'bathymetry' dans 'data'
```

Effacer un dossier
```
rmdir dossier (supprime le dossier 'dossier'. Attention, il doit être vide)
```

Effacer un fichier
```
rm -R (effacer récursivement)
rm file (effacer le fichier 'file')
rm -rf dossier (supprime le répertoire et tout son contenu, sans confirmation)
```

Ouvrir un fichier
```
vi file.txt (si le fichier n'existe pas, le fichier est créé)
```

### Créer un alias pour une application
Dans le terminal, imaginons que nous sommes dans une repo git `gfw-scrapper`. 
```
(base) ➜  gfw-scrapper git:(main)
```

Nous aimerions pouvoir ouvrir le dossier dans Visual Studio Code et commencer directement à travailler dessus. Une manière de faire est de passer par la ligne de commande longue :
```
open -a 'Applications/Visual\ Studio\ Code.app' .
```
Sauf que si je le fais 3 fois par jour, ça commence à devenir compliqué. Ce qu'on peut faire, c'est créer un alias qui permet d'appeler rapidement cette commande :

1. On ouvre le fichier dans lequel on édite les alias :
```
cd ~
vi .bashrc
```

2. Dans le fichier, on écrit la commande suivante (pour insérer des caractères, appuyer sur la touche **i** :
```
alias code='open -a /Applications/Visual\ Studio\ Code.app'
```

3. On sauvegarde le fichier : appuyer sur la touche **esc** et taper **:wq** puis appuyer sur la touche **return**

4. On applique les modifications
```
source ./.bash_profile
```
5. On peut maintenant ouvrir notre repo git dans VSCode à l'aide de la ligne de commande :
```
open gfw-scrapper
```

### Git : commandes de base

Cloner un repo
```
git clone [url]
```

Lister toutes les branches
```
git branch --all
```

Récupérer les branches distantes sur github
```
git fetch --all
```

Récupérer les informations distantes sur github et mettre à jour les branches locales
```
git pull
```

Créer une branche
```
git checkout -b [nom-de-la-branche]
```

Changer de branche
```
git checkout [nom-de-la-branche]
```

Pour commit et push, je conseille de passer par VSCode

<img width="354" alt="Capture d’écran 2025-03-06 à 6 15 50 PM" src="https://github.com/user-attachments/assets/47c4701d-7201-4e88-9b7e-618b6098082d" />

## Coder en Python

### Installation
Installer Python : https://www.python.org/downloads/

### Packages installer
[`pip`](https://pip.pypa.io/en/stable/installation/) est très utilisé pour installer des packages Python

Pour installer un package :
```
pip install [package]
```
