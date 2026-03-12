# Diagramme de cas d’utilisation — V1

## Objectif
La V1 du diagramme de cas d’utilisation délimite le **périmètre fonctionnel** de l’application *Gestion de Centres de Congrès*.
Elle se concentre sur les actions métier du **Gestionnaire**.

## Acteurs
- **Gestionnaire** *(acteur principal)* : configure les centres, gère les réservations, tarifs, disponibilités et statistiques.
- **Système de paiement externe** *(acteur secondaire, optionnel)* : paiement hors application, la confirmation est enregistrée côté système.

## Cas d’utilisation

### Gestion des réservations
- **Créer une réservation**
- **Confirmer une réservation**
- **Modifier une réservation**
- **Annuler une réservation**
- **Gérer les réservations non confirmées** (délai dépassé)

### Gestion des disponibilités
- **Consulter les disponibilités**
- **Gérer des indisponibilités**
- *(optionnel)* **Contraintes de location** (durée minimale, jours interdits…)

### Gestion des tarifs
- **Définir / modifier un tarif**
- **Calculer le coût** (durée + tarif + options)

### Statistiques
- **Consulter les statistiques** (événements, CA, taux d’occupation, utilisation ressources)

### Configuration du centre
- **Configurer un centre** (salles/parties, capacités, ressources/prestations)
