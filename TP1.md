# Compte-Rendu Administration
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

#### Commandes importantes

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

6- La commande *ls ..*  liste l'ensemble des fichiers et dossiers (ne commançant pas par ".") présents dans le répertoire parent de l'emplacement courant de l'utilisateur dans l'arborescence des fichiers linux.

**NB**: pour plus de pertinence et pour n'omettre aucun fichier, on peut utiliser *la ..* qui listera l'ensemble des fichirs et dossiers présents dans le répertoire parent de l'emplacement courant de l'utilisateur dans l'arborescence des fichiers linux.

7- 




     







 
 

