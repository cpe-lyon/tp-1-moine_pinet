# Compte-Rendu Administration
## Partie 1
### Prise en main de l’interpréteur de commandes

#### Manuel
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

#### Navigation dans l’arborescence des fichiers

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

* *cd ~* (on revient à la racine !!!)
* *mkdir dossier1* ; *mkdir dossier2* (on crée les dossiers dans la racine)
* *cd dossier1* ; *touch fichier1* (on va dans "dossier1" et on crée "fichier1")
  
  **NB** : "ls" permet de voir le contenu d'un dossier et donc de vérifier la présence (et en ce sens leur création) 
  des fichiers et dossiers dans l'emplacement courant
     
* *cd ~/dossier2* (on va dans le "dossier2" via le chemin absolu)
* *mkdir dossier2.1* ; *mkdir dossier2.2* (on créer les dossiers dans "dossier2")
     
* *cd dossier2.2* ; *touch fichier2* ; *touch fichier3* (on créer les fichiers "fichier2" et "fichier3" dans le "dossier2.2")
     







 
 

