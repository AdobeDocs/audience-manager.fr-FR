---
description: Les composants de traitement de données comprennent Hadoop, Snowflake, SOLR et Tableau.
seo-description: Les composants de traitement de données comprennent Hadoop, Snowflake, SOLR et Tableau.
seo-title: Composants de traitement de données
solution: Audience Manager
title: Composants de traitement de données
uuid: d458d869-7a23-4016-871d-0b994cf4af06
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Composants de traitement de données{#data-processing-components}

Les composants de traitement de données comprennent Hadoop, Snowflake, SOLR et Tableau.

<!-- 

c_comproc.xml

 -->

Audience Manager utilise les composants suivants pour traiter les données :

## Hadoop {#hadoop}

Dans [!DNL Audience Manager]Hadoop est la base de données principale qui contient tout [!DNL Audience Manager] ce qu’un utilisateur sait sur lui. Par exemple, lorsque les serveurs [de cache de](../../reference/system-components/components-data-collection.md) profil créent des fichiers journaux contenant des données sur vos utilisateurs, ils les envoient à Hadoop pour stockage. Les autres éléments importants de Hadoop sont les suivants :

* **** Hive : Entrepôt de données pour Hadoop. Hive gère les requêtes ad hoc sur les données stockées dans Hadoop.

* **** HBase : Une très grande base de données Hadoop. Il traite et gère les données entrantes et sortantes, les règles de caractéristiques, les informations de modélisation algorithmique et exécute de nombreuses autres fonctions liées au stockage et au déplacement des données vers différents systèmes.

Les clients n'ont pas accès directement à ces systèmes. Cependant, les clients travaillent avec eux indirectement, car ces composants stockent des données importantes sur les visiteurs de leur site.

## Flocon de neige {#snowflake}

[Snowflake](https://www.snowflake.net/) est une base de données massive sur les nuages. Il fournit des données à de nombreux graphiques de tableaux de bord et à leurs zones de texte associées qui affichent la modification en % de chaque élément du graphique. Si vous utilisez [!DNL Audience Manager] et regardez les rapports des tableaux de bord, vous interagissez avec les données fournies par [!UICONTROL Snowflake].



![](assets/dashboardreport.png)

Il ne s’agit en aucun cas d’une liste exhaustive, mais certains rapports de tableau de bord courants [!UICONTROL Snowflake] sont responsables :

* [Rapport Variation de caractéristiques quotidiennes](/help/using/reporting/audience-optimization-reports/daily-trait-variation-report.md)
* [Rapport sur la livraison et les performances](/help/using/reporting/dynamic-reports/delivery-performance-report.md)
* Tous les rapports de chevauchement (voir la section Rapports [](/help/using/reporting/dynamic-reports/dynamic-reports.md) interactifs pour en savoir plus sur chaque rapport de chevauchement).
* [Rapport Signaux inutilisés](/help/using/reporting/dynamic-reports/unused-signals.md)

## SOLR {#solr}

SOLR est une base de données open-source et un système serveur d'Apache. Il offre des fonctionnalités de recherche robustes et rapides sur nos ensembles de données volumineux. En tant que [!DNL Audience Manager] client, vous pouvez voir SOLR en action lorsque vous créez des segments. Il fournit des données au [!UICONTROL Estimated Historic Segment Size] rapport. SOLR est idéal pour ce rôle à cause de sa vitesse. Par exemple, SOLR peut mettre à jour les données de taille historique lorsque vous créez des règles et ajoutez de nouvelles caractéristiques à un segment.



![](assets/audsize.png)

## Tableau {#tableau}

[!DNL Audience Manager] utilise [Tableau](https://www.tableausoftware.com/) pour afficher les données dans les rapports [](../../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) interactifs et les rapports [d’optimisation de l’](../../reporting/audience-optimization-reports/audience-optimization-reports.md)audience. Les rapports interactifs affichent des données de performances et de chevauchement pour les caractéristiques et les segments. Au lieu d’utiliser des nombres organisés en colonnes et en lignes, ils renvoient des données en utilisant des formes, des couleurs et des tailles différentes. De plus, vous pouvez choisir des groupes ou des individus de points de données et parcourir les résultats du rapport pour plus d’informations. Ces techniques de visualisation et l’interactivité des rapports facilitent la compréhension de grandes quantités de données numériques.



![](assets/advertiser_analytics.png)

