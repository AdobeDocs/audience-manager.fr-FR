---
description: Ce rapport renvoie une liste des caractéristiques qui ont été réalisées au moins 10 000 fois au cours des 30 jours précédant la ou les date(s) sélectionnée(s) et dont l’écart type est supérieur ou égal à 1,7 dans l’une ou l’autre des directions au cours du même intervalle de temps. Le rapport vous aide à évaluer la manière dont le nombre d’impressions d’utilisateurs uniques d’une caractéristique varie au fil du temps.
seo-description: Ce rapport renvoie une liste des caractéristiques qui ont été réalisées au moins 10 000 fois au cours des 30 jours précédant la ou les date(s) sélectionnée(s) et dont l’écart type est supérieur ou égal à 1,7 dans l’une ou l’autre des directions au cours du même intervalle de temps. Le rapport vous aide à évaluer la manière dont le nombre d’impressions d’utilisateurs uniques d’une caractéristique varie au fil du temps.
seo-title: Rapport Variation de caractéristiques quotidiennes
solution: Audience Manager
title: Rapport Variation de caractéristiques quotidiennes
uuid: 4e82bb17-d447-4ed1-a4fc-e15b0f1b47f0
translation-type: tm+mt
source-git-commit: 8f2ec880cbbe2f516ebc240a712337dc09c4e7f7

---


# Rapport Variation de caractéristiques quotidiennes {#daily-trait-variation-report}

Ce rapport renvoie une liste des caractéristiques qui ont été réalisées au moins 10 000 fois au cours des 30 jours précédant la ou les date(s) sélectionnée(s) et dont l’écart type est supérieur ou égal à 1,7 dans l’une ou l’autre des directions au cours du même intervalle de temps. Le rapport vous aide à évaluer la manière dont le nombre d’impressions d’utilisateurs uniques d’une caractéristique varie au fil du temps.

>[!NOTE]
>
>Le rapport Variation de caractéristiques quotidiennes d’Audience Manager respecte les principes RBAC. Vous pouvez uniquement afficher les caractéristiques des sources de données auxquelles vous avez accès en fonction du groupe [d’utilisateurs](/help/using/features/administration/administration-overview.md) RBAC auquel vous appartenez.

L’écart type mesure la variation ou la dispersion par rapport à la moyenne (ou la valeur moyenne/attendue). Un écart type faible indique que les points de données tendent à être très proches de la moyenne. Un écart type élevé indique que les points de données sont répartis sur une large plage de valeurs.

![](assets/daily_trait_variation.png)

Utilisez la [!UICONTROL Date] liste pour sélectionner une ou plusieurs dates pour votre rapport. Un graphique à barres codé par couleur s’affiche au bas de la liste et fournit une représentation visuelle de la plage d’écart type pour toutes les caractéristiques sur toutes les dates sélectionnées. La ligne verticale noire indique la moyenne.

La colonne du milieu contient une liste de caractéristiques, identifiées par [!UICONTROL Trait ID] et [!UICONTROL Trait Name]. Cliquez sur une caractéristique pour accéder à une boîte de dialogue contextuelle qui vous permet de sélectionner l’une des options suivantes :

* **** Conserver uniquement : Supprime toutes les autres caractéristiques du rapport et affiche uniquement les données correspondant à cette caractéristique.
* **** Exclure : Supprime cette caractéristique du rapport et affiche des données pour toutes les autres caractéristiques. Vous pouvez exclure plusieurs caractéristiques.
* **** Afficher les données : Permet d’afficher les données de cette ligne. Vous pouvez également télécharger toutes les lignes sous forme de fichier texte.

La [!UICONTROL Standard Deviation] colonne affiche des graphiques à barres codés par couleur qui affichent l’écart type pour chaque caractéristique sur l’intervalle sélectionné. Les barres rouges indiquent les caractéristiques présentant un écart-type négatif (les points de données tendent à être inférieurs à la moyenne). Les barres vertes indiquent les caractéristiques présentant un écart-type positif (les points de données tendent à être supérieurs à la moyenne). Placez le pointeur de la souris sur une barre pour afficher une boîte de dialogue contextuelle contenant plus d’informations et d’options permettant de conserver ou d’exclure cette caractéristique et d’afficher plus d’informations.

Les icônes s’affichent au bas du rapport, ce qui vous permet d’exporter des données dans divers formats, de rétablir les modifications que vous avez apportées au rapport (telles que l’exclusion des caractéristiques), d’activer ou de désactiver les mises à jour automatiques et d’actualiser les données du rapport. Voir Icônes de [rapport et outils expliqués](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained).

## Cas d’utilisation {#use-cases}

**Exemple 1**: ce rapport peut être très utile dans les situations où vous avez des caractéristiques avec un niveau de haute saison. Par exemple, supposons que votre boutique en ligne teste les promotions saisonnières de différents types et prix. Les caractéristiques suivantes sont définies dans [!DNL Audience Manager]:

* `productPage == "December Promotion"`
* `price > "500"`

Disons que vous lancez le [!UICONTROL Daily Trait Variation] rapport le 20 décembre et que vous constatez une nette déviation positive des caractéristiques mentionnées ci-dessus au cours des 30 derniers jours. Cela peut indiquer que vos visiteurs recherchent les produits mentionnés dans votre promotion saisonnière. Pour tirer parti de cette tendance, vous pouvez ensuite investir davantage d’efforts dans le ciblage des créatifs pour cette catégorie de produits spécifique sur les visiteurs qui y sont intéressés.

**Exemple n° 2**: ce rapport peut vous aider à identifier les anomalies de ciblage liées aux problèmes de balisage ou aux erreurs de configuration des caractéristiques. Imaginez que vous ayez défini la caractéristique suivante en fonction des catégories de votre boutique en ligne :

* `productPage == "smartphones"`

En raison d’une reconfiguration de votre boutique, vous divisez la page des smartphones en plusieurs pages, en fonction des noms de marque. Toutefois, vous oubliez de mettre à jour les caractéristiques définies dans [!DNL Audience Manager].

Un mois plus tard, vous lancez le [!UICONTROL Daily Trait Variation] rapport et constatez une importante déviation négative sur la `productPage == "smartphones"` caractéristique, bien que le nombre de visiteurs ait augmenté, selon les analyses de votre site. Sur la base de ces informations, vous réalisez que vous n’avez pas mis à jour les caractéristiques de [!DNL Audience Manager] vos nouvelles pages de produits. Vous devez donc créer les caractéristiques suivantes :

* productPage == "samsung"
* productPage == "apple"
* productPage == "huawei"

Une fois que vous aurez effectué cette opération, vous verrez votre audience se qualifier pour les nouvelles caractéristiques créées.
