---
description: La modélisation analogue vous permet de découvrir de nouvelles audiences uniques grâce à l’analyse automatisée des données. Cet article répond aux questions les plus fréquemment posées.
seo-description: Look-Alike Modeling helps you discover new, unique audiences through automated data analysis. This article provides answers to the most frequently asked questions.
seo-title: Look-Alike Modeling FAQ
solution: Audience Manager
title: FAQ sur la modélisation analogue
feature: Algorithmic Models
exl-id: c6e92db0-129f-489e-8cf0-600e0e09698b
source-git-commit: 37823ae54e106e32aa195a6b69e0f1ebfc322f09
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 0%

---

# FAQ sur la modélisation analogue

## Présentation {#overview}

Cet article répond aux questions les plus fréquemment posées sur [!UICONTROL Look-Alike Modeling].

## Questions {#questions}

**Pourquoi ai-je un graphique [!UICONTROL Accuracy & Reach] plat ?**

Un graphique [!UICONTROL Accuracy & Reach] plat signifie que presque tous les utilisateurs ont reçu le même score par le modèle. Cela peut se produire lorsque vous incluez la caractéristique du visiteur du site dans les sources de données sur lesquelles vous avez exécuté le modèle. Pour éviter cela, supprimez la caractéristique générique de l’entrée du modèle au cours de l’étape de création du modèle, à l’aide du champ [!UICONTROL Exclusions] .

 

**Pourquoi certaines de mes caractéristiques les plus influentes ont-elles de très petites audiences ?**

L’algorithme sélectionne des caractéristiques qui sont fortement corrélées à la caractéristique de base. Par exemple, si une caractéristique donnée se chevauche à 100 % avec la caractéristique de base, elle aura un poids très élevé, même si le nombre d’utilisateurs et d’utilisatrices de cette caractéristique est faible.

 

**Pourquoi mon modèle n’a-t-il pas été exécuté/réexécuté ?**

Les modèles qui ont produit des résultats continueront à s’exécuter uniquement si vous avez créé au moins une caractéristique algorithmique active et que vous l’avez mappée à un segment actif et à une destination.

 

**Pourquoi mon modèle n’a-t-il produit aucun résultat ?**

Cela est généralement dû au fait que les caractéristiques ne se chevauchent pas de manière significative entre la population de base et la population des sources de données sélectionnées.

 

**Y a-t-il une recommandation sur la caractéristique de base ou la taille de segment ?**

Quelques milliers d’utilisateurs devraient suffire pour exécuter le modèle, étant donné qu’il y a un chevauchement significatif des caractéristiques entre la population de base et la population dans les sources de données sélectionnées. [!UICONTROL Look-Alike Modeling] produit des résultats plus précis, plus la ligne de base est grande.

 

**Quelles sources de données tierces dois-je choisir pour mon modèle ?**

Utilisez des sources de données qui se chevauchent au moins partiellement avec votre caractéristique/segment de base, mais qui font en même temps appel à d’autres utilisateurs. Vous devez également tenir compte du coût associé à chaque flux de données. Les modèles de coût et de tarification varient d’un fournisseur de données à l’[!UICONTROL Audience Marketplace].

 

**L’utilisation de données tierces pour la modélisation coûte-t-elle cher ?**

Cela dépend du modèle de tarification du flux de données sélectionné. Certains flux permettent la modélisation sans frais, tandis que d’autres vous facturent des frais. Pour plus d’informations, consultez [Facturation pour les acheteurs de flux de données](../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md).

 

**Combien de modèles/caractéristiques suis-je autorisé à créer ?**

Actuellement, vous pouvez créer jusqu’à 20 modèles algorithmiques et 50 caractéristiques algorithmiques.

 

**Quelle est la fréquence d’actualisation de la population d’entraînement du modèle et de caractéristiques algorithmiques ?**

Le modèle se reforme une fois tous les 8 jours, en actualisant la population de caractéristiques algorithmiques.
