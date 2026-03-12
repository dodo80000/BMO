# Diagramme d’état — V1

## Objectif
Ce diagramme d’état décrit le **cycle de vie** des objets et les **transitions** possibles entre états.
Le diagramme principal concerne la classe **`Reservation`**, comme demandé dans le sujet.

## Reservation — États
- **EnAttenteConfirmation** : réservation créée mais non confirmée.
- **Confirmee** : réservation validée dans le délai.
- **Expiree** : délai de confirmation dépassé (annulation possible à la discrétion du gestionnaire).
- **Annulee** : réservation annulée (avant début d’événement).
- **EnCours** : l’événement a commencé, réservation active.
- **Terminee** : l’événement est fini, réservation conservée pour les statistiques.

## Transitions principales
```text
creerReservation() : [*] -> EnAttenteConfirmation
confirmer()        : EnAttenteConfirmation -> Confirmee   [estDansDelaiConfirmation()]
delaiDepasse()     : EnAttenteConfirmation -> Expiree     [!estDansDelaiConfirmation()]
annuler()          : EnAttenteConfirmation/Confirmee/Expiree -> Annulee [avant début événement]
debutEvenement()   : Confirmee -> EnCours
finEvenement()     : EnCours -> Terminee
modifierDates(...) : Confirmee -> Confirmee               [estModifiable()]
```
