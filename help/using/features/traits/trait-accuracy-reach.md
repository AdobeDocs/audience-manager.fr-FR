---
description: Décrit la relation entre la précision et la portée dans les caractéristiques algorithmiques.
seo-description: Décrit la relation entre la précision et la portée dans les caractéristiques algorithmiques.
seo-title: Précision et portée
solution: Audience Manager
title: Précision et portée
uuid: d121e099-6642-4003-ad4f-507d21e478d8
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 0%

---


# Précision et portée {#accuracy-and-reach}

Décrit la relation entre la précision et la portée dans les caractéristiques algorithmiques.

<!-- c_accuracy_reach.xml -->

## Précision/Portée : A propos

Il est important de comprendre la relation entre la précision et la portée lorsque l&#39;on travaille avec des caractéristiques algorithmiques. La précision est représentée par une valeur notée qui reflète la ressemblance des utilisateurs avec votre ligne de base. L&#39;échelle de précision est comprise entre 0 (la moins précise) et 1 (la plus précise). La portée est simplement une valeur qui représente le nombre d’utilisateurs uniques que vous souhaitez inclure dans une caractéristique. La portée et la précision sont inversement liées. Les caractéristiques précises atteignent moins d&#39;utilisateurs et les caractéristiques ayant une plus grande portée sont moins précises. L&#39;illustration suivante illustre ce concept.

![](assets/Reach_v_Accuracy.png)

## Précision et portée affectent la taille de l&#39;Audience

Les objectifs de votre entreprise doivent vous aider à prendre les bonnes décisions en matière de précision et d’atteinte lors de l’utilisation de caractéristiques algorithmiques. Si la précision est votre objectif, notez que la population d’un trait peut augmenter ou diminuer d’une exécution de modèle à l’autre. Les changements de population sont les résultats des décisions prises par l’algorithme au cours de chaque période d’évaluation. Parfois, l’algorithme recherche des utilisateurs plus qualifiés au cours d’un cycle de traitement et, dans d’autres cas, il peut en trouver moins. Les résultats sont déterminés par les données de base utilisées pour créer le modèle et les nouveaux visiteurs et qualifications de caractéristiques qui sont arrivés depuis l&#39;exécution du modèle précédent. En revanche, lorsque vous travaillez avec portée, le nombre d’utilisateurs reste constant. Par exemple, si vous souhaitez atteindre 10 000 utilisateurs, l’algorithme s’assurera qu’il atteint toujours ce nombre pour chaque exécution de modèle.

## Cas d’utilisation généraux pour l’exactitude ou la portée

L’accent mis sur la précision ou la portée dépend de ce que vous souhaitez obtenir avec un segment particulier. Le tableau suivant peut vous aider à évaluer la précision par rapport à la portée lors de la création d’une caractéristique.

| Avantages de la décision sur les caractéristiques | Aide à la recherche |
|---|---|
| **Précision** | Utilisateurs similaires aux clients de base dans votre modèle. Utile pour les campagnes ciblées lorsque vous souhaitez atteindre une audience spécifique. |
| **Portée** | Nombre spécifique d’utilisateurs pour chaque exécution de données. Utile pour les campagnes de marque lorsque vous souhaitez atteindre une audience d’une taille spécifique. |