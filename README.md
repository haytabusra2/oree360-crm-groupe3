# Orée 360 – CRM et portail client (fiche D)

Prototype pédagogique du service **Relation client** du cabinet fictif « Orée Expertise & Conseil »
(cours *Implantation des PGI*, Master 2 CCA, IAE Limoges). **Groupe 3** : Busra HAYTA, Marius BERLANDE,
Omar BEN KATOU, Titouan VINCENT, Alexandre MAZET. Remise : 20/10/2026.

> Toutes les données sont fictives. Aucune donnée réelle de client ne doit être saisie ni déposée.
> L'envoi de messages et la signature sont simulés (mention « simulation » visible).

## Contenu du dépôt

| Fichier | Rôle |
|---|---|
| `crm_oree360.html` | L'application complète (un seul fichier : HTML, CSS et JavaScript, sans bibliothèque externe) |
| `README.md` | Ce document |
| `DEPENDANCES.md` | Liste des dépendances et de leur rôle |

## Accès à l'outil

L'application est publiée comme artefact de la plateforme claude.ai :
https://claude.ai/artifact/RaZhR2pqff14WnN5tNuA5j
(accès réservé à l'organisation du propriétaire et aux personnes invitées ; la base de données et le dépôt de
fichiers sont ceux de la plateforme). Le fichier `crm_oree360.html` seul ne fonctionne pas hors de la plateforme :
il utilise ses services de base de données, d'identité, de téléchargement et de fichiers.

## Ce que fait l'outil

- Organisations et contacts, détection de doublons (identifiant, e-mail, nom), champs RGPD (information, base légale,
  consentement, opposition), fiche de **vigilance** simplifiée exigée avant l'activation d'un client (RG32).
- Pipeline d'opportunités contrôlé par les données (RG06 à RG08), échanges, tâches, tableau de bord D.9.
- Propositions versionnées (validation par un autre profil, envoi simulé, expiration), PDF généré par l'application.
- Lettres de mission, signature simulée, activation du client avec identifiant stable `CLI-…`, export CSV.
- Portail client séparé : demande de pièce, dépôt d'un fichier, correction, acceptation, traitement.
- Relances simulées, fusion de doublons (fiche source archivée, historique conservé).
- Journal d'audit (auteur, date, profil, action, avant/après, refus), grille de recette (33 tests), scénario de
  démonstration en 6 étapes, remise aux données de base.

## Profils

Commercial, Responsable développement, Assistante, Responsable de dossier, Direction, Client (portail).
Le profil se choisit dans un menu : ce sont des **profils de démonstration** (voir limites).

## Scénario de démonstration (fiche D)

1. Créer un prospect et détecter un doublon · 2. Qualifier une opportunité et enregistrer un échange ·
3. Générer une proposition · 4. Simuler la contractualisation et activer le client ·
5. Déposer une pièce depuis le portail · 6. Demander sa correction.
Le compteur « Scénario de démonstration » de l'onglet Recette se coche tout seul (6 / 6).

## Données de démonstration et remise à zéro

Onglet **Recette** (profil Responsable développement ou Direction) : « Réinitialiser les données de démonstration »
recharge le jeu de départ (10 organisations dont 2 clients, 11 opportunités, 3 propositions, 1 lettre, etc.).
« Décocher recette et démonstrations » remet les cases à zéro.

## Tests

La grille de recette T01 à T33 est dans l'onglet **Recette**. 20 tests se cochent à partir du journal ;
les autres se testent à la main. Chaque test compare le résultat observé au résultat attendu puis est accepté ou refusé.

## Limites connues

- Les droits par rôle et l'isolation des clients sont appliqués **par l'interface**, pas par un serveur
  (T13, T22, T30). La plateforme n'applique côté serveur que des règles par chemin et niveau d'accès (journal, identité).
- Le lien direct d'un fichier déposé s'ouvre sans contrôle côté serveur.
- Chaque utilisateur peut modifier ses propres lignes de journal ; le propriétaire de l'artefact peut en écrire.
- Vigilance simplifiée (pas de contrôle de listes de sanctions ni de justificatif réel).
- Pas de synchronisation avec les autres modules ; volumes réels inconnus ; pas de double authentification.
- Version avec serveur et comptes réels : méthode préparée, non déployée.

## Structure du code

Le fichier `crm_oree360.html` est organisé en sections commentées : données de départ (`SEED`), droits (`RIGHTS`),
journal et traçabilité (`act`, `refuse`, `auditWrite`), formulaires (`openForm`), vues (`vDashboard`, `vOrganisations`,
`vOpps`, `vContrat`, `vPortail`, `vJournal`, `vRecette`, `vLimites`), règles de gestion (RG01 à RG32) et tests (`TESTS`).
