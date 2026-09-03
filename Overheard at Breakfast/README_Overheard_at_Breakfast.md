# Overheard at Breakfast - Investigation OSINT

Ce projet présente une investigation **OSINT** réalisée dans un environnement de laboratoire autorisé sur TryHackMe.

L'objectif était d'analyser une conversation, d'en extraire des indices exploitables et de retrouver un profil public qu'un utilisateur pensait difficile à découvrir.

> Le flag, sa valeur encodée et les éléments permettant de le reconstituer ne sont volontairement pas publiés.

## Contexte

Le scénario débute avec une capture d'écran d'une conversation entre deux personnes présentes dans un hôtel fictif. Certains passages révèlent des informations utilisables comme pivots de recherche :

- le pseudonyme `Lambo!` ;
- une adresse électronique associée au Byte Lotus Hotel ;
- la mention d'un ancien service gratuit ;
- un service dont le nom commence par la lettre `G` ;
- la possibilité de créer un profil et de relier différentes présences en ligne.

## Objectifs

1. Examiner la conversation fournie.
2. Distinguer les indices pertinents du bruit contextuel.
3. Transformer les informations découvertes en pivots OSINT.
4. Identifier le service évoqué dans la conversation.
5. Localiser le profil public correspondant.
6. Valider le résultat par le recoupement de plusieurs éléments.

## Méthodologie

L'investigation repose sur une démarche passive utilisant uniquement des informations publiquement accessibles.

### 1. Collecte des indices

La conversation est examinée manuellement afin d'identifier les pseudonymes, les informations de contact, le contexte professionnel et les caractéristiques du service recherché.

### 2. Formulation d'une hypothèse

La lettre `G`, la notion de profil et la possibilité de relier une identité à plusieurs services orientent l'investigation vers **Gravatar**.

### 3. Recherche ciblée

Une requête combinant le nom du service supposé et le pseudonyme permet de limiter les résultats non pertinents :

```text
gravatar Lambo!
```

### 4. Validation croisée

Le profil découvert est validé grâce à la convergence de plusieurs éléments :

| Critère | Élément observé | Niveau de concordance |
| --- | --- | --- |
| Pseudonyme | Le profil utilise le nom Lambo | Directe |
| Plateforme | Le profil est hébergé sur Gravatar | Forte |
| Contexte | Le résultat mentionne le Byte Lotus Hotel | Forte |
| Fonction | Il s'agit d'un profil public réutilisable sur le Web | Cohérente |

## Résultat

L'enquête permet de localiser le profil public recherché avec un **niveau de confiance élevé**.

Cette conclusion ne repose pas sur un indice isolé, mais sur le recoupement du pseudonyme, du contexte hôtelier, de la description du service et du résultat indexé par le moteur de recherche.

## Principaux constats

| ID | Constat | Risque associé |
| --- | --- | --- |
| OB-01 | Pseudonyme exposé dans une conversation | Recherche d'autres profils utilisant le même nom |
| OB-02 | Adresse électronique rendue visible | Phishing ciblé et corrélation d'identité |
| OB-03 | Contexte professionnel identifiable | Désambiguïsation et personnalisation d'une attaque |
| OB-04 | Profil indexé par un moteur de recherche | Découverte facilitée par une requête simple |

## Outils et sources

- Analyse manuelle de la conversation.
- Moteur de recherche Google.
- Profil public Gravatar.
- Journal d'analyse pour conserver les hypothèses et les résultats.

## Compétences démontrées

- Extraction et hiérarchisation d'indices.
- Création de pivots de recherche OSINT.
- Formulation et validation d'hypothèses.
- Utilisation de requêtes ciblées.
- Corrélation entre pseudonyme, plateforme et contexte.
- Évaluation du niveau de confiance d'une attribution.
- Protection des informations sensibles dans un livrable public.
- Rédaction d'un rapport OSINT professionnel.

## Recommandations

- Éviter de publier une adresse électronique personnelle dans un espace public.
- Utiliser des pseudonymes différents selon les contextes.
- Vérifier régulièrement les informations indexées par les moteurs de recherche.
- Contrôler les paramètres de visibilité des profils publics.
- Supprimer ou révoquer immédiatement tout secret publié accidentellement.
- Sensibiliser les utilisateurs aux risques liés à l'agrégation des données OSINT.

## Rapports complets

- `Rapport_OSINT_Overheard_at_Breakfast_style_Beach_Bar.pdf`
- `Rapport_OSINT_Overheard_at_Breakfast_style_Beach_Bar.docx`

## Avertissement légal

Cette investigation a été réalisée exclusivement dans un environnement pédagogique autorisé. Les techniques OSINT doivent être utilisées avec une finalité légitime, dans le respect de la vie privée et du droit applicable.
