---
description: Les audiences prédictives vous aident à classer les audiences inconnues en personas distinctes en temps réel à l’aide de la science des données.
seo-description: Predictive Audiences help you classify unknown audiences into distinct personas in real-time, using data science.
seo-title: Predictive Audiences Overview
solution: Audience Manager
title: Audiences prédictives d’Audience Manager
feature: Algorithmic Models
exl-id: 57eaeb09-0e0e-4ce9-9b25-f1a27f4f35ce
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '1470'
ht-degree: 3%

---

# Présentation de [!UICONTROL Predictive Audiences] {#predictive-audiences}

[!UICONTROL Predictive Audiences] vous permet de classer une audience inconnue en personnages distincts, en temps réel, à l’aide de techniques avancées de science des données.

>[!IMPORTANT]
>Cet article contient la documentation du produit destinée à vous guider tout au long de la configuration et de l’utilisation de cette fonctionnalité. Rien dans le présent document n&#39;est un avis juridique. Veuillez consulter votre propre service juridique pour obtenir des conseils juridiques.

Dans un contexte marketing, une personne est un segment d’audience défini par les visiteurs, les utilisateurs ou les acheteurs potentiels qui partagent un ensemble spécifique de caractéristiques, telles que les données démographiques, les habitudes de navigation, l’historique d’achats, etc.

Les modèles de [!UICONTROL Predictive Audiences] approfondissent encore ce concept en vous permettant d’utiliser les capacités d’apprentissage automatique d’Audience Manager pour classer les audiences inconnues en différentes personas. Audience Manager vous aide à y parvenir en calculant la propension de votre audience propriétaire inconnue pour un ensemble d’audiences propriétaires connues.

Lorsque vous créez un modèle de [!UICONTROL Predictive Audiences], la première étape consiste à choisir les caractéristiques ou les segments de base par lesquels vous souhaitez que votre audience cible soit classée. Ces caractéristiques ou segments définiront vos rôles.

Au cours de la phase d’évaluation, le modèle crée un segment de [!UICONTROL Predictive Audiences] pour chaque caractéristique ou segment que vous avez défini comme ligne de base. La prochaine fois qu’Audience Manager verra un visiteur de votre audience cible qui n’est pas classé pour une personne (qui ne s’est qualifiée pour aucune de vos caractéristiques ou segments de base), le modèle de [!UICONTROL Predictive Audiences] déterminera à quels segments prédictifs le visiteur doit appartenir et ajoutera le visiteur à ce segment.

Vous pouvez identifier les segments prédictifs créés par le modèle dans la page [!UICONTROL Segments] . Chaque modèle de [!UICONTROL Predictive Audiences] possède son propre dossier sous le dossier [!UICONTROL Predictive Audiences] et vous pouvez afficher les segments de chaque modèle en cliquant sur le dossier des modèles.

![predictive-audiences-segments](assets/predictive-audiences-segments.png)

## Cas d’utilisation {#use-cases}

Pour mieux comprendre quand et comment utiliser [!UICONTROL Predictive Audiences], consultez les cas d’utilisation ci-dessous que les clients Audience Manager peuvent résoudre à l’aide de cette fonctionnalité.

### #1 de cas d’utilisation

En tant que spécialiste marketing dans une société de commerce électronique, je souhaite classer tous mes visiteurs sur le web et mobiles dans différentes catégories d’affinité de marque, afin de pouvoir personnaliser leur expérience utilisateur.

### #2 de cas d’utilisation

En tant que spécialiste marketing dans une société de médias, je souhaite classer mes visiteurs web et mobiles non authentifiés par genres préférés, afin de leur proposer du contenu personnalisé sur tous les canaux.

### #3 de cas d’utilisation

En tant qu&#39;annonceur pour une compagnie aérienne, je veux m&#39;assurer de classer mon audience en fonction de son intérêt pour les destinations de voyage, afin de pouvoir lui faire de la publicité en temps réel, dans un court créneau de reciblage.

### #4 de cas d’utilisation

En tant qu&#39;annonceur, je souhaite classer mon audience propriétaire en temps réel, afin de pouvoir réagir rapidement aux tendances.

### #5 de cas d’utilisation

En tant que spécialiste marketing, je souhaite prédire dans quelle phase du parcours client se trouvent les visiteurs de mon site web, comme la découverte, l’engagement, l’achat ou la rétention, afin de pouvoir les cibler en conséquence.

### #6 de cas d’utilisation

En tant que société de médias, je souhaite catégoriser mon audience afin de pouvoir vendre mon espace publicitaire à un prix supérieur, tout en offrant à mes visiteurs des publicités pertinentes.

## Fonctionnement des modèles [!UICONTROL Predictive Audiences] {#how-predictive-audiences-models-work}

Lorsque vous créez un modèle de [!UICONTROL Predictive Audiences], vous passez par trois étapes :

