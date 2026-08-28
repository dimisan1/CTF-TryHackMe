# HASAN2 — Rapport d’analyse forensique

Ce projet documente l’analyse forensique d’une image disque **E01** avec Autopsy. L’objectif était de reconstituer les actions réalisées sur un poste Windows compromis, d’identifier les outils employés et de produire une chronologie exploitable.

## Objectifs

- Vérifier et examiner l’image disque fournie.
- Identifier le système, les comptes et les artefacts pertinents.
- Reconstituer l’activité PowerShell.
- Rechercher les traces d’outils de récupération d’identifiants.
- Établir une chronologie et relever les indicateurs de compromission.

## Démarche d’investigation

1. Importation de l’image E01 dans Autopsy et vérification de son empreinte MD5.
2. Analyse des ruches de registre Windows, notamment SAM et SOFTWARE.
3. Examen de l’historique PowerShell et des fichiers récemment manipulés.
4. Identification de traces associées à LaZagne et Mimikatz.
5. Analyse d’un script `exploit.ps1` lié à une tentative d’élévation de privilèges.
6. Corrélation avec la création de `hacked.txt` et les autres événements de la chronologie.

## Principales constatations

| Constat | Interprétation | Criticité |
| --- | --- | --- |
| Présence de LaZagne | Tentative de récupération d’identifiants | Élevée |
| Présence de Mimikatz | Accès potentiel à des secrets d’authentification | Critique |
| Exécution de `exploit.ps1` | Tentative d’élévation de privilèges | Élevée |
| Création de `hacked.txt` | Indicateur d’une action post-compromission | Moyenne |
| Historique PowerShell exploitable | Reconstitution partielle des actions | Informationnelle |

## Outils et sources analysées

- Autopsy 4.18 pour l’examen de l’image disque.
- Empreinte MD5 pour le contrôle d’intégrité.
- Ruches du registre Windows.
- Historique PowerShell.
- Métadonnées, fichiers supprimés et chronologie du système.

## Compétences démontrées

- Préservation et vérification d’une preuve numérique.
- Analyse d’une image disque Windows.
- Interprétation des artefacts du registre.
- Investigation de commandes PowerShell.
- Identification d’outils offensifs et d’indicateurs de compromission.
- Construction d’une chronologie forensique argumentée.

## Rapports

- `Rapport_Forensic_HASAN2_style_Beach_Bar.pdf`
- `Rapport_Forensic_HASAN2_style_Beach_Bar.docx`

## Avertissement

Cette analyse a été menée dans un cadre pédagogique autorisé. Les conclusions reposent sur les artefacts disponibles dans l’image examinée et doivent être interprétées en tenant compte de leur contexte et de leurs limites.
