---
description: Les signaux sont la plus petite unité d’informations d’Audience Manager. Elles représentent les interactions de l’utilisateur ou l’activité de l’utilisateur sur vos propriétés en ligne et sont transmises à Audience Manager pour être utilisées dans les règles de caractéristiques.
seo-description: Les signaux sont la plus petite unité d’informations d’Audience Manager. Elles représentent les interactions de l’utilisateur ou l’activité de l’utilisateur sur vos propriétés en ligne et sont transmises à Audience Manager pour être utilisées dans les règles de caractéristiques.
seo-title: Présentation des signaux
title: Présentation des signaux
uuid: 04a0554e-954e-484a-8838-9161ef416872
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Présentation des signaux

Les signaux sont la plus petite unité d’informations d’Audience Manager. Elles représentent les interactions de l’utilisateur ou l’activité de l’utilisateur sur vos propriétés en ligne et sont transmises à Audience Manager pour être utilisées dans les règles de caractéristiques.

[!DNL Audience Manager] utilise des paires clé-valeur pour représenter les signaux. Par exemple, le signal suivant peut indiquer qu’un visiteur a atteint une page Web contenant de l’électronique :

* `page = electronics`

Le tableau de bord [](../../features/data-explorer/data-explorer-signals-dashboard.md) Signals présente plusieurs types d’attributs de signal que vous pouvez utiliser pour créer de nouvelles caractéristiques. Voici une vue détaillée des propriétés de signal disponibles :

* *La paire* clé-valeur montre la paire clé-valeur du signal reçu par [!DNL Audience Manager].
* *Le type* de signal décrit la catégorie de chaque signal. Les signaux appartiennent à l’une des catégories suivantes :
   * [Fichiers](/help/using/integration/media-data-integration/actionable-log-files.md)journaux utilisables : les signaux en temps réel reçus de vos fichiers journaux de performances multimédia ;
   * [!DNL Adobe Analytics]: signaux en temps réel reçus de votre [!DNL Adobe Analytics] compte ;
   * Données générales en ligne : données en temps réel générées par l’activité de votre audience et non incluses dans les fichiers journaux et [!DNL Adobe Analytics];
   * Enregistrements intégrés : données reçues par le biais de transferts de données par lots.
* *La source* du signal dépend du type de signal :
   * Pour les signaux embarqués, la source du signal est le nom de la source de données.
   * Pour les signaux provenant de [!DNL Adobe Analytics], la source de données sera toujours une suite de rapports.
   * Pour les fichiers journaux exploitables et les données générales en ligne, aucune information sur la source du signal n’est affichée.
* *Nombre total de décomptes* indique le nombre total de fois où un signal en temps réel a été reçu [!DNL Audience Manager] au cours des 7 derniers jours.
* *Inclus dans Caractéristiques* vous indique si le signal fait partie d’une caractéristique. Cliquez sur la flèche pour afficher les caractéristiques qui incluent le signal correspondant. Pour les signaux qui ne font partie d’aucune caractéristique, la valeur de colonne devient [!UICONTROL Create Onboarded Trait] ou [!UICONTROL Create Rule-Based Trait].

## Fréquence d'actualisation des données du signal

En raison de la grande quantité de données qu’Audience Manager traite quotidiennement, [!UICONTROL Data Explorer] actualise les données de signal affichées à intervalles fixes, selon le type de signal :

* Les données de signal en temps réel (fichiers journaux exploitables, [!DNL Adobe Analytics] données et données générales en ligne) sont actualisées toutes les 4 à 6 heures.
* Les données du signal intégré sont actualisées toutes les 24 heures.

## Concepts associés

[Signaux, caractéristiques et segments](/help/using/reference/signal-trait-segment.md)