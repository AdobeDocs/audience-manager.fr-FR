---
description: Les audiences prédictives vous aident à classer les audiences inconnues en personas distinctes en temps réel à l’aide de la science des données.
seo-description: Les audiences prédictives vous aident à classer les audiences inconnues en personas distinctes en temps réel à l’aide de la science des données.
seo-title: Présentation des audiences prédictives
solution: Audience Manager
title: Audiences prédictives d’Audience Manager
feature: Modèles algorithmiques
exl-id: 57eaeb09-0e0e-4ce9-9b25-f1a27f4f35ce
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '1513'
ht-degree: 8%

---

# [!UICONTROL Predictive Audiences] Présentation {#predictive-audiences}

[!UICONTROL Predictive Audiences] vous aide à classer en temps réel une audience inconnue en différentes personas à l’aide de techniques avancées de science des données.

>[!IMPORTANT]
>Cet article contient la documentation du produit destinée à vous guider tout au long de la configuration et de l’utilisation de cette fonctionnalité. Rien dans le présent article n&#39;est un avis juridique. Veuillez consulter votre propre service juridique pour obtenir des conseils juridiques.

Dans un contexte marketing, une persona est un segment d’audience défini par des visiteurs, des utilisateurs ou des acheteurs potentiels qui partagent un ensemble spécifique de caractéristiques comme des données démographiques, des habitudes de navigation, un historique des achats, etc.

Les modèles de [!UICONTROL Predictive Audiences] approfondissent encore ce concept en vous permettant d’utiliser les capacités d’apprentissage automatique d’Audience Manager pour classer les audiences inconnues en différentes personas. Pour ce faire, Audience Manager calcule la propension de votre audience propriétaire inconnue pour un ensemble d’audiences propriétaires connues.

Lorsque vous créez un modèle [!UICONTROL Predictive Audiences], la première étape consiste à choisir les caractéristiques ou les segments de base selon lesquels votre audience cible doit être classée. Ces caractéristiques ou segments définissent vos personas.

Au cours de la phase d’évaluation, le modèle crée un segment [!UICONTROL Predictive Audiences] pour chaque caractéristique ou segment que vous avez défini comme ligne de base. La prochaine fois qu’une Audience Manager voit un visiteur de votre audience cible qui n’est pas classé pour une persona (qui ne répond à aucun de vos segments ou caractéristiques de ligne de base), le modèle [!UICONTROL Predictive Audiences] détermine à quel segment prédictif le visiteur doit appartenir et l’ajoute à ce segment.

Vous pouvez identifier les segments prédictifs créés par le modèle, dans la page [!UICONTROL Segments]. Chaque modèle [!UICONTROL Predictive Audiences] comporte son propre dossier sous le dossier [!UICONTROL Predictive Audiences] et vous pouvez afficher les segments de chaque modèle en cliquant sur le dossier du modèle.

![predictive-audiences-segments](assets/predictive-audiences-segments.png)

## Cas d’utilisation {#use-cases}

Pour vous aider à mieux comprendre comment et quand vous pouvez utiliser [!UICONTROL Predictive Audiences], voici quelques cas d’utilisation que les clients d’Audience Manager peuvent résoudre à l’aide de cette fonctionnalité.

### Cas d’utilisation #1

En tant que marketeur dans une société de commerce électronique, je souhaite classer tous mes visiteurs web et mobiles dans différentes catégories d’affinité avec les marques, afin de pouvoir personnaliser leur expérience utilisateur.

### Cas d’utilisation #2

En tant que spécialiste du marketing dans une société de médias, je veux classer mes visiteurs web et mobiles non authentifiés par genres favoris, afin de leur proposer du contenu personnalisé sur tous les canaux.

### Cas d’utilisation #3

En tant qu&#39;annonceur pour une compagnie aérienne, je veux m&#39;assurer que je classe mon audience en fonction de son intérêt pour les destinations de voyage, afin que je puisse leur faire de la publicité en temps réel, dans un court intervalle de reciblage.

### Cas d’utilisation #4

En tant qu&#39;annonceur, je souhaite classer mon public propriétaire en temps réel, afin de pouvoir réagir rapidement aux informations de tendance.

### Cas d’utilisation #5

En tant que marketeur, je souhaite prédire la phase de parcours client dans laquelle se trouvent les visiteurs de mon site web, telle que la découverte, l’engagement, l’achat ou la rétention, afin de pouvoir les cibler en conséquence.

### Cas d’utilisation #6

En tant que société de médias, je souhaite catégoriser mon public, de sorte que je puisse vendre mon espace publicitaire à des prix très élevés, tout en proposant à mes visiteurs des publicités pertinentes.

## Fonctionnement des [!UICONTROL Predictive Audiences] modèles {#how-predictive-audiences-models-work}

Lorsque vous créez un modèle [!UICONTROL Predictive Audiences], vous procédez comme suit :

