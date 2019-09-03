---
description: Un rapport Général renvoie des données de performances sur les caractéristiques, les segments et les destinations.
seo-description: Un rapport Général dans Audience Manager renvoie des données de performances sur les caractéristiques, les segments et les destinations.
seo-title: Rapports généraux dans Audience Manager
solution: Audience Manager
title: Rapports généraux
uuid: 0 cea 75 a 0-969 e -4 ee 3-971 a -60 b 911711 e 52
translation-type: tm+mt
source-git-commit: 1c626c770208150d209d93f666b581113ada8de9

---


# Rapports généraux{#general-reports}

Un [!UICONTROL General] rapport renvoie des données de performances sur les caractéristiques, les segments et les destinations.

## Aperçu {#general-reports-overview}

<!-- 

c_general_reports.xml

 -->

[!DNL Audience Manager] utilise [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]) pour étendre les autorisations de groupe d'utilisateurs aux [!UICONTROL General] rapports. Les utilisateurs peuvent afficher uniquement les caractéristiques et les segments dans les rapports auxquels ils sont autorisés à accéder. [!UICONTROL RBAC] vous permet de contrôler quelles données de rapport les équipes internes peuvent afficher. Par exemple, une agence qui gère différents comptes publicitaires peut configurer les autorisations des groupes d'utilisateurs de sorte qu'une équipe qui gère le compte publicitaire A ne puisse pas voir les données de rapport de l'annonceur B.

Exécutez un [!UICONTROL General] rapport lorsque vous devez :

* Examinez les performances par caractéristique, segment ou destination.
* Effectuez le suivi des impressions (total et unique) aux intervalles 1, 7, 14, 30, 60 et 90 jours.
* Examinez le nombre total et le nombre de chargements uniques.
* Comparaison des performances des segments et des caractéristiques.
* Identifiez les caractéristiques et les segments performants ou médiocres, analysez la demande ou comparez les données de charge/feu à des rapports tiers.
* Exporter des données (format. csv) pour une analyse et un partage plus poussés.

L'illustration suivante fournit une présentation générale des éléments clés du [!UICONTROL General] rapport.

![](assets/general_reports.png)

1. Configurez les options suivantes :

   * **Type de rapport :** Sélectionnez le type de rapport souhaité (Caractéristique, Segment ou Destination).

   * **Pour les dates par :** Spécifiez la plage de dates du rapport.

2. Recherchez une caractéristique, un segment ou une destination par nom ou par identifiant.
3. Dans la liste des dossiers, faites glisser les caractéristiques, segments ou destinations que vous souhaitez signaler au [!UICONTROL Selections] panneau sur le côté droit.
4. Générez le rapport à afficher dans un tableau exportable.

## Run a General Report {#run-general-report}

Cette section décrit l'exécution d'un [!UICONTROL General] rapport et la définition de l'heure et d'autres options de performances.

<!-- 

t_run_general_report.xml

 -->

1. Dans **[!UICONTROL Analytics]** le tableau de bord, cliquez **[!UICONTROL General Reports]** sur.
1. Dans la liste **[!UICONTROL Report Type]** déroulante, sélectionnez le type de votre choix : Caractéristique, Segment ou Destination.
1. *Conditionnel* Cliquez sur la zone de date pour afficher un calendrier, puis sélectionnez la date de fin de votre rapport si vous souhaitez spécifier une date autre que aujourd'hui.
1. Recherchez une caractéristique, un segment ou une destination par nom ou par identifiant.
1. Dans la liste des dossiers, faites glisser les caractéristiques, segments ou destinations que vous souhaitez signaler au [!UICONTROL Selections] panneau sur le côté droit.
1. Cliquez sur **[!UICONTROL Run Report]**.

   Les résultats s'affichent dans un tableau exportable. Cliquez sur les en-têtes de colonne pour trier les résultats par ordre croissant ou décroissant.
1. Sélectionnez le bouton d'option de votre choix dans la partie supérieure du rapport pour filtrer les données par performance ( [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations]ou [!UICONTROL Total Trait Population]) ou par heure (1, 7, 14, 30, 60 ou 90 jours).

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] sont calculés [!UICONTROL Rule-based Traits] uniquement.

1. *Clic facultatif***[!UICONTROL Export to CSV]**. Cette opération exporte le [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations]et [!UICONTROL Total Trait Population] pour toutes les plages de dates.

## Résultats généraux des rapports généraux {#general-reports-explained}

Les nombres du rapport [!UICONTROL General Reports] sont générés directement à partir de [!UICONTROL User Profile Store]notre. Les résultats reflètent le nombre d'utilisateurs qui se sont [!DNL Audience Manager] contenus dans le serveur principal au moment de la génération de ces numéros de rapports.

