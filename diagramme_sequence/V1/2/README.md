# UC2 — Confirmer une réservation (SSD)

## Scénario nominal
1. Le **Gestionnaire** lance la confirmation d’une réservation (paiement réalisé **hors application**).
2. Le **Système** charge la réservation et vérifie que la confirmation est dans le délai.
3. Si OK, le **Système** passe la réservation à l’état **CONFIRMEE** et renvoie un succès.

## Exceptions (alt)
- Réservation inconnue
- Réservation déjà confirmée
- Réservation annulée
- Délai de confirmation dépassé

