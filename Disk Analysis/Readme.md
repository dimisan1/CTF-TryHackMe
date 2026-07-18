# Disk Analysis — TryHackMe

Ce write-up couvre une investigation forensique complète menée avec Autopsy 4.18.0 sur une image disque au format E01, dans le cadre d'un challenge d'analyse post-mortem (dead-box forensics).

L'objectif : reconstituer, à partir d'une simple image disque, l'histoire complète d'un poste de travail compromis — identification du système, comptes utilisateurs, activité récente, et traces laissées par un utilisateur malveillant en interne.

Au programme :


Vérification d'intégrité de l'image (hash MD5)
Extraction des informations système via les ruches de registre (SYSTEM, SAM, SOFTWARE)
Reconstruction de l'activité utilisateur (favoris navigateur, fond d'écran, historique PowerShell)
Détection d'outils offensifs de récupération de mots de passe (LaZagne, Mimikatz)
Analyse d'un script d'élévation de privilèges exécuté localement


Un bon exercice pour s'entraîner à la lecture d'artefacts Windows côté Blue Team, sans mettre les mains sur un vrai incident.

📄 Write-up complet et rapport forensic : voir Rapport_Forensic_HASAN2.pdf
