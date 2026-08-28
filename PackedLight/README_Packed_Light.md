# Packed Light — Rapport d’analyse réseau et forensique

Ce projet présente l’analyse d’une capture réseau liée à l’activité suspecte observée sur le poste interne `192.168.1.141`. L’investigation vise à identifier la charge téléchargée, comprendre son fonctionnement et reconstituer le mécanisme d’exfiltration.

## Objectifs

- Identifier les hôtes et les flux réseau suspects.
- Extraire et examiner les objets transférés en HTTP.
- Comprendre le comportement du script malveillant récupéré.
- Reconstituer les données exfiltrées.
- Produire des indicateurs de compromission et des recommandations.

## Démarche d’investigation

1. Analyse de la capture avec Wireshark.
2. Identification des communications entre `192.168.1.141` et `34.41.103.191`.
3. Extraction du fichier `update.py` téléchargé en HTTP.
4. Analyse du script et identification d’un comportement de keylogger.
5. Repérage de l’exfiltration dans le cookie HTTP `hotel_sess_state`.
6. Reconstruction des données puis décodage Base64 et XOR avec la clé `H`.

## Principales constatations

| Constat | Impact | Criticité |
| --- | --- | --- |
| Téléchargement de `update.py` en HTTP | Introduction d’une charge malveillante | Élevée |
| Fonction de capture des frappes clavier | Vol potentiel d’informations sensibles | Critique |
| Exfiltration par cookie HTTP | Dissimulation des données dans un trafic applicatif | Élevée |
| Encodage Base64 et XOR faible | Obfuscation facilement réversible | Moyenne |

## Indicateurs de compromission

- Hôte interne observé : `192.168.1.141`
- Hôte distant observé : `34.41.103.191`
- Fichier suspect : `update.py`
- Cookie d’exfiltration : `hotel_sess_state`

Les éventuels secrets ou drapeaux découverts pendant l’exercice ne sont pas publiés dans ce README.

## Outils et techniques

- Wireshark pour l’analyse des paquets et des flux HTTP.
- Extraction d’objets réseau.
- Analyse statique de code Python.
- CyberChef pour le décodage Base64 et XOR.
- Corrélation temporelle des requêtes et des données exfiltrées.

## Compétences démontrées

- Analyse forensique réseau.
- Détection de communications malveillantes.
- Extraction et analyse d’une charge Python.
- Reconstruction d’un canal d’exfiltration.
- Décodage de données obfusquées.
- Production d’IOC et de recommandations défensives.

## Rapports

- `Rapport_Analyse_Packed_Light_style_Beach_Bar.pdf`
- `Rapport_Analyse_Packed_Light_style_Beach_Bar.docx`

## Avertissement

Cette analyse a été réalisée dans un cadre pédagogique autorisé. Les adresses IP et artefacts sont documentés uniquement pour expliquer l’investigation et faciliter la détection dans le contexte du laboratoire.
