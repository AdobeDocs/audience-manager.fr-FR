---
description: Décrit les segments, leurs parties constituantes et la création de règles avec le créateur de segments.
seo-description: Décrit les segments, leurs parties constituantes et la création de règles avec le créateur de segments.
seo-title: Finalité des segments, composition et règles
solution: Audience Manager
title: Finalité des segments, composition et règles
uuid: 886 d 4 abe-b 1 b 6-4983-b 4 fb-b 552 d 54 d 51 ba
translation-type: tm+mt
source-git-commit: c229bf71da5b07277811219cbf2794c3ca7bc89d

---


# Segments: Purpose, Composition, and Rules {#segments-purpose-composition-and-rules}

Describes segments, their constituent parts, and rule creation with [!UICONTROL Segment Builder].

## Objectif des segments

A *`segment`* (or an *`audience`*) is a set of users who share common attributes. Dans Audience Manager, vous créez des segments avec des règles côté serveur. Ces règles vous permettent de créer des groupes d&#39;audiences en fonction des attributs des visiteurs du site tels que :

* Comportement;
* Données démographiques (âge, sexe, revenu, etc.);
* Autres caractéristiques que vous pouvez définir dans l&#39;interface utilisateur.

## Composition de segment

Un segment Audience Manager est une règle côté serveur qui consiste en une personne ou des groupes de caractéristiques. Les caractéristiques sont composées d&#39;éléments de données appelés paires clé-valeur. Outre les règles que vous définissez au niveau du segment, ces paires clé-valeur contiennent les critères qui qualifient les visiteurs pour l&#39;appartenance aux caractéristiques et aux segments.

## Remarques sur le mappage des segments Adobe Analytics

Lors du mappage des segments ou des suites de rapports Adobe Analytics à votre organisation Experience Cloud, Audience Manager crée automatiquement des segments et caractéristiques en lecture seule correspondants. Vous ne pouvez pas modifier ni modifier l&#39;emplacement de stockage de ces segments à partir d&#39;Audience Manager. Toutefois, toute modification que vous effectuez sur vos segments ou suites de rapports mappés est répercutée dans Audience Manager.

>[!TIP]
>
>Audience Manager segments are different from [!DNL Adobe Analytics] segments. Read [Understanding Segments in Analytics and Audience Manager](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/aam-analytics-segments.html) for an in-depth description of the differences.

## Création de segments basés sur des règles avec le créateur de segments

Contrairement aux pixels traditionnels qui se déclenchent en réponse à des conditions simples oui/aucune, le créateur de segments vous permet de créer des exigences de segment complexes. Like traits, segments evaluate data using [!DNL Boolean] expressions ([!DNL AND], [!DNL OR], [!DNL NOT]), comparison operators (greater than, less than, equal to, etc.), and recency/frequency criteria. Ces fonctionnalités permettent de créer des segments d&#39;audience orientés vers vos besoins.

## Avantages

Les segments améliorent les processus standard de création/segmentation d&#39;audiences en pixels, car ils vous permettent :

* Créez des segments pertinents et pertinents avec des caractéristiques propriétaires et tierces.
* Créez des règles de segmentation complexes et complexes avec des opérateurs booléens, des expressions de comparaison et des critères récence/fréquence.
* Envoyez des données de segment à un partenaire de destination.
* Surveillez les performances avec les rapports Audience Manager.

>[!MORE_ LIKE_ THIS]
>
>* [Signaux, caractéristiques et segments](../../reference/signal-trait-segment.md)

