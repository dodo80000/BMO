# UC3 — Modifier une réservation (SSD)

## Scénario nominal
1. Le **Gestionnaire** demande la modification (nouvelles dates et/ou nouvelles ressources).
2. Le **Système** :
   - vérifie que la réservation est **modifiable** (événement non commencé),
   - vérifie disponibilité sur la nouvelle période,
   - vérifie ressources/stock,
   - met à jour les dates,
   - recalcule le coût total.
3. Le **Système** renvoie la confirmation de modification + le nouveau coût.

## Exceptions (alt)
- Réservation non modifiable (événement déjà commencé)
- Nouvelle période indisponible
- Ressource indisponible / stock insuffisant

