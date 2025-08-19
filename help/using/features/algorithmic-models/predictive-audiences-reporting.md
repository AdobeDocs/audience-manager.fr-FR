---
description: Les audiences prédictives vous aident à classer les audiences inconnues en personas distinctes en temps réel à l’aide de la science des données.
seo-description: Predictive Audiences help you classify unknown audiences into distinct personas in real-time, using data science.
seo-title: Predictive Audiences Reporting
solution: Audience Manager
title: Rapports Prédictifs Sur Les Audiences
feature: Algorithmic Models
exl-id: 43a4272c-d9be-47f6-9b81-15472b0366ab
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '608'
ht-degree: 2%

---

# Rapports Prédictifs Sur Les Audiences

Après avoir enregistré un modèle [!UICONTROL Predictive Audiences], Audience Manager commence à l’entraîner. Dans quelques heures, le modèle calculé commencera à analyser les audiences sur les [serveurs de collecte de données](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/system-components/components-data-collection.html?lang=fr#dcs-pcs). Les rapports seront disponibles le lendemain.

Pour afficher les résultats de votre classification [!UICONTROL Predictive Audiences], accédez à **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**, puis cliquez sur votre modèle dans la liste.

Utilisez les options de filtrage sur le côté gauche pour rechercher le nom du modèle ou filtrer les résultats en fonction du type de modèle.

![predictive-audiences-filter](assets/predictive-audiences-filter-models.png)

Le tableau des modèles affiche les informations suivantes :

* **[!UICONTROL ID]** : l’ID de modèle identifie de manière unique chaque modèle dans votre compte Audience Manager ;
* **[!UICONTROL Name]** : nom que vous avez fourni à l’étape de création du modèle ;
* **[!UICONTROL Description]** : description que vous avez fournie à l’étape de création du modèle ;
* **[!UICONTROL Model Type]** : le type de chaque modèle ([!UICONTROL Look-Alike Modeling] ou [!UICONTROL Predictive Audiences]);
* **[!UICONTROL Status]** : l&#39;état de chaque modèle :
   * **[!UICONTROL Pending]** : le modèle est en cours d’initialisation et commencera bientôt à produire des résultats ;
   * **[!UICONTROL Active]** : le modèle s’exécute correctement et produit des résultats ;
   * **[!UICONTROL Warning]** : le modèle n’a pas produit de résultats en raison de données insuffisantes (c’est-à-dire une faible population de lignes de base, les profils utilisateur ne sont pas riches) ;
   * **[!UICONTROL Error]** : échec de l’exécution du modèle. Vous devez contacter votre représentant Adobe.

## Rapport de vue d’ensemble du modèle{#model-report}

Une fois que vous avez choisi un modèle, sa page de rapport se charge. En haut de la page, vous pouvez voir les 5 segments prédictifs les plus importants, basés sur la réalisation en temps réel d’un jour, par lesquels le modèle a classé votre audience cible. La catégorie **[!UICONTROL Other]** inclut le reste des rôles, qui n’étaient pas inclus dans les 5 segments prédictifs les plus importants.

Audience Manager affiche à la fois un graphique en anneau à code couleur et un graphique chronologique pour votre [!UICONTROL Predictive Audiences].

Cliquez sur les onglets Personnes en haut de la page pour les ajouter ou les supprimer du graphique et du graphique.

Le graphique en anneau vous présente une répartition basée sur les rôles de votre audience cible, tandis que le graphique vous montre la tendance de la population en temps réel sur 1 jour de vos segments prédictifs au cours des 6 derniers jours.

Si l’état du modèle est [!UICONTROL Pending], [!UICONTROL Warning] ou [!UICONTROL Error], l’état du modèle s’affiche à la place des graphiques.

![smart-persona-report](assets/predictive-audiences-report.png)

Le tableau de rapport affiche les informations suivantes pour chaque segment de [!UICONTROL Predictive Audiences].

1. **[!UICONTROL SEGMENT ID]** : identifiant de segment du segment créé automatiquement associé à chaque persona ;
1. **[!UICONTROL NAME]** : le nom du persona ;
1. **[!UICONTROL STATUS]** : statut du segment [!UICONTROL Predictive Audiences] :
   * **[!UICONTROL Succeeded]** : les utilisateurs sont classés dans ce segment ;
   * **[!UICONTROL Pending]** : le segment est toujours en cours d’initialisation ;
   * **[!UICONTROL Insufficient Training Data]** : les utilisateurs ne sont pas classés dans ce segment en raison de données insuffisantes. La population totale de la ligne de base est trop faible et ne fournit pas suffisamment de données pour en tirer des enseignements.
1. **[!UICONTROL 1 DAY REAL TIME POPULATION]** : nombre de réalisations de segment pour chaque personnage au cours des dernières 24 heures.
1. **[!UICONTROL 1 DAY REAL TIME POPULATION %]** : pourcentage de réalisations de segments pour chaque personnage, au cours des dernières 24 heures, sur la population totale des modèles.

## Caractéristiques influentes{#influential-traits}

[!UICONTROL Influential Traits] sont les caractéristiques que l’algorithme [!UICONTROL Predictive Audiences] a découvertes comme étant les prédicteurs les plus fiables pour déterminer la classification de persona d’un visiteur.

Leur signe indique si la présence de la caractéristique augmente(+) ou diminue(-) la probabilité que l’utilisateur appartienne à la personne sélectionnée.

Pour afficher les caractéristiques principales de tous vos profils, cliquez sur [!UICONTROL View All Influential Traits].

La fenêtre [!UICONTROL Influential Traits] affiche les informations suivantes, pour chaque persona du modèle sélectionné :

![traits-influents](assets/predictive-audiences-influential-traits.png)

1. **[!UICONTROL TRAIT ID]** : identifiant de caractéristique de chaque caractéristique influente pour la personne sélectionnée ;
1. **[!UICONTROL NAME]** : le nom de chaque caractéristique influente pour la personne sélectionnée ;
1. **[!UICONTROL DESCRIPTION]** : la description de chaque caractéristique influente pour le persona sélectionné ;
1. **[!UICONTROL WEIGHT]** : le poids de chaque caractéristique d’influence pour la personne sélectionnée. Les [!UICONTROL Influential Traits] sont par défaut triées par poids, dans l’ordre décroissant.  La valeur des poids indique leur pouvoir prédictif. Le signe indique si la présence du trait augmente(+) ou diminue(-) la probabilité d&#39;appartenir à une personne.
1. **[!UICONTROL 30 DAY REAL TIME POPULATION]** : nombre de réalisations de caractéristiques uniques pour chaque caractéristique influente pour la personne sélectionnée, au cours des 30 derniers jours.
