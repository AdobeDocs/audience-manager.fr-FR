---
description: La qualification des caractéristiques, ou réalisation des caractéristiques, est traitée différemment dans  Gestionnaire de  de, selon le type de caractéristique. Consultez le tableau ci-dessous pour obtenir des informations détaillées sur la qualification des caractéristiques.
keywords: trait qualification;trait realization;Unique Trait Realizations;UTR;Total Trait Population;TTP
seo-description: La qualification des caractéristiques, ou réalisation des caractéristiques, est traitée différemment dans  Gestionnaire de  de, selon le type de caractéristique. Consultez le tableau ci-dessous pour obtenir des informations détaillées sur la qualification des caractéristiques.
seo-title: Référence de qualification des traits
solution: Audience Manager
title: Référence de qualification des traits
uuid: 07e0a639-2fb2-45d8-bad7-10fb46b08ba9
translation-type: tm+mt
source-git-commit: bd0ebcddc89c2141e9ce55d7fa2e68b5ca1cbb22

---


# Référence de qualification des traits {#trait-qualification-reference}

La qualification des caractéristiques, ou réalisation des caractéristiques, est traitée différemment dans  Gestionnaire de  de, selon le type de caractéristique. Consultez le tableau ci-dessous pour obtenir des informations détaillées sur la qualification des caractéristiques.

## Qualification des caractéristiques par type de caractéristiques {#trait-type}

| Type de caractéristiques | Critères de qualification |
|---|---|
| Caractéristiques basées sur des règles | La qualification des caractéristiques se produit en temps réel, car les utilisateurs remplissent les conditions requises pour obtenir une caractéristique dans leur navigateur. Vos utilisateurs  avoir droit à une caractéristique basée sur des règles environ 4 heures après avoir [créé la caractéristique](create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) dans l’interface utilisateur. Les caractéristiques basées sur des règles vous permettent d’utiliser les contrôles de [récence et de fréquence](../segments/recency-and-frequency.md) pour le plafonnement de la fréquence des annonces et d’autres cas d’utilisation. |
| Caractéristiques intégrées | La qualification des caractéristiques se produit après le traitement d’un fichier entrant, c’est-à-dire que le fichier entrant est [importé dans  Gestionnaire](../../faq/faq-inbound-data-ingestion.md) de  de, et c’est-à-dire lorsque la qualification des caractéristiques se produit. Vous devez attendre environ 4 heures après avoir créé une caractéristique intégrée avant de télécharger un fichier entrant en vue de son traitement. Pour les caractéristiques intégrées, le nombre maximal de qualifications pour un utilisateur est 1. |
| Caractéristiques algorithmiques | Pour les caractéristiques algorithmiques, le nombre maximal de qualifications pour un utilisateur est 1. |
| Caractéristiques des dossiers | Une caractéristique de dossier résume les qualités des caractéristiques qu’elle contient. Caractéristiques [des dossiers de lecture : À propos](about-folder-traits.md) de. |
| Caractéristiques actives   des et caractéristiques synchronisées de la source de données | Une [!UICONTROL Active Audience] caractéristique contient tous les périphériques sous gestion dans votre compte  Manager . [!UICONTROL Data Source Synced Traits] effectuez le suivi de tous les utilisateurs associés à une source de données. En savoir plus sur les  [actifs  caractéristiques et les caractéristiques](client-activity-synced-audience-traits.md)synchronisées des sources de données. |

## Valorisation des caractéristiques uniques et population totale des caractéristiques {#unique-trait-realizations}

![réalisation-caractéristique unique](assets/trait-graph.png)

En fonction du type de résultats que vous souhaitez afficher sur le graphique (filtrés par ID [!UICONTROL Device ID] [!UICONTORL ou ID]de plusieurs périphériques), les mesures ont des significations différentes :

Lors du filtrage des résultats par [!UICONTROL Device ID]:

* [!UICONTROL Unique Trait Realizations] est le nombre de vos de périphériques anonymes qui ont ajouté la caractéristique à leur  de diffusion au cours de différentes périodes.
* [!UICONTROL Total Trait Population] est le nombre de vos de périphériques anonymes qui ont cette caractéristique sur leur  de.

Lors du filtrage des résultats par [!UICONTROL Cross-Device ID]:

* [!UICONTROL Unique Trait Realizations] est le nombre de vos authentifiés qui ont ajouté la caractéristique à leur  de, dans des plages de temps différentes.
* [!UICONTROL Total Trait Population] est le nombre de vos authentifiés qui ont cette caractéristique sur leur  de.

