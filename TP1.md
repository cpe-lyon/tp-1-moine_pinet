# Compte-Rendu Administration
## Partie 1
### Prise en main de l’interpréteur de commandes

1. Commande : *which [-a] nom_de_fichier*


Cette commande permet de renvoyer le chemin des fichiers éxécutés ultérieurement dans l'environnement
si les arguments données en commande dans l'interpreteur de commande sont conformes à **POSIX**.
En conséquence, *which* cherche la variable **PATH** dans les fichiers éxécutables.


-a => affiche tous les chemins correspondant à chaque argument (nom_de_fichier)

Valeur de retour :
 0	toutes commanes spé sont trouvées et éxe
 1	si une commande spé n'existe pas ou n'est pas éxe
 2	si une option non valable est spé
