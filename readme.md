# Architecture & pattern
Les choix entre architecture de déploiement et interne sont indépendants, exemple : 
- Monolithe en 3 tiers
- Monolithe en clean architecture
- Microservice en 3 tiers 
- ...

Les choix de patterns à utiliser doivent être là pour solutionner une problématique. Il ne faut pas ajouter des patterns car « Ça pourrait servir ».

## Architecture de déploiement
Comment l'application est découpée : 
- Définit les éléments à déployer
- Définit la communication entre les éléments  

[Listing non exhaustif architectures de déploiement](arch_deploy.md)

## Architecture interne
Comment on organise et structure le code
- Dossier des classes
- Les dépendances

[Listing non exhaustif architectures interne](arch_internal.md)

## Principes de conception

### SOLID 
Objectif : 
- Rendre le code plus compréhensible
- Faciliter l'évolution et la maintenance
- Permet la mise en place des tests plus facilement

#### Single responsibility
Un élément ne doit avoir qu'une seule raison de changer.

#### Open / Closed
Une classe doit être :
- Ouverte à l'extension (Héritage, Méthode d'extension, ...)
- Fermée à la modification 

On peut ajouter un comportement, sans modifier un code testé.

#### Liskov substitution
Un objet d'une classe dérivée doit pouvoir remplacer un objet de la classe de base sans casser le programme.

#### Interface segregation
Un client ne doit pas implémenter des méthodes dont il n'a pas l'utilité. Préférer d'avoir des interfaces ciblées qu'une seule avec tout le brol.

#### Dependency inversion
Les éléments "métier" ne doivent pas dépendre des éléments techniques. Ceux-ci doivent dépendre d'une abstraction (interface).

### KISS (Keep It Simple, Stupid)
Le code doit rester le plus simple possible.  
La complexité doit être justifiée par un besoin _(En gros, ne pas ajouter des patterns car on a envie)_.

### YAGNI (You aren't gonna need it)
Ne pas mettre en place de fonctionnalité ou abstraction "au cas où".

### DRY (Don't Repeat Yourself)
Ne pas répéter du code dans le même objectif.  
Attention, ne pas refactoriser du code qui se ressemble par hasard.

## Documentation sur les patterns
[Refactoring guru](https://refactoring.guru/design-patterns/catalog)