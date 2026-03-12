# Diagramme de classes — V5 (final)

## Objectif
Stabiliser le modèle pour qu’il soit **exploitable dans BESSER** : ajout de constructeurs, nettoyage de l’héritage, et correction des collisions de noms (attributs vs paramètres), tout en conservant les opérations métier.

## Évolutions depuis V4
### Retrait / simplification des types Date/Datetime
- Suppression des classes **Date** et **Datetime** et retour à des types attendus par l’outil (`date`/`datetime`) dans les signatures nécessaires.

### Ajout de constructeurs
- Ajout de constructeurs explicites (exemples) :
  - `CentreCongres(...)`
  - `Salle(...)`
  - `Reservation(...)`
  - `Evenement(...)`
  - `Tarif(...)`
  - `Ressource(...)`, `Materiel(...)`, `Prestation(...)`

### Nettoyage de l’héritage (Ressource)
- Suppression d’attributs redondants dans les sous-classes :
  - `Materiel.nom` et `Prestation.nom` supprimés car hérités de **Ressource**.

### Corrections “anti-collisions” (compatibilité BESSER)
- Renommage de paramètres de méthodes et constructeurs pour éviter les doublons de noms avec les attributs :
  - suffixes/préfixes du type `...Param`, `...Init`, etc.

### Ajustements de méthodes
- Harmonisation de certaines signatures (retours/paramètres) pour correspondre au générateur BESSER.

## Résultat
Version finale **fonctionnelle** : le modèle conserve les concepts du cahier des charges et les opérations nécessaires, tout en restant compatible avec les contraintes de l’outil.
