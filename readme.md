# Architecture & pattern
Les choix entre architecture de déploiement et interne sont indépendants, exemple : 
- Monolithe en 3 tiers
- Monolithe en clean architecture
- Microservice en 3 tiers 
- ...

Les choix de pattern à utilisé, doivent être là pour solutioner une problematique. Il ne faut pas ajouter des patterns car « Ca pourrait servir ».

## Architecture de déploiement
Comment l'application est découpé : 
- Défini les éléments à déployer
- Défini la communication entre  

[Listing non exhaustif architectures de déploiement](arch_deploy.md)

## Architecture interne
Comment le organise et structure le code
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
Un element ne doit avoir qu'une seule raison de changer.

#### Open / Closed
Une classe doit être :
- Ouverte à l'extension (Héritage, Méthode d'extension, ...)
- Fermé à la modification 

On peut ajouter un comportement, sans modifier un code testé.

#### Liskov substitution
Un objet d'une classe dérivée doit pouvoir remplacer un objet de la classe de base sans casser le programme.

#### Interface segregation
Un client ne doit pas implémenter des methodes dont il n'a pas l'utilité. Préférer d'avoir des interfaces ciblées qu'une seule avec tout le brol.

#### Dependency inversion
Les elements "métier" ne doivent pas dépendre des elements techniques. Ceux-ci doivent dépendre d'une abstraction (interface).

### KISS (Keep It Simple, Stupid)
Le code doit rester le plus simple possible.  
La complexité doit être justifiée par un besoin _(En gros, ne pas ajouter des patterns car on a envie)_.

### YAGNI (You aren't gonna need it)
Ne pas mettre en place de fonctionnalité ou abstraction "au cas où".

### DRY (Don't Repeat Yourself)
Ne pas répéter du code dans le même objectif.  
Attention, ne pas refactorisé du code qui se ressemble par hasard.

## Documentation sur les patterns
[Refactoring guru](https://refactoring.guru/design-patterns/catalog)