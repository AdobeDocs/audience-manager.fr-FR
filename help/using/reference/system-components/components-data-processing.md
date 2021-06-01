---
description: Les composants de traitement des données incluent Hadoop, Snowflake, SOLR et Tableau.
seo-description: Les composants de traitement des données incluent Hadoop, Snowflake, SOLR et Tableau.
seo-title: Composants de traitement des données
solution: Audience Manager
title: Composants de traitement des données
uuid: d458d869-7a23-4016-871d-0b994cf4af06
feature: 'Composants système '
exl-id: 9ff2b82b-aad0-4d24-96e6-230763019311
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 4%

---

# Composants de traitement des données{#data-processing-components}

Les composants de traitement des données incluent Hadoop, Snowflake, SOLR et Tableau.

<!-- 

c_comproc.xml

 -->

Audience Manager utilise les composants suivants pour traiter les données :

## Hadoop {#hadoop}

Dans [!DNL Audience Manager], Hadoop est la base de données principale qui contient tout ce que [!DNL Audience Manager] sait sur un utilisateur. Par exemple, lorsque les [serveurs de cache de profils](../../reference/system-components/components-data-collection.md) créent des fichiers journaux contenant des données sur vos utilisateurs, ils envoient ces données à Hadoop pour stockage. Autres éléments importants de l’Hadoop :

* **Hive :** entrepôt de données pour Hadoop. Hive gère des requêtes ad hoc sur les données stockées dans Hadoop.

* **HBase :** une base de données d’Hadoop très volumineuse. Il traite et gère les données entrantes et sortantes, les règles de caractéristiques, les informations de modélisation algorithmique et exécute de nombreuses autres fonctions liées au stockage et au déplacement des données vers différents systèmes.

Les clients n’ont pas d’accès direct à ces systèmes. Cependant, les clients travaillent avec eux indirectement, car ces composants stockent des données importantes sur les visiteurs de leur site.

## Snowflake {#snowflake}

[](https://www.snowflake.net/) Snowflakeest une énorme base de données en nuage. Il fournit des données à de nombreux graphiques du tableau de bord et aux zones de texte associées qui affichent la modification en % de chaque élément du graphique. Si vous utilisez [!DNL Audience Manager] et que vous consultez les rapports du tableau de bord, vous interagissez avec les données fournies par [!UICONTROL Snowflake].



![](assets/dashboardreport.png)

Il ne s’agit en aucun cas d’une liste exhaustive, mais certains rapports courants du tableau de bord qui portent la responsabilité de [!UICONTROL Snowflake] incluent :

* [Rapport de variation des caractéristiques quotidiennes](/help/using/reporting/audience-optimization-reports/daily-trait-variation-report.md)
* Tous les rapports de chevauchement (voir la section [Rapports interactifs](/help/using/reporting/dynamic-reports/dynamic-reports.md) pour plus d’informations sur chaque rapport de chevauchement).
* [Rapport des signaux inutilisés](/help/using/reporting/dynamic-reports/unused-signals.md)

## SOLR {#solr}

SOLR est un système de serveur et de base de données Open Source d’Apache. Il offre des fonctionnalités de recherche robustes et rapides sur nos jeux de données volumineux. En tant que client [!DNL Audience Manager], vous pouvez voir SOLR en action lorsque vous créez des segments. Il fournit des données au rapport [!UICONTROL Estimated Historic Segment Size]. SOLR est idéale pour ce rôle à cause de sa vitesse. Par exemple, SOLR peut mettre à jour les données de taille historique lorsque vous créez des règles et ajoutez de nouvelles caractéristiques à un segment.



![](assets/audsize.png)

## Tableau {#tableau}

[!DNL Audience Manager] utilise  [](https://www.tableausoftware.com/) Tablette pour afficher automatiquement les données dans les  [rapports ](../../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) interactifs et les rapports d’ [Audience Optimization](../../reporting/audience-optimization-reports/audience-optimization-reports.md). Les rapports interactifs affichent des données de performances et de chevauchement pour les caractéristiques et les segments. Au lieu d’utiliser des nombres organisés en colonnes et en lignes, ils renvoient des données avec des formes, des couleurs et des tailles différentes. En outre, vous pouvez sélectionner des groupes ou des individus de points de données et parcourir les résultats du rapport pour plus d’informations. Ces techniques de visualisation et d’interactivité des rapports permettent de comprendre plus facilement de grandes quantités de données numériques.



![](assets/advertiser_analytics.png)
