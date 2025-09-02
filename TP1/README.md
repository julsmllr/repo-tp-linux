# TP1 - Introduction Linux

On commence toujours par ouvrir un cmd et on tape 
```bash
PS1="$ "
```

## 1er Exercice  

### Quelques commandes
`$ date` : Donne la date + heure

`$ cal` : Ouvre le calendrier du mois

`$ cal 3 2022` : Ouvre le calendrier du mois mis en argument (ici 03/22)

`$ who` : pas de réponse du terminal (la suite non plus car la commande c'est whoami) | *La vraie commande est `whoami`*

`$ uname` : Donne le nom de la distribution de l'OS

`$ uname -m -r` : Donne la version de l'OS avec le socket du processeur + bits d'encodage (86 bits)

`$ uname -mrs` : Donne le nom de la distribution complète (uname + uname -m -r)

`$ echo`: print en console (en supprimant les espaces en trop)

### Raccourcis

-  Les fleches permettent de parcourir l'historique des commandes saisie | *ou `CTRL+P` et `CTRL+N`* 
-  `CTRL + L` (ou `cls`) :  clear le shell

- `CTRL + U` : Supprime le contenu de la ligne

- `CTRL + D` : Ferme le shell ou tout process si rien n'est fait dessus

### Remarques

L'historique entre la fermeture du shell et son réouverture ne se clear pas

---
## 2e Exercice 

### Nouvelles commandes
- `pwd` : Donne le chemin absolu de notre localisation
- `cd ..` : revenir au dossier précédent
- `cd` : fait revenir au home
- `cd /` : va à la racine / du disque
 - `ls` : liste le contenu du dossier

- `cat` : affiche le contenu (on peut mettre plusieurs fichiers un après l'autre, ça les affiche à la suite)
- `wc` (word count) : Donne nb ligne, nb mots, nb car


### Dossiers importants

- `share/man` : On dirait des langues disponibles (fr, en, el, da, es, ...)

- `usr/bin` : librairies de la session

### Comprendre le `~` 

Le symbole `~` désigne le **home** de la session. 

*Par exemple : un utilisateur aura comme dossier par défaut `home/utilisateur`, `~` désignera ce chemin*

Donc :

- `echo ~` renvoie le `pwd` initial de la session
- `cd ~` fait revenir au home

---

## 3e Exercice

### Création de dossiers

On utilise `mkdir`
*Exemples :*

- `mkdir abeilles tp_shell/tp1 ~/arbres` : Il crée 3 dossiers "Abeilles" à la base, "TP1" dans "tp_shell" et "Arbres" à la racine aussi avec `~`

- `mkdir -p vivant/plante/fleur tp_shell/tp1/exos/ex1` | Ici `-p` permet de créer tous les dossiers intermédiaires. (Si on veut créer fleur, il faut d'abord créer plante)


### Chemin relatif et absolu

Un chemin absolu est un chemin qui marchera tout le temps. Relatif, il dépend du dossier dans lequel on se situe

*Exemple du TP :*

- Chemin relatif : `tp_shell/tp1`, `abeilles` 
- Chemin Absolu : `~/arbres` *(car ~ correspond à `home/student/`)*

### Suppression de dossiers
On utilise `rmdir`

> Attention le dossier sélectionné doit être vide


### Création de fichiers vides
On utilise `touch`

### MOVE de fichiers
On utilise `mv <fichier à bouger> <nouvelle destination + nouveau nom>`

- `mv : move + renommer` *(exemple : `mv arbres/hello.c arbres/bonjour.c`)*
- `mv arbres/hello.c arbres/bonjour.c` : renomme
- `mv abeilles arbres vivant/` : déplace `abeilles` et `arbres` dans `vivant/`
- `mv bidule vivant` : déplace `bidule` dans `vivant/`
- `mv vivant vie` : `vie` n'existe pas donc vivant est renommé

### COPY de fichiers/Dossiers

On utilise `cp <fichier à copier> <vers où copier>`

- `cp vie/arbres/bonjour.c salut.c` : Créer une copie de `bonjour.c` dans `/home/student` nommé `salut.c`

- `cp salut.c vie/abeilles/truc.txt copies` : copie `salut` + `truc` dans `copies` (fichier puis dossier)

**Et pour copier des dossiers ?**

On utilise le paramètres `-R` 

- `cp vie/bidule tp_shell copies` : Il y a une erreur, tp_shell est un dossier
- `cp -R vie/bidule tp_shell copies` : copie `bidule` + dossier `tp_shell` dans `copies`
- `cp -R vie copie_vie` : copie de `vie` dans un nouveau dossier `copie_vie` *(vu que copie_vie n'existe pas)* 


### REMOVE de fichiers

On utilise `rm <fichier à supprimer>`

- `rm vie/bidule` : supprime `bidule`
- `rm copies` : pas possible copies est un dossier

**Même raisonnement que précédemment pour les dossiers**

- `rm -r copies` : supprime le dossier copies
- `rm -R copie_vie` : supprime le dossier copies_vie
- `rm i- vie/arbres/bonjour.c vie/abeilles/truc.txt` : supprime les fichier `bonjour` et `truc` avec une demande de confirmation (`-i`)

---

## Exercice 4 
```bash
$ mkdir Mail Rapport Web
$ touch Rapport/rapport.txt Web/index.html
$ mkdir Rapport/Docs
$ mkdir Rapport/Docs/Afaire Rapport/Docs/Fait
$ cd ~/Rapport/Docs/Afaire
$ cd ../Fait
$ cp ../rapport.txt ./
$ mv rapport.txt rapport_copie.txt
$ cd ~/Rapport
$ cat ../Web/index.html
$ ls ../Web
$ cd ~
$ rm -R Mail Rapport Web
```

---
## Exercice 5 
Il existe plusieurs type de commande : 
- externes : besoin d'un librairie
- internes : présentes dans l'OS de base
- fonctions du shell : commandes définies par le user
- alias : raccourcis pour des commandes du user


### Comment connaître le type d'une commande ? 
```bash
type <commande>
```

- `type cd` : primitive
- `type touch` : haché (externe et présent dans le /bin)
- `type mv` : haché (externe et présent dans le /bin)
- `type cp` : haché (externe et présent dans le /bin)
- `type rm` : haché (externe et présent dans le /bin)
- `type ls` : alias (externe et présent dans le /bin)

Plupart des programmes dans le usr/bin ?

---

## Exercice 6

commande `man` : manuel des commandes externes

commande `help` : manuel des commandes internes

#### Doc pour `man ls` 

ls -a : all
ls -l : Pour utiliser un format de listing long avec tous les droits


rm -f : force le delete

touch edit timestamps


### Doc Man


`man 1 printf` ouvre la doc de `printf` à partir de la ficher 7

Dans le man d'une fonction, dans le **synopsys**, on peut trouver des choses du genre `man [man options] [[section] page ...] ...` :
- `[]` sont en option
- `...` sont répétables

---

## Exercice 7 

Le caractère joker est remplacé par les fichiers présents dans le dossier. Il permet donc de faire de la recherche avec des filtres

Caractères joker :
- `*` : réprésente une chaine de car peut etre vide (pas si c'est le 1er car et qu'elle commence par un .)
- `?` : Un seul car quelconque
- `[]` : représente un seul car qui est dans un intervalle de car spécifié.`[a-z]`, `[0-5]`. On peut inverser la recherche. Par exemple on ne veut pas de chiffre, on utilise alors **^** `[^0-9]`
 
### Création dossier
```bash
mkdir tp_joker
cd tp_joker
touch annee1 Annee2 annee4 annee45 annee41 annee510 annee_saucisse annee_banane bonbon
```

### Premières commandes
`$ echo *` (cs.log tous les fichiers)
`$ echo *_*` (cs.log annee_saucisse annee_banane)
`$ echo [ab]*` (cs.log tous les fichiers avec un a ou un b) ATTENTION [] ne représente qu'un seul car (ici le premier des fichiers)
`$ echo [^ab]*` (cs.log Annee2)
`$ echo c*` (cs.log c*)
`$ echo ??????` (cs.log annee1 Annee2 annee4 bonbon) (6 car)

### Commandes ls
se terminent par 5 :
- `ls *5 (annee45)`

commencent par annee4 :
- `ls annee4*` (annee4 annee41 annee45)

commencent par annee4 et ont un max de 7 lettres :
- `ls annee4?` (annee41 annee45)

commencent par annee et dont le 6e car n'est pas un chiffre :
- `ls annee[^0-9]*` (annee_banane annee_saucisse)

continennent la chaine ana :
- `ls *ana*` (annee_banane)

commencent par a ou A :
- `ls [aA]*` (renvoie tous sauf "bonbon")

dont l'avant-dernier car est 4 ou 1 :
- `ls *[41]?` (annee41 annee45 annee510)


### Fichiers secrets (commençant par un .)
```bash
$ ls .*
```

### Rechercher dans les sous-répertoires

```bash
cd /usr/include
ls std*.h
```

Peut pas vérifier
