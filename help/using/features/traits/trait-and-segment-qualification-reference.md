---
description: La qualification des caractéristiques, ou réalisation des caractéristiques, est traitée différemment en Audience Manager, selon le type de caractéristique. Consultez le tableau ci-dessous pour obtenir des informations détaillées sur la qualification des caractéristiques.
keywords: trait qualification;trait realization;Unique Trait Realizations;UTR;Total Trait Population;TTP
seo-description: La qualification des caractéristiques, ou réalisation des caractéristiques, est traitée différemment en Audience Manager, selon le type de caractéristique. Consultez le tableau ci-dessous pour obtenir des informations détaillées sur la qualification des caractéristiques.
seo-title: Référence de qualification des traits
solution: Audience Manager
title: Référence de qualification des traits
uuid: 07e0a639-2fb2-45d8-bad7-10fb46b08ba9
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '825'
ht-degree: 2%

---


# Référence de qualification des caractéristiques et des segments {#trait-qualification-reference}

La qualification des caractéristiques, ou réalisation des caractéristiques, est traitée différemment en Audience Manager, selon le type de caractéristique. Voir Qualification des [caractéristiques par type](#trait-type) de caractéristique pour plus d’informations sur la qualification de type de caractéristique.

De plus, voir Population des segments en temps [réel et Population](#real-time-segment) totale des segments pour plus d’informations sur la qualification des segments.



## Qualification de caractéristiques par type de caractéristiques {#trait-type}

| Type de caractéristique | Critères de qualification |
|---|---|
| Caractéristiques basées sur des règles | La qualification des caractéristiques se produit en temps réel, dans la mesure où les utilisateurs remplissent les critères d’une caractéristique dans leur navigateur. Les utilisateurs débuts bénéficier d’une caractéristique basée sur des règles environ 4 heures après avoir [créé la caractéristique](create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) dans l’interface utilisateur. Les caractéristiques basées sur des règles vous permettent d’utiliser des contrôles de [récence et de fréquence](../segments/recency-and-frequency.md) pour le plafonnement de la fréquence des annonces et d’autres cas d’utilisation. |
| Caractéristiques intégrées | La qualification des caractéristiques se produit après le traitement d&#39;un fichier entrant, c&#39;est-à-dire que le fichier entrant est [importé dans l&#39;Audience Manager](../../faq/faq-inbound-data-ingestion.md) et c&#39;est-à-dire lorsque la qualification des caractéristiques se produit. Attendez environ 4 heures après avoir créé une caractéristique intégrée avant de télécharger un fichier entrant en vue de son traitement. Pour les caractéristiques embarquées, le nombre maximal de qualifications pour un profil utilisateur est 1. |
| Caractéristiques algorithmiques | Pour les caractéristiques algorithmiques, le nombre maximal de qualifications pour un profil utilisateur est 1. |
| Caractéristiques des dossiers | Une caractéristique de dossier résume les qualités des caractéristiques qu&#39;elle contient. Caractéristiques [des dossiers de lecture : À propos](about-folder-traits.md) de. |
| Caractéristiques d’audience active et caractéristiques synchronisées de sources de données | Une [!UICONTROL Active Audience] caractéristique contient tous les périphériques gérés dans votre compte d’Audience Manager. [!UICONTROL Data Source Synced Traits] effectuez le suivi de tous les utilisateurs associés à une source de données. En savoir plus sur les caractéristiques d’Audience [active et les caractéristiques](client-activity-synced-audience-traits.md)synchronisées de source de données. |

## Valorisation des caractéristiques uniques et population totale des caractéristiques {#unique-trait-realizations}

![réalisation de caractéristiques uniques](assets/trait-graph.png)

Selon le type de résultats que vous souhaitez afficher sur le graphique (filtré par [!UICONTROL Device ID] ou [!UICONTROL Cross-Device ID]), les mesures ont des significations différentes :

Lors du filtrage des résultats par [!UICONTROL Device ID]:

* [!UICONTROL Unique Trait Realizations] est le nombre de visiteurs anonymes de votre périphérique qui ont ajouté la caractéristique à leur profil dans différentes plages de temps.
* [!UICONTROL Total Trait Population] est le nombre de visiteurs anonymes de votre périphérique qui ont cette caractéristique sur leur profil.

Lors du filtrage des résultats par [!UICONTROL Cross-Device ID]:

* [!UICONTROL Unique Trait Realizations] est le nombre de vos visiteurs authentifiés qui ont ajouté la caractéristique à leur profil, dans des plages de temps différentes.
* [!UICONTROL Total Trait Population] est le nombre de vos visiteurs authentifiés qui ont cette caractéristique sur leur profil.

Pensez aux chiffres de cette façon. Dans l’image ci-dessus, à partir de la vue Détails [de la](../../features/traits/trait-details-page.md) Caractéristique, 90 173 représente le nombre de périphériques actifs qui ont visité vos propriétés hier. Le nombre [!UICONTROL Total Trait Population] de 55 757 correspond au nombre d’utilisateurs actuellement qualifiés pour cette caractéristique. Ce [!UICONTROL Total Trait Population] chiffre indique le nombre total d’utilisateurs pouvant être utilisés pour la segmentation/le ciblage. En règle générale, les utilisateurs restent une caractéristique pendant 120 jours.

Parce que nous exécutons deux emplois de calcul différents pour calculer les deux populations, le [!UICONTROL Total Trait Population] devance toujours le [!UICONTROL Unique Trait Realizations] de 24 heures. Dans le graphique ci-dessus, vous pouvez voir environ 90 400 [!UICONTROL Unique Trait Realizations] et un [!UICONTROL Total Trait Population] d&#39;environ 90 300 pour le 5 février. Les 90 400 profils sont ajoutés au [!UICONTROL Total Trait Population] jour suivant.

Pour enfoncer le clou, si vous avez connu un pic de 10 000 visiteurs en ce moment, ils apparaîtraient dans le match de demain [!UICONTROL Unique Trait Realizations], mais n&#39;apparaîtraient que 24 heures plus tard dans le [!UICONTROL Total Trait Population]match.

Tout changement dans les créations de caractéristiques se répercute dans les populations de segments.

## Population des segments en temps réel et population totale des segments {#real-time-segment}

![réalisation de caractéristiques uniques](assets/segment-graph.png)

Le [!UICONTROL Real-time Segment Population] compte le nombre de périphériques qui se sont qualifiés pour le segment sélectionné et ont atteint vos propriétés, dans l’intervalle de temps sélectionné.

Le [!UICONTROL Total Segment Population] compte le nombre de périphériques qui se sont qualifiés pour le segment sélectionné au cours de la période sélectionnée. Le [!UICONTROL 1 Day] rapport représente le décompte de population de segments le plus récent.

Pensez aux chiffres de cette façon. Dans l’image ci-dessus, à partir de la vue Détails [du](../../features/segments/segment-summary-view.md) segment, 9 993 représente le nombre de périphériques actifs, qui ont visité vos propriétés hier et se sont qualifiés pour le segment. Le nombre [!UICONTROL Total Segment Population] de 699 532 correspond au nombre total de périphériques actuellement qualifiés pour ce segment. La [!UICONTROL Total Segment Population] figure indique le nombre total de périphériques pouvant être utilisés pour la segmentation/le ciblage.

Parce que nous exécutons deux emplois de calcul différents pour calculer les deux populations, le [!UICONTROL Total Segment Population] devance toujours le [!UICONTROL Real-time Segment Population] de 24 heures. Dans le graphique ci-dessus, vous pouvez voir un 8 116 [!UICONTROL Real-time Segment Population] et un [!UICONTROL Total Segment Population] de 742 000 pour le 2 février. Les 8 116 profils sont ajoutés au [!UICONTROL Total Segment Population] jour suivant.

Pour enfoncer le clou, si vous avez connu un pic de 10 000 visiteurs en ce moment, ils apparaîtraient dans le match de demain [!UICONTROL Real-time Segment Population], mais n&#39;apparaîtraient que 24 heures plus tard dans le [!UICONTROL Total Segment Population]match.

## Limite de qualification des caractéristiques {#trait-qualification-limit}

Nous appliquons une limite de 150 000 qualifications de caractéristiques pour chaque profil utilisateur, qu’il s’agisse d’un profil authentifié ([DPUUID](../../reference/ids-in-aam.md)) ou d’un ID de périphérique ([UUID](../../reference/ids-in-aam.md)). Notez que si les DPUUID sont propres à une instance spécifique de [!DNL Audience Manager], les UUID sont partagés sur la [!DNL Audience Manager] plate-forme. Pour [!UICONTROL UUID]nous, nous imposons une politique d&#39;équité dans le stockage des qualifications relatives aux caractéristiques. Un algorithme garantit qu’une part égale du [!UICONTROL UUID] profil est rendue disponible pour chaque instance de [!DNL Audience Manager].

