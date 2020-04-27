---
description: Les composants de traitement de données comprennent Hadoop, Snowflake, SOLR et Tableau.
seo-description: Les composants de traitement de données comprennent Hadoop, Snowflake, SOLR et Tableau.
seo-title: Composants de traitement de données
solution: Audience Manager
title: Composants de traitement de données
uuid: d458d869-7a23-4016-871d-0b994cf4af06
translation-type: tm+mt
source-git-commit: d4c5f2008a0b5da889d9192bf4b9db8ba343de9a

---


# Composants de traitement de données{#data-processing-components}

Les composants de traitement de données comprennent Hadoop, Snowflake, SOLR et Tableau.

<!-- 

c_comproc.xml

 -->

 Gestionnaire de  de utilise les composants suivants pour traiter les données :

## Hadoop {#hadoop}

Dans [!DNL Audience Manager]Hadoop est la base de données principale qui contient tout [!DNL Audience Manager] ce qu’un utilisateur sait sur lui. Par exemple, lorsque les serveurs [de mise en cache](../../reference/system-components/components-data-collection.md) du créent des fichiers journaux contenant des données sur vos utilisateurs, ils les envoient à Hadoop pour   . Les autres éléments importants de Hadoop sont les suivants :

* **Hive :** Entrepôt de données pour Hadoop. Hive gère les ad hoc  aux données stockées dans Hadoop.

* **HBase :** Une très grande base de données Hadoop. Il traite et gère les données entrantes et sortantes, les règles de caractéristiques, les informations de modélisation algorithmique et exécute de nombreuses autres fonctions liées au stockage et au déplacement des données vers différents systèmes.

Les clients n&#39;ont pas accès directement à ces systèmes. Cependant, les clients travaillent avec eux indirectement, car ces composants stockent des données importantes sur leurs de site.

## Flocon de neige {#snowflake}

[Snowflake](https://www.snowflake.net/) est une base de données massive sur les nuages. Il fournit des données à la plupart des graphiques de  et aux zones de texte qui y sont associées, qui affichent le pourcentage de changement pour chaque élément du graphique. Si vous utilisez [!DNL Audience Manager] et consultez les rapports , vous interagissez avec les données fournies par [!UICONTROL Snowflake].



![](assets/dashboardreport.png)

Il ne s&#39;agit en aucun cas d&#39;une  complète, mais certains rapports  de qui [!UICONTROL Snowflake] portent sur les sujets suivants :

* [Rapport Variation de caractéristiques quotidiennes](/help/using/reporting/audience-optimization-reports/daily-trait-variation-report.md)
* Tous les rapports de chevauchement (voir la section Rapports [](/help/using/reporting/dynamic-reports/dynamic-reports.md) interactifs pour plus d’informations sur chaque rapport de chevauchement).
* [Rapport Signaux inutilisés](/help/using/reporting/dynamic-reports/unused-signals.md)

## SOLR {#solr}

SOLR est une base de données open-source et un système serveur d&#39;Apache. Il offre des fonctionnalités de recherche robustes et rapides sur nos ensembles de données volumineux. En tant que [!DNL Audience Manager] client, vous pouvez voir SOLR en action lorsque vous créez des segments. Il fournit des données au [!UICONTROL Estimated Historic Segment Size] rapport. SOLR est idéal pour ce rôle à cause de sa vitesse. Par exemple, SOLR peut mettre à jour les données de taille historique lorsque vous créez des règles et ajoutez de nouvelles caractéristiques à un segment.



![](assets/audsize.png)

## Tableau {#tableau}

[!DNL Audience Manager] utilise [Tableau](https://www.tableausoftware.com/) pour afficher les données dans les rapports [](../../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) interactifs et dans les rapports [d’optimisation](../../reporting/audience-optimization-reports/audience-optimization-reports.md). Les rapports interactifs affichent des données de performances et de chevauchement pour les caractéristiques et les segments. Au lieu d’utiliser des nombres organisés en colonnes et en rangées, ils renvoient des données en utilisant des formes, des couleurs et des tailles différentes. De plus, vous pouvez choisir des groupes ou des individus de points de données et approfondir l’analyse des résultats du rapport pour en savoir plus. Ces techniques de visualisation et l’interactivité des rapports facilitent la compréhension de grandes quantités de données numériques.



![](assets/advertiser_analytics.png)

