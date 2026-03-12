# UC5 — Définir un tarif (SSD)

## Scénario nominal
1. Le **Gestionnaire** définit un tarif saisonnier (nom de saison, prix, unité, période).
2. Le **Système** vérifie la validité de la période et l’absence de conflit.
3. Le **Système** crée le tarif et l’associe à la salle (ou ressource selon le modèle).

## Exceptions (alt)
- Période invalide (`dateDebutSaison > dateFinSaison`)
- Chevauchement / conflit de saison avec un tarif existant

