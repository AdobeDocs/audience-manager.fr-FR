---
description: Décrit les segments, leurs parties constituantes et la création de règles à l’aide du créateur de segments.
seo-description: Describes segments, their constituent parts, and rule creation with Segment Builder.
seo-title: Segments  Purpose, Composition, and Rules
solution: Audience Manager
title: Segments Objectif, composition et règles
uuid: 886d4abe-b1b6-4983-b4fb-b552d54d51ba
feature: Segments
exl-id: 4e4da7a7-3267-4564-b1c5-663dcddf2b93
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 1%

---

# Segments : objectif, composition et règles {#segments-purpose-composition-and-rules}

Décrit [!UICONTROL segments], leurs parties constituantes et la création de règles avec [!UICONTROL Segment Builder].

## Objectif de [!UICONTROL Segments]

Un *`segment`* (ou un *`audience`*) est un ensemble d’utilisateurs qui partagent des attributs communs. Dans Audience Manager, vous créez [!UICONTROL segments] avec des règles côté serveur. Ces règles permettent de créer des groupes d’audiences en fonction des attributs des visiteurs du site, tels que :

* Comportement;
* Données démographiques (âge, sexe, revenu, etc.);
* Autres caractéristiques que vous pouvez définir dans l’interface utilisateur.

## [!UICONTROL Segment] Composition

Une Audience Manager [!UICONTROL segment] est une règle côté serveur qui se compose de caractéristiques individuelles ou de groupes de caractéristiques. Les caractéristiques sont composées d’éléments de données appelés paires clé-valeur. Outre les règles que vous définissez au niveau de [!UICONTROL segment], ces paires clé-valeur contiennent les critères qui qualifient les visiteurs pour les caractéristiques et l’appartenance à [!UICONTROL segment].

## Considérations sur le mappage [!UICONTROL Adobe Analytics] [!UICONTROL Segment]

Lors du mappage d’Adobe Analytics [!UICONTROL segments] ou de suites de rapports à votre organisation Experience Cloud, l’Audience Manager crée automatiquement de nouvelles caractéristiques [!UICONTROL segments] et  en lecture seule correspondantes. Vous ne pouvez pas modifier ni modifier l’emplacement de stockage de ces [!UICONTROL segments] à partir de l’Audience Manager. Cependant, toute modification que vous effectuez sur votre Adobe Analytics [!UICONTROL segments] ou suite de rapports mappée se reflète dans l’Audience Manager.

>[!TIP]
>
>L&#39;Audience Manager [!UICONTROL segments] diffère de [!DNL Adobe Analytics] [!UICONTROL segments]. Lisez la section [Présentation des segments dans Analytics et l’Audience Manager](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html) pour obtenir une description détaillée des différences.

## Créer [!UICONTROL Segments] basé sur des règles avec [!UICONTROL Segment Builder]

Contrairement aux pixels traditionnels qui se déclenchent en réponse à de simples conditions oui/non, [!UICONTROL Segment Builder] vous permet de créer des exigences [!UICONTROL segment] complexes. Comme [!UICONTROL traits], [!UICONTROL segments] évaluent les données à l’aide d’expressions [!DNL Boolean] ([!DNL AND], [!DNL OR], [!DNL NOT]), d’opérateurs de comparaison (supérieur, inférieur, égal à, etc.) et de critères de récence/fréquence. Ces fonctionnalités permettent de créer une audience [!UICONTROL segments] ciblée adaptée aux besoins de votre entreprise.

## Avantages

[!UICONTROL Segments] améliore les processus standard de création/segmentation d’audience basés sur les pixels, car ils permettent :

* Créez des [!UICONTROL segments] pertinents et utiles avec des caractéristiques propriétaires et tierces.
* Créez des règles de segmentation complexes et sophistiquées avec des opérateurs booléens, des expressions de comparaison et des critères de récence/fréquence.
* Envoyez des données [!UICONTROL segment] à un partenaire de destination.
* Surveillez les performances à l’aide de rapports d’Audience Manager.

>[!MORELIKETHIS]
>
>* [Signaux, caractéristiques et segments](../../reference/signal-trait-segment.md)
