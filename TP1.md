# Compte-Rendu Administration
## Partie 1
### Prise en main de l’interpréteur de commandes

1- Commande : *which [-a] nom_de_fichier*

*-a* => affiche tous les chemins correspondant à chaque argument (en l'occurrence ici nom_de_fichier)

Cette commande permet de renvoyer le chemin des fichiers éxécutés ultérieurement dans l'environnement
si les arguments données en commande dans l'interpreteur de commande sont conformes à **POSIX**.
En conséquence, *which* cherche la variable **PATH** dans les fichiers éxécutables.

Valeurs de retour :

     0	- toutes les commandes spécifiés sont trouvées et éxécutées
 
     1	- si une commande spécifiée n'existe pas ou n'est pas éxécutée
 
     2	- si une option non valable est spécifiée
     
2- Il est possible de rechercher un terme dans le manuel (appelé avec la commande *man*). Pour cela on utilise la commande : */ terme_recherche*  (dans l'interface du manuel). Le symbole *"/"* précède le nom du terme recherché. Par exemple, *"/option"* recherchera l'ensemble des occurences du terme "option" dans la page du manuel actuellement affichée.

Il est important de noter que ces recherches adopte différentes options, plus ou moins utiles en fonction de notre "position" dans le manuel consulté (par cela j'entends dire à quelle page nous nous situons). En ce sens, nous avons les options suivantes :

     /	- pour chercher un terme devant notre position relative dans le manuel consulté
 
     ?	- pour chercher un terme derrière notre position relative dans le manuel consulté
 
     &	- pour afficher seulement les lignes qui "matchent" avec notre recherche
     
3- On peut quitter le manuel actuellement consulté à tous moment en appuyant sur la touche *q*

4- 



 
 

