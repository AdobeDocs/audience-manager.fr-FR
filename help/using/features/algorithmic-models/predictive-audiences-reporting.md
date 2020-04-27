---
description: Les  prédictifs  vous aident à classer les de  inconnu en personnes distinctes en temps réel, à l’aide de la science des données.
seo-description: Les  prédictifs  vous aident à classer les de  inconnu en personnes distinctes en temps réel, à l’aide de la science des données.
seo-title: ' prédictif  '
solution: Audience Manager
title: ' Gestionnaire de   Gestionnaire de  Prédictif'
translation-type: tm+mt
source-git-commit: 8259f07c91efa0efd88e8f7c87cb1829ffadd77d

---


#  prédictif  

Une fois que vous avez enregistré un [!UICONTROL Predictive Audiences] modèle,  Gestionnaire de  de  le de l’avoir formé. En quelques heures, le modèle calculé  l&#39;analyse  sur les serveurs [de collecte de](https://docs.adobe.com/content/help/en/audience-manager/user-guide/reference/system-components/components-data-collection.html#dcs-pcs)données.  sera disponible le lendemain.

Pour afficher les résultats de votre [!UICONTROL Predictive Audiences] classification, accédez à **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**, puis cliquez sur votre modèle dans le  de.

Utilisez les options de filtrage sur le côté gauche pour rechercher le nom du modèle ou filtrez les résultats en fonction du type de modèle.

![--prédictif-filtre](assets/predictive-audiences-filter-models.png)

Le tableau des modèles présente les informations suivantes :

* **[!UICONTROL ID]**: l&#39;ID de modèle identifie de manière unique chaque modèle dans votre compte  Gestionnaire de  de ;
* **[!UICONTROL Name]**: le nom fourni à l&#39;étape de création du modèle ;
* **[!UICONTROL Description]**: la description que vous avez fournie à l&#39;étape de création du modèle;
* **[!UICONTROL Model Type]**: le type de chaque modèle ([!UICONTROL Look-Alike Modeling] ou [!UICONTROL Predictive Audiences]);
* **[!UICONTROL Status]**: le statut de chaque modèle:
   * **[!UICONTROL Pending]**: le modèle est en cours d&#39;initialisation et  produira des résultats sous peu;
   * **[!UICONTROL Active]**: le modèle fonctionne correctement et produit des résultats;
   * **[!UICONTROL Warning]**: le modèle n&#39;a pas produit de résultats, en raison d&#39;une insuffisance de données (population de référence faible,  utilisateurs ne sont pas riches);
   * **[!UICONTROL Error]**: le modèle n&#39;a pas pu s&#39;exécuter. Contactez votre représentant Adobe.

## Rapport Présentation du modèle{#model-report}

Une fois que vous avez choisi un modèle, sa page de  se charge. En haut de la page, vous pouvez voir les 5 principaux segments prédictifs, d&#39;après la prise de conscience en temps réel d&#39;une journée, selon laquelle le modèle a classifié votre  par  de. Le **[!UICONTROL Other]** inclut le reste des personnages, qui n’étaient pas inclus dans les 5 principaux segments de prévision.

 Gestionnaire de  de affiche à la fois un graphique en anneau codé en couleur et un graphique de chronologie pour votre [!UICONTROL Predictive Audiences]graphique.

Lorsque vous cliquez sur les onglets personnalisés en haut de la page, vous les ajoutez ou les supprimez du graphique et du graphique.

Le graphique en anneau vous montre une ventilation personnelle de vos   de l&#39;, tandis que le graphique vous montre la tendance de population en temps réel de 1 jour de vos segments prédictifs au cours des 6 derniers jours.

Si l’état du modèle est [!UICONTROL Pending], [!UICONTROL Warning]ou [!UICONTROL Error], l’état du modèle s’affiche à la place des graphiques.

![smart-persona-report](assets/predictive-audiences-report.png)

Le tableau du rapport présente les informations suivantes pour chaque [!UICONTROL Predictive Audiences] segment.

1. **[!UICONTROL SEGMENT ID]**: l&#39;ID de segment du segment créé automatiquement associé à chaque personne ;
1. **[!UICONTROL NAME]**: le nom de la personne;
1. **[!UICONTROL STATUS]**: l’état du [!UICONTROL Predictive Audiences] segment :
   * **[!UICONTROL Succeeded]**: les utilisateurs sont classés dans ce segment ;
   * **[!UICONTROL Pending]**: le segment est toujours en cours d’initialisation ;
   * **[!UICONTROL Insufficient Training Data]**: les utilisateurs ne sont pas classés dans ce segment en raison de données insuffisantes. La population de base totale est trop faible et ne fournit pas suffisamment de données pour en tirer des enseignements.
1. **[!UICONTROL 1 DAY REAL TIME POPULATION]**: Nombre de réalisations de segment pour chaque personne, au cours des dernières 24 heures.
1. **[!UICONTROL 1 DAY REAL TIME POPULATION %]**: Pourcentage de réalisations de segments pour chaque personne, au cours des 24 dernières heures, sur la population totale du modèle.

## Caractéristiques influentes{#influential-traits}

[!UICONTROL Influential Traits] sont des caractéristiques que l’ [!UICONTROL Predictive Audiences] algorithme a découvert comme étant les plus puissants prédicteurs pour déterminer la classification personnelle d’un.

Leur signe indique si la présence de la caractéristique augmente (+) ou diminue (-) la probabilité que l’utilisateur appartienne à la personne sélectionnée.

Pour  les traits d’influence de tous vos personnages, cliquez sur [!UICONTROL View All Influential Traits].

La [!UICONTROL Influential Traits] fenêtre affiche les informations suivantes, pour chaque personne du modèle sélectionné :

![influence-traits](assets/predictive-audiences-influential-traits.png)

1. **[!UICONTROL TRAIT ID]**: l&#39;identifiant de caractéristique de chaque caractéristique influente pour la personne sélectionnée;
1. **[!UICONTROL NAME]**: le nom de chaque caractéristique influente pour la personne sélectionnée;
1. **[!UICONTROL DESCRIPTION]**: la description de chaque caractéristique influente pour la personne sélectionnée;
1. **[!UICONTROL WEIGHT]**: le  de chaque caractéristique influente pour la personne sélectionnée. [!UICONTROL Influential Traits] sont triées par défaut par , dans l’ordre décroissant.  La valeur du  indique leur puissance prédictive. Le signe indique si la présence du trait augmente (+) ou diminue (-) la probabilité d’appartenance à une personne.
1. **[!UICONTROL 30 DAY REAL TIME POPULATION]**: nombre de réalisations de caractéristiques uniques pour chaque caractéristique influente pour la personne sélectionnée, au cours des 30 derniers jours.