1. Tout d’abord, vous sélectionnez au moins deux caractéristiques ou deux segments qui définiront vos personas.
1. Vous choisissez ensuite une caractéristique ou un segment qui définit l’audience cible que vous souhaitez classer.
1. Enfin, vous choisissez un nom pour le modèle, une source de données qui stockera les segments prédictifs et une valeur [!UICONTROL Profile Merge Rule] pour le modèle.

### Critères de sélection des personas {#selection-personas}

Vous pouvez choisir l’un de vos segments ou caractéristiques propriétaires pour définir vos personas. Cependant, pour des résultats optimaux, voici un ensemble de bonnes pratiques recommandées :

* Choisissez vos caractéristiques de persona ou vos segments de sorte que chaque persona dispose d’au moins quelques centaines [d’identifiants d’appareil](../../reference/ids-in-aam.md).
* Si vos caractéristiques sont basées sur des [identifiants multi-appareils](../../reference/ids-in-aam.md), vous pouvez les encapsuler dans des segments avec des [règles de fusion de profils](../profile-merge-rules/merge-rules-overview.md) qui utilisent des [identifiants d’appareil](../../reference/ids-in-aam.md), tels que [!UICONTROL Device Graph]. Cela permet de s’assurer qu’il existe suffisamment d’[identifiants d’appareil](../../reference/ids-in-aam.md) dont l’algorithme peut tirer des leçons.
* Nous vous recommandons de choisir des caractéristiques ou des segments simples pour vos personas, composés de 1 à 3 caractéristiques.
* Choisissez des caractéristiques de ligne de base ou des segments qui présentent un chevauchement minimal.
* Assurez-vous de capturer des caractéristiques granulaires dans vos propriétés numériques.

### Critères de sélection de l’audience cible {#selection-audience}

Selon votre cas d’utilisation, que vous souhaitiez classer les utilisateurs en temps réel, par lots ou les deux, choisissez une audience cible ([!UICONTROL trait] ou [!UICONTROL segment]) qui a une population totale et/ou en temps réel significative. Tout comme pour la sélection de persona, nous recommandons que votre audience cible [!UICONTROL trait] ou [!UICONTROL segment] ait des utilisateurs avec des profils riches (ensembles riches de [!UICONTROL traits]).

Lors de la sélection de l’audience cible, analysez votre cas d’utilisation et décidez quels types d’ID vous souhaitez classer : [!UICONTROL device IDs] ou [!UICONTROL cross-device IDs]. [!UICONTROL Profile Merge Rule] que vous sélectionnez lors de la création du modèle définit les données qui seront utilisées pour placer chaque utilisateur dans la [!UICONTROL segments] prédictive.

Il est recommandé de choisir un [!UICONTROL Profile Merge Rule] ayant la même configuration que votre audience cible [!UICONTROL Profile Merge Rule] ou un qui inclut le type de profil (profil de périphérique ou profil authentifié) de votre audience cible.

### [!UICONTROL Predictive Audiences] Phase de formation du modèle  {#model-training}

Avant de pouvoir classer votre audience propriétaire en différentes personnes, l’algorithme doit s’entraîner sur vos données.

Pour chaque personnage que vous définissez, l’algorithme analyse son audience respective et évalue toute activité de caractéristique en temps réel et/ou intégrée pour ses utilisateurs au cours des 30 derniers jours.
Cette étape se produit une fois toutes les 24 heures pour tenir compte des modifications apportées à votre audience propriétaire.

### [!UICONTROL Predictive Audiences] Phase de classification de modèle  {#model-classification}

Pour la classification des audiences en temps réel et par lots, le modèle vérifie d’abord si un utilisateur appartient à l’audience cible. Si l’utilisateur est admissible pour l’audience cible et n’appartient à aucune des personnes, le modèle lui affecte un score de qualification de persona.

Lors de l’évaluation d’audiences propriétaires et de l’attribution de scores, le modèle utilise la valeur par défaut **[!UICONTROL Profile Merge Rule]** définie dans votre compte. Enfin, le visiteur est classé dans la personne pour laquelle il a reçu le meilleur score.

![predictive-audiences-graph](assets/predictive-audiences-graph.png)

## Considérations et limites {#considerations}

>[!IMPORTANT]
> Lisez attentivement cette section avant de passer à la phase de mise en oeuvre.

Lors de la configuration de vos modèles [!UICONTROL Predictive Audiences], gardez à l’esprit les considérations et limitations suivantes :

