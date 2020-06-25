---
description: 'Les composants de traitement de données sont les suivants : Hadoop, Snowflake, SOLR et Tableau.'
seo-description: 'Les composants de traitement de données sont les suivants : Hadoop, Snowflake, SOLR et Tableau.'
seo-title: Composants de traitement des données
solution: Audience Manager
title: Composants de traitement des données
uuid: d458d869-7a23-4016-871d-0b994cf4af06
feature: system components
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 0%

---


# Composants de traitement des données{#data-processing-components}

Les composants de traitement de données sont les suivants : Hadoop, Snowflake, SOLR et Tableau.

<!-- 

c_comproc.xml

 -->

L’Audience Manager utilise les composants suivants pour traiter les données :

## Hadoop {#hadoop}

Dans [!DNL Audience Manager], Hadoop est la base de données principale qui contient tout [!DNL Audience Manager] ce que l’utilisateur sait. Par exemple, lorsque les serveurs [de mise en cache des](../../reference/system-components/components-data-collection.md) Profils créent des fichiers journaux contenant des données sur vos utilisateurs, ils les envoient à Hadoop pour enregistrement. Les autres éléments importants de Hadoop sont les suivants :

* **Ruche :** Un data warehouse pour Hadoop. Hive gère les requêtes ad hoc sur les données stockées dans Hadoop.

* **HBase :** Une très grande base de données Hadoop. Il traite et gère les données entrantes et sortantes, les règles de caractéristiques, les informations de modélisation algorithmique et exécute de nombreuses autres fonctions liées au stockage et au déplacement des données vers différents systèmes.

Les clients n&#39;ont pas d&#39;accès direct à ces systèmes. Cependant, les clients travaillent avec eux indirectement, car ces composants stockent des données importantes sur leurs visiteurs de site.

## Snowflake {#snowflake}

[Snowflake](https://www.snowflake.net/) est une base de données de cloud massive. Il fournit des données à de nombreux graphiques de tableau de bord et à leurs zones de texte associées qui affichent la modification en % pour chaque élément du graphique. Si vous utilisez [!DNL Audience Manager] et consultez les rapports de tableau de bord, vous interagissez avec les données fournies par [!UICONTROL Snowflake].



![](assets/dashboardreport.png)

Il ne s&#39;agit en aucun cas d&#39;une liste globale, mais certains rapports tableaux de bord communs qui [!UICONTROL Snowflake] portent sur :

* [Rapport Variation de caractéristiques quotidiennes](/help/using/reporting/audience-optimization-reports/daily-trait-variation-report.md)
* Tous les rapports de chevauchement (voir la section Rapports [](/help/using/reporting/dynamic-reports/dynamic-reports.md) interactifs pour en savoir plus sur chaque rapport de chevauchement).
* [Rapport Signaux inutilisés](/help/using/reporting/dynamic-reports/unused-signals.md)

## SOLR {#solr}

SOLR est une base de données open-source et un système serveur d&#39;Apache. Il offre des capacités de recherche robustes et rapides sur nos ensembles de données volumineux. En tant que [!DNL Audience Manager] client, vous pouvez voir les SOLR en action lorsque vous créez des segments. Il fournit des données au [!UICONTROL Estimated Historic Segment Size] rapport. Le SOLR est idéal pour ce rôle en raison de sa vitesse. Par exemple, SOLR peut mettre à jour les données de taille historique lorsque vous créez des règles et ajoutez de nouvelles caractéristiques à un segment.



![](assets/audsize.png)

## Tableau {#tableau}

[!DNL Audience Manager] utilise [Tableau](https://www.tableausoftware.com/) pour afficher les données dans les rapports [](../../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) interactifs et les rapports [d’optimisation des](../../reporting/audience-optimization-reports/audience-optimization-reports.md)Audiences. Les rapports interactifs affichent les données de performances et de chevauchement pour les caractéristiques et les segments. Au lieu d&#39;utiliser des nombres organisés en colonnes et en rangées, ils renvoient des données en utilisant des formes, des couleurs et des tailles différentes. De plus, vous pouvez choisir des points de données individuels ou des groupes de points de données et parcourir les résultats du rapport pour en savoir plus. Ces techniques de visualisation et l’interactivité des rapports facilitent la compréhension de grandes quantités de données numériques.



![](assets/advertiser_analytics.png)

