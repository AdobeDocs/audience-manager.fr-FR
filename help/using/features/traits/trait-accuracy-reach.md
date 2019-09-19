---
description: Décrit la relation entre la précision et la portée dans les caractéristiques algorithmiques.
seo-description: Décrit la relation entre la précision et la portée dans les caractéristiques algorithmiques.
seo-title: Précision et portée
solution: Audience Manager
title: Précision et portée
uuid: d121e099-6642-4003-ad4f-507d21e478d8
translation-type: tm+mt
source-git-commit: 44bb4d511215a7bbc8889cc9518b3b5ffcb79a2a

---


# Précision et portée {#accuracy-and-reach}

Décrit la relation entre la précision et la portée dans les caractéristiques algorithmiques.

<!-- c_accuracy_reach.xml -->

## Précision et portée : À propos de

Il est important de comprendre la relation entre la précision et la portée quand on travaille avec des caractéristiques algorithmiques. La précision est représentée par une valeur notée qui reflète la similarité des utilisateurs avec votre ligne de base. L’échelle de précision est comprise entre 0 (la moins précise) et 1 (la plus précise). La portée est simplement une valeur qui représente le nombre d’utilisateurs uniques que vous souhaitez inclure dans une caractéristique. La portée et la précision sont inversement liées. Les caractéristiques précises atteignent moins d’utilisateurs et les caractéristiques ayant une plus grande portée sont moins précises. L'illustration suivante illustre ce concept.

![](assets/Reach_v_Accuracy.png)

## La précision et la portée affectent la taille de l’audience

Les objectifs de votre entreprise doivent vous aider à prendre les bonnes décisions concernant la précision et la portée lorsque vous travaillez avec des caractéristiques algorithmiques. Si la précision est votre objectif, notez que la population d’un trait peut augmenter ou diminuer d’un modèle à l’autre. Les changements de population sont les résultats des décisions prises par l’algorithme durant chaque période d’évaluation. Parfois, l’algorithme trouve des utilisateurs plus qualifiés pendant un cycle de traitement et, dans d’autres cas, il peut en trouver moins. Les résultats sont déterminés par les données de référence utilisées pour créer le modèle et les nouveaux visiteurs et les qualifications de caractéristiques qui sont venues depuis l’exécution du modèle précédent. En revanche, lorsque vous travaillez avec portée, le nombre d’utilisateurs reste constant. Par exemple, si vous souhaitez atteindre 10 000 utilisateurs, l’algorithme s’assurera qu’il atteint toujours ce nombre pour chaque exécution de modèle.

## Cas d’utilisation généraux pour la précision par rapport à la portée

L’accent mis sur la précision ou la portée dépend de ce que vous souhaitez obtenir avec un segment particulier. Le tableau suivant peut vous aider à évaluer la précision par rapport à la portée lors de la création d’une caractéristique.

| Les préférences de la décision sur les caractéristiques | Aide à la recherche |
|---|---|
| **Précision** | Utilisateurs similaires aux clients de base dans votre modèle. Utile pour les campagnes ciblées lorsque vous souhaitez atteindre un public spécifique. |
| **Portée** | Nombre spécifique d’utilisateurs pour chaque exécution de données. Utile pour les campagnes de marque lorsque vous souhaitez atteindre une audience d’une taille spécifique. |