1. Tout d’abord, sélectionnez au moins deux caractéristiques ou deux segments qui définiront vos profils.
1. Ensuite, choisissez une caractéristique ou un segment qui définit l’audience cible que vous souhaitez classer.
1. Enfin, choisissez un nom pour le modèle, une source de données qui stockera les segments prédictifs et un [!UICONTROL Profile Merge Rule] pour le modèle.

### Critères de sélection des rôles {#selection-personas}

Vous pouvez choisir n’importe laquelle de vos caractéristiques ou segments propriétaires pour définir vos rôles. Toutefois, pour des résultats optimaux, voici un ensemble de bonnes pratiques recommandées :

* Choisissez les caractéristiques ou les segments de votre persona afin que chaque personnage dispose d’au moins quelques centaines [identifiants d’appareil](../../reference/ids-in-aam.md).
* Si vos caractéristiques sont basées sur des [identifiants d’appareil](../../reference/ids-in-aam.md), vous pouvez les encapsuler dans des segments avec des [règles de fusion de profil](../profile-merge-rules/merge-rules-overview.md) qui utilisent des [identifiants d’appareil](../../reference/ids-in-aam.md) tels que [!UICONTROL Device Graph]. Cela permet de s’assurer qu’il y a suffisamment d[identifiants d’appareil](../../reference/ids-in-aam.md) dont l’algorithme peut s’inspirer.
* Nous vous recommandons de choisir des caractéristiques ou des segments simples pour vos profils, consistant en 1 à 3 caractéristiques.
* Choisissez des caractéristiques de ligne de base ou des segments qui se chevauchent le moins possible.
* Assurez-vous de capturer des caractéristiques granulaires sur vos propriétés numériques.

### Critères de sélection du public cible {#selection-audience}

Selon votre cas d’utilisation, que vous souhaitiez classer les utilisateurs en temps réel, par lots, ou les deux, choisissez une audience cible ([!UICONTROL trait] ou [!UICONTROL segment]) qui a une population totale et/ou en temps réel significative. Tout comme pour la sélection de personas, nous recommandons que votre audience cible [!UICONTROL trait] ou [!UICONTROL segment] comporte des utilisateurs avec des profils riches (jeux de [!UICONTROL traits] riches).

Lors de la sélection de l’audience cible, analysez votre cas d’utilisation et décidez des types d’identifiants à classer : [!UICONTROL device IDs] ou [!UICONTROL cross-device IDs]. Le [!UICONTROL Profile Merge Rule] que vous sélectionnez lors de la création du modèle définit les données qui seront utilisées pour placer chaque utilisateur dans le [!UICONTROL segments] prédictif.

Nous vous recommandons de choisir une [!UICONTROL Profile Merge Rule] qui présente la même configuration que votre audience cible [!UICONTROL Profile Merge Rule], ou qui inclut le type de profil (profil d’appareil ou profil authentifié) de votre audience cible.

### Phase de formation du modèle de [!UICONTROL Predictive Audiences] {#model-training}

Avant que l’algorithme puisse classer votre audience propriétaire en bonnes personnes, il doit s’entraîner sur vos données.

Pour chaque personnage que vous définissez, l’algorithme analyse son audience respective et évalue toute activité de caractéristiques en temps réel et/ou intégrée pour ses utilisateurs au cours des 30 derniers jours.
Cette étape a lieu toutes les 24 heures, pour tenir compte des modifications de votre audience propriétaire.

### Phase de classification du modèle [!UICONTROL Predictive Audiences] {#model-classification}

Pour la classification des audiences en temps réel et par lots, le modèle vérifie d’abord si un utilisateur appartient à l’audience cible. Si l’utilisateur est qualifié pour l’audience cible et n’appartient à aucun des rôles, le modèle lui affecte un score de qualification de rôle.

Lors de l’évaluation des audiences propriétaires et de l’attribution de scores, le modèle utilise le **[!UICONTROL Profile Merge Rule]** par défaut défini dans votre compte. Enfin, le visiteur est classé dans la persona pour laquelle il a reçu la note la plus élevée.

![predictive-audiences-graph](assets/predictive-audiences-graph.png)

## Considérations et restrictions {#considerations}

>[!IMPORTANT]
> Lisez attentivement cette section avant de passer à la phase d’implémentation.

Lors de la configuration de vos modèles [!UICONTROL Predictive Audiences], gardez à l’esprit les points et limites suivants :

