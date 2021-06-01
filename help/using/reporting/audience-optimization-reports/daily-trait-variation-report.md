---
description: Ce rapport renvoie une liste des caractéristiques qui ont été réalisées au moins 10 000 fois au cours des 30 jours précédant les dates sélectionnées et dont l’écart type est supérieur ou égal à 1,7 dans l’une ou l’autre direction au cours du même intervalle de temps. Le rapport vous aide à évaluer la manière dont le nombre d’impressions d’utilisateurs uniques dans une caractéristique fluctue au fil du temps.
seo-description: Ce rapport renvoie une liste des caractéristiques qui ont été réalisées au moins 10 000 fois au cours des 30 jours précédant les dates sélectionnées et dont l’écart type est supérieur ou égal à 1,7 dans l’une ou l’autre direction au cours du même intervalle de temps. Le rapport vous aide à évaluer la manière dont le nombre d’impressions d’utilisateurs uniques dans une caractéristique fluctue au fil du temps.
seo-title: Rapport de variation des caractéristiques quotidiennes
solution: Audience Manager
title: Rapport de variation des caractéristiques quotidiennes
uuid: 4e82bb17-d447-4ed1-a4fc-e15b0f1b47f0
feature: Rapports d’Audience Optimization
exl-id: c84a3f13-70fb-4167-b05b-de5cf518ec03
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '776'
ht-degree: 2%

---

# Rapport de variation des caractéristiques quotidiennes {#daily-trait-variation-report}

Ce rapport renvoie une liste des caractéristiques qui ont été réalisées au moins 10 000 fois au cours des 30 jours précédant les dates sélectionnées et dont l’écart type est supérieur ou égal à 1,7 dans l’une ou l’autre direction au cours du même intervalle de temps. Le rapport vous aide à évaluer la manière dont le nombre d’impressions d’utilisateurs uniques dans une caractéristique fluctue au fil du temps.

>[!NOTE]
>
>Le rapport Daily Trait Variation en Audience Manager adhère aux principes RBAC. Vous ne pouvez afficher que les caractéristiques des sources de données auxquelles vous avez accès en fonction du [groupe d’utilisateurs RBAC](/help/using/features/administration/administration-overview.md) auquel vous appartenez.

L’écart type mesure la quantité de variation ou de dispersion par rapport à la moyenne (ou la valeur moyenne/attendue). Un écart type faible indique que les points de données ont tendance à être très proches de la moyenne. Un écart type élevé indique que les points de données sont répartis sur une large plage de valeurs.

![](assets/daily_trait_variation.png)

Utilisez la liste [!UICONTROL Date] pour sélectionner une ou plusieurs dates pour votre rapport. Un graphique à barres avec code-couleur s’affiche au bas de la liste. Il fournit une représentation visuelle de la plage de l’écart-type pour toutes les caractéristiques parmi toutes les dates sélectionnées. La ligne verticale noire indique la moyenne.

La colonne du milieu contient une liste de caractéristiques, identifiées par [!UICONTROL Trait ID] et [!UICONTROL Trait Name]. Cliquez sur une caractéristique pour accéder à une boîte de dialogue contextuelle qui vous permet de sélectionner l’une des options suivantes :

* **Conserver uniquement :** supprime toutes les autres caractéristiques du rapport et affiche uniquement les données correspondant à cette caractéristique.
* **Exclure :** supprime cette caractéristique du rapport et affiche des données pour toutes les autres caractéristiques. Vous pouvez exclure plusieurs caractéristiques.
* **Afficher les données :** permet d’afficher les données de cette ligne. Vous pouvez également télécharger toutes les lignes sous forme de fichier texte.

La colonne [!UICONTROL Standard Deviation] affiche des graphiques à barres codés par les couleurs qui affichent l’écart type pour chaque caractéristique sur l’intervalle sélectionné. Les barres rouges indiquent les caractéristiques présentant un écart-type négatif (les points de données ont tendance à être inférieurs à la moyenne). Les barres vertes indiquent les caractéristiques présentant un écart-type positif (les points de données ont tendance à être supérieurs à la moyenne). Placez le pointeur de la souris sur une barre pour afficher une boîte de dialogue contextuelle contenant plus d’informations et d’options permettant de conserver ou d’exclure cette caractéristique et d’afficher plus d’informations.

Des icônes s’affichent au bas du rapport. Elles vous permettent d’exporter des données dans divers formats, d’annuler toute modification apportée au rapport (telle que l’exclusion des caractéristiques), d’activer ou de désactiver des mises à jour automatiques et d’actualiser les données du rapport. Voir [Explication des icônes de rapport et des outils](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained).

## Cas d’utilisation {#use-cases}

**Exemple 1** : ce rapport peut s’avérer très utile dans les situations où vous avez des caractéristiques avec un niveau de haute saison. Par exemple, supposons que votre boutique en ligne teste des promotions saisonnières de différents types et prix. Les caractéristiques suivantes sont définies dans [!DNL Audience Manager] :

* `productPage == "December Promotion"`
* `price > "500"`

Supposons que vous exécutiez le rapport [!UICONTROL Daily Trait Variation] le 20 décembre et que vous remarquiez une solide déviation positive des caractéristiques mentionnées ci-dessus au cours des 30 derniers jours. Cela peut indiquer que vos visiteurs recherchent les produits mentionnés dans votre promotion saisonnière. Pour capitaliser sur cette tendance, vous pouvez ensuite investir davantage d’efforts dans le ciblage des créatifs pour cette catégorie de produits spécifique sur les visiteurs qui y sont intéressés.

**Exemple 2** : ce rapport peut vous aider à identifier les anomalies de ciblage liées à des problèmes de balisage ou à des erreurs de configuration de caractéristiques. Imaginez que vous ayez défini la caractéristique suivante en fonction des catégories de votre boutique en ligne :

* `productPage == "smartphones"`

En raison d’une reconfiguration de votre boutique, vous divisez la page des smartphones en plusieurs pages, en fonction des noms de marque. Cependant, vous oubliez de mettre à jour les caractéristiques définies dans [!DNL Audience Manager].

Un mois plus tard, vous exécutez le rapport [!UICONTROL Daily Trait Variation] et notez une grande déviation négative sur la caractéristique `productPage == "smartphones"`, bien que le nombre de visiteurs ait augmenté, selon les analyses de votre site. Sur la base de ces informations, vous réalisez que vous n’avez pas mis à jour les caractéristiques dans [!DNL Audience Manager] pour vos nouvelles pages de produits. Vous savez donc que vous devez créer les caractéristiques suivantes :

* productPage == &quot;samsung&quot;
* productPage == &quot;apple&quot;
* productPage == &quot;huawei&quot;

Une fois que vous avez effectué cette opération, votre audience se qualifiera pour les caractéristiques nouvellement créées.
