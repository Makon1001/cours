# Docker

## Commande docker : 

### Pour lancer une image : ici on lance un server nginx
````docker run -d -p 8080:80 nginx````

Les instructions : 
````-d````permet de détacher le conteneur du processus principal de la console

````-p````pour définir l’utilisation des ports. Ici on transfert le trafic du port 8080 vers le port 80 , ainsi si on se rend à l’adresse http://127.0.0.1:8000 

````-a````pour lister All

Pour executer un bash sur le conteneur : 
````docker exec -ti ID_RETOURNÉ_LORS_DU_DOCKER_RUN bash````

````-ti````pour le mode tty

````bash```` pour un acces au bash 

Stoper un service : 

````docker stop ID_RETOURNÉ_LORS_DU_DOCKER_RUN ````

Supprimer une image : 

````docker rm ID_RETOURNÉ_LORS_DU_DOCKER_RUN````

Pour récupérer une image sur DockerHub sans lancer le contenu : (ici l'image hello-world')

````docker pull hello-world```` 

Lister l'ensemble des conteneurs actifs : 

````docker ps````

Lister l'ensemble des images : 

````docker images -a````

Pour faire le ménage : 

````docker system prune````
WARNING! This will remove:
- all stopped containers
- all networks not used by at least one container
- all dangling images
- all dangling build cache

## Dockerfile type pour node.js : 
````FROM debian:9

RUN apt-get update -yq \
&& apt-get install curl gnupg -yq \
&& curl -sL https://deb.nodesource.com/setup_10.x | bash \
&& apt-get install nodejs -yq \
&& apt-get clean -y

ADD . /app/
WORKDIR /app
RUN npm install

EXPOSE 2368
VOLUME /app/logs

CMD npm run start
````

## Les explications osur le Dockerfile : 
FROM qui vous permet de définir l'image source ;

RUN qui vous permet d’exécuter des commandes dans votre conteneur ;

ADD qui vous permet d'ajouter des fichiers dans votre conteneur ;

WORKDIR qui vous permet de définir votre répertoire de travail ;

EXPOSE qui permet de définir les ports d'écoute par défaut ;

VOLUME qui permet de définir les volumes utilisables ;

CMD qui permet de définir la commande par défaut lors de l’exécution de vos conteneurs Docker.


## Création d'un .dockerignore : 
````
node_modules
.git
````



Créer une image docker depuis le dockerfile : 
````docker build -t NomDeLimage .````

````-t````permet de definir le nom 
```` . ```` défini le répertoire dans lequel se trouve le Dockerfile

Lancer le conteneur : 
````docker run -d -p 2368:2368 ocr-docker-build```` : Vous retrouvez, dans le dossier logs, les logs de votre application, et vous pourrez y accéder sur le port 2368, soit via l'URL http://127.0.0.1:2368.


