---
description: Les signaux sont la plus petite unité d'information au sein de l'Audience Manager. Elles représentent les interactions des utilisateurs ou l’activité des utilisateurs sur vos propriétés en ligne et sont transmises à l’Audience Manager pour être utilisées dans les règles de caractéristiques.
seo-description: Les signaux sont la plus petite unité d'information au sein de l'Audience Manager. Elles représentent les interactions des utilisateurs ou l’activité des utilisateurs sur vos propriétés en ligne et sont transmises à l’Audience Manager pour être utilisées dans les règles de caractéristiques.
seo-title: Présentation des signaux
title: Présentation des signaux
uuid: 04a0554e-954e-484a-8838-9161ef416872
feature: Data Explorer
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 0%

---


# Présentation des signaux

Les signaux sont la plus petite unité d&#39;information au sein de l&#39;Audience Manager. Elles représentent les interactions des utilisateurs ou l’activité des utilisateurs sur vos propriétés en ligne et sont transmises à l’Audience Manager pour être utilisées dans les règles de caractéristiques.

[!DNL Audience Manager] utilise des paires clé-valeur pour représenter des signaux. Par exemple, le signal suivant pourrait indiquer qu’un visiteur a atteint une page Web contenant des éléments électroniques :

* `page = electronics`

Le Tableau de bord [](../../features/data-explorer/data-explorer-signals-dashboard.md) Signals présente plusieurs types d’attributs de signal que vous pouvez utiliser pour créer de nouvelles caractéristiques. Voici une vue détaillée des propriétés de signal disponibles :

* *La paire* valeur-clé vous montre la paire clé-valeur du signal reçu par [!DNL Audience Manager].
* *Le type* de signal décrit la catégorie de chaque signal. Les signaux tombent dans l’une des catégories suivantes :
   * [Fichiers journaux](/help/using/integration/media-data-integration/actionable-log-files.md)utilisables : les signaux en temps réel reçus de vos fichiers journaux de performances multimédia ;
   * [!DNL Adobe Analytics]: les signaux en temps réel reçus de votre [!DNL Adobe Analytics] compte ;
   * Données générales en ligne : les données en temps réel générées par votre activité d&#39;audience et non incluses dans les fichiers journaux et [!DNL Adobe Analytics];
   * Enregistrements intégrés : données reçues par le biais de transferts de données par lot.
* *La source* du signal dépend du type de signal :
   * Pour les signaux embarqués, la source du signal est le nom de la source de données.
   * Pour les signaux provenant de [!DNL Adobe Analytics], la source de données sera toujours une suite de rapports.
   * Pour les fichiers journaux exploitables et les données générales en ligne, aucune information sur la source du signal n’est affichée.
* *Nombre total de décomptes* indique le nombre total de fois où un signal en temps réel a été reçu [!DNL Audience Manager] au cours des 7 derniers jours.
* *Inclus dans Caractéristiques* vous indique si le signal fait partie d’une caractéristique. Cliquez sur la flèche pour afficher les caractéristiques qui incluent le signal correspondant. Pour les signaux qui ne font partie d’aucune caractéristique, la valeur de colonne devient [!UICONTROL Create Onboarded Trait] ou [!UICONTROL Create Rule-Based Trait].

## Fréquence d&#39;actualisation des données de signal

En raison de la grande quantité de données que l’Audience Manager traite quotidiennement, [!UICONTROL Data Explorer] actualise les données de signal affichées à intervalles fixes, selon le type de signal :

* Les données de signal en temps réel (fichiers journaux exploitables, [!DNL Adobe Analytics] données et données générales en ligne) sont actualisées toutes les 4 à 6 heures.
* Les données de signal intégrées sont actualisées toutes les 24 heures.

## Concepts connexes

[Signaux, caractéristiques et segments](/help/using/reference/signal-trait-segment.md)