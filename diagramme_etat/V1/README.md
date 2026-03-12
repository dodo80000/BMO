\# Diagrammes d’état — Gestion de Centres de Congrès



\## Objectif

Les diagrammes d’état décrivent le \*\*cycle de vie\*\* des objets du système et les \*\*transitions\*\* possibles entre leurs états.

Ils servent à :

\- formaliser les règles métier (ce qui est autorisé / interdit),

\- guider l’implémentation (notamment via un pattern de type \*State\*),

\- préparer les scénarios de test (liés aux diagrammes de séquence).



Le sujet demande explicitement des diagrammes d’état pour les classes pertinentes, \*\*en particulier la classe `Reservation`\*\*.



---



\## 1) Diagramme d’état — `Reservation` (principal)



\### États modélisés

\- \*\*EnAttenteConfirmation\*\* : réservation créée mais non confirmée (paiement géré hors application).

\- \*\*Confirmee\*\* : réservation validée dans le délai.

\- \*\*Expiree\*\* : délai de confirmation dépassé (le gestionnaire peut décider d’annuler).

\- \*\*Annulee\*\* : réservation annulée (possible tant que l’événement n’a pas commencé).

\- \*\*EnCours\*\* : l’événement a commencé, la réservation est active.

\- \*\*Terminee\*\* : l’événement est fini, la réservation est conservée pour les statistiques.



\### Transitions principales

\- `creerReservation()` : `\[\*] -> EnAttenteConfirmation`

\- `confirmer()` : `EnAttenteConfirmation -> Confirmee` \*\*si\*\* la confirmation est faite dans les temps.

\- `delaiDepasse()` : `EnAttenteConfirmation -> Expiree` si la date limite est dépassée.

\- `annuler()` : possible depuis `EnAttenteConfirmation` / `Confirmee` / `Expiree` (selon règles), \*\*tant que l’événement n’a pas commencé\*\*.

\- `modifierDates(...)` : autorisé uniquement en état `Confirmee` et si `estModifiable() == true`.

\- `debutEvenement()` : `Confirmee -> EnCours`

\- `finEvenement()` : `EnCours -> Terminee`



\### Règles métier couvertes

\- Une réservation non confirmée au bout d’un délai peut être annulée par le gestionnaire.

\- Une réservation confirmée peut être modifiée ou annulée \*\*tant que l’événement n’a pas commencé\*\*.

\- Les réservations passées sont conservées pour les statistiques.



---



\## 2) Diagramme d’état — `Tarif` (optionnel)

Un tarif est lié à une période de saison. Le cycle de vie est simple :

\- \*\*Inactif\*\* (créé mais pas encore dans sa période),

\- \*\*Actif\*\* (pendant la saison),

\- \*\*Expire\*\* (après la saison).



But : clarifier l’application des tarifs selon la date.



---



\## 3) Diagramme d’état — `Evenement` (optionnel)

Cycle de vie possible :

\- \*\*Planifie\*\*

\- \*\*EnCours\*\*

\- \*\*Termine\*\*

\- (optionnel) \*\*Annule\*\*



But : relier le démarrage/fin d’un événement avec la réservation.



---



\## 4) Diagramme d’état — `Salle` (optionnel)

Modèle simplifié :

\- \*\*Disponible\*\*

\- \*\*Indisponible\*\* (maintenance/travaux)

\- \*\*Reservee\*\* (sur une période)



But : représenter les périodes d’indisponibilité et la disponibilité globale.



---



\## Notes de modélisation

\- Les transitions temporelles (début/fin/délai) peuvent être vues comme des événements déclenchés par la date courante.

\- Le diagramme d’état de `Reservation` est le plus important car il structure les cas d’utilisation :

&nbsp; - création,

&nbsp; - confirmation,

&nbsp; - modification,

&nbsp; - annulation,

&nbsp; - passage en “en cours / terminé”.



---



\## Livrables associés

\- Diagrammes de séquence (nominal + exceptions) pour chaque cas d’utilisation.

\- Diagramme d’état (au minimum `Reservation`).

\- Diagramme de classes final cohérent avec ces transitions (méthodes `confirmer`, `annuler`, `modifierDates`, `estModifiable`, etc.).

