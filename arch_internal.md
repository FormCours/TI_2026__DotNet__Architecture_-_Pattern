# Architectures internes
L'organisation du code et des dépendances


## Architecture en couches (N-Tier / Layered)
Découpe horizontal en fonction des responsabilités techniques.

La découpe la plus frequente est la « 3 tiers » 
- Présentation : Affichage + Interaction
- Métier : Appliquer les régles business
- Accès aux données : Lecture et ecriture (Db, Fichier, Service ext, ...)  
![Schema N-Tier](./ressources/n-tier.png)

### Forces
- Simple
- Parfait pour des applications (CRUD)

### Limites
- Couplage fort de chaque couches
    - Changer un element peut impacter les autres 
    - Mapping entre les models de chaque couches
-  Difficile à faire évoluer à long terme


## Architecture Hexagonale
L'objectif est d'isolé les régles métiers et de définir des ports (interfaces) de communication vers l'exterieur.
Adapteur (exterieur) qui implémente les ports.  
![Schema Hexagonale](./ressources/hexa.png)

### Forces
- Regles métier testable facilement (Indepenant).
- Technologies remplaçables sans affecter le métier. 

### Limites
- Mise en place complexe (Plus d'interface et mapping)
- Execissif pour des petites applications


## Clean Architecture
Basé sur l'idée de l'architecture Hexagonal et l'architecture oignon. Organision du code sous forme cercles concentriques.  
![Schema Clean archi](./ressources/clean.png)

**Régle d'or :** _Les dépendances du code ne pointent que vers l'intérieur, un élémént interieur ne connait jamais la couche suppérieur._

### Forces
- Structure organisé avec les régles de dépendances
  - Visualisation "simple" du projet
  - Evolution du projet facilité
- Le métier est très protégé (Chaque use case isolé)
- Régles métier facilement testable

### Limites
- Beaucoup de code de structure
- Risque de sur-ingenierie sur les projets simple


## Vertical Slice
Contrairement à la N-Tier qui découpe en couche basé sur les rôles techniques.  
Cette architecture découpe le projet verticalement sur base des fonctionnalités.  
![Schema Vertical](./ressources/vertical.png)

### Forces
- Les fonctionnalités sont peu couplées entre elles.
- Chaque fonctionnalité est isolé 
  - Elle peut être adapté au besoin (implémentation différente possible).
  - Facilité pour : Ajout, modification et débug un tranche.

### Limites
- Risque de répéter les régles métiers (Necessite une refactorisation).
- Une modification métier ou data peut avoir des impacts dans plusieurs tranches.