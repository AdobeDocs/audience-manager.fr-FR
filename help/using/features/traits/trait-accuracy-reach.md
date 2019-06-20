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

Il est important de comprendre la relation entre la précision et la portée lorsque vous travaillez avec des caractéristiques algorithmiques. La précision est représentée par une valeur notée qui reflète la manière dont les utilisateurs similaires sont à votre ligne de base. L&#39;échelle de précision est comprise entre 0 (moins précis) et 1 (la plus précise). La portée est simplement une valeur qui représente le nombre d&#39;utilisateurs uniques que vous souhaitez inclure dans une caractéristique. La portée et la précision sont liées de manière inversée. Les caractéristiques précises atteignent moins d&#39;utilisateurs et les caractéristiques dont la portée est plus grande sont moins précises. L&#39;image suivante illustre ce concept.

![](assets/Reach_v_Accuracy.png)

## Exactitude et portée affectent la taille de l&#39;audience

Vos objectifs commerciaux doivent vous aider à prendre les bonnes décisions concernant la précision et la portée lorsque vous travaillez avec des caractéristiques algorithmiques. Si la précision est votre objectif, notez que la population d&#39;une caractéristique peut augmenter ou diminuer l&#39;exécution du modèle. Les modifications de population sont les résultats de l&#39;algorithme qui décisions lors de chaque période d&#39;évaluation. Parfois, l&#39;algorithme recherche plus d&#39;utilisateurs qualifiés durant un cycle de traitement et, pendant d&#39;autres, il peut en trouver moins. Les résultats sont déterminés par les données de base utilisées pour créer le modèle et les nouveaux visiteurs et les caractéristiques de caractéristiques qui sont arrivés depuis l&#39;exécution du modèle précédent. En revanche, lorsque vous travaillez avec la portée, le nombre de population d&#39;utilisateurs reste constant. Par exemple, si vous souhaitez atteindre 10 000 utilisateurs, l&#39;algorithme vérifie qu&#39;il atteint toujours ce nombre pour chaque exécution de modèle.

## Cas d&#39;utilisation généraux pour la précision par rapport à la portée

La précision ou la portée dépend de ce que vous voulez obtenir avec un segment particulier. Le tableau suivant peut vous aider à évaluer la précision par rapport à la portée lors de la création d&#39;une caractéristique.

| Favdecision Favors | Aide à rechercher |
|---|---|
| **Précision** | Utilisateurs semblables aux clients de base dans votre modèle. Utile pour les campagnes ciblées lorsque vous souhaitez atteindre une audience spécifique. |
| **Portée** | Un nombre spécifique d&#39;utilisateurs pour chaque exécution de données. Utile pour les campagnes de marque lorsque vous souhaitez atteindre une audience d&#39;une taille spécifique. |