Pensez aux chiffres de cette façon. Dans l’image ci-dessus, à partir du Détails [de](../../features/traits/trait-details-page.md) caractéristiques, 90 173 représente le nombre de périphériques actifs qui ont visité vos propriétés hier. La valeur [!UICONTROL Total Trait Population] de 55 757 représente le nombre d’utilisateurs actuellement qualifiés pour cette caractéristique. La [!UICONTROL Total Trait Population] figure indique le nombre total d’utilisateurs pouvant être utilisés pour la segmentation/le ciblage. En règle générale, les utilisateurs restent une caractéristique pendant 120 jours.

Parce que nous exécutons deux tâches de calcul différentes pour calculer les deux populations, le [!UICONTROL Total Trait Population] reste en retard par rapport au [!UICONTROL Unique Trait Realizations] de 24 heures. Sur le graphique ci-dessus, vous pouvez voir environ 90 400 [!UICONTROL Unique Trait Realizations] et un [!UICONTROL Total Trait Population] de 90 300 pour le 5 février. Les 90 400  sont ajoutés au [!UICONTROL Total Trait Population] jour suivant.

Pour continuer sur le point de rentrer chez vous, si vous avez connu un pic de 10 000 en ce moment, ils apparaîtraient dans celui de demain [!UICONTROL Unique Trait Realizations], mais n&#39;apparaîtraient que 24 heures plus tard dans le [!UICONTROL Total Trait Population].

Tout changement dans la réalisation des caractéristiques se reflète dans les populations de segments.

## Population des segments en temps réel et population totale des segments {#real-time-segment}

![réalisation-caractéristique unique](assets/segment-graph.png)

Le [!UICONTROL Real-time Segment Population] compte le nombre de périphériques qui se sont qualifiés pour le segment sélectionné et qui ont atteint vos propriétés, dans l’intervalle de temps sélectionné.

Le [!UICONTROL Total Segment Population] compte le nombre de périphériques qui se sont qualifiés pour le segment sélectionné au cours de la période sélectionnée. Le [!UICONTROL 1 Day] rapport représente le nombre de segments de population le plus récent.

Pensez aux chiffres de cette façon. Dans l’image ci-dessus, à partir du  Détails [du](../../features/segments/segment-summary-view.md) segment, 9 993 représente le nombre de périphériques actifs qui ont visité vos propriétés hier et sont qualifiés pour le segment. Le nombre [!UICONTROL Total Segment Population] de 699 532 correspond au nombre total de périphériques actuellement qualifiés pour ce segment. La [!UICONTROL Total Segment Population] figure indique le nombre total de périphériques pouvant être utilisés pour la segmentation/le ciblage.

Parce que nous exécutons deux tâches de calcul différentes pour calculer les deux populations, le [!UICONTROL Total Segment Population] reste en retard par rapport au [!UICONTROL Real-time Segment Population] de 24 heures. Dans le graphique ci-dessus, vous pouvez voir 8 116 [!UICONTROL Real-time Segment Population] [!UICONTROL Total Segment Population] et 742 000 pour le 2 février. Les 8 116  sont ajoutés au [!UICONTROL Total Segment Population] jour suivant.

Pour continuer sur le point de rentrer chez vous, si vous avez connu un pic de 10 000 en ce moment, ils apparaîtraient dans celui de demain [!UICONTROL Real-time Segment Population], mais n&#39;apparaîtraient que 24 heures plus tard dans le [!UICONTROL Total Segment Population].

## Limite de qualification des caractéristiques {#trait-qualification-limit}

Nous imposons une limite de 150 000 qualifications de caractéristiques pour chaque  d’utilisateur, qu’il s’agisse d’un authentifié ([DPUUID](../../reference/ids-in-aam.md)) ou d’un ID d’appareil ([UUID](../../reference/ids-in-aam.md)). Notez que si les DPUUID sont propres à une instance spécifique de [!DNL Audience Manager], les UUID sont partagés sur la [!DNL Audience Manager] plateforme. Pour [!UICONTROL UUID]nous, nous imposons une politique d’équité dans le stockage des qualifications relatives aux caractéristiques. Un algorithme permet de s’assurer qu’une part égale de la  du [!UICONTROL UUID] est rendue disponible pour chaque instance de [!DNL Audience Manager].
