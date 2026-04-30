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

