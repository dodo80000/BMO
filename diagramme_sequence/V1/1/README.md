# UC1 — Créer une réservation (SSD)

## Scénario nominal
1. Le **Gestionnaire** demande la création d’une réservation (période, salle, informations d’événement, ressources optionnelles, date limite de confirmation).
2. Le **Système** :
   - vérifie la disponibilité de la salle sur la période,
   - vérifie la capacité par rapport au nombre de participants,
   - vérifie la disponibilité/stock des ressources demandées,
   - calcule le coût total.
3. Le **Système** crée la réservation avec le statut **EN_ATTENTE** et retourne l’identifiant + le coût + la date limite.

## Exceptions (alt)
- **Salle indisponible** → retour `erreur("Salle indisponible sur la période")`
- **Capacité insuffisante** → retour `erreur("Capacité insuffisante")`
- **Ressource non disponible / stock insuffisant** → retour `erreur("Ressource indisponible ou stock insuffisant")`
- **Dates invalides** (`dateDebut > dateFin`) → retour `erreur("dateDebut doit être avant dateFin")`

