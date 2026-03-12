\# Diagramme de cas d’utilisation — V1



\## Objectif

La version V1 du diagramme de cas d’utilisation vise à \*\*délimiter le périmètre fonctionnel\*\* de l’application de \*gestion de centres de congrès\*.  

On se concentre sur les besoins du \*\*gestionnaire\*\* : configurer un centre, gérer les réservations, consulter les disponibilités, définir des tarifs et accéder à des statistiques.



\## Acteurs

\- \*\*Gestionnaire\*\* \*(acteur principal)\* : utilisateur de l’application. Il crée et pilote les réservations, configure le centre, gère tarifs/disponibilités et consulte les statistiques.

\- \*\*Système de paiement externe\*\* \*(optionnel selon le diagramme)\* : le paiement est géré hors application ; l’application ne fait que gérer l’état “confirmée” d’une réservation après paiement.



\## Cas d’utilisation



\### 1) Gestion des réservations

\- \*\*Créer une réservation\*\* : réserver une ou plusieurs parties d’un centre sur une période donnée, avec éventuellement du matériel et des prestations.

\- \*\*Confirmer une réservation\*\* : valider une réservation après paiement (paiement hors application).

\- \*\*Modifier une réservation\*\* : possible tant que l’événement n’a pas commencé.

\- \*\*Annuler une réservation\*\* : possible tant que l’événement n’a pas commencé.

\- \*\*Annuler une réservation non confirmée\*\* : si la réservation n’est pas confirmée après un délai, le gestionnaire peut l’annuler (à sa discrétion).



\### 2) Gestion des disponibilités

\- \*\*Consulter les disponibilités\*\* : visualiser la disponibilité des salles/parties du centre.

\- \*\*Gérer une indisponibilité\*\* : déclarer des périodes de maintenance/travaux.

\- \*\*Gérer des contraintes de location\*\* \*(optionnel)\* : durée minimale, jours interdits (week-end/jours fériés…).



\### 3) Gestion des tarifs

\- \*\*Définir / modifier un tarif\*\* : haute, moyenne et basse saison pour les parties du centre.

\- \*\*Calculer le coût d’une réservation\*\* : calcul automatique du coût selon la durée et le tarif sélectionné.



\### 4) Statistiques

\- \*\*Consulter les statistiques\*\* : événements prévus et passés, chiffre d’affaires par période (mois/année), taux d’occupation, utilisation des ressources/options.



\### 5) Configuration du centre

\- \*\*Configurer un centre\*\* : gérer les éléments (salles, amphi, restauration…), définir capacités, ressources et prestations associées.



\## Remarques

\- Les réservations passées sont \*\*conservées\*\* pour alimenter les statistiques.

\- Les diagrammes de séquence et d’états (notamment pour `Reservation`) s’appuieront sur ces cas d’utilisation comme scénarios de test.



\## Limites de la V1

La V1 est volontairement centrée sur les fonctionnalités essentielles. Les détails techniques (règles fines, contraintes, exceptions) seront précisés dans les versions suivantes via :

\- diagrammes de séquence (nominal + exceptions),

\- diagrammes d’états,

\- raffinements du diagramme de classes.

