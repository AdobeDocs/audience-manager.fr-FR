---
description: Décrit les segments, leurs parties constituantes et la création de règles avec le créateur de segments.
seo-description: Describes segments, their constituent parts, and rule creation with Segment Builder.
seo-title: Segments  Purpose, Composition, and Rules
solution: Audience Manager
title: Objectif, composition et règles des segments
uuid: 886d4abe-b1b6-4983-b4fb-b552d54d51ba
feature: Segments
exl-id: 4e4da7a7-3267-4564-b1c5-663dcddf2b93
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 1%

---

# Segments : objectif, composition et règles {#segments-purpose-composition-and-rules}

Décrit les [!UICONTROL segments], leurs éléments constitutifs et la création de règles avec [!UICONTROL Segment Builder].

## But de la [!UICONTROL Segments]

Un *`segment`* (ou une *`audience`*) est un ensemble d’utilisateurs qui partagent des attributs communs. Dans Audience Manager, vous créez des [!UICONTROL segments] avec des règles côté serveur. Ces règles vous permettent de créer des groupes d’audiences en fonction des attributs du visiteur du site, tels que :

* Comportement ;
* Données démographiques (âge, sexe, revenu, etc.);
* Autres caractéristiques que vous pouvez définir dans l’interface utilisateur.

## Composition [!UICONTROL Segment]

Une [!UICONTROL segment] Audience Manager est une règle côté serveur qui se compose de caractéristiques individuelles ou de groupes de caractéristiques. Les caractéristiques sont composées d’éléments de données appelés paires clé-valeur. Avec les règles que vous définissez au niveau de la [!UICONTROL segment], ces paires clé-valeur contiennent les critères qui qualifient les visiteurs pour l’appartenance à une caractéristique et à une [!UICONTROL segment].

## Considérations relatives [!UICONTROL Adobe Analytics] mappage [!UICONTROL Segment]

Lors du mappage de [!UICONTROL segments] ou de suites de rapports Adobe Analytics à votre organisation Experience Cloud, Audience Manager crée automatiquement de nouvelles caractéristiques et [!UICONTROL segments] en lecture seule correspondantes. Vous ne pouvez pas modifier ni changer l’emplacement de stockage de ces [!UICONTROL segments] à partir d’Audience Manager. Cependant, toute modification que vous apportez à vos [!UICONTROL segments] Adobe Analytics ou suites de rapports mappées est répercutée dans Audience Manager.

>[!TIP]
>
>Les [!UICONTROL segments] Audience Manager sont différentes des [!DNL Adobe Analytics] [!UICONTROL segments]. Lisez [Présentation des segments dans Analytics et Audience Manager](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html?lang=fr) pour une description détaillée des différences.

## Créer Des [!UICONTROL Segments] Basés Sur Des Règles Avec [!UICONTROL Segment Builder]

Contrairement aux pixels traditionnels qui se déclenchent en réponse à des conditions oui/non simples, [!UICONTROL Segment Builder] permet de créer des exigences de [!UICONTROL segment] complexes. Comme [!UICONTROL traits], [!UICONTROL segments] évaluez les données à l’aide d’expressions [!DNL Boolean] ([!DNL AND], [!DNL OR], [!DNL NOT]), d’opérateurs de comparaison (supérieur à, inférieur à, égal à, etc.) et de critères de récence/fréquence. Ces fonctionnalités permettent de créer des [!UICONTROL segments] d’audience ciblés adaptés aux besoins de votre entreprise.

## Avantages

[!UICONTROL Segments] améliorer les processus standard de création/segmentation d’audience basés sur les pixels, car ils vous permettent d’effectuer les opérations suivantes :

* Créez des [!UICONTROL segments] utiles et pertinentes avec des caractéristiques propriétaires et tierces.
* Créez des règles de segmentation complexes et sophistiquées avec des opérateurs booléens, des expressions de comparaison et des critères de récence/fréquence.
* Envoyez des données [!UICONTROL segment] à un partenaire de destination.
* Surveillez les performances à l’aide des rapports Audience Manager.

>[!MORELIKETHIS]
>
>* [Signaux, caractéristiques et segments](../../reference/signal-trait-segment.md)
