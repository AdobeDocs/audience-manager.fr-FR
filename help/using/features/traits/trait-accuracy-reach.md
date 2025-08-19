---
description: Décrit la relation entre la précision et la portée dans les caractéristiques algorithmiques.
seo-description: Describes the relationship between accuracy and reach in algorithmic traits.
seo-title: Accuracy and Reach
solution: Audience Manager
title: Précision et portée
uuid: d121e099-6642-4003-ad4f-507d21e478d8
feature: Traits
exl-id: 647b283a-fcfa-4e3f-8667-50c6aacbc78a
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '342'
ht-degree: 0%

---

# Précision et portée {#accuracy-and-reach}

Décrit la relation entre la précision et la portée dans les caractéristiques algorithmiques.

<!-- c_accuracy_reach.xml -->

## Précision et portée : à propos

Il est important de comprendre la relation entre la précision et la portée lorsque vous travaillez avec des traits algorithmiques. La précision est représentée par une valeur notée qui reflète la similitude des utilisateurs avec votre ligne de base. L’échelle de précision va de 0 (la moins précise) à 1 (la plus précise). La portée est simplement une valeur qui représente le nombre d’utilisateurs uniques que vous souhaitez inclure dans une caractéristique. La portée et la précision sont inversement liées. Les caractéristiques précises atteignent moins d’utilisateurs et celles dont la portée est plus grande sont moins précises. L’image suivante illustre ce concept.

![](assets/Reach_v_Accuracy.png)

## La précision et la portée affectent la taille de l’audience

Vos objectifs commerciaux doivent vous aider à prendre les bonnes décisions en matière de précision et de portée lorsque vous utilisez des caractéristiques algorithmiques. Si l’exactitude est votre objectif, notez que la population d’une caractéristique peut augmenter ou diminuer entre les exécutions de modèle. Les changements de population sont le résultat de l&#39;algorithme qui prend des décisions au cours de chaque période d&#39;évaluation. Parfois, l’algorithme trouve plus d’utilisateurs qualifiés au cours d’un cycle de traitement et, d’autres fois, il en trouve moins. Les résultats sont déterminés par les données de référence utilisées pour créer le modèle et les nouveaux visiteurs et qualifications de caractéristiques qui sont venus depuis l’exécution du modèle précédent. En revanche, lorsque vous utilisez REACH, le nombre d’utilisateurs et d’utilisatrices reste constant. Par exemple, si vous souhaitez atteindre 10 000 utilisateurs, l’algorithme s’assure qu’il atteint toujours ce nombre pour chaque exécution de modèle.

## Cas d’utilisation généraux de la précision par rapport à la portée

L’accent mis sur la précision ou la portée dépend de ce que vous souhaitez obtenir avec un segment particulier. Le tableau suivant peut vous aider à évaluer la précision par rapport à la portée lors de la création d’une caractéristique.

| Caractéristiques des faveurs de décision | Permet de trouver |
|---|---|
| **Précision** | Utilisateurs similaires aux clients de base dans votre modèle. Utile pour les campagnes ciblées lorsque vous souhaitez atteindre une audience spécifique. |
| **Portée** | Un nombre spécifique d’utilisateurs pour chaque exécution de données. Utile pour les campagnes de marque lorsque vous souhaitez atteindre une audience d’une taille spécifique. |
