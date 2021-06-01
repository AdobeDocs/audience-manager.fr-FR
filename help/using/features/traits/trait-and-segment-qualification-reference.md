---
description: La qualification des caractéristiques, ou la réalisation d’une caractéristique, est traitée différemment en Audience Manager, selon le type de caractéristique. Consultez le tableau ci-dessous pour plus d’informations sur la qualification des caractéristiques.
keywords: Qualification des caractéristiques,Réalisation des caractéristiques,Réalisations de caractéristiques uniques,UTR,Population totale des caractéristiques,TTP
seo-description: La qualification des caractéristiques, ou la réalisation d’une caractéristique, est traitée différemment en Audience Manager, selon le type de caractéristique. Consultez le tableau ci-dessous pour plus d’informations sur la qualification des caractéristiques.
seo-title: Référence de qualification des traits
solution: Audience Manager
title: Référence de qualification des traits
uuid: 07e0a639-2fb2-45d8-bad7-10fb46b08ba9
feature: 'Caractéristiques '
exl-id: 223f5fc6-c939-4bc6-94a3-5d953abc601a
source-git-commit: c844ce5ed85e9071227df67b5b20e6ee674408be
workflow-type: tm+mt
source-wordcount: '838'
ht-degree: 2%

---

# Référence de qualification des caractéristiques et des segments {#trait-qualification-reference}

