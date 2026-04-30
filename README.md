\# Workshop Docker - DVWA



\## Objectif



Déploiement d'une infrastructure web vulnérable avec Docker Compose.



\## Services



\- DVWA : application web vulnérable

\- MySQL : base de données

\- NGINX : reverse proxy

\- phpMyAdmin : bonus optionnel



\## Architecture



Le navigateur accède uniquement à NGINX sur le port 8080.



NGINX redirige vers DVWA.



DVWA communique avec MySQL via un réseau Docker interne.



MySQL n'est pas exposé directement sur la machine hôte.



\## Commandes principales



```bash

docker compose up -d

docker compose ps

docker compose down



\## Vérifications réalisées



\- Les conteneurs Docker sont lancés avec Docker Compose.

\- DVWA est accessible via NGINX sur http://localhost:8080.

\- DVWA n'est pas exposé directement.

\- MySQL n'est pas accessible depuis la machine hôte.

\- DVWA communique avec MySQL via le réseau Docker interne.

\- Une injection SQL a été testée sur DVWA en niveau Low.



\## Réponses aux questions



\### Pourquoi l'attaque SQL Injection fonctionne-t-elle ?



Elle fonctionne car l'application utilise une entrée utilisateur directement dans une requête SQL sans filtrage suffisant. L'entrée malveillante modifie la logique de la requête.



\### Quel est le rôle de la base de données ?



La base de données stocke les informations de l'application. Dans cette faille, elle exécute la requête SQL envoyée par l'application, même si celle-ci a été modifiée par l'attaquant.



\### Docker protège-t-il contre cette vulnérabilité ?



Non. Docker permet d'isoler les services et de limiter l'exposition réseau, mais il ne corrige pas les failles du code applicatif.

