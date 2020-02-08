# Compte-Rendu Administration Système
## Partie 1
### Prise en main de l’interpréteur de commandes

#### I Manuel
<br/>
<br/>

1- Commande : *which [-a] nom_de_fichier*

*-a* => affiche tous les chemins correspondant à chaque argument (en l'occurrence ici nom_de_fichier)

Cette commande permet de renvoyer le chemin des fichiers éxécutés ultérieurement dans l'environnement
si les arguments données en commande dans l'interpreteur de commande sont conformes à **POSIX**.
En conséquence, *which* cherche la variable **PATH** dans les fichiers éxécutables.

Valeurs de retour :

     0	- toutes les commandes spécifiés sont trouvées et éxécutées
 
     1	- si une commande spécifiée n'existe pas ou n'est pas éxécutée
 
     2	- si une option non valable est spécifiée
     
2- Il est possible de rechercher un terme dans le manuel (appelé avec la commande *man*). Pour cela on utilise la commande : */ terme_recherche*  (dans l'interface du manuel). 

Le symbole *"/"* précède le nom du terme recherché. Par exemple, *"/option"* recherchera l'ensemble des occurences du terme "option" dans la page du manuel actuellement affichée.

Il est important de noter que ces recherches adopte différentes options, plus ou moins utiles en fonction de notre "position" dans le manuel consulté (par cela j'entends dire à quelle page nous nous situons). En ce sens, nous avons les options suivantes :

     /	- pour chercher un terme devant notre position relative dans le manuel consulté
 
     ?	- pour chercher un terme derrière notre position relative dans le manuel consulté
 
     &	- pour afficher seulement les lignes qui "matchent" avec notre recherche
     
3- On peut quitter le manuel actuellement consulté à tous moment en appuyant sur la touche *q*

4- Les informations relatives aux numéros des sections se trouvent dans le tableau ci-dessus :

![Section](https://github.com/cpe-lyon/tp-1-moine_pinet/blob/master/tp41.PNG)

Ainsi, en conséquence pour afficher la première page du manuel de la section 6, on utilise la commande : *man 6 intro*

Cette section traite des jeux et des programmes amusants disponibles sur le système d'exploitation linux (distribution **Ubuntu -Server** dans le cas présent).

<br/>
<br/>

####  II Navigation dans l’arborescence des fichiers

<br/>
<br/>

1- Pour allez dans le dossier  **/var/log** depuis notre position actuel (à savoir le répertoire personnelle) on utilise la commande : *cd /var/log*

**NB** : *cd* est la commande qui permet de se déplacer dans une arborescence linux. Elle prend principalement en paramètre le chemin associé à l'emplacement à atteindre dans l'arborescence. En outre, il est important de spécifier que *cd* peut utiliser des chemins relatifs où absolus. 

Un chemin est dit relatif lorsque'il est instancié par rapport à l'endroit où l'utilisateur se situe dans l'arborescence.

Un chemin est dit absolu lorsque'il est instancié par rapport à la racine (depuis *"/"*).

2- Pour remonter dans le dossier parent en utilisant un chemin relatif, on utilise la commande : *cd ..*

3- Pour retourner dans le dossier personnel, on utlise la commande : *cd \~*

4- Pour retourner dans le dossier précédemment consulté, on utilise la commande : *cd -*

5- Il est important qu'en tant que simple utlisateur, l'accès au dossier *root* est restreint pour des questions de sécurité. La commande *cd /root/* résulte par le résultat : *permission denied*

6- La commande *sudo cd /root/* donne le résultat : *command not found*

7- L'arborescence souhaitée est la suivante :

![Arborescence](https://github.com/cpe-lyon/tp-1-moine_pinet/blob/master/tpexo1.PNG)

L'ensemble des commandes réalisées pour crée l'architecture ci-dessus sont :

1. *cd \~* (on revient à la racine !!!)
2. *mkdir dossier1* ; *mkdir dossier2* (on crée les dossiers dans la racine)
3. *cd dossier1* ; *touch fichier1* (on va dans "dossier1" et on crée "fichier1")
  
  **NB** : "ls" permet de voir le contenu d'un dossier et donc de vérifier la présence (et en ce sens leur création) 
  des fichiers et dossiers dans l'emplacement courant
     
4. *cd \~/dossier2* (on va dans le "dossier2" via le chemin absolu)
5. *mkdir dossier2.1* ; *mkdir dossier2.2* (on créer les dossiers dans "dossier2")
     
6. *cd dossier2.2* ; *touch fichier2* ; *touch fichier3* (on créer les fichiers "fichier2" et "fichier3" dans le "dossier2.2")

8- Commandes : 

1. *cd \~*
2. *rm fichier1* => *Cannot remove 'fichier1' : No such file in directory* (fichier non présent/introuvable 
   dans répertoire courant !!!)
3. *rm dossier1* => *Cannot remove 'dossier1' : Is a directory*

**Remarque** : 
* On ne peut supprimer un fichier qui n'est pas présen dans le répertoire courant (répertoire où l'on se situe)
* On ne peut supprimer simplement un dossier contenant un ensemble de fichiers ou de données. Pour se faire, se référer à la question 10 de la partie 1.II .

9/10- L'ensemble des commandes permettant de supprimer un dossier sont :
* *rm* => supprime dossier ou fichier
* *rmdir* => supprime dossier vide

11- Pour supprimer le "dossier2" on tente la commande : *rm dossier2*. Or on obtient, à l'écran : *Cannot remove 'dossier2' : Is a directory* 

12- Pour supprimer en une même ligne le "dossier2" on note : *rm -r dossier2* . Cette commande supprime récursivement les fichiers et dossiers de "dossier2" ce qui permet, en outre, de supprimer "dossier2" ainsi que son contenu.

</br>
</br>

#### III Commandes importantes

</br>
</br>

1- La commande qui permet l'affchage de l'heure dans un terminal linux est : *date*

**NB** : on verra dans la partie 2 qu'il est possible de modifier le fichier ".bashrc" afin que le shell affiche en à chaque "retour chariot" (ou bien "entrée"), le nom de l'utilisateur, le nom de la machine et même l'heure (avec ou sans les secondes).

Commande : *time commande [arg]*

Cette renvoie des statsitiques sur le temps d'execution de la commande. Elle génère trois chronomètres :

* *user*
* *sys*
* *real*

2- Commandes :

* *ls* => liste les fichiers/dossiers dans le répertoire courant
* *la* => même chose mais n'ignore pas les dossiers cachés (ceux qui commence par . , comme par exemple ".bashrc" présent dans le répertoire personnel)

3- Le programme ls se situe dans le répertoire "/usr/bin". Pour trouver se dit résultat, on utilise la commande : *which ls* 

4- La commande *ll* n'admet pas d'entrée manuel. En effet, en utilisant la commande *alias ll*, cette dernière retourne *ls -alF*. Ainsi on peut dire que *ll* n'a pas d'entrée manuel car c'est un alias de *ls*. En outre, *ll* agit comme *ls* mais avec trois options supplémentaires :


     a	- n'ignore pas les fichiers commençant par "."
 
     l	- utilise des listings de long format
 
     F	- "classify" => classe les fichiers
     
5- La commande permettant d'afficher l'ensemble des fichiers contenus dans "/bin" est : *la /bin*

**NB** : on peut aussi utiliser *ls /bin*, car après observation, il n'y a pas de fichiers commençant par "." dans le dossier */bin*.

6- La commande *ls ..* , liste l'ensemble des fichiers et dossiers (ne commançant pas par ".") présents dans le répertoire parent de l'emplacement courant de l'utilisateur dans l'arborescence des fichiers linux.

**NB** : pour plus de pertinence et pour n'omettre aucun fichier, on peut utiliser *la ..* qui listera l'ensemble des fichirs et dossiers présents dans le répertoire parent de l'emplacement courant de l'utilisateur dans l'arborescence des fichiers linux.

7- Commande : *pwd*

Cette commande donne le chemin complet du dossier courant.

8- Commande : *echo 'yo'>plop* ; *echo 'yo'>plop*

   => crée le fichier "plop" lors de la première instance puis écrit 'yo' lors de la seconde instance.
   
9- Commandes : *echo 'yo'>>plop* ; *echo 'yo'>>plop*
   
   => créer le fichier "plop" et écrit 'yo'  dans le fichier lors de la première instance et écrit à nouveau 'yo' (à la ligne) dans le fichier lors de la seconde instance.
   
10- La commande file test l'argument (nom du fichier/dossier) dans l'intention de le classer.
Elle procède selon 3 traitements : filesystem tests, magic tests, language tets. Le premier test 
qui réussi engendre la classification et l'affichage à l'écran du résultat de cette classification.

1. filesytem tests => le programme regarde si le fichier est vide ou si il est une sorte
de fichier spécial (par exemple les points d'accès préparés par le système 
aux périphériques présent dans "/dev"). Tous fichiers inconnus appropriés au systeme 
en cours (socket, liens symboliques, ...) sont instancié s'ils sont définis dans le systeme header file <sys/sta.h> .

2. magic tests => utilisé pour checker les fichiers avec des formats fixés particuliers.
Un exemple commun est le format de sorti de compilation d'un prog C, soit a.out , définis
dans elf.h. Ces fichiers ont un nombre magic stockés dans une place spécifique
proche du début du fichier où il est dit que le system Unix opérant traite ce fichier
comme un fichier binaire éxécutable. Ce concept de magic test est appliqué par extenxion aux 
fichiers de données. N'importe quel fichier avec des idientifiants à propos d'un
offset fixé (offset = place du fichier) peut bénéficier du test. Les infos qui identifie
les fichiers sont stockés dans /etc/magic et pour les fichiers compilés dans usr/share/misc/magic.mgc .


3. language test => si aucun test ne réussit, le test de language examine si le fichier est 
un fichier text. Le system analyse alors le rangement des caractères ASCII, ISO-8859-x, ...
et leur rangement, ou bien séquence, pour voir si cela constitue une empreinte de type fichier text.
Aussi le language test regarde les chaînes de caractères particulières (ex : names.h) qui 
peuvent appairaitres n'importe où dans les premiers blocs du fichier. Par exemple, le mot
clé "struct" indique que le fichier est programme C.

Commandes :

* *file dossier1* => *dossier1: directory*
* *file fichier1* => *fichier1: empty*

11- Commande :

1. *echo 'Hello Toto' >> toto*    => création du fichier "toto" contenant 'Hello Toto' en texte
2. *cat toto*                     => vérifie que le fichier "toto" contient bien 'Hello Toto' en texte
3. *ln toto titi*                 => création d'un lien de titi vers toto
4. *echo 'yoyo' >> toto*          => écriture de 'yoyo' dans le fichier "toto"
5. *cat toto*      
6. *cat titi*       => même contenu entre le fichier  "toto" et "titi"
7. *rm toto*         => supprime toto
8. *cat toto*        => retourne une erreur
9. *cat titi*        => affiche "Hello Toto ; yoyo"
			  
En conséquence supprimer le fichier "toto" n' impact pas le fichier "titi" (qui est une copie de "toto")

12- Commandes :

1. *ln -s titi tutu* => création d'un lien symbolique de tutu vers titi
2. *cat titi*      
3. *cat tutu*       => meme contenu entre titi et tutu
4. *echo 'bleach' >> titi* => écriture de 'bleach' dans le fichier "titi"
5. *cat titi* => vérification de l'écriture de 'bleach' dans le fichier "titi"
6. *cat tutu* => même contenu entre titi et tutu
7. *echo 'bleach' >> tutu
8. *cat titi*                 
9. *cat tutu*             => meme contenu entre titi et tutu
10. *rm titi* => on supprime titi
11. *cat tutu* => *tutu : No such file or directory*

**NB** : avec la commande *ls* on observe que le fichier "tutu" est toujours présent dans le répertoire personnelle mais est affiché en rouge (via la commande *ls*). En effet, le fichier "tutu" pointe vers une zone mémoire autrefois occupée par "titi" mais dorénavant vide !!!

13- Commande  : *cat /var/log/syslog*

Cette commande permet d'afficher le fichier "syslog" relativement long. Par conséquent il est possible d'interrompre (*ctrl + s*) le défilement du fichier, ou de le reprendre (*ctrl + q*).

14- Commandes :

* *head -n 5 /var/log/syslog* => affiche les 5 premières lignes de /var/log/syslog
* *tail -n 15 /var/log/syslog* => affiche les 15 dernières lignes de /var/log/syslog
* *head -n 10 /var/log/syslog | tail -n 20* => affiche les lignes 10-20 de /var/log/syslog

15- Commande : *dsmeg | less*

Cette commande se décortique sous deux termes :

	 dsmeg  -  affiche la mémoire tampon de message du noyau linux
	|less   -  permet de lire le fichier (ici spécifier avant  "|") page par page sans le modifier

16- Commande : *cat /etc/passwd* => affiche contenu du fichier "passwd"

De plus, le fichier "passwd" contient une base de données textuelle d'informations sur l'ensemble des utilisateurs qui peuvent se connecter au système en cours de fonctionnement.

Pour afficher le manuel associée au fichier passwd, on note dans le terminal la commande : *man passwd*

17- Afin de trier la première colone de /etc/passwd par ordre alphabétique inverse on note la commande suivante : *sort +0 -0 -r /etc/passwd*

Cette commande se décompose de la manière suivante :

	sort        -  trie un fichier selon les options définis par la suite dans la même ligne de commande
	+0          -  commence le trie du fichier à la première colone (pour la seconde colone au notera +1, ainsi de suite)
	-0          -  fini le trie du fichier à la première colone (pour la seconde colone au notera -1, ainsi de suite)
	-r          -  trie selon l'ordre alphabétique inverse
	/etc/passwd -  le fichier à trier

18- Afin d'afficher seulement les utilisateurs de la machine, cela même contenu dans le fichier "passwd", on utilise la commande : *cut -f1 -d: /etc/passwd*

Cette commande se décompose de la manière suivante :

	cut          -  extraction d'un texte du fichier spécifié
	f1           -  spécifie que le "terrain" (field) à extraire est le numéro 1
	d:           -  spécifie que le délimiteur de terrain est ":"
	/etc/passwd  -  le fichier dont on souhaite extraire l'information

19- Afin de déterminer l'ensemble des pages de manuels comportant le mot-clé 'conversion', on utilise la commande suivante : *man -k conversion* . En conséquence, on observe à l'écran l'affichage de 4 pages de manuels, contenant le mot-clé 'conversion' dans leur description.

20- Dans le but d'afficher l'ensemble des fichiers présents sur la machine se nommant passwd on utilise la commande : *find -name passwd* . Il est toutefois plus pertinent de précéder la commande ci-dessus par "sudo" car certains fichiers ont un accès restreint aux simples utilisateurs. Ainsi, en appliquant la commande *sudo find -name passwd* on obtient le résultat suivant :

![Recherche passwd](https://github.com/cpe-lyon/tp-1-moine_pinet/blob/master/tpexo12.PNG)

21- Afin d'enregistrer cette même recherche dans un fichier dénommé "list_passwd_files.txt", on éxécutera la commande : *man -k -conversion >> ~/list_passwd_files.txt*

22- Dans le but de rechercher dans quel fichier du répertoire personnel est défini l'alias *ll*, on utilisera la commande suivante : *grep -r -i ll ./*

Cette commande se décortique de la manière suivante :

	-r   -  recherche récursive
	-i   -  insensible à la casse (majuscule-minuscule)
	./   -  recherche dans tous le répertoire
   
On trouve finalement que l'alias de 'll' est dans ".bashrc"

23- Afin de localiser le fichier "history.log", on utilisera la commande : *locate history.log* . On obtient à l'écran l'affichage de la ligne suivante : */var/log/apt/hystory.log* . En conséquence, "history.log" est présent dans le répertoire "/var/log/apt/".

24- Commandes :
1. *mkdir jesuisla*
2. *locate jesuisla*
3. Résulat => ""
Le fichier n'apparaît pas car locate rapporte seulement les fichiers créent après la plus récente mise à jour de la base de données courante.

 </br>
 </br>
 
## Partie 2

### Personnalisation du shell

 </br>
 </br>
 
Il est important que de noter que le shell présent dans le terminal minux peut se personnaliser. A cette effet, il est nécessaire de tenir compte de l'ensemble des outils que l'on peut disposer en ce shell, comme le montre le tableau ci-dessous :

![Personnilation du sheel](https://github.com/cpe-lyon/tp-1-moine_pinet/blob/master/tp14.PNG)

En décommentant la ligne *force_color_prompt=yes* pour activer la couleur et en utilisant la commande *source .bashrc* on obtient le rendu suivant :

![Personnilation du sheel étape 1](https://github.com/cpe-lyon/tp-1-moine_pinet/blob/master/tp11.PNG)

Par la suite, on implémente la ligne *PS1* attitré à la personnalisation du shell comme ci-dessous :

![Personnilation du sheel étape 2](https://github.com/cpe-lyon/tp-1-moine_pinet/blob/master/tp13.png)

On obtient en conséquence le shell suivant :

![Personnilation du sheel étape 3](https://github.com/cpe-lyon/tp-1-moine_pinet/blob/master/tp12.PNG)

L'ensemble des couleurs relatives au texte du shell sont données dans le tableau ci-dessous :

![Personnilation du sheel étape 4](https://github.com/cpe-lyon/tp-1-moine_pinet/blob/master/tp15.PNG)

 </br>
 </br>
 </br>
 </br>
 </br>
 </br>
 </br>
 </br>
 
 ![Charizard ascii](https://github.com/cpe-lyon/tp-1-moine_pinet/blob/master/charizard.PNG)




     







 
 

