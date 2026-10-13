# Dépendances – Orée 360 CRM (groupe 3)

## Bibliothèques externes
Aucune. Le code n'importe ni bibliothèque JavaScript, ni feuille de style, ni police, ni image externe.
Le PDF des propositions est produit par un générateur écrit dans l'application (PDF 1.4, police Helvetica).

## Services de la plateforme (obligatoires)
| Service | Usage | Remarque |
|---|---|---|
| Base de données partagée de l'artefact | Organisations, contacts, opportunités, échanges, tâches, propositions, lettres, pièces, journal, recette | Règles d'accès sur le chemin du journal (écriture réservée à son auteur) |
| Identité de l'utilisateur | Rattachement de chaque action à une personne identifiée | Un seul compte par personne ; le profil est un menu de démonstration |
| Téléchargement de fichiers | Export CSV, PDF de proposition | |
| Stockage de fichiers | Pièces déposées par le client (PDF, PNG, JPG, CSV, TXT, 5 Mo) | Lien direct sans contrôle serveur |

Contrat d'exécution des artefacts claude.ai utilisé : version 0.2.75 (relevée dans la documentation de la plateforme).

## Navigateurs
Navigateurs récents (Chrome, Edge, Safari, Firefox). Stockage local du navigateur utilisé pour le profil choisi et les
brouillons de formulaires (organisation, contact, opportunité, échange, tâche).

## Outils d'IA utilisés pour produire le code
Assistant Claude (Anthropic) via claude.ai ; avis externe par Gemini (Google) ; essai non abouti de Lovable avec Supabase
(version avec serveur, non déployée). Détails et journal de prompts : annexe IA.

## Dépendance à la plateforme
Le fichier ne fonctionne pas hors de la plateforme. Les données peuvent être exportées en CSV. Une version avec base de
données propre (Postgres avec règles d'accès, hébergement UE) a été préparée mais n'est pas déployée.
