# UC4 — Annuler une réservation (SSD)

## Scénario nominal
1. Le **Gestionnaire** demande l’annulation d’une réservation.
2. Le **Système** vérifie que l’événement n’a pas commencé.
3. Le **Système** annule la réservation et renvoie un succès (statut **ANNULEE**).

## Exceptions (alt)
- Annulation impossible : événement déjà commencé

