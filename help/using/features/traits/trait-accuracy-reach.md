---
description: Décrit la relation entre la précision et la portée dans les caractéristiques algorithmiques.
seo-description: Décrit la relation entre la précision et la portée dans les caractéristiques algorithmiques.
seo-title: Précision et portée
solution: Audience Manager
title: Précision et portée
uuid: d 121 e 099-6642-4003-ad 4 f -507 d 21 e 478 d 8
translation-type: tm+mt
source-git-commit: 44bb4d511215a7bbc8889cc9518b3b5ffcb79a2a

---


# Accuracy and Reach {#accuracy-and-reach}

Décrit la relation entre la précision et la portée dans les caractéristiques algorithmiques.

<!-- c_accuracy_reach.xml -->

## Exactitude par rapport à Portée : A propos de

Il est important de comprendre la relation entre la précision et la portée lorsque vous travaillez avec des caractéristiques algorithmiques. La précision est représentée par une valeur notée qui reflète la manière dont les utilisateurs similaires sont à votre ligne de base. L'échelle de précision est comprise entre 0 (moins précis) et 1 (la plus précise). La portée est simplement une valeur qui représente le nombre d'utilisateurs uniques que vous souhaitez inclure dans une caractéristique. La portée et la précision sont liées de manière inversée. Les caractéristiques précises atteignent moins d'utilisateurs et les caractéristiques dont la portée est plus grande sont moins précises. L'image suivante illustre ce concept.

![](assets/Reach_v_Accuracy.png)

## Exactitude et portée affectent la taille de l'audience

Vos objectifs commerciaux doivent vous aider à prendre les bonnes décisions concernant la précision et la portée lorsque vous travaillez avec des caractéristiques algorithmiques. Si la précision est votre objectif, notez que la population d'une caractéristique peut augmenter ou diminuer l'exécution du modèle. Les modifications de population sont les résultats de l'algorithme qui décisions lors de chaque période d'évaluation. Parfois, l'algorithme recherche plus d'utilisateurs qualifiés durant un cycle de traitement et, pendant d'autres, il peut en trouver moins. Les résultats sont déterminés par les données de base utilisées pour créer le modèle et les nouveaux visiteurs et les caractéristiques de caractéristiques qui sont arrivés depuis l'exécution du modèle précédent. En revanche, lorsque vous travaillez avec la portée, le nombre de population d'utilisateurs reste constant. Par exemple, si vous souhaitez atteindre 10 000 utilisateurs, l'algorithme vérifie qu'il atteint toujours ce nombre pour chaque exécution de modèle.

## Cas d'utilisation généraux pour la précision par rapport à la portée

La précision ou la portée dépend de ce que vous voulez obtenir avec un segment particulier. Le tableau suivant peut vous aider à évaluer la précision par rapport à la portée lors de la création d'une caractéristique.

| Favdecision Favors | Aide à rechercher |
|---|---|
| **Précision** | Utilisateurs semblables aux clients de base dans votre modèle. Utile pour les campagnes ciblées lorsque vous souhaitez atteindre une audience spécifique. |
| **Portée** | Un nombre spécifique d'utilisateurs pour chaque exécution de données. Utile pour les campagnes de marque lorsque vous souhaitez atteindre une audience d'une taille spécifique. |