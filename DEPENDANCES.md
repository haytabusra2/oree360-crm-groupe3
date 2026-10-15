# Dépendances – Orée 360 CRM (groupe 3)

## Bibliothèques externes
Aucune. Le code n'importe ni bibliothèque JavaScript, ni feuille de style, ni police, ni image externe, et il n'envoie
aucune requête vers un autre site. Le PDF des propositions et des lettres de mission est produit par un générateur écrit
dans l'application (PDF 1.4, police Helvetica).

## Deux versions du même code
| Version | Adresse | Données | Fichiers déposés |
|---|---|---|---|
| Plateforme claude.ai (artefact) | https://claude.ai/artifact/RaZhR2pqff14WnN5tNuA5j | Base partagée de l'artefact | Stockage de fichiers de l'artefact (lien direct, sans contrôle serveur) |
| Version autonome | https://crm-oree360.netlify.app | Stockage local du navigateur (localStorage), propre à chaque visiteur | IndexedDB du navigateur |

La version autonome ne dépend d'aucun service de la plateforme : le fichier `index.html` s'ouvre aussi hors ligne une fois chargé.
Les données sont fictives dans les deux versions.

## Services de la plateforme (version artefact uniquement)
| Service | Usage | Remarque |
|---|---|---|
| Base de données partagée de l'artefact | Organisations, contacts, opportunités, échanges, tâches, propositions, lettres, pièces, référentiel, journal, recette | Règles d'accès sur le chemin du journal (écriture réservée à son auteur) |
| Identité de l'utilisateur | Rattachement de chaque action à une personne identifiée | Un seul compte par personne ; le profil est un menu de démonstration protégé par une connexion simulée |
| Téléchargement de fichiers | Exports CSV, PDF de proposition et de lettre, export des données d'un contact (JSON) | |
| Stockage de fichiers | Pièces déposées par le client (PDF, PNG, JPG, CSV, TXT, 5 Mo) | Lien direct sans contrôle serveur |

Contrat d'exécution des artefacts claude.ai utilisé : version 0.2.75 (relevée dans la documentation de la plateforme).

## Navigateurs
Navigateurs récents (Chrome, Edge, Safari, Firefox). Le stockage local du navigateur conserve le profil choisi et les
brouillons de formulaires (organisation, contact, opportunité, échange, tâche).

## Outils d'IA utilisés pour produire le code
Assistant Claude (Anthropic) via claude.ai ; avis externe par Gemini (Google). Détails et journal de prompts : annexe IA.

## Dépendance à la plateforme et réversibilité
La version artefact ne fonctionne pas hors de la plateforme, d'où la version autonome, publiée sur Netlify, qui reprend le même code.
Les données peuvent être exportées en CSV (organisations, opportunités, journal d'audit, grille de recette) et les données d'un contact
en JSON. Le code complet figure dans ce dépôt.