* Ces nombres n'incluent pas les ID de visiteur avec un trafic excessif. Le trafic provenant de robots est filtré avant d'atteindre notre système principal. En outre, le trafic de robots est ignoré lors d'une tâche de nettoyage hebdomadaire dans le serveur principal.
* Si les données au fil du temps par le biais du traitement entrant ont masqué l' [!DNL Audience Manager] UUID et que ces identifiants incluent des utilisateurs qui ne sont plus actifs dans notre système, ces identifiants UUID inactifs [!DNL Audience Manager] n'atteignent jamais la [!UICONTROL User Profile Store] valeur et ne sont pas signalés.
* [!UICONTROL Total Trait Realizations] sont calculés [!UICONTROL Rule-based Traits] uniquement.

## Résultats généraux des rapports pour les caractéristiques {#general-report-results-traits}

Les mesures ci-dessous sont disponibles lorsque vous exécutez un rapport Général et que vous sélectionnez **[!UICONTROL Trait]** le type de rapport :

**Realizations de caractéristiques uniques**

Cette mesure représente le nombre unique d'utilisateurs uniques [Audience Manager - ID (UUID)](../reference/ids-in-aam.md) qui remplissent les critères de la caractéristique dans la période sélectionnée. Par exemple, si un utilisateur se rend trois fois sur votre page d'accueil sur la 1 ère page, vous verrez une réalisation de caractéristique unique.

**Realizations de caractéristiques totales**

Cette mesure représente la quantité totale de caractéristiques déclenchées pour la caractéristique dans la période sélectionnée. Par exemple, si un utilisateur a visité votre page d'accueil, puis a navigué vers vos actualités techniques et vos nouvelles sections de sports, elles apparaissent dans le rapport général sous la forme de trois realizations de caractéristiques totales et d'une concrétisation unique.

**Population totale de caractéristiques**

Cette mesure représente la quantité totale des UUID Audience Manager actuellement qualifiés pour la caractéristique. Utilisez ce nombre pour comprendre le nombre total d'utilisateurs que vous pouvez utiliser pour la segmentation et le ciblage. En règle générale, les utilisateurs restent dans une caractéristique pendant [120 jours](../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval). Par exemple, un utilisateur qui consulte votre page d'accueil trois fois aujourd'hui et qui ne revient jamais après, restera comme un utilisateur dans cette population tous les jours jusqu'à 120 jours. Au bout de 120 jours, elles seront supprimées de la population. Consultez notre [référence de qualification des caractéristiques](../features/traits/trait-qualification-reference.md) pour en savoir plus sur la différence entre les realizations de caractéristiques uniques et la population totale de caractéristiques.

L'illustration ci-dessous montre les résultats d'exécution d'un rapport général pour le type de rapport Caractéristique.

![](assets/general_reports_metrics.png)

## Résultats généraux des rapports pour les segments {#general-report-results-segments}

Les mesures ci-dessous sont disponibles lorsque vous exécutez un rapport Général et que vous sélectionnez **[!UICONTROL Segment]** le type de rapport :

**Population de segments en temps réel**

Cette mesure représente le nombre réel de visiteurs uniques vus en temps réel pour la période spécifiée et qui ont été qualifiés pour le segment au moment où ils ont été vus par Audience Manager.

**Population totale de segments**

Cette mesure représente le nombre total d'UUID Audience Manager qui sont qualifiés pour le segment au cours de la période de recherche que vous avez sélectionnée. Votre population de segment total 1 jour représente la base d'utilisateurs la plus précise pour le ciblage.

>[!NOTE]
>
>Sélectionnez **[!UICONTROL Include Destination Mappings]** une ventilation de la population de segments pour les destinations activées.

L'illustration ci-dessous montre les résultats d'exécution d'un rapport général pour le type de rapport Segment.

![](assets/general_reports_segment_metrics.png)

## Résultats généraux des rapports pour les destinations {#general-report-results-destinations}

Les mesures ci-dessous sont disponibles lorsque vous exécutez un rapport Général et que vous sélectionnez **[!UICONTROL Destination]** le type de rapport :

**Population de segments en temps réel**

Cette mesure représente le nombre réel de visiteurs uniques vus en temps réel pour la période spécifiée et qui ont été qualifiés pour le segment au moment où ils ont été vus par Audience Manager.

**Population totale de segments**

Cette mesure représente le nombre total d'UUID Audience Manager appartenant à un segment dans la période de recherche, qui ont été envoyés à une destination.

L'illustration ci-dessous montre les résultats d'exécution d'un rapport général pour le type de rapport Destinations.

![](assets/general_reports_destinations.png)
