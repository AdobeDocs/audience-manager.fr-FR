---
description: La qualification de la caractéristique, ou réalisation de la caractéristique, est traitée différemment dans Audience Manager, selon le type de caractéristique. Consultez le tableau ci-dessous pour obtenir des informations détaillées sur la qualification des caractéristiques.
keywords: Qualification des caractéristiques, Réalisation des caractéristiques, Réalisations des caractéristiques uniques, UTR, Population totale des caractéristiques, TTP
seo-description: Trait qualification, or trait realization, is treated differently in Audience Manager, depending on trait type. See the table below for detailed information on trait qualification.
seo-title: Trait Qualification Reference
solution: Audience Manager
title: Référence de qualification de caractéristique
uuid: 07e0a639-2fb2-45d8-bad7-10fb46b08ba9
feature: Traits
exl-id: 223f5fc6-c939-4bc6-94a3-5d953abc601a
source-git-commit: c844ce5ed85e9071227df67b5b20e6ee674408be
workflow-type: tm+mt
source-wordcount: '826'
ht-degree: 0%

---

# Référence de qualification des caractéristiques et des segments {#trait-qualification-reference}

La qualification de la caractéristique, ou réalisation de la caractéristique, est traitée différemment dans Audience Manager, selon le type de caractéristique. Voir [Qualification des caractéristiques par type de caractéristique](#trait-type) pour plus d’informations sur la qualification des types de caractéristique.

En outre, consultez [Population de segments en temps réel et Population totale de segments](#real-time-segment) pour plus d’informations sur la qualification du segment.



## Qualification des caractéristiques par type de caractéristique {#trait-type}

| Type de caractéristique | Critères de qualification |
|---|---|
| Caractéristiques basées sur des règles | La qualification de caractéristique se produit en temps réel, car les utilisateurs remplissent les critères d’une caractéristique dans leur navigateur. Vos utilisateurs commenceront à se qualifier pour une caractéristique basée sur des règles environ 4 heures après que vous [avez créé la caractéristique](create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) dans l’interface utilisateur. Les caractéristiques basées sur des règles vous permettent d’utiliser des contrôles [récence et fréquence](../segments/recency-and-frequency.md) pour le capping de la fréquence des publicités et d’autres cas d’utilisation. |
| Caractéristiques intégrées | La qualification de caractéristique se produit une fois qu’un fichier entrant est traité, c’est-à-dire que le fichier entrant est [importé dans Audience Manager](../../faq/faq-inbound-data-ingestion.md) et c’est à ce moment que la qualification de caractéristique se produit. Vous devez attendre environ 4 heures après la création d’une caractéristique intégrée avant de charger un fichier entrant pour traitement. Pour les caractéristiques intégrées, le nombre maximal de qualifications pour un profil utilisateur est de 1. |
| Caractéristiques algorithmiques | Pour les caractéristiques algorithmiques, le nombre maximal de qualifications pour un profil utilisateur est de 1. |
| Caractéristiques du dossier | Une caractéristique de dossier résume les qualifications des caractéristiques qu’elle contient. Lisez [Caractéristiques du dossier : À propos](about-folder-traits.md) pour plus d’informations. |
| Caractéristiques d’audience actives et caractéristiques synchronisées de Data Source | Une caractéristique [!UICONTROL Active Audience] contient tous les appareils gérés dans votre compte Audience Manager. [!UICONTROL Data Source Synced Traits] tous les utilisateurs associés à une source de données. En savoir plus sur [Caractéristiques d’audience actives et Caractéristiques synchronisées de Data Source](client-activity-synced-audience-traits.md). |

## Réalisations des caractéristiques uniques et population totale des caractéristiques {#unique-trait-realizations}

![réalisation-caractéristique-unique](assets/trait-graph.png)

La signification des mesures varie en fonction du type de résultats que le graphique doit afficher (filtrés par [!UICONTROL Device ID] ou [!UICONTROL Cross-Device ID]) :

Lors du filtrage des résultats par [!UICONTROL Device ID] :

* [!UICONTROL Unique Trait Realizations] est le nombre de visiteurs anonymes de votre appareil qui ont ajouté la caractéristique à leur profil au cours de différentes périodes.
* [!UICONTROL Total Trait Population] est le nombre de visiteurs anonymes de votre appareil qui ont cette caractéristique sur leur profil.

Lors du filtrage des résultats par [!UICONTROL Cross-Device ID] :

* [!UICONTROL Unique Trait Realizations] est le nombre de vos visiteurs authentifiés qui ont ajouté la caractéristique à leur profil, dans différentes périodes.
* [!UICONTROL Total Trait Population] est le nombre de vos visiteurs authentifiés qui ont cette caractéristique sur leur profil.

Pensez aux chiffres de cette façon. Dans l’image ci-dessus, dans la vue [Détails des caractéristiques](../../features/traits/trait-details-page.md), 90 173 représente le nombre d’appareils actifs qui ont visité vos propriétés hier. Le [!UICONTROL Total Trait Population] de 55 757 représente le nombre d’utilisateurs actuellement qualifiés pour cette caractéristique. La figure [!UICONTROL Total Trait Population] est destinée à montrer le nombre total d’utilisateurs qui peuvent être utilisés pour la segmentation/le ciblage. En règle générale, les utilisateurs et utilisatrices restent dans une caractéristique pendant 120 jours.

Comme nous exécutons deux traitements informatiques différents pour calculer les deux populations, le [!UICONTROL Total Trait Population] est toujours en retard de 24 heures par rapport au [!UICONTROL Unique Trait Realizations]. Dans le graphique ci-dessus, vous pouvez voir environ 90 400 [!UICONTROL Unique Trait Realizations] et une [!UICONTROL Total Trait Population] d’environ 90 300 pour le 5 février. Les 90 400 profils sont ajoutés à la [!UICONTROL Total Trait Population] le jour suivant.

Pour enfoncer le clou, si vous avez connu un pic de 10 000 visiteurs en ce moment, ils se présenteraient dans les [!UICONTROL Unique Trait Realizations] de demain, mais ils ne se présenteraient que 24 heures plus tard dans la [!UICONTROL Total Trait Population].

Toute modification des réalisations de caractéristiques se reflète dans les populations de segments.

## Population de segments en temps réel et Population totale de segments {#real-time-segment}

![réalisation-caractéristique-unique](assets/segment-graph.png)

Le [!UICONTROL Real-time Segment Population] compte le nombre d’appareils qui se sont qualifiés pour le segment sélectionné et qui ont atteint vos propriétés, dans l’intervalle de temps sélectionné.

Le [!UICONTROL Total Segment Population] compte le nombre d’appareils qualifiés pour le segment sélectionné au cours de la période sélectionnée. Le rapport [!UICONTROL 1 Day] représente le nombre de segments le plus récent.

Pensez aux chiffres de cette façon. Dans l’image ci-dessus, dans la vue [Détails du segment](../../features/segments/segment-summary-view.md), 9 993 représente le nombre d’appareils actifs, ayant visité vos propriétés hier et qualifiés pour le segment. Le [!UICONTROL Total Segment Population] de 699 532 représente le nombre total d’appareils actuellement qualifiés pour ce segment. La figure [!UICONTROL Total Segment Population] est destinée à afficher le nombre total d’appareils qui peuvent être utilisés pour la segmentation/le ciblage.

Comme nous exécutons deux traitements informatiques différents pour calculer les deux populations, le [!UICONTROL Total Segment Population] est toujours en retard de 24 heures par rapport au [!UICONTROL Real-time Segment Population]. Dans le graphique ci-dessus, vous pouvez voir un [!UICONTROL Real-time Segment Population] de 8 116 et un [!UICONTROL Total Segment Population] de 742 000 pour le 2 février. Les 8 116 profils sont ajoutés au [!UICONTROL Total Segment Population] le jour suivant.

Pour enfoncer le clou, si vous avez connu un pic de 10 000 visiteurs en ce moment, ils se présenteraient dans les [!UICONTROL Real-time Segment Population] de demain, mais ils ne se présenteraient que 24 heures plus tard dans la [!UICONTROL Total Segment Population].

## Limite de qualification des caractéristiques {#trait-qualification-limit}

Nous imposons une limite de 150 000 qualifications de caractéristique pour chaque profil utilisateur, qu’il s’agisse d’un profil authentifié ([DPUUID](../../reference/ids-in-aam.md)) ou d’un identifiant d’appareil ([UUID](../../reference/ids-in-aam.md)). Notez que les DPUUID sont propres à une instance spécifique de [!DNL Audience Manager], mais les UUID sont partagés sur l’ensemble de la plateforme [!DNL Audience Manager]. Pour les [!UICONTROL UUID], nous imposons une politique d&#39;équité lors du stockage des caractéristiques. Un algorithme garantit qu’une part égale du profil [!UICONTROL UUID] est disponible pour chaque instance de [!DNL Audience Manager].
