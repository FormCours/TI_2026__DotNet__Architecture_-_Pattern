# Architectures de déploiement

## Monolithe
Toute l'application est construite comme un seul bloc.  
Généralement avec une seule base de données.

### Force
- Simple à dev, à maintenir, à tester.
- Simple à déployer (un seul "package").
- Les appels entre services sont stables et rapides

### Limites
- Il faut redéployer l'application à la moindre modification.
- Difficile à upscaler.
- Nécessite de la rigueur pour éviter que ce soit un bordel.


## Monolithe modulaire
Même concept que le `Monolithe` (un seul bloc à déployer), par contre l'intérieur est découpé sous forme de modules (techniques ou métier).  
Chaque module possède ses données et méthodes accessibles. 

### Force
- On conserve la simplicité de déploiement (un seul "package") du Monolithe
- Le code est organisé sous forme de modules.

### Limites
- Idem que Monolithe
- L'isolation en module repose sur la discipline de l'équipe.


## Microservices
L'application est composée de petits services indépendants.  
Chaque service possède son propre environnement (serveur, db).  

Type de communication possible : 
- Par réseau : HTTP
- Par événements : RabbitMQ, Kafka  (Event-Driven)

### Forces
- Chaque service peut choisir sa technologie
- Le déploiement est indépendant
    - Montée en charge (Puissance du serveur)
    - L'arrêt d'un service n'entraîne pas forcément l'arrêt d'autres services 

### Limites
- Nécessite la mise en place d'un système de communication
    - Plus complexe
    - Sensible à la panne
- Flux de communication entre services complexe (Transaction, déboguer)


## Serverless
Le code est découpé en fonctions qui sont déclenchées par des événements et exécutées sur les plateformes cloud (Azure function, AWS Lambda, ...).  
Pas de gestion de serveur, on paie à l'utilisation.

### Forces
- Montée en charge automatique.
- Pas de coût quand il n'est pas utilisé.

### Limites
- Temps de démarrage.
- Durée d'exécution "limitée".
- Dépendances au fournisseur cloud.