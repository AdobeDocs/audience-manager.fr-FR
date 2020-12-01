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

Décrit [!UICONTROL segments], leurs parties constituantes et la création de règles avec [!UICONTROL Segment Builder].

## Objectif de [!UICONTROL Segments]

Un *`segment`* (ou un *`audience`*) est un ensemble d&#39;utilisateurs qui partagent des attributs communs. En Audience Manager, vous créez [!UICONTROL segments] avec des règles côté serveur. Ces règles vous permettent de créer des groupes d&#39;audiences en fonction des attributs du visiteur du site, tels que :

* Comportement;
* Données démographiques (âge, sexe, revenu, etc.);
* Autres caractéristiques que vous pouvez définir dans l’interface utilisateur.

## [!UICONTROL Segment] Composition

Une Audience Manager [!UICONTROL segment] est une règle côté serveur qui comprend des groupes ou des individus de caractéristiques. Les caractéristiques sont composées d’éléments de données appelés paires clé-valeur. Outre les règles que vous définissez au niveau [!UICONTROL segment], ces paires clé-valeur contiennent les critères qui permettent aux visiteurs de bénéficier d’une caractéristique et d’une appartenance [!UICONTROL segment].

## Considérations sur le mappage [!UICONTROL Adobe Analytics] [!UICONTROL Segment]

Lorsque vous mappez des suites de rapports ou Adobe Analytics [!UICONTROL segments] à votre organisation Experience Cloud, l’Audience Manager crée automatiquement de nouvelles caractéristiques, correspondantes, en lecture seule [!UICONTROL segments] et des caractéristiques. Vous ne pouvez pas modifier ou modifier l&#39;emplacement d&#39;enregistrement de ces [!UICONTROL segments] à partir de l&#39;Audience Manager. Toutefois, toute modification que vous effectuez sur votre Adobe Analytics [!UICONTROL segments] mappée ou vos suites de rapports se reflète dans l’Audience Manager.

>[!TIP]
>
>L&#39;Audience Manager [!UICONTROL segments] est différente de [!DNL Adobe Analytics] [!UICONTROL segments]. Consultez [Présentation des segments dans Analytics et l’Audience Manager](https://docs.adobe.com/content/help/fr-FR/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html) pour obtenir une description détaillée des différences.

## Créer des règles basées sur [!UICONTROL Segments] avec [!UICONTROL Segment Builder]

Contrairement aux pixels traditionnels qui se déclenchent en réponse à de simples conditions oui/non, [!UICONTROL Segment Builder] vous permet de créer des exigences complexes [!UICONTROL segment]. Comme [!UICONTROL traits], [!UICONTROL segments] évaluent les données à l&#39;aide d&#39;expressions [!DNL Boolean] ([!DNL AND], [!DNL OR], [!DNL NOT]), d&#39;opérateurs de comparaison (supérieurs, inférieurs, égaux à, etc.) et de critères de récence/fréquence. Ces fonctionnalités permettent de créer une audience [!UICONTROL segments] ciblée adaptée à vos besoins professionnels.

## Avantages

[!UICONTROL Segments] améliorez les processus standard de création/segmentation d’audiences basés sur les pixels, car ils vous permettent d’effectuer les opérations suivantes :

* Créez des [!UICONTROL segments] pertinents et utiles avec des caractéristiques propriétaires et tiers.
* Créez des règles de segmentation complexes avec des opérateurs booléens, des expressions de comparaison et des critères de récence/fréquence.
* Envoyer des données [!UICONTROL segment] à un partenaire de destination.
* Surveillez les performances à l’aide de rapports d’Audience Manager.

>[!MORELIKETHIS]
>
>* [Signaux, caractéristiques et segments](../../reference/signal-trait-segment.md)

