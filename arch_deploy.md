# Architectures de déploiement

## Monolithe
Tout l'application est construire comme un seul bloc.  
Généralement avec une seul base de donnée.

### Force
- Simple à dev, à maintenir, à tester.
- Simple a déployer (un seul "package").
- Les appels entre services sont stable et rapide

### Limites
- Il faut redéployer l'application à la moindre modification.
- Difficile à upscaler.
- Necessite de la rigueur pour éviter que ce soit un bordel.


## Monolithe modulaire
Même concept que le `Monolithe` (un seul bloc à déployer), par contre l'intérieur est découpé sous forme de module (technique ou métier).  
Chaque module possède ses données et méthodes accessible. 

### Force
- On conserve la simplicité de déploiement (un seul "package") du Monolithe
- Le code est organisé sous forme de module.

### Limites
- Idem que Monolithe
- L'isolation en module repose sur la discipline de l'équipe.


## Microservices
L'application est composé de petits services indépendants.  
Chaque services possede son propre environnement (serveur, db).  

Type de communication possible : 
- Par réseau : HTTP
- Par événements : RabbitMQ, Kafka  (Event-Driven)

### Forces
- Chaque service peut choisir sa technologie
- Le déploiement est indépendant
    - Montée en charge (Puissance du serveur)
    - L'arrêt d'un service n'entraine pas forcement l'arrêt d'autres services 

### Limites
- Necessite la mise en place d'un systeme de communication
    - Plus complexe
    - Sensible à la panne
- Flux de communication entre service complexe (Transaction, deboguer)


## Serverless
Le code est découpé en fonctions qui sont déclenchées par des évents et exécutées sur les plate-formes cloud (Azure function, AWS Lambda, ...).  
Pas de gestion de serveur, on paie à l'utilisation.

### Forces
- Montée en charge automatique.
- Pas de coût quand il n'est pas utilisé.

### Limites
- Temps de démarrage.
- Durée de execution "limité".
- Dépendances au fournisseur cloud.