# Diagramme de classes — V3

## Objectif
Introduire le **comportement métier** : ajout des principales méthodes correspondant aux cas d’utilisation (réservations, disponibilités, tarifs, statistiques).

## Évolutions depuis V2
### Ajouts de méthodes
- **Evenement**
  - Ajout de méthodes de calcul/agrégation (ex. participants, statistiques).
- **Gestionnaire**
  - Ajout des opérations de pilotage (créer/modifier/annuler une réservation, définir un tarif, consulter des statistiques…).
  - Renommage de l’attribut `attribute` → `attribut`.
- **Reservation**
  - Ajout des opérations du cycle de vie (confirmer, annuler, modifier, calculer coût, vérifications…).
- **Salle**
  - Ajout de méthodes de disponibilité/contraintes (ex. indisponibilités, vérification capacité, coût).
- **Ressource**
  - Ajout de méthodes de disponibilité, stock et coût.
- **Tarif**
  - Ajout de méthodes `estApplicable(...)` et `calculerPrix(...)`.

## Remarque
Cette version est la base idéale pour produire :
- les **diagrammes de séquence** (les opérations existent),
- le **diagramme d’état** de `Reservation` (cycle de vie explicité).
