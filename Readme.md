TP 1 - Docker

- TP1/exercice1 : manipulation de base des conteneurs
Version de Docker : docker --version
Images locales : docker images
Télécharger hello-world : docker pull hello-world
Exécuter hello-world : docker run hello-world
Conteneurs actifs : docker ps
Tous les conteneurs : docker ps -a
Supprimer un conteneur : docker rm <ID_conteneur>
Supprimer une image : docker rmi <ID_image>

- TP1/exercice2 : Création d'un serveur web avec Docker
Télécharger Nginx : docker pull nginx
Lancer Nginx sur le port 8080 : docker run -d -p 8080:80 --name mon_nginx nginx
Conteneurs actifs : docker ps
Accès navigateur : http://localhost:8080
Arrêter le conteneur : docker stop mon_nginx
Supprimer le conteneur : docker rm mon_nginx