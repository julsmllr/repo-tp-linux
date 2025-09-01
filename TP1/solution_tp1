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

- `pwd` : Donne le chemin absolu de notre localisation
- `cd ..` : revenir au dossier précédent
- `cd` : fait revenir au home
- `cd /` : va à la racine / du disque
 - `ls` : liste le contenu du dossier

- `cat` : affiche le contenu (on peut mettre plusieurs fichiers un après l'autre, ça les affiche à la suite)
- `wc` (word count) : Donne nb ligne, nb mots, nb car


9. On dirait des langues disponibles (fr, en, el, da, es, ...)

10. Oui (sql)

11. 
echo ~ : donne le pwd du chemin initial de la sessions

Le ~ prend le chemin de base de l'utilisateur

12.
/ 
  usr
    include
    share
      man
  bin
  
 -------- 3e Exercice ---------
mkdir abeilles tp_shell/tp1 ~/arbres : Il crée 3 dossiers "Abeilles", "TP1" "Arbres"

Chemin relatif : tp_shell/tp1, abeilles 
Chemin Absolu : ~/arbres

$ mkdir -p vivant/plante/fleur tp_shell/tp1/exos/ex1

-p : Créer des arborescence de fichiers/les répertoires intermédiaires

mkdir : créer des dossiers
rmdir : remove (dossier doit etre vide)
touch : créer un fichier vide

10. MOVE
mv : move + renommer (exemple : mv arbres/hello.c arbres/bonjour.c)
mv arbres/hello.c arbres/bonjour.c : renomme
mv abeilles arbres vivant/ : déplace abeilles + arbres dans vivant/
mv bidule vivant : déplace bidule dans vivant
mv vivant vie : renomme vivant en vie


10. COPY
cp vie/arbres/bonjour.c salut.c : créer une copie de bonjour.c dans /home/student nommé salut.c
cp salut.c vie/abeilles/truc.txt copies : copie salut + truc dans copies (fichier puis dossier)
cp vie/bidule tp_shell copies : erreur il faut rajouter un droit de lecture
cp -R vie/bidule tp_shell copies : copie bidule + dossier tp_shell dans copies
cp -R vie copie_vie : copie de vie dans un nouveau dossier copie_vie 

-R permet de copier le contenu de tout le dossier


11. REMOVE
rm vie/bidule : supprime bidule
rm copies : pas possible copies est un dossier
rm -r copies : supprime le dossier copies
rm -R copie_vie : supprime le dossier copies_vie
-R et -r ?
rm i- vie/arbres/bonjour.c vie/abeilles/truc.txt : supprime les fichier bonjour et truc avec une demande de confirmation (-i)


--------------- Exercice 4 ---------------
mkdir 

--------------- Exercice 5 ---------------
Commandes externes, internes, fonctions du shell et alias

Comment l'avoir ? 
type <commande>

cd : primitive
touch : haché (externe et présent dans le /bin)
mv : haché
cp : haché
rm : haché
ls : alias

Plupart des programmes dans le usr/bin ?

--------------- Exercice 6 ---------------
commande <man> : manuel des commandes externes
commande <help> : manuel des commandes internes

man ls 

ls -a : all
ls -l : Pour utiliser un format de listing long avec tous les droits

rm -f : force le delete

touch edit timestamps
