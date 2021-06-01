---
description: Décrit les segments, leurs parties constituantes et la création de règles à l’aide du créateur de segments.
seo-description: Décrit les segments, leurs parties constituantes et la création de règles à l’aide du créateur de segments.
seo-title: Segments Objectif, composition et règles
solution: Audience Manager
title: Segments Objectif, composition et règles
uuid: 886d4abe-b1b6-4983-b4fb-b552d54d51ba
feature: 'Segments '
exl-id: 4e4da7a7-3267-4564-b1c5-663dcddf2b93
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 6%

---

# Segments : objectif, composition et règles {#segments-purpose-composition-and-rules}

Décrit [!UICONTROL segments], leurs parties constituantes et la création de règles avec [!UICONTROL Segment Builder].

## Objectif de [!UICONTROL Segments]

Un *`segment`* (ou un *`audience`*) est un ensemble d’utilisateurs qui partagent des attributs communs. En Audience Manager, vous créez [!UICONTROL segments] avec des règles côté serveur. Ces règles permettent de créer des groupes d’audiences en fonction des attributs des visiteurs du site, tels que :

* Comportement;
* Données démographiques (âge, sexe, revenu, etc.);
* Autres caractéristiques que vous pouvez définir dans l’interface utilisateur.

## [!UICONTROL Segment] Composition

Une Audience Manager [!UICONTROL segment] est une règle côté serveur qui se compose de caractéristiques individuelles ou de groupes de caractéristiques. Les caractéristiques sont composées d’éléments de données appelés paires clé-valeur. Outre les règles que vous définissez au niveau [!UICONTROL segment], ces paires clé-valeur contiennent les critères qui qualifient les visiteurs pour les caractéristiques et l’appartenance à [!UICONTROL segment].

## Considérations sur le [!UICONTROL Adobe Analytics] [!UICONTROL Segment] mappage

Lors du mappage des suites de rapports Adobe Analytics [!UICONTROL segments] ou d’à votre organisation Experience Cloud, l’Audience Manager crée automatiquement de nouvelles caractéristiques [!UICONTROL segments] et  correspondantes, en lecture seule. Vous ne pouvez pas modifier ni modifier l’emplacement de stockage de ces [!UICONTROL segments] à partir de l’Audience Manager. Toutefois, toute modification que vous effectuez sur vos suites de rapports ou Adobe Analytics mappées se reflète dans l’Audience Manager.[!UICONTROL segments]

>[!TIP]
>
>L’Audience Manager [!UICONTROL segments] diffère de [!DNL Adobe Analytics] [!UICONTROL segments]. Voir [Présentation des segments dans Analytics et l’Audience Manager](https://docs.adobe.com/content/help/fr-FR/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html) pour une description détaillée des différences.

## Créer des règles basées sur [!UICONTROL Segments] avec [!UICONTROL Segment Builder]

Contrairement aux pixels traditionnels qui se déclenchent en réponse à de simples conditions oui/non, [!UICONTROL Segment Builder] vous permet de créer des exigences [!UICONTROL segment] complexes. Comme [!UICONTROL traits], [!UICONTROL segments] évaluent les données à l’aide d’expressions [!DNL Boolean] ([!DNL AND], [!DNL OR], [!DNL NOT]), d’opérateurs de comparaison (supérieur, inférieur à, égal à, etc.) et de critères de récence/fréquence. Ces fonctionnalités permettent de créer une audience [!UICONTROL segments] ciblée adaptée aux besoins de votre entreprise.

## Avantages

[!UICONTROL Segments] améliorer les processus standard de création/segmentation d’audiences basés sur les pixels, car ils permettent :

* Créez des [!UICONTROL segments] pertinents et utiles avec des caractéristiques propriétaires et tierces.
* Créez des règles de segmentation complexes et sophistiquées avec des opérateurs booléens, des expressions de comparaison et des critères de récence/fréquence.
* Envoyez des données [!UICONTROL segment] à un partenaire de destination.
* Surveillez les performances à l’aide de rapports d’Audience Manager.

>[!MORELIKETHIS]
>
>* [Signaux, caractéristiques et segments](../../reference/signal-trait-segment.md)

