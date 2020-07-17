---
description: Décrit les segments, leurs parties constituantes et la création de règles avec le créateur de segments.
seo-description: Décrit les segments, leurs parties constituantes et la création de règles avec le créateur de segments.
seo-title: Segments Objectif, composition et règles
solution: Audience Manager
title: Segments Objectif, composition et règles
uuid: 886d4abe-b1b6-4983-b4fb-b552d54d51ba
feature: Segments
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 6%

---


# Segments : objectif, composition et règles {#segments-purpose-composition-and-rules}

Décrit [!UICONTROL segments]leurs parties constituantes et crée des règles avec [!UICONTROL Segment Builder].

## Objectif [!UICONTROL Segments]

A *`segment`* (or an *`audience`*) is a set of users who share common attributes. En Audience Manager, vous créez [!UICONTROL segments] avec des règles côté serveur. Ces règles vous permettent de créer des groupes d&#39;audiences en fonction des attributs du visiteur du site, tels que :

* Comportement;
* Données démographiques (âge, sexe, revenu, etc.);
* Autres caractéristiques que vous pouvez définir dans l’interface utilisateur.

## [!UICONTROL Segment] Composition

Une Audience Manager [!UICONTROL segment] est une règle côté serveur qui comprend des caractéristiques individuelles ou des groupes de caractéristiques. Les caractéristiques sont composées d’éléments de données appelés paires clé-valeur. Outre les règles que vous définissez au [!UICONTROL segment] niveau, ces paires clé-valeur contiennent les critères qui qualifient les visiteurs pour les caractéristiques et l’ [!UICONTROL segment] appartenance.

## Considérations sur le [!UICONTROL Adobe Analytics][!UICONTROL Segment] mappage

Lors du mappage des suites de rapports [!UICONTROL segments] ou Analytics Adobe à votre organisation Experience Cloud, l’Audience Manager crée automatiquement de nouvelles caractéristiques, correspondantes, en lecture seule [!UICONTROL segments] et en lecture seule. Vous ne pouvez pas modifier ou modifier l’emplacement d’enregistrement de ces [!UICONTROL segments] Audiences Manager. Toutefois, toute modification que vous effectuez sur votre Analytics Adobe mappé [!UICONTROL segments] ou vos suites de rapports est répercutée dans l’Audience Manager.

>[!TIP]
>
>L&#39;Audience Manager [!UICONTROL segments] est différente de [!DNL Adobe Analytics][!UICONTROL segments]. Read [Understanding Segments in Analytics and Audience Manager](https://docs.adobe.com/content/help/fr-FR/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html) for an in-depth description of the differences.

## Créer des règles basées sur [!UICONTROL Segments] des [!UICONTROL Segment Builder]

Contrairement aux pixels traditionnels qui se déclenchent en réponse à de simples conditions oui/non, [!UICONTROL Segment Builder] vous permet de créer des [!UICONTROL segment] exigences complexes. Comme [!UICONTROL traits], [!UICONTROL segments] évaluez les données à l’aide d’ [!DNL Boolean] expressions ([!DNL AND], [!DNL OR], [!DNL NOT]), d’opérateurs de comparaison (supérieurs, inférieurs, égaux à, etc.) et de critères de récence/fréquence. Ces fonctionnalités vous aident à créer une audience ciblée [!UICONTROL segments] adaptée à vos besoins professionnels.

## Avantages

[!UICONTROL Segments] améliorez les processus standard de création/segmentation d’audiences basés sur les pixels, car ils vous permettent d’effectuer les opérations suivantes :

* Créez des éléments pertinents et utiles [!UICONTROL segments] avec des caractéristiques propriétaires et tiers.
* Créez des règles de segmentation complexes avec des opérateurs booléens, des expressions de comparaison et des critères de récence/fréquence.
* Envoyer [!UICONTROL segment] des données à un partenaire de destination.
* Surveillez les performances à l’aide de rapports d’Audience Manager.

>[!MORELIKETHIS]
>
>* [Signaux, caractéristiques et segments](../../reference/signal-trait-segment.md)

