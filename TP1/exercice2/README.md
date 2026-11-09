TP 2 : Création d'un serveur web avec Docker

Commandes réalisées
1. Télécharger Nginx : docker pull nginx
2. Lancer Nginx sur le port 8080 : docker run -d -p 8080:80 --name mon_nginx nginx
3. Conteneurs actifs : docker ps
4. Accès navigateur : http://localhost:8080
5. Arrêter le conteneur : docker stop mon_nginx
6. Supprimer le conteneur : docker rm mon_nginx