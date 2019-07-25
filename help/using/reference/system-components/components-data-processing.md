---
description: Données - les composants de traitement comprennent Hadoop, Snowflake, SOLR et Tableau.
seo-description: Données - les composants de traitement comprennent Hadoop, Snowflake, SOLR et Tableau.
seo-title: Données - Traitement des composants
solution: Audience Manager
title: Données - Traitement des composants
uuid: d 458 d 869-7 a 23-4016-871 d -0 b 994 cf 4 af 06
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Data Processing Components{#data-processing-components}

Données - les composants de traitement comprennent Hadoop, Snowflake, SOLR et Tableau.

<!-- 

c_comproc.xml

 -->

Audience Manager utilise les composants suivants pour traiter les données :

## Hadoop {#hadoop}

In [!DNL Audience Manager], Hadoop is the master database that contains everything [!DNL Audience Manager] knows about a user. For example, when the [Profile Cache Servers](../../reference/system-components/components-data-collection.md) create log files that contain data about your users, it sends that data to Hadoop for storage. Les autres éléments importants Hadoop incluent :

* **Hive :** Entrepôt de données pour Hadoop. Hive gère la publicité - requêtes ad hoc aux données stockées dans Hadoop.

* **Hbase :** Une base de données Hadoop très volumineuse. Il traite et gère les données entrants et sortantes, les règles de caractéristiques, les informations de modélisation algorithmique et effectue de nombreuses autres fonctions relatives au stockage et au déplacement de données vers différents systèmes.

Les clients n'ont pas accès directement à ces systèmes. Toutefois, les clients travaillent avec eux indirectement car ces composants stockent des données importantes sur les visiteurs de leur site.

## Snowflake {#snowflake}

[Le flake de neige](https://www.snowflake.net/) est une base de données de cloud massive. Il fournit des données à bon nombre des graphiques du tableau de bord et de leurs zones de texte associées qui affichent la modification % pour chaque élément du graphique. If you use [!DNL Audience Manager] and look at the dashboard reports, you're interacting with data provided by [!UICONTROL Snowflake].



![](assets/dashboardreport.png)

This is by no means a comprehensive list, but some common dashboard reports that [!UICONTROL Snowflake] is responsible for include:

* [Rapport Variation de caractéristique quotidienne](/help/using/reporting/audience-optimization-reports/daily-trait-variation-report.md)
* [Rapport de remise et de performance](/help/using/reporting/dynamic-reports/delivery-performance-report.md)
* All the overlap reports (see the [Interactive Reports](/help/using/reporting/dynamic-reports/dynamic-reports.md) section for information about each overlap report).
* [Rapport Signaux inutilisés](/help/using/reporting/dynamic-reports/unused-signals.md)

## SOLR {#solr}

SOLR est une base de données Open Source et un système serveur d'Apache. Il offre des capacités de recherche robustes et rapides par rapport à nos jeux de données volumineux. As an [!DNL Audience Manager] customer, you can see SOLR in action when you build segments. It provides data to the [!UICONTROL Estimated Historic Segment Size] report. SOLR est idéal pour ce rôle en raison de sa vitesse. Par exemple, SOLR peut mettre à jour les données de taille historiques lorsque vous créez des règles et ajouter de nouvelles caractéristiques à un segment.



![](assets/audsize.png)

## Tableau {#tableau}

[!DNL Audience Manager] utilise [Tableau](https://www.tableausoftware.com/) pour afficher les données dans les rapports [Interactifs](../../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) et Optimisation [de l'audience](../../reporting/audience-optimization-reports/audience-optimization-reports.md). Les rapports interactifs affichent des données de performances et de chevauchement pour les caractéristiques et les segments. Au lieu d'utiliser des nombres organisés en colonnes et lignes, ils renvoient des données à l'aide de différentes formes, couleurs et tailles. En outre, vous pouvez choisir des groupes de données ou des groupes de points de données et les analyser pour plus d'informations. Ces techniques de visualisation et l'interactivité des rapports facilitent la compréhension de grandes quantités de données numériques.



![](assets/advertiser_analytics.png)

