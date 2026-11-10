# TP Docker
---

## TP 1

* **Exercice 1 : Manipulation de base des conteneurs**
  * Version de Docker : docker --version
  * Images locales : docker images
  * Télécharger hello-world : docker pull hello-world
  * Exécuter hello-world : docker run hello-world
  * Conteneurs actifs : docker ps
  * Tous les conteneurs : docker ps -a
  * Supprimer un conteneur : docker rm <ID_conteneur>
  * Supprimer une image : docker rmi <ID_image>

* **Exercice 2 : Création d'un serveur web avec Docker**
  * Télécharger Nginx : docker pull nginx
  * Lancer Nginx sur le port 8080 : docker run -d -p 8080:80 --name mon_nginx nginx
  * Conteneurs actifs : docker ps
  * Accès navigateur : http://localhost:8080
  * Arrêter le conteneur : docker stop mon_nginx
  * Supprimer le conteneur : docker rm mon_nginx

* **Exercice 3 : Déploiement d'une application Python Flask**
  * Création et conteneurisation d'une application web Python Flask minimale avec un Dockerfile (dossier TP_Flask).

* **Exercice 4 : Utilisation de Docker Compose**
  * Orchestration de l'application Flask avec une base de données MongoDB via docker-compose.yml.

---

## TP 2

* **Baseline : Image d'origine non optimisée**
  * Configuration : node:latest, paquets apt-get, pas d'optimisation de cache
  * 1.89 GB (Content Size : 476 MB)

* **Étape 1 : Choix d'une image de base minimale**
  * Modification : Passage sur node:20-alpine et nettoyage des dépendances système superflues
  * 222 MB (Content Size : 54 MB)

* **Étape 2 : Optimisation de la mise en cache (Layer Caching)**
  * Modification : Copie isolée de package*.json avant RUN npm install pour préserver le cache
  * 222 MB (Content Size : 54 MB)

* **Étape 3 : Multi-stage build & Sécurité**
  * Modification : Étape de build séparée, npm ci --only=production dans l'image finale et exécution avec l'utilisateur non-root node
  * 217 MB (Content Size : 53.2 MB)