* Vous pouvez créer jusqu’à 10 modèles de [!UICONTROL Predictive Audiences].
* Pour chaque modèle, vous pouvez choisir jusqu’à 50 caractéristiques/segments de base.
* Les données secondaires et tierces ne sont actuellement pas prises en charge dans [!UICONTROL Predictive Audiences].
* [!UICONTROL Predictive Audiences] effectue une classification d’audience en fonction de vos caractéristiques propriétaires, à partir de toutes vos sources de données propriétaires.
* L’évaluation des segments pour [!UICONTROL Predictive Audiences] utilise les **[!UICONTROL Profile Merge Rule]** que vous choisissez lors de la création du modèle. Pour en savoir plus sur les [!UICONTROL Profile Merge Rules], consultez la [documentation](../profile-merge-rules/merge-rules-overview.md) dédiée.
* Certaines caractéristiques et certains segments ne sont pas pris en charge en tant que lignes de base ou audiences cibles. L’enregistrement des modèles [!UICONTROL Predictive Audiences] échoue lors du choix de l’un des éléments suivants comme niveaux de référence ou audiences cibles :
   * caractéristiques prédictives et segments créés avec des caractéristiques prédictives ;
   * [Adobe Experience Platform](../integration/../../integration/integration-aep/aam-aep-audience-sharing.md) caractéristiques ou segments ;
   * caractéristiques algorithmiques ;
   * Caractéristiques secondaires et tierces.
* [!UICONTROL Predictive Audience] [!UICONTROL segments] ne peut pas être utilisé dans [!UICONTROL Audience Lab].

## [!UICONTROL Data Export Controls] {#dec}

Les segments prédictifs créés par [!UICONTROL Predictive Audiences] modèles héritent des [ Contrôles d’exportation de données ](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-export-controls.html) des sources de données propriétaires suivantes :

1. Source de données propriétaire que vous choisissez lors de la création du modèle.
1. Les sources de données propriétaires de votre audience cible. Plus précisément, les contrôles d’exportation des données des [!UICONTROL traits] ou [!UICONTROL segments] qui constituent votre audience cible.
1. Les [ Contrôles d’exportation de données ](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-export-controls.html) du [!UICONTROL Profile Merge Rule] que vous avez sélectionné pour le modèle.

Les nouveaux [!UICONTROL traits] prédictifs et [!UICONTROL segments] auront les mêmes restrictions de confidentialité que l’union des sources de données propriétaires décrites ci-dessus.

Les caractéristiques qui comportent des restrictions supplémentaires qui ne font pas partie des restrictions de confidentialité du segment [!UICONTROL Predictive Audiences] seront exclues de la phase d’entraînement et ne deviendront pas influentes pour le modèle.

## [!UICONTROL Profile Merge Rules] {#pmr}

Tous les segments prédictifs se verront attribuer le [!UICONTROL Profile Merge Rule] que vous avez sélectionné lors de la création du modèle. Le [!UICONTROL Profile Merge Rule] que vous choisissez est important pour les raisons suivantes :

* Il définit les appareils et/ou les profils authentifiés qui doivent être pris en compte lorsque le modèle analyse les [!UICONTROL traits] d’influence au moment de classer un utilisateur dans une [!UICONTROL segment] prédictive.
* Il détermine les types de [!UICONTROL trait] (niveau d’appareil ou entre appareils) qui doivent être utilisés au cours de l’étape d’entraînement du modèle et qui doivent apparaître comme des [!UICONTROL traits] influents. Les [!UICONTROL segments] prédictives sont des sous-ensembles de votre audience cible.
   * Si l’audience cible est un segment, nous vous recommandons de sélectionner le même [!UICONTROL Profile Merge Rule] pour le modèle que celui affecté à votre audience cible, ou un [!UICONTROL Profile Merge Rule] qui inclut le type de profil de votre audience cible.
   * Si l’audience cible est un [!UICONTROL trait], nous vous recommandons de sélectionner un [!UICONTROL Profile Merge Rule] qui peut accéder au même type de données que la caractéristique de l’audience cible (données de profil de l’appareil ou données de profil sur l’ensemble des appareils).
* Les [!UICONTROL Profile Merge Rules] utilisant les options [!UICONTROL Current Authenticated Profiles] et [!UICONTROL No Device Profile] ne sont prises en charge que pour la classification d’audiences en temps réel. Pour plus d’informations, voir [Options de règles de fusion de profil définies](../profile-merge-rules/merge-rule-definitions.md).

La sélection d’une [!UICONTROL Profile Merge Rule] qui utilise à la fois les données de l’appareil et les données inter-appareils maximise le nombre de [!UICONTROL traits] qui peuvent être utilisées pour la formation des modèles et la classification des utilisateurs dans le [!UICONTROL segments] prédictif.

## [!UICONTROL Role-Based Access Controls] {#rbac}

Les caractéristiques et les segments que vous choisissez pour les rôles et la classification d’audience sont soumis aux [contrôles d’accès en fonction du rôle](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/administration/administration-overview.html) d’Audience Manager.

Les utilisateurs d’Audience Manager peuvent uniquement sélectionner des caractéristiques ou des segments pour les personnes et les audiences cibles, qu’ils sont [autorisés à afficher](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/administration/administration-overview.html#wild-card-permissions).
