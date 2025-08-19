---
description: Les signaux constituent la plus petite unité d’information d’Audience Manager. Ils représentent les interactions ou l’activité des utilisateurs sur vos propriétés en ligne et sont transmis à Audience Manager pour être utilisés dans les règles de caractéristiques.
seo-description: Signals are the smallest unit of information within Audience Manager. They represent user interactions or user activity on your online properties, and get passed on to Audience Manager to be used in trait rules.
seo-title: Understanding Signals
title: Comprendre les signaux
uuid: 04a0554e-954e-484a-8838-9161ef416872
feature: Data Explorer
exl-id: 12ab53e5-302b-4a82-9d8e-07b60139c65e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 1%

---

# Comprendre les signaux

Les signaux constituent la plus petite unité d’information d’Audience Manager. Ils représentent les interactions ou l’activité des utilisateurs sur vos propriétés en ligne et sont transmis à Audience Manager pour être utilisés dans les règles de caractéristiques.

[!DNL Audience Manager] utilise des paires clé-valeur pour représenter les signaux. Par exemple, le signal suivant peut indiquer qu’un visiteur a atteint une page web contenant des éléments électroniques :

* `page = electronics`

Le tableau de bord [Signals Dashboard](../../features/data-explorer/data-explorer-signals-dashboard.md) vous présente plusieurs types d’attributs de signal que vous pouvez utiliser pour créer de nouvelles caractéristiques. Voici une vue détaillée des propriétés de signal disponibles :

* *Paire clé-valeur* indique la paire clé-valeur du signal reçu par [!DNL Audience Manager].
* *Type de signal* décrit la catégorie de chaque signal. Les signaux appartiennent à l&#39;une des catégories suivantes :
   * [Fichiers journaux exploitables](/help/using/integration/media-data-integration/actionable-log-files.md) : signaux en temps réel reçus de vos fichiers journaux de performances multimédia.
   * [!DNL Adobe Analytics] : signaux en temps réel reçus de votre compte [!DNL Adobe Analytics] ;
   * Données générales en ligne : données en temps réel générées par l’activité de votre audience et non incluses dans les fichiers journaux et les [!DNL Adobe Analytics] exploitables.
   * Enregistrements intégrés : données reçues par le biais de transferts de données par lots.
* *Signal Source* dépend du type de signal :
   * Pour les signaux embarqués, la source de signal est le nom de la source de données.
   * Pour les signaux provenant de l’adresse [!DNL Adobe Analytics], la source de données sera toujours une suite de rapports.
   * Pour les fichiers journaux exploitables et les données générales en ligne, aucune information sur la source du signal ne s&#39;affiche.
* *Nombre total* indique le nombre total de fois où un signal en temps réel a été reçu par [!DNL Audience Manager] au cours des 7 derniers jours.
* *Inclus dans les caractéristiques* vous indique si le signal fait partie d’une caractéristique. Cliquez sur la flèche pour afficher les caractéristiques qui incluent le signal correspondant. Pour les signaux qui ne font partie d’aucune caractéristique, la valeur de la colonne devient [!UICONTROL Create Onboarded Trait] ou [!UICONTROL Create Rule-Based Trait].

## Fréquence d&#39;actualisation des données du signal

En raison de la grande quantité de données qu’Audience Manager traite quotidiennement, [!UICONTROL Data Explorer] actualise les données de signal affichées à des intervalles de temps fixes, en fonction du type de signal :

* Les données de signal en temps réel (fichiers journaux exploitables, données [!DNL Adobe Analytics] et données générales en ligne) sont actualisées toutes les 4 à 6 heures.
* Les données des signaux embarqués sont actualisées toutes les 24 heures.

## Concepts connexes

[Signaux, caractéristiques et segments](/help/using/reference/signal-trait-segment.md)
