# Beach Bar — Rapport de pentest PTES

Ce dépôt présente un test d’intrusion réalisé sur la machine **Beach Bar**, dans un environnement de laboratoire TryHackMe. L’objectif est de transformer un write-up technique en un rapport de pentest clair, structuré et conforme à la méthodologie **PTES**.

## Objectif

- Identifier les services exposés et les vulnérabilités exploitables.
- Évaluer leur impact sur la confidentialité, l’intégrité et la disponibilité.
- Retracer la chaîne d’attaque jusqu’à l’élévation de privilèges.
- Proposer des mesures correctives adaptées.

## Méthodologie PTES

Le rapport suit les sept phases du **Penetration Testing Execution Standard** :

1. Pré-engagement
2. Collecte de renseignements
3. Modélisation des menaces
4. Analyse des vulnérabilités
5. Exploitation
6. Post-exploitation
7. Rapport

## Résumé de la chaîne d’attaque

1. Découverte des services SSH et HTTP avec Nmap.
2. Identification d’informations sensibles exposées dans le code HTML.
3. Accès à une fonctionnalité d’importation de fichiers YAML.
4. Exploitation d’une désérialisation YAML non sécurisée permettant l’exécution de commandes.
5. Obtention d’un accès au système et découverte d’un secret dans les arguments d’un processus.
6. Réutilisation de ce secret pour obtenir les privilèges administrateur.

> Les identifiants, secrets et flags ont volontairement été retirés de ce dépôt.

## Vulnérabilités identifiées

| Référence | Vulnérabilité | Sévérité | CWE |
|---|---|---:|---:|
| BB-01 | Identifiants exposés dans des commentaires HTML | Moyenne | CWE-615 |
| BB-02 | Désérialisation YAML non sécurisée menant à une RCE | Critique | CWE-502 |
| BB-03 | Secret exposé dans les arguments d’un processus | Élevée | CWE-214 |
| BB-04 | Réutilisation d’un secret privilégié | Élevée | — |

## Recommandations principales

- Supprimer toute information sensible du code envoyé au navigateur.
- Utiliser un chargeur YAML sûr et refuser les types Python arbitraires.
- Valider strictement les fichiers importés côté serveur.
- Ne jamais transmettre de secret dans les arguments d’un processus.
- Utiliser des secrets uniques, avec une rotation régulière et des privilèges minimaux.
- Mettre en place une journalisation et une surveillance des actions sensibles.

## Outils utilisés

- Nmap
- Navigateur et outils de développement
- Netcat
- Outils Linux standards

## Contenu du projet

- `Rapport_Pentest_Beach_Bar_PTES.docx` : rapport de pentest complet.
- `README.md` : présentation synthétique du projet.

## Avertissement

Ce projet a été réalisé uniquement dans un environnement de laboratoire autorisé, à des fins pédagogiques. Les techniques présentées ne doivent être utilisées que sur des systèmes pour lesquels une autorisation explicite a été obtenue.

## Auteur

**dimisan221**