* Vous pouvez créer jusqu’à 10 modèles [!UICONTROL Predictive Audiences]. 
* Pour chaque modèle, vous pouvez choisir jusqu’à 50 caractéristiques/segments de base.
* Les données de deuxième et de troisième niveau ne sont actuellement pas prises en charge dans [!UICONTROL Predictive Audiences].
* [!UICONTROL Predictive Audiences] effectue une classification d’audience en fonction de vos caractéristiques propriétaires, à partir de toutes vos sources de données propriétaires.
* L’évaluation des segments pour [!UICONTROL Predictive Audiences] utilise la balise **[!UICONTROL Profile Merge Rule]** que vous choisissez lors de la création du modèle. Pour en savoir plus sur [!UICONTROL Profile Merge Rules], consultez la [documentation ](../profile-merge-rules/merge-rules-overview.md) dédiée.
* Certaines caractéristiques et certains segments ne sont pas pris en charge en tant que lignes de base ou audiences cibles. [!UICONTROL Predictive Audiences] les modèles ne seront pas enregistrés lors du choix de l’une des lignes de base ou des audiences cibles suivantes :
   * les caractéristiques prédictives et les segments créés avec des caractéristiques prédictives ;
   * [Caractéristiques ou segments Adobe Experience ](../integration/../../integration/integration-aep/aam-aep-audience-sharing.md) Platform ;
   * les caractéristiques algorithmiques ;
   * Caractéristiques secondaires et tierces.
* [!UICONTROL Predictive Audience] [!UICONTROL segments] ne peut pas être utilisé dans  [!UICONTROL Audience Lab].

## [!UICONTROL Data Export Controls] {#dec}

Les segments prédictifs créés par les modèles [!UICONTROL Predictive Audiences] héritent des [contrôles des exportations de données](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-export-controls.html) des sources de données propriétaires suivantes :

1. Source de données propriétaire que vous choisissez lors de la création du modèle.
1. Sources de données propriétaires de votre audience cible. Plus précisément, les contrôles des exportations de données des [!UICONTROL traits] ou [!UICONTROL segments] qui constituent votre audience cible.
1. [Contrôles des exportations de données](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-export-controls.html) de la [!UICONTROL Profile Merge Rule] que vous avez sélectionnée pour le modèle.

Les [!UICONTROL traits] et [!UICONTROL segments] prédictifs nouvellement créés auront les mêmes restrictions de confidentialité que l’union des sources de données propriétaires décrites ci-dessus.

Les caractéristiques qui comportent des restrictions supplémentaires qui ne font pas partie des restrictions de confidentialité des segments [!UICONTROL Predictive Audiences] seront exclues de la phase de formation et n’auront pas d’influence sur le modèle.

## [!UICONTROL Profile Merge Rules] {#pmr}

Tous les segments prédictifs se verront attribuer le [!UICONTROL Profile Merge Rule] que vous avez sélectionné lors de la création du modèle. Le [!UICONTROL Profile Merge Rule] que vous choisissez est important pour les raisons suivantes :

* Il définit les appareils et/ou les profils authentifiés à prendre en compte lorsque le modèle analyse l’influent [!UICONTROL traits], au moment de classer un utilisateur dans une [!UICONTROL segment] prédictive.
* Il détermine quels types [!UICONTROL trait] (niveau périphérique ou niveau multi-périphérique) doivent être utilisés pendant l’étape de formation du modèle et sont affichés comme étant influents [!UICONTROL traits]. Les [!UICONTROL segments] prédictifs sont des sous-ensembles de votre audience cible.
   * Si l’audience cible est un segment, nous vous recommandons de sélectionner le même [!UICONTROL Profile Merge Rule] pour le modèle que celui affecté à votre audience cible, ou une [!UICONTROL Profile Merge Rule] qui inclut le type de profil de votre audience cible.
   * Si l’audience cible est une [!UICONTROL trait], nous vous recommandons de sélectionner une [!UICONTROL Profile Merge Rule] pouvant accéder au même type de données que la caractéristique de l’audience cible (données de profil de l’appareil ou données de profil multi-appareils).
* [!UICONTROL Profile Merge Rules] l’utilisation des  [!UICONTROL Current Authenticated Profiles] options  [!UICONTROL No Device Profile] et n’est prise en charge que pour la classification d’audience en temps réel. Pour plus d’informations, voir [Options des règles de fusion de profils définies](../profile-merge-rules/merge-rule-definitions.md).

La sélection d’une balise [!UICONTROL Profile Merge Rule] qui utilise à la fois les données de l’appareil et les données entre appareils optimise le nombre de [!UICONTROL traits] pouvant être utilisés pour la formation du modèle et la classification des utilisateurs dans la variable prédictive [!UICONTROL segments].

## [!UICONTROL Role-Based Access Controls] {#rbac}

Les caractéristiques et les segments que vous choisissez pour les personnages et la classification des audiences sont soumis à l’Audience Manager [Contrôles d’accès en fonction du rôle](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/administration/administration-overview.html).

Les utilisateurs de l’Audience Manager ne peuvent sélectionner que des caractéristiques ou des segments pour les personnes et les audiences cibles, qu’ils ont la [autorisation d’afficher](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/administration/administration-overview.html#wild-card-permissions).