La qualification des caractéristiques, ou la réalisation d’une caractéristique, est traitée différemment en Audience Manager, selon le type de caractéristique. Voir [Qualification des caractéristiques par type de caractéristique](#trait-type) pour plus d’informations sur la qualification des types de caractéristiques.

Voir également [Population des segments en temps réel et Population totale des segments](#real-time-segment) pour plus d’informations sur la qualification des segments.



## Qualification des caractéristiques par type de caractéristique {#trait-type}

| Type de caractéristique | Critères de qualification |
|---|---|
| Caractéristiques basées sur des règles | La qualification des caractéristiques se produit en temps réel, car les utilisateurs remplissent les critères d’une caractéristique dans leur navigateur. Vos utilisateurs commenceront à se qualifier pour une caractéristique basée sur des règles environ 4 heures après avoir [créé la caractéristique](create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) dans l’interface utilisateur. Les caractéristiques basées sur des règles vous permettent d’utiliser des contrôles [récence et fréquence](../segments/recency-and-frequency.md) pour la limitation de la fréquence des publicités et d’autres cas d’utilisation. |
| Caractéristiques intégrées | La qualification des caractéristiques se produit après le traitement d’un fichier entrant, c’est-à-dire que le fichier entrant est [importé dans l’Audience Manager](../../faq/faq-inbound-data-ingestion.md) et c’est lorsque la qualification des caractéristiques se produit. Patientez environ 4 heures après la création d’une caractéristique intégrée avant de charger un fichier entrant en vue de son traitement. Pour les caractéristiques intégrées, le nombre maximal de qualifications pour un profil utilisateur est 1. |
| Caractéristiques algorithmiques | Pour les caractéristiques algorithmiques, le nombre maximal de qualifications pour un profil utilisateur est 1. |
| Caractéristiques du dossier | Une caractéristique de dossier récapitule les qualifications de caractéristiques des caractéristiques qu’elle contient. Lire [Caractéristiques du dossier : À propos de ](about-folder-traits.md) pour plus d’informations. |
| Caractéristiques d’audience active et caractéristiques synchronisées de sources de données | Une caractéristique [!UICONTROL Active Audience] contient tous les appareils gérés dans votre compte d’Audience Manager. [!UICONTROL Data Source Synced Traits] effectuer le suivi de tous les utilisateurs associés à une source de données ; En savoir plus sur [Principales caractéristiques d’audience et caractéristiques synchronisées de source de données](client-activity-synced-audience-traits.md). |

## Réalisations de caractéristiques uniques et population totale de caractéristiques {#unique-trait-realizations}

![unique-caractéristique-réalisation](assets/trait-graph.png)

En fonction du type de résultats que le graphique doit afficher (filtré par [!UICONTROL Device ID] ou [!UICONTROL Cross-Device ID]), les mesures ont des significations différentes :

Lors du filtrage des résultats par [!UICONTROL Device ID] :

* [!UICONTROL Unique Trait Realizations] est le nombre de visiteurs de votre appareil anonyme qui ont ajouté la caractéristique à leur profil au cours de différentes périodes.
* [!UICONTROL Total Trait Population] est le nombre de visiteurs de votre appareil anonyme qui ont cette caractéristique sur leur profil.

Lors du filtrage des résultats par [!UICONTROL Cross-Device ID] :

* [!UICONTROL Unique Trait Realizations] est le nombre de visiteurs authentifiés qui ont ajouté la caractéristique à leur profil, au cours de différentes périodes.
* [!UICONTROL Total Trait Population] est le nombre de vos visiteurs authentifiés présentant cette caractéristique sur leur profil.

Pensez aux chiffres de cette façon. Dans l’image ci-dessus, dans la vue [Détails des caractéristiques](../../features/traits/trait-details-page.md), 90 173 représente le nombre d’appareils principaux qui ont visité vos propriétés hier. La valeur [!UICONTROL Total Trait Population] de 55 757 représente le nombre d’utilisateurs actuellement qualifiés pour cette caractéristique. La valeur [!UICONTROL Total Trait Population] est destinée à indiquer le nombre total d’utilisateurs pouvant être utilisés pour la segmentation/le ciblage. En règle générale, les utilisateurs font toujours partie d’une caractéristique pendant 120 jours.

Comme nous exécutons deux tâches computationnelles différentes pour calculer les deux populations, [!UICONTROL Total Trait Population] est toujours en retard par rapport à [!UICONTROL Unique Trait Realizations] de 24 heures. Dans le graphique ci-dessus, vous pouvez voir environ 90 400 [!UICONTROL Unique Trait Realizations] et une [!UICONTROL Total Trait Population] d’environ 90 300 pour le 5 février. Les 90 400 profils sont ajoutés à la [!UICONTROL Total Trait Population] le jour suivant.

Pour enfoncer le clou à la maison, si vous rencontrez un pic de 10 000 visiteurs en ce moment, ils apparaîtront dans le [!UICONTROL Unique Trait Realizations] de demain, mais seulement 24 heures plus tard dans le [!UICONTROL Total Trait Population].

Tout changement dans les réalisations de caractéristiques se reflète dans les populations de segments.

## Population des segments en temps réel et population totale des segments {#real-time-segment}

![unique-caractéristique-réalisation](assets/segment-graph.png)

[!UICONTROL Real-time Segment Population] comptabilise le nombre d’appareils qualifiés pour le segment sélectionné et ayant atteint vos propriétés, dans l’intervalle de temps sélectionné.

[!UICONTROL Total Segment Population] comptabilise le nombre d’appareils qualifiés pour le segment sélectionné au cours de la période sélectionnée. Le rapport [!UICONTROL 1 Day] représente le nombre de populations de segments le plus récent.

Pensez aux chiffres de cette façon. Dans l’image ci-dessus, à partir de la vue [Détails du segment](../../features/segments/segment-summary-view.md), 9 993 représente le nombre d’appareils principaux, qui ont visité vos propriétés hier et ont rempli les critères du segment. La valeur [!UICONTROL Total Segment Population] de 699 532 représente le nombre total d’appareils actuellement qualifiés pour ce segment. La valeur [!UICONTROL Total Segment Population] est destinée à indiquer le nombre total d’appareils pouvant être utilisés pour la segmentation/le ciblage.

Comme nous exécutons deux tâches computationnelles différentes pour calculer les deux populations, [!UICONTROL Total Segment Population] est toujours en retard par rapport à [!UICONTROL Real-time Segment Population] de 24 heures. Dans le graphique ci-dessus, vous pouvez voir 8 116 [!UICONTROL Real-time Segment Population] et une [!UICONTROL Total Segment Population] de 742 000 pour le 2 février. Les 8.116 profils sont ajoutés à [!UICONTROL Total Segment Population] le jour suivant.

Pour enfoncer le clou à la maison, si vous rencontrez un pic de 10 000 visiteurs en ce moment, ils apparaîtront dans le [!UICONTROL Real-time Segment Population] de demain, mais seulement 24 heures plus tard dans le [!UICONTROL Total Segment Population].

## Limite de qualification des traits {#trait-qualification-limit}

Nous appliquons une limite de 150 000 qualifications de caractéristiques pour chaque profil utilisateur, qu’il s’agisse d’un profil authentifié ([DPUUID](../../reference/ids-in-aam.md)) ou d’un identifiant d’appareil ([UUID](../../reference/ids-in-aam.md)). Notez que même si les DPUUID sont propres à une instance spécifique de [!DNL Audience Manager], les UUID sont partagés sur la plateforme [!DNL Audience Manager]. Pour les [!UICONTROL UUID]s, nous imposons une politique d’équité lors du stockage des qualifications de caractéristiques. Un algorithme garantit qu’une part égale du profil [!UICONTROL UUID] est disponible pour chaque instance de [!DNL Audience Manager].
