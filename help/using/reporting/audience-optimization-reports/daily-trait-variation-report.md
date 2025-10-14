---
description: Ce rapport renvoie une liste des caractéristiques qui ont été réalisées au moins 10 000 fois au cours des 30 jours précédant la ou les dates sélectionnées et qui présentent un écart type supérieur ou égal à 1,7 dans les deux sens sur le même intervalle de temps. Le rapport vous permet d’évaluer la façon dont le nombre d’impressions d’utilisateurs uniques d’une caractéristique fluctue au fil du temps.
seo-description: This report returns a list of traits that have been realized at least 10,000 times in the 30 days prior to the selected date(s) and have a standard deviation greater or equal to 1.7 in either direction over the same time interval. The report helps you evaluate how the number of impressions from unique users in a trait fluctuate over time.
seo-title: Daily Trait Variation Report
solution: Audience Manager
title: Rapport Quotidien Sur Les Variations De Caractéristiques
uuid: 4e82bb17-d447-4ed1-a4fc-e15b0f1b47f0
feature: Audience Optimization Reports
exl-id: c84a3f13-70fb-4167-b05b-de5cf518ec03
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '717'
ht-degree: 0%

---

# Rapport Quotidien Sur Les Variations De Caractéristiques {#daily-trait-variation-report}

Ce rapport renvoie une liste des caractéristiques qui ont été réalisées au moins 10 000 fois au cours des 30 jours précédant la ou les dates sélectionnées et qui présentent un écart type supérieur ou égal à 1,7 dans les deux sens sur le même intervalle de temps. Le rapport vous permet d’évaluer la façon dont le nombre d’impressions d’utilisateurs uniques d’une caractéristique fluctue au fil du temps.

>[!NOTE]
>
>Le rapport Variation quotidienne des caractéristiques dans Audience Manager respecte les principes RBAC. Vous pouvez uniquement afficher les caractéristiques des sources de données auxquelles vous avez accès en fonction du [groupe d’utilisateurs RBAC](/help/using/features/administration/administration-overview.md) auquel vous appartenez.

L’écart type mesure le degré de variation ou de dispersion par rapport à la moyenne (ou à la moyenne/valeur attendue). Un écart type faible indique que les points de données ont tendance à être très proches de la moyenne. Un écart type élevé indique que les points de données sont répartis sur une large plage de valeurs.

![](assets/daily_trait_variation.png)

Utilisez la liste [!UICONTROL Date] pour sélectionner une ou plusieurs dates pour votre rapport. Un graphique à barres avec code-couleur s’affiche au bas de la liste et fournit une représentation visuelle de la plage d’écart-type pour toutes les caractéristiques sur toutes les dates sélectionnées. La ligne verticale noire indique la moyenne.

La colonne du milieu contient une liste de caractéristiques, identifiées par [!UICONTROL Trait ID] et [!UICONTROL Trait Name]. Cliquez sur une caractéristique pour accéder à une boîte de dialogue pop-up qui vous permet de sélectionner l’une des options suivantes :

* **Conserver uniquement :** supprime toutes les autres caractéristiques du rapport et affiche uniquement les données relatives à cette caractéristique.
* **Exclure :** supprime cette caractéristique du rapport et affiche les données de toutes les autres caractéristiques. Vous pouvez exclure plusieurs caractéristiques.
* **Afficher les données :** permet d’afficher les données de cette ligne. Vous pouvez également télécharger toutes les lignes sous la forme d’un fichier texte.

La colonne [!UICONTROL Standard Deviation] affiche des graphiques à barres avec code-couleur qui indiquent l’écart type de chaque caractéristique sur l’intervalle sélectionné. Les barres rouges indiquent les caractéristiques avec un écart type négatif (les points de données ont tendance à être inférieurs à la moyenne). Les barres vertes indiquent les caractéristiques avec un écart type positif (les points de données ont tendance à être supérieurs à la moyenne). Placez le pointeur de la souris sur une barre pour afficher une boîte de dialogue pop-up contenant plus d’informations et d’options permettant de conserver ou d’exclure cette caractéristique et d’afficher plus d’informations.

Des icônes s’affichent au bas du rapport pour vous permettre d’exporter des données dans divers formats, d’annuler les modifications que vous avez apportées au rapport (telles que l’exclusion de caractéristiques), d’activer ou de désactiver les mises à jour automatiques et d’actualiser les données du rapport. Voir [&#x200B; Présentation des icônes de rapport et des outils](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained).

## Cas d’utilisation {#use-cases}

**Exemple de #1** : ce rapport peut s’avérer très utile dans les situations où vous disposez de caractéristiques avec un niveau de saisonnalité élevé. Par exemple, supposons que votre boutique en ligne teste des promotions saisonnières de différents types et prix. Les caractéristiques suivantes sont définies dans [!DNL Audience Manager] :

* `productPage == "December Promotion"`
* `price > "500"`

Supposons que vous exécutiez le rapport [!UICONTROL Daily Trait Variation] le 20 décembre et que vous remarquiez un écart positif solide sur les caractéristiques mentionnées ci-dessus au cours des 30 derniers jours. Cela peut indiquer que vos visiteurs recherchent les produits mentionnés dans votre promotion saisonnière. Pour tirer parti de cette tendance, vous pouvez ensuite investir davantage d’efforts dans le ciblage des contenus publicitaires de cette catégorie de produits spécifique sur les visiteurs qui s’intéressent à eux.

**Exemple de #2** : ce rapport peut vous aider à identifier les anomalies de ciblage liées à des problèmes de balisage ou à des configurations incorrectes de caractéristiques. Imaginez que vous ayez défini la caractéristique suivante en fonction des catégories de votre boutique en ligne :

* `productPage == "smartphones"`

En raison d’une reconfiguration de votre boutique, vous divisez la page des smartphones en plusieurs pages, en fonction des noms de marque. Cependant, vous oubliez de mettre à jour les caractéristiques définies dans [!DNL Audience Manager].

Un mois plus tard, vous exécutez le rapport [!UICONTROL Daily Trait Variation] et constatez un écart négatif important sur la caractéristique `productPage == "smartphones"`, bien que le nombre de visiteurs ait augmenté, selon les analyses de votre site. Sur la base de ces informations, vous réalisez que vous n’avez pas mis à jour les caractéristiques dans [!DNL Audience Manager] pour vos nouvelles pages de produits, vous savez donc que vous devez créer les caractéristiques suivantes :

* productPage == « samsung »
* productPage == « apple »
* productPage == « huawei »

Une fois que vous aurez effectué cette opération, votre audience se qualifiera pour les caractéristiques nouvellement créées.
