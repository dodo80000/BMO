# Diagramme de classes — V4

## Objectif
Adapter le modèle à une contrainte de modélisation : introduire des types **Date** et **Datetime** et les utiliser dans les signatures des méthodes.

## Évolutions depuis V3
### Ajouts
- Ajout des classes **Date** et **Datetime**.

### Modifications (types)
- **Gestionnaire**
  - Les méthodes de création de réservation et définition de tarif utilisent `Date` au lieu de `date`.
- **Reservation**
  - `modifierDates(...)` utilise `Date`.
- **Salle** et **Ressource**
  - `estDisponible(...)` utilise `Date`.

## Remarque
Cette version sert à formaliser des types “valeurs” en UML (Date/Datetime). La compatibilité générateur/outil sera stabilisée dans la version suivante.
