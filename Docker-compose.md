# Docker-Compose

Verifier la version dipo sur notre poste : 

````docker-compose --version````

Ecriture des configs dans : 

````docker-composer.yaml````


Lancer un ensemble de contener/démarrer une stack : (c'est l'équivalent de docker run pour lancer un seul conteneur)

````docker-compose up````

Verifier l'état des conteneurs lancés : 

````docker-compose ps````


Afficher les logs des conteneur lancé, et limiter la taille aux 5 premières lignes : 

````docker-compose logs -f --tail 5````

Stopper une stack : 

````docker-compose stop````

Detruire l'ensemble des ressources produites : 

````docker-compose down````

Verifier la syntaxe avant de lancer une stack : 

````docker-compose config````
