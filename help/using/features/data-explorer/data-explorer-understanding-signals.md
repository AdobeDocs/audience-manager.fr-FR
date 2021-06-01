---
description: Les signaux constituent la plus petite unité d’information de l’Audience Manager. Elles représentent les interactions de l’utilisateur ou l’activité de l’utilisateur sur vos propriétés en ligne et sont transmises à l’Audience Manager afin d’être utilisée dans les règles de caractéristiques.
seo-description: Les signaux constituent la plus petite unité d’information de l’Audience Manager. Elles représentent les interactions de l’utilisateur ou l’activité de l’utilisateur sur vos propriétés en ligne et sont transmises à l’Audience Manager afin d’être utilisée dans les règles de caractéristiques.
seo-title: Présentation des signaux
title: Présentation des signaux
uuid: 04a0554e-954e-484a-8838-9161ef416872
feature: 'Explorateur de données '
exl-id: 12ab53e5-302b-4a82-9d8e-07b60139c65e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 3%

---

# Présentation des signaux

Les signaux constituent la plus petite unité d’information de l’Audience Manager. Elles représentent les interactions utilisateur ou l’activité utilisateur sur vos propriétés en ligne et sont transmises à l’Audience Manager afin d’être utilisées dans les règles de caractéristiques.

[!DNL Audience Manager] utilise des paires clé-valeur pour représenter des signaux. Par exemple, le signal suivant peut indiquer qu’un visiteur a atteint une page web contenant des éléments électroniques :

* `page = electronics`

Le [tableau de bord des signaux](../../features/data-explorer/data-explorer-signals-dashboard.md) présente plusieurs types d’attributs de signal que vous pouvez utiliser pour créer de nouvelles caractéristiques. Voici une vue détaillée des propriétés de signal disponibles :

* *L’* paires clé-valeur vous montre la paire clé-valeur du signal reçu par  [!DNL Audience Manager].
* *Le* type de signal décrit la catégorie de chaque signal. Les signaux appartiennent à l’une des catégories suivantes :
   * [Fichiers journaux pratiques](/help/using/integration/media-data-integration/actionable-log-files.md) : les signaux en temps réel reçus de vos fichiers journaux de performances multimédia ;
   * [!DNL Adobe Analytics]: les signaux en temps réel reçus de votre  [!DNL Adobe Analytics] compte ;
   * Données générales en ligne : données en temps réel générées par votre activité d’audience et non incluses dans les fichiers journaux exploitables et [!DNL Adobe Analytics] ;
   * Enregistrements intégrés : données reçues par le biais de transferts de données par lots.
* *La* source du signal dépend du type du signal :
   * Pour les signaux intégrés, la source du signal est le nom de la source de données.
   * Pour les signaux provenant de [!DNL Adobe Analytics], la source de données sera toujours une suite de rapports.
   * Pour les fichiers journaux exploitables et les données générales en ligne, aucune information de source de signal n’est affichée.
* *Nombre total* de messages indique le nombre total de fois où un signal en temps réel a été reçu par  [!DNL Audience Manager] au cours des 7 derniers jours.
* *Inclus dans* Caractéristiques indique si le signal fait partie d’une caractéristique. Cliquez sur la flèche pour afficher les caractéristiques qui incluent le signal correspondant. Pour les signaux qui ne font partie d’aucune caractéristique, la valeur de colonne passe à [!UICONTROL Create Onboarded Trait] ou [!UICONTROL Create Rule-Based Trait].

## Fréquence d’actualisation des données de signal

En raison de la grande quantité de données que l’Audience Manager traite quotidiennement, [!UICONTROL Data Explorer] actualise les données de signal affichées à intervalles réguliers, selon le type de signal :

* Les données de signal en temps réel (fichiers journaux exploitables, [!DNL Adobe Analytics] données et données générales en ligne) sont actualisées toutes les 4 à 6 heures.
* Les données du signal intégré sont actualisées toutes les 24 heures.

## Concepts associés

[Signaux, caractéristiques et segments](/help/using/reference/signal-trait-segment.md)
