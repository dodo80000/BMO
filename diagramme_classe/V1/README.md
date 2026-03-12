# Diagramme de classes — V1

## Objectif
Cette première version pose le **socle du modèle** pour la gestion de centres de congrès : centres, salles, événements, réservations, ressources (matériel/prestations) et tarification.

## Contenu du modèle
### Classes
- **CentreCongres** : représentation d’un centre (données d’identification) et point d’ancrage des salles.
- **Salle** : partie réservable d’un centre (capacité/prix de base).
- **Evenement** : description d’un événement (nom, description, participants, référent).
- **Reservation** : réservation d’une salle sur une période, avec information de confirmation.
- **Tarif** : tarification (saisonnalité/prix).
- **Ressource** *(abstraite)* : base commune pour les options réservables.
  - **Materiel** (hérite de Ressource)
  - **Prestation** (hérite de Ressource)
- **Gestionnaire** : pilote la configuration et les réservations.

### Relations (idée générale)
- Un **CentreCongres** regroupe des **Salle**.
- Une **Reservation** est associée à une **Salle** et à un **Evenement**.
- Une **Reservation** peut inclure des **Ressource** (matériel/prestations).
- Les **Tarif** s’appliquent aux éléments tarifables (salles et/ou ressources selon le modèle).

## Remarque
V1 est volontairement orientée **structure** (classes, attributs, liens). Les méthodes métier arrivent dans les versions suivantes.
