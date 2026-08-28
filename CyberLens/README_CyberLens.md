# CyberLens — Rapport de test d’intrusion

Ce projet présente l’audit de la machine Windows **CyberLens** dans un environnement de laboratoire autorisé. L’exploitation combine une vulnérabilité d’exécution de code à distance, l’exposition d’identifiants et une configuration Windows dangereuse permettant d’atteindre le niveau `SYSTEM`.

## Objectifs

- Identifier les services et composants applicatifs exposés.
- Déterminer les versions vulnérables présentes.
- Obtenir un premier accès distant à la machine.
- Rechercher des secrets et des chemins d’élévation de privilèges.
- Évaluer l’impact global de la chaîne d’attaque.

## Chaîne d’attaque

1. Reconnaissance réseau et identification d’Apache Tika 1.17.
2. Exploitation de la vulnérabilité CVE-2018-1335 pour exécuter des commandes à distance.
3. Obtention d’un shell sur la cible.
4. Découverte d’identifiants stockés en clair dans `CyberLens-Management.txt`.
5. Utilisation de ces identifiants pour ouvrir une session RDP.
6. Détection de `AlwaysInstallElevated` dans les ruches HKCU et HKLM.
7. Exploitation de cette configuration pour exécuter un paquet MSI avec les privilèges `SYSTEM`.

## Principales constatations

| Constat | Impact | Sévérité |
| --- | --- | --- |
| Apache Tika 1.17 vulnérable à CVE-2018-1335 | Exécution de code à distance | Critique |
| Identifiants stockés en clair | Compromission d’un compte Windows | Élevée |
| Accès RDP avec les identifiants récupérés | Accès interactif à la cible | Élevée |
| `AlwaysInstallElevated` actif dans HKCU et HKLM | Élévation de privilèges vers `SYSTEM` | Critique |

## Outils et techniques

- Nmap pour la reconnaissance.
- Requêtes HTTP et exploitation contrôlée d’Apache Tika.
- Shell distant pour la post-exploitation.
- RDP pour l’accès interactif.
- Inspection du registre Windows.
- Génération et exécution d’un paquet MSI de démonstration.

## Compétences démontrées

- Identification et validation d’une CVE.
- Exploitation d’un service web vulnérable.
- Recherche de secrets sur un système Windows.
- Analyse des politiques Windows et du registre.
- Élévation de privilèges jusqu’au niveau `SYSTEM`.
- Rédaction de recommandations hiérarchisées.

## Rapports

- `Rapport_Pentest_CyberLens_style_Beach_Bar.pdf`
- `Rapport_Pentest_CyberLens_style_Beach_Bar.docx`

## Avertissement

Les manipulations décrites ont été réalisées exclusivement dans un environnement de formation autorisé. Elles ne doivent jamais être reproduites sur un système sans l’accord explicite de son propriétaire.
