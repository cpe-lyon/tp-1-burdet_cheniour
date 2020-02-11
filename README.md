# tp-1-burdet_cheniour
## Exercice 2. Prise en main de l’interpréteur de commandes

### Manuel
1. ```which``` permet de localiser une commande. Renvoie le chemin des fichiers (ou liens) qui seraient exécutés dans l'environnement courrant
2. ```&/option```
3. ```q```
4. ```t6```

### Navigation dans l’arborescence des fichiers
1. ```cd /var/log```
2. ```cd /var```
3. ```cd /home/serveur```
4. ```cd ../../var/```
5. ```cd /root``` Permission denied
6. ```sudo cd /root``` Il demande le mot de passe
7. 
```
cd /home/serveur
mkdir Dossier1
mkdir Dossier2
touch Dossier1/Fichier1
mkdir Dossier2/Dossier2.1
mkdir Dossier2/Dossier2.2
touch Dossier2/Dossier2.1/Fichier2
touch Dossier2/Dossier2.1/Fichier3
```
8. 
```
cd /home/serveur
rm Dossier1/Fichier1
rm Dossier1
```
Cannot remove Dossier1 : is a directory
9. ```rm -d Dossier1/```
10. Directory not empty
11. ```rm -r Dossier2/```


### Commandes importantes

1. ```date``` Permet d'afficher l'heure. ```time``` permet d'évaluer le temps d'éxécution d'un programme
2. ```ls``` Permet d'afficher les fichiers et dossiers et ```la``` permet d'afficher les fichiers et dossiers cachés
3. ```whereis ls``` le chemin est : /bin/ls/usr/share/man/man1/ls.1.gz
4. No manual entry for ```ll``` donc en tappant ```alias``` nous apprenons que ```ll``` est le racourci de la commande ```ls -alF```
5. ```ls /bin/```
6. ```ls ..``` afiche le contenu du dossier parent
7. ```pwd```
8. ```echo 'yo' > plop``` exécutée 2 fois créer un fichier avec un yo à l'intérieur
9. ```echo 'yo' >> plop``` exécutée 2 fois créer un fichier avec deux yo à l'intérieur
10. ```file``` détermine le type de fichier exemple : ASCII text
11. ```echo 'Hello Toto !' > toto``` puis créer un lien vers ce fichier avec ```ln toto titi```
Pour visualiser et modifier le contenu ```vim toto``` puis ```:w :q``` on observe que titi est modifié également
```rm toto``` mais titi existe toujours
12. ```ln -s titi tutu``` créer lien symbolique, si je modifie titi, tutu est modifié également et inversement
Si je supprime titi, tutu est alors vide
13. ```vim /var/log/syslog``` et ```:q``` permet de quitter ou bien ```cat /var/log/syslog``` et ```ctrl + s ou ctrl + q```
14. ```head -5 /var/log/syslog``` 5 premiere
```tail -15 /var/log/syslog``` 15 dernière
```head -20 /var/log/syslog | tail -11``` les lignes 10 à 20
15. ```dmesg | less``` affiche la mémoire tampon de message du noyau
16. ```vim /etc/passwd``` fichier des utilisateurs du système
```man /etc/passwd``` ou ```man passwd```
17. ```cat /etc/passwd | cut -d ':' -f1 | sort```
18. ```wc -l < /etc/passwd```
19. ```apropos "conversion" | wc -l``` ou ```man -k```
20. ```sudo find / -name "passwd"```
21. ```sudo find / -name "passwd" > /home/serveur/list_passwd_files.txt 2> /dev/null```
22. ```grep -rl ll```
23. ```locate "history.log"```
24. ```cd /home/serveur``` ```touch tototo``` ```locate "tototo"``` Il n'apparait pas car Instead it searches in a database which contains all files. This database it usually updated once per day, typically around 3 AM.

## Exercice 3. Découverte de l’éditeur de texte nano

1. ```cp /var/log/syslog /home/serveur/log.txt``` puis ```nano log.txt```
2. ```ctrl + \``` ```kernel``` ```noyau``` ```a```
3. ```ctrl + k``` ```ctrl + _``` ```ctrl + v``` ```ctrl + u``` ```ctrl + o```
4. ```alt + u```
5. ```ctrl + s```

## Exercice 4. Personnalisation du shell

1. ```cp .bashrc .bashrc_bac```
2. ```nano .bashrc``` ```ctrl + s```
3. ```source .bashrc```
4. ```nano .bashrc``` ```ctrl + w```
5. ```PS1='\[\033[01;91m\]\t ${debian_chroot:+```