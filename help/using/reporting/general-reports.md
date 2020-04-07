---
description: Un rapport Général renvoie des données de performances sur les caractéristiques, les segments et les destinations.
seo-description: Un rapport Général dans  Gestionnaire de  de renvoie des données de performances sur les caractéristiques, les segments et les destinations.
seo-title: Rapports généraux dans  Gestionnaire  de
solution: Audience Manager
title: Rapports généraux
uuid: 0cea75a0-969e-4ee3-971a-60b911711e52
translation-type: tm+mt
source-git-commit: 8493705b0f200b5b43d937dfd452210403a52b33

---


# Rapports généraux{#general-reports}

Un [!UICONTROL General] rapport renvoie des données de performances sur les caractéristiques, les segments et les destinations.

## Aperçu {#general-reports-overview}

<!-- 

c_general_reports.xml

 -->

[!DNL Audience Manager] utilise [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]) pour étendre les autorisations des groupes d’utilisateurs aux [!UICONTROL General] rapports. Les utilisateurs ne peuvent voir que les caractéristiques et les segments dans le  qu’ils ont les autorisations d’ de. [!UICONTROL RBAC] permet de contrôler les  de données que les équipes internes sont en mesure de . Par exemple, une agence qui gère différents comptes d’annonceurs peut configurer des autorisations de groupe d’utilisateurs afin qu’une équipe qui gère le compte de l’annonceur A ne puisse pas voir les données  de l’annonceur B.

Exécutez un [!UICONTROL General] rapport lorsque vous devez :

* Examinez les performances par caractéristique, segment ou destination.
* Effectuez le suivi des impressions (totales et uniques) à des intervalles de 1, 7, 14, 30, 60 et 90 jours.
* Examinez le nombre total et unique de charges.
* Comparer les performances des caractéristiques et des segments.
* Identifiez les caractéristiques de performances et les segments forts ou médiocres, analysez la demande ou comparez les données de charge/feu aux rapports tiers.
* Exportez les données (format .csv) pour  plus de  et de partage.

L’illustration suivante présente un aperçu général des éléments clés du [!UICONTROL General] rapport.

![](assets/general_reports.png)

1. Configurez les options suivantes :

   * **Type de rapport :** Sélectionnez le type de rapport souhaité (Caractéristique, Segment ou Destination).

   * **Pour les dates de passage à :** Spécifiez la plage de dates du rapport.

2. Recherchez une caractéristique, un segment ou une destination par nom ou ID.
3. A partir du  du dossier, faites glisser et déposez les caractéristiques, segments ou destinations que vous souhaitez rapporter dans le [!UICONTROL Selections] panneau de droite.
4. Générez le rapport à afficher dans un tableau exportable.

## Run a General Report {#run-general-report}

Cette section décrit comment exécuter un [!UICONTROL General] rapport et définir l’heure et d’autres options de performances.

<!-- 

t_run_general_report.xml

 -->

1. Dans le **[!UICONTROL Analytics]** , cliquez sur **[!UICONTROL General Reports]**.
1. Dans le  **[!UICONTROL Report Type]** déroulant, sélectionnez le type de votre choix : Caractéristique, segment ou destination.
1. *Conditionnel* Cliquez sur la zone de date pour afficher un calendrier, puis sélectionnez la date de fin de votre rapport si vous souhaitez spécifier une date autre qu&#39;aujourd&#39;hui.
1. Recherchez une caractéristique, un segment ou une destination par nom ou ID.
1. A partir du  du dossier, faites glisser et déposez les caractéristiques, segments ou destinations que vous souhaitez rapporter dans le [!UICONTROL Selections] panneau de droite.
1. Cliquez sur **[!UICONTROL Run Report]**.

   Les résultats s’affichent dans un tableau exportable. Cliquez sur les en-têtes de colonne pour trier les résultats par ordre croissant ou décroissant.
1. Sélectionnez le bouton d’option de votre choix en haut du rapport pour filtrer les données par performances ( [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations]ou [!UICONTROL Total Trait Population]) ou par heure (1, 7, 14, 30, 60 ou période de 90 jours).

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] sont calculées pour [!UICONTROL Rule-based Traits] uniquement.

1. *Facultatif* Cliquez **[!UICONTROL Export to CSV]**. Cette option exporte les données [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations]et [!UICONTROL Total Trait Population] pour toutes les plages de jours.

## Rapports généraux Explication des résultats {#general-reports-explained}

Les nombres dans le [!UICONTROL General Reports] sont générés directement à partir de notre [!UICONTROL User Profile Store]. Les résultats reflètent le nombre d’utilisateurs [!DNL Audience Manager] contenus dans le serveur principal au moment de la génération de ces numéros de.

* Ces nombres n’incluent pas les ID de avec un trafic excessif. Le trafic des robots est filtré avant d&#39;atteindre notre système principal. En outre, un certain trafic de robots est ignoré lors de l’exécution d’une tâche de nettoyage hebdomadaire dans le serveur principal.
* Si vous embarquez des données via un traitement entrant en dehors de l’ [!DNL Audience Manager] UUID et que ces ID incluent des utilisateurs qui ne sont plus actifs dans notre système, ces [!DNL Audience Manager] UUID inactifs n’atteignent jamais l’UUID [!UICONTROL User Profile Store] et ne sont pas signalés.
* [!UICONTROL Total Trait Realizations] sont calculées pour [!UICONTROL Rule-based Traits] uniquement.

## Rapports généraux Résultats pour les caractéristiques {#general-report-results-traits}

Les mesures ci-dessous sont disponibles lorsque vous exécutez un rapport Général et que vous sélectionnez **[!UICONTROL Trait]** comme type de rapport :

**Valorisations de caractéristiques uniques**

Cette mesure représente le nombre unique d’ID d’utilisateur unique (UUID) [du gestionnaire de ](../reference/ids-in-aam.md) qui se sont qualifiés pour la caractéristique de la période sélectionnée. Par exemple, si un utilisateur a visité votre page d&#39;accueil trois fois le 10/1, vous verrez une réalité de caractéristiques uniques.

**Total des conversions de caractéristiques**

Cette mesure représente la quantité totale de déclenchements de caractéristiques pour la caractéristique de la période sélectionnée. Par exemple, si un utilisateur a consulté votre page d’accueil, puis accédé à vos nouvelles techniques et à vos sections d’actualités sportives, elles apparaissent dans le rapport général sous la forme de trois réalisations de caractéristiques totales et d’une réalisation de caractéristiques unique.

**Population totale des caractéristiques**

Cette mesure représente le nombre total de  UUID Gestionnaire de  qui sont actuellement qualifiés pour la caractéristique. Utilisez ce nombre pour comprendre le nombre total d’utilisateurs que vous pouvez utiliser pour la segmentation et le ciblage. En règle générale, les utilisateurs restent une caractéristique pendant [120 jours](../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval). Par exemple, un utilisateur visitant votre page d&#39;accueil trois fois aujourd&#39;hui et ne revenant jamais par la suite resterait en tant qu&#39;utilisateur dans cette population tous les jours jusqu&#39;à 120 jours. À 120 jours, ils seraient retirés de la population. Lisez notre Guide de référence [](../features/traits/trait-and-segment-qualification-reference.md) sur les caractéristiques et les caractéristiques des segments pour obtenir d’autres exemples sur la différence entre les caractéristiques uniques et la population totale de caractéristiques.

L&#39;illustration ci-dessous montre les résultats de l&#39;exécution d&#39;un rapport général pour le type de rapport Caractéristiques.

![](assets/general_reports_metrics.png)

## Rapports généraux Résultats pour les segments {#general-report-results-segments}

Les mesures ci-dessous sont disponibles lorsque vous exécutez un rapport Général et que vous sélectionnez **[!UICONTROL Segment]** comme type de rapport :

**Population des segments en temps réel**

Cette mesure représente le nombre réel de uniques affichés en temps réel pendant la période spécifiée et qui étaient qualifiés pour le segment au moment où ils étaient vus par  Gestionnaire de  de.

**Population totale des segments**

Cette mesure représente le nombre total d’UUID  Gestionnaire de  qui sont qualifiés pour le segment au cours de la période de recherche précédente que vous avez sélectionnée. Votre population totale de segments de 1 jour représente votre base d’utilisateurs la plus précise pour le ciblage.

>[!NOTE]
>
>Sélectionnez cette option **[!UICONTROL Include Destination Mappings]** pour afficher la ventilation de la population de segments pour les destinations activées.

L&#39;illustration ci-dessous montre les résultats de l&#39;exécution d&#39;un rapport général pour le type de rapport Segment.

![](assets/general_reports_segment_metrics.png)

## Rapports généraux Résultats pour les destinations {#general-report-results-destinations}

Les mesures ci-dessous sont disponibles lorsque vous exécutez un rapport Général et que vous sélectionnez **[!UICONTROL Destination]** comme type de rapport :

**Population des segments en temps réel**

Cette mesure représente le nombre réel de uniques affichés en temps réel pendant la période spécifiée et qui étaient qualifiés pour le segment au moment où ils étaient vus par  Gestionnaire de  de.

**Population totale des segments**

Cette mesure représente le nombre total de  UUID du Gestionnaire de  de appartenant à un segment au cours de la période de recherche précédente, qui ont été envoyés vers une destination.

L&#39;illustration ci-dessous montre les résultats de l&#39;exécution d&#39;un rapport général pour le type de rapport Destinations.

![](assets/general_reports_destinations.png)
