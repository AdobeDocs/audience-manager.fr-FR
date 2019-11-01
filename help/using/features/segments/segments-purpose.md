---
description: Décrit les segments, leurs parties constitutives et la création de règles avec le créateur de segments.
seo-description: Décrit les segments, leurs parties constitutives et la création de règles avec le créateur de segments.
seo-title: Objectif, composition et règles des segments
solution: Audience Manager
title: Objectif, composition et règles des segments
uuid: 886d4abe-b1b6-4983-b4fb-b552d54d51ba
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Segments : Objectif, composition et règles {#segments-purpose-composition-and-rules}

Décrit les segments, leurs parties constitutives et la création de règles avec [!UICONTROL Segment Builder].

## Objectif des segments

Un *`segment`* (ou un *`audience`*) est un ensemble d’utilisateurs qui partagent des attributs communs. Dans Audience Manager, vous créez des segments avec des règles côté serveur. Ces règles permettent de créer des groupes d’audiences en fonction des attributs des visiteurs du site, tels que :

* Comportement;
* Données démographiques (âge, sexe, revenu, etc.);
* Autres caractéristiques que vous pouvez définir dans l’interface utilisateur.

## Composition de segment

Un segment Audience Manager est une règle côté serveur qui se compose de caractéristiques individuelles ou de groupes de caractéristiques. Les caractéristiques sont composées d’éléments de données appelés paires clé-valeur. Outre les règles que vous définissez au niveau du segment, ces paires clé-valeur contiennent les critères qui permettent aux visiteurs de bénéficier d’une caractéristique et d’une appartenance à un segment.

## Remarques sur le mappage des segments dans Adobe Analytics

Lors du mappage de segments ou de suites de rapports Adobe Analytics avec votre organisation Experience Cloud, Audience Manager crée automatiquement de nouveaux segments et caractéristiques correspondants en lecture seule. Vous ne pouvez pas modifier ni modifier l’emplacement de stockage de ces segments à partir d’Audience Manager. Toutefois, toute modification que vous apportez à vos segments ou suites de rapports Adobe Analytics mappés est répercutée dans Audience Manager.

>[!TIP]
>
>Les segments d’Audience Manager sont différents des [!DNL Adobe Analytics] segments. Consultez [Compréhension des segments dans Analytics et Audience Manager](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/aam-analytics-segments.html) pour obtenir une description détaillée des différences.

## Création de segments basés sur des règles avec le créateur de segments

Contrairement aux pixels traditionnels qui se déclenchent en réponse à de simples conditions oui/non, le créateur de segments vous permet de créer des exigences de segment complexes. Comme les caractéristiques, les segments évaluent les données à l’aide [!DNL Boolean] d’expressions ([!DNL AND], [!DNL OR], [!DNL NOT]), d’opérateurs de comparaison (supérieur, inférieur, égal à, etc.) et de critères de récence/fréquence. Ces fonctionnalités permettent de créer des segments d’audience ciblés correspondant aux besoins de votre entreprise.

## Avantages

Les segments s’améliorent avec les processus standard de création/segmentation d’audience basés sur les pixels, car ils vous permettent d’effectuer les opérations suivantes :

* Créez des segments pertinents et utiles avec des caractéristiques propriétaires et tiers.
* Créez des règles de segmentation complexes et sophistiquées avec des opérateurs booléens, des expressions de comparaison et des critères de récence/fréquence.
* Envoyez des données de segment à un partenaire de destination.
* Surveillez les performances avec les rapports Audience Manager.

>[!MORELIKETHIS]
>
>* [Signaux, caractéristiques et segments](../../reference/signal-trait-segment.md)

