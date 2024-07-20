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

## Précision et portée : À propos

Il est important de comprendre la relation entre la précision et la portée lorsque vous utilisez des caractéristiques algorithmiques. La précision est représentée par une valeur notée qui reflète la ressemblance entre les utilisateurs et votre ligne de base. L’échelle de précision est comprise entre 0 (la moins précise) et 1 (la plus précise). La portée est simplement une valeur qui représente le nombre d’utilisateurs uniques que vous souhaitez inclure dans une caractéristique. La portée et la précision sont inversement liées. Les caractéristiques précises atteignent moins d’utilisateurs et les caractéristiques ayant une plus grande portée sont moins précises. L’image suivante illustre ce concept.

![](assets/Reach_v_Accuracy.png)

## Précision et portée Affectent la taille de l’audience

Les objectifs de votre entreprise doivent vous aider à prendre les bonnes décisions concernant la précision et la portée lorsque vous utilisez des caractéristiques algorithmiques. Si la précision est votre objectif, notez que la population d’une caractéristique peut augmenter ou diminuer d’une exécution à l’autre. Les changements de population sont les résultats des décisions de l’algorithme au cours de chaque période d’évaluation. Parfois, l’algorithme trouve des utilisateurs plus qualifiés au cours d’un cycle de traitement et, lors d’autres, il peut en trouver moins. Les résultats sont déterminés par les données de base utilisées pour créer le modèle, ainsi que les nouveaux visiteurs et les qualifications de caractéristiques qui se sont produits depuis l’exécution du modèle précédent. En revanche, lorsque vous utilisez la portée, le nombre de personnes reste constant. Par exemple, si vous souhaitez atteindre 10 000 utilisateurs, l’algorithme s’assure qu’il atteint toujours ce nombre pour chaque exécution de modèle.

## Cas d’utilisation généraux pour la précision par rapport à la portée

L’accent mis sur la précision ou la portée dépend de ce que vous souhaitez obtenir avec un segment particulier. Le tableau suivant peut vous aider à évaluer la précision par rapport à la portée lors de la création d’une caractéristique.

| Avantages de décision de caractéristique | Aide à la recherche |
|---|---|
| **Précision** | Utilisateurs similaires aux clients de base de votre modèle. Utile pour les campagnes ciblées lorsque vous souhaitez atteindre une audience spécifique. |
| **Portée** | Un nombre spécifique d’utilisateurs pour chaque exécution de données. Utile pour les campagnes de marque lorsque vous souhaitez atteindre une audience d’une taille spécifique. |
