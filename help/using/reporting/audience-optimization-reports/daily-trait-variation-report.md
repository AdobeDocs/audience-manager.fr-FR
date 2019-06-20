---
description: Ce rapport renvoie une liste des caractéristiques qui ont été réalisées au moins 10 000 fois dans les 30 jours qui précèdent la ou les dates sélectionnées et où un écart type est supérieur ou égal à 1.7 dans l'une ou l'autre direction sur le même intervalle de temps. Le rapport permet d'évaluer la manière dont le nombre d'impressions provenant d'utilisateurs uniques d'une caractéristique fluctue au fil du temps.
seo-description: Ce rapport renvoie une liste des caractéristiques qui ont été réalisées au moins 10 000 fois dans les 30 jours qui précèdent la ou les dates sélectionnées et où un écart type est supérieur ou égal à 1.7 dans l'une ou l'autre direction sur le même intervalle de temps. Le rapport permet d'évaluer la manière dont le nombre d'impressions provenant d'utilisateurs uniques d'une caractéristique fluctue au fil du temps.
seo-title: Rapport Variation de caractéristique quotidienne
solution: Audience Manager
title: Rapport Variation de caractéristique quotidienne
uuid: 4 e 82 bb 17-d 447-4 ed 1-a 4 fc-e 15 b 0 f 1 b 47 f 0
translation-type: tm+mt
source-git-commit: 8f2ec880cbbe2f516ebc240a712337dc09c4e7f7

---


# Daily Trait Variation Report {#daily-trait-variation-report}

Ce rapport renvoie une liste des caractéristiques qui ont été réalisées au moins 10 000 fois dans les 30 jours qui précèdent la ou les dates sélectionnées et où un écart type est supérieur ou égal à 1.7 dans l&#39;une ou l&#39;autre direction sur le même intervalle de temps. Le rapport permet d&#39;évaluer la manière dont le nombre d&#39;impressions provenant d&#39;utilisateurs uniques d&#39;une caractéristique fluctue au fil du temps.

>[!NOTE]
>
>Le rapport Variation de caractéristique quotidienne d&#39;Audience Manager adhère aux principes RBAC. You can only see traits from data sources that you have access to based on the [RBAC User Group](/help/using/features/administration/administration-overview.md) that you belong to.

L&#39;écart type évalue la variation ou la dispersion de la moyenne (ou moyenne/attendue). Un faible écart type indique que les points de données tendent à être très proches de la moyenne. Un écart type élevé indique que les points de données sont répartis sur une grande plage de valeurs.

![](assets/daily_trait_variation.png)

Use the [!UICONTROL Date] list to select one or more dates for your report. Un graphique à barres codées par couleur s&#39;affiche au bas de la liste, qui fournit un représentant visuel de l&#39;écart type de toutes les caractéristiques pour toutes les dates sélectionnées. La ligne verticale noire indique la moyenne.

The middle column contains a list of traits, identified by [!UICONTROL Trait ID] and [!UICONTROL Trait Name]. Cliquez sur une caractéristique pour accéder à une boîte de dialogue contextuelle qui vous permet de choisir parmi les options suivantes :

* **Conserver uniquement :** Supprime toutes les autres caractéristiques du rapport et affiche uniquement les données de cette caractéristique.
* **Exclure :** Supprime cette caractéristique du rapport et affiche les données pour toutes les autres caractéristiques. Vous pouvez exclure plusieurs caractéristiques.
* **Afficher les données :** Permet d&#39;afficher les données de cette ligne. Vous pouvez également télécharger toutes les lignes sous forme de fichier texte.

The [!UICONTROL Standard Deviation] column displays color-coded bar charts that display the standard deviation for each trait over the selected interval. Les barres rouges indiquent des caractéristiques avec un écart type négatif (les points de données tendent à se trouver sous la moyenne). Les barres vertes indiquent des caractéristiques avec un écart type positif (les points de données tendent à se situer au-dessus de la moyenne). Placez le pointeur de la souris sur une barre pour afficher une boîte de dialogue contextuelle contenant davantage d&#39;informations et d&#39;options pour conserver ou exclure cette caractéristique et afficher plus d&#39;informations.

Les icônes s&#39;affichent dans la partie inférieure du rapport grâce à laquelle vous pouvez exporter des données dans divers formats, rétablir toutes les modifications apportées au rapport (par exemple, exclure des caractéristiques), activer ou désactiver les mises à jour automatiques et actualiser les données du rapport. See [Report Icons and Tools Explained](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained).

## Cas d’utilisation {#use-cases}

**Exemple # 1**: ce rapport peut s&#39;avérer très utile dans les cas où vous avez des caractéristiques avec un niveau de caractère saisonnier élevé. Par exemple, imaginons que votre boutique en ligne testent des promotions saisonnières de différents types et prix. You have the following traits defined in [!DNL Audience Manager]:

* `productPage == "December Promotion"`
* `price > "500"`

Say you run the [!UICONTROL Daily Trait Variation] report on the 20th of December and you notice a solid positive deviation on the above mentioned traits in the past 30 days. Cela peut indiquer que vos visiteurs recherchent les produits mentionnés dans votre promotion saisonnière. Pour capitaliser sur cette tendance, vous pouvez ensuite investir davantage d&#39;efforts pour cibler les créatifs pour cette catégorie de produits spécifique sur les visiteurs qui y sont intéressés.

**Exemple n ° 2**: ce rapport peut vous aider à identifier les anomalies de ciblage liées aux problèmes de balisage ou aux mauvaises misconfigurations. Imaginez que vous ayez défini la caractéristique suivante en fonction des catégories de votre boutique en ligne :

* `productPage == "smartphones"`

En raison d&#39;une reconfiguration de votre magasin, vous fractionnez la page smartphones en plusieurs pages, en fonction des noms de marque. However, you forget to update the traits defined in [!DNL Audience Manager].

One month later, you run the [!UICONTROL Daily Trait Variation] report and notice a large negative deviation on the `productPage == "smartphones"` trait, although your visitor number has increased, according to your site analytics. Based on this information, you realize that you haven&#39;t updated the traits in [!DNL Audience Manager] for your new product pages, so you know that you need to create the following traits:

* Productpage = = « samsung »
* Productpage = = « pomme »
* Productpage = = « huawei »

Une fois que vous avez effectué cette opération, votre public sera éligible pour les caractéristiques nouvellement créées.
