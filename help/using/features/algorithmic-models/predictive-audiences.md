---
description: Les audiences prédictives vous aident à classer les audiences inconnues en personas distinctes en temps réel à l’aide de la science des données.
seo-description: Les audiences prédictives vous aident à classer les audiences inconnues en personas distinctes en temps réel à l’aide de la science des données.
seo-title: Présentation des audiences prédictives
solution: Audience Manager
title: Audiences prédictives d’Audience Manager
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: 3c39ef38d2833d5d706641f70649251d79b2ee6f
workflow-type: tm+mt
source-wordcount: '1511'
ht-degree: 8%

---


# [!UICONTROL Predictive Audiences] Présentation {#predictive-audiences}

[!UICONTROL Predictive Audiences] permet de classer une audience inconnue en différentes personnes, en temps réel, à l’aide de techniques avancées de science des données.

>[!IMPORTANT]
>Cet article contient la documentation du produit destinée à vous guider tout au long de la configuration et de l’utilisation de cette fonction. Rien dans ce document n&#39;est un conseil juridique. Veuillez consulter votre propre conseiller juridique pour obtenir des conseils juridiques.

Dans un contexte marketing, une persona est un segment d’audience défini par des visiteurs, des utilisateurs ou des acheteurs potentiels qui partagent un ensemble spécifique de caractéristiques comme des données démographiques, des habitudes de navigation, un historique des achats, etc.

Les modèles de [!UICONTROL Predictive Audiences] approfondissent encore ce concept en vous permettant d’utiliser les capacités d’apprentissage automatique d’Audience Manager pour classer les audiences inconnues en différentes personas. Pour ce faire, Audience Manager calcule la propension de votre audience propriétaire inconnue pour un ensemble d’audiences propriétaires connues.

Lorsque vous créez un modèle [!UICONTROL Predictive Audiences], la première étape consiste à choisir les caractéristiques ou segments de base par lesquels votre audience de cible doit être classée. Ces caractéristiques ou segments définissent vos personnages.

Au cours de la phase d’évaluation, le modèle crée un nouveau segment [!UICONTROL Predictive Audiences] pour chaque caractéristique ou segment que vous avez défini comme ligne de base. La prochaine fois que l&#39;Audience Manager voit un visiteur de votre audience de cible qui n&#39;est pas classé pour une personne (ne correspond à aucun de vos traits ou segments de base), le modèle [!UICONTROL Predictive Audiences] détermine à quels segments de prévision le visiteur doit appartenir et ajoute le visiteur à ce segment.

Vous pouvez identifier les segments prédictifs créés par le modèle, dans la page [!UICONTROL Segments]. Chaque modèle [!UICONTROL Predictive Audiences] possède son propre dossier sous le dossier [!UICONTROL Predictive Audiences] et vous pouvez afficher les segments de chaque modèle en cliquant sur le dossier du modèle.

![audiences-prédictives-segments](assets/predictive-audiences-segments.png)

## Cas d’utilisation {#use-cases}

Pour vous aider à mieux comprendre comment et quand utiliser [!UICONTROL Predictive Audiences], voici quelques cas d&#39;utilisation que les clients d&#39;Audience Manager peuvent résoudre en utilisant cette fonctionnalité.

### Cas d’utilisation 1

En tant que spécialiste du marketing dans une société de commerce électronique, je souhaite classer tous mes visiteurs Web et mobiles en différentes catégories d&#39;affinité de marque, afin de pouvoir personnaliser leur expérience utilisateur.

### Cas d’utilisation no 2

En tant que spécialiste du marketing dans une société multimédia, je souhaite classer mes visiteurs non authentifiés du web et des mobiles par genres favoris, afin de leur suggérer un contenu personnalisé sur tous les canaux.

### Cas d’utilisation no 3

En tant qu&#39;annonceur d&#39;une société aérienne, je veux m&#39;assurer que je classe mon audience en fonction de leur intérêt pour les destinations de voyage, afin de pouvoir leur faire de la publicité en temps réel, dans une courte fenêtre de reciblage.

### Cas d’utilisation no 4

En tant qu&#39;annonceur, je veux classer mon audience propriétaire en temps réel, afin de pouvoir réagir rapidement aux informations de tendance.

### Cas d’utilisation no 5

En tant que spécialiste du marketing, je veux prédire dans quelle phase de voyage des clients se trouvent mes visiteurs de site Web, tels que la découverte, l&#39;engagement, l&#39;achat ou la rétention, afin que je puisse les cible en conséquence.

### Cas d’utilisation no 6

En tant que société des médias, je veux classer mon audience par catégorie, afin de pouvoir vendre mon espace publicitaire à des prix très élevés, tout en offrant à mes visiteurs des annonces pertinentes.

## Fonctionnement des [!UICONTROL Predictive Audiences] modèles {#how-predictive-audiences-models-work}

Lorsque vous créez un modèle [!UICONTROL Predictive Audiences], vous effectuez trois étapes :

1. Tout d’abord, vous sélectionnez au moins deux caractéristiques ou deux segments qui définiront vos personnages.
1. Ensuite, vous choisissez une caractéristique ou un segment qui définit l’audience de cible à classifier.
1. Enfin, vous choisissez un nom pour le modèle, une source de données qui stockera les segments prédictifs et un [!UICONTROL Profile Merge Rule] pour le modèle.

### Critères de sélection pour les personnalités {#selection-personas}

Vous pouvez choisir l’une de vos caractéristiques ou segments propriétaires pour définir vos personnalités. Cependant, pour des résultats optimaux, voici un ensemble de bonnes pratiques recommandées :

* Choisissez vos caractéristiques ou segments de personnalité afin que chaque personne ait au moins quelques centaines d&#39;ID de périphérique [](../../reference/ids-in-aam.md).
* Si vos caractéristiques sont basées sur [des ID inter-périphériques](../../reference/ids-in-aam.md), vous pouvez les encapsuler dans des segments avec [des règles de fusion de Profil](../profile-merge-rules/merge-rules-overview.md) qui utilisent [des ID d&#39;unité](../../reference/ids-in-aam.md), par exemple [!UICONTROL Device Graph]. Ainsi, il y aura suffisamment d&#39;[ID de périphérique](../../reference/ids-in-aam.md) dont l&#39;algorithme pourra tirer les leçons.
* Nous vous recommandons de choisir des caractéristiques ou des segments simples pour vos personnages, composés de 1 à 3 caractéristiques.
* Choisissez des caractéristiques ou des segments de base qui présentent un chevauchement minimal.
* Assurez-vous de capturer des caractéristiques granulaires sur vos propriétés numériques.

### Critères de sélection pour l&#39;Audience de Cible {#selection-audience}

Selon votre cas d’utilisation, que vous souhaitiez classer les utilisateurs en temps réel, par lot ou les deux, choisissez une audience de cible ([!UICONTROL trait] ou [!UICONTROL segment]) qui possède une population importante en temps réel et/ou totale. Comme pour la sélection de personnes, nous vous recommandons de faire en sorte que votre audience de cible [!UICONTROL trait] ou [!UICONTROL segment] contienne des utilisateurs avec des profils riches (ensembles riches de [!UICONTROL traits]).

Lors de la sélection de l’audience de cible, analysez votre cas d’utilisation et décidez quels types d’ID vous souhaitez classer : [!UICONTROL device IDs] ou [!UICONTROL cross-device IDs]. Le [!UICONTROL Profile Merge Rule] que vous sélectionnez lors de la création du modèle définit les données qui seront utilisées pour placer chaque utilisateur dans le [!UICONTROL segments] prédictif.

En règle générale, il est recommandé de choisir un [!UICONTROL Profile Merge Rule] qui possède la même configuration que votre audience de cible [!UICONTROL Profile Merge Rule], ou qui inclut le type de profil (profil de périphérique ou profil authentifié) de votre audience de cible.

### [!UICONTROL Predictive Audiences] Phase de formation du modèle  {#model-training}

Avant que l’algorithme puisse classifier votre audience propriétaire en personnes appropriées, il doit s’entraîner sur vos données.

Pour chaque personne que vous définissez, l’algorithme analyse son audience respective et évalue toute activité de caractéristiques en temps réel et/ou intégrée pour ses utilisateurs au cours des 30 derniers jours.
Cette étape a lieu une fois toutes les 24 heures, afin de tenir compte des modifications apportées à votre audience propriétaire.

### [!UICONTROL Predictive Audiences] Phase de classification du modèle  {#model-classification}

Pour la classification des audiences en temps réel et par lot, le modèle vérifie d’abord si un utilisateur appartient à l’audience de cible. Si l&#39;utilisateur est admissible pour l&#39;audience de cible et n&#39;appartient à aucune des personnes, le modèle lui attribue un score de qualification personnelle.

Lors de l’évaluation des audiences propriétaires et de l’attribution de scores, le modèle utilise le **[!UICONTROL Profile Merge Rule]** par défaut défini dans votre compte. Enfin, le visiteur est classé dans la personne pour laquelle il a obtenu le score le plus élevé.

![graphique à audiences prédictives](assets/predictive-audiences-graph.png)

## Considérations et limites {#considerations}

>[!IMPORTANT]
> Lisez attentivement cette section avant de passer à la phase de mise en oeuvre.

Lors de la configuration de vos modèles [!UICONTROL Predictive Audiences], gardez à l’esprit les considérations et limitations suivantes :

* Vous pouvez créer jusqu’à 10 modèles [!UICONTROL Predictive Audiences]. 
* Pour chaque modèle, vous pouvez choisir jusqu’à 50 caractéristiques / segments de base.
* Les données tierces et secondaires ne sont actuellement pas prises en charge dans [!UICONTROL Predictive Audiences].
* [!UICONTROL Predictive Audiences] effectue une classification des audiences en fonction de vos caractéristiques propriétaires, à partir de toutes vos sources de données propriétaires.
* L&#39;évaluation des segments pour [!UICONTROL Predictive Audiences] utilise le **[!UICONTROL Profile Merge Rule]** que vous choisissez lors de la création du modèle. Pour en savoir plus sur [!UICONTROL Profile Merge Rules], consultez la [documentation ](../profile-merge-rules/merge-rules-overview.md) qui lui est consacrée.
* Certaines caractéristiques et certains segments ne sont pas pris en charge en tant que lignes de base ou audiences de cible. [!UICONTROL Predictive Audiences] les modèles ne peuvent pas être enregistrés lorsque vous sélectionnez l&#39;une des audiences suivantes comme lignes de base ou cible :
   * Caractéristiques prédictives et segments créés avec des caractéristiques prédictives ;
   * [Adobe Experience ](../integration/../../integration/integration-aep/aam-aep-audience-sharing.md) Plateformes ou segments ;
   * Caractéristiques algorithmiques ;
   * Caractéristiques des deuxième et troisième parties.
* [!UICONTROL Predictive Audience] [!UICONTROL segments] ne peut pas être utilisé dans  [!UICONTROL Audience Lab].

## [!UICONTROL Data Export Controls] {#dec}

Les segments prédictifs créés par les modèles [!UICONTROL Predictive Audiences] héritent des [contrôles d’exportation de données](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-export-controls.html) des sources de données propriétaires suivantes :

1. Source de données propriétaire que vous choisissez lors de la création du modèle.
1. Sources de données propriétaires de votre audience de cible. Plus précisément, les contrôles d&#39;exportation des données de [!UICONTROL traits] ou [!UICONTROL segments] qui constituent votre audience de cible.
1. [Contrôles d&#39;exportation de données](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-export-controls.html) du [!UICONTROL Profile Merge Rule] que vous avez sélectionné pour le modèle.

Les [!UICONTROL traits] et [!UICONTROL segments] prédictifs nouvellement créés auront les mêmes restrictions de confidentialité que l’union des sources de données propriétaires décrites ci-dessus.

Les caractéristiques qui comportent des restrictions supplémentaires qui ne font pas partie des restrictions de confidentialité des segments [!UICONTROL Predictive Audiences] seront exclues de la phase de formation et n’auront pas d’influence sur le modèle.

## [!UICONTROL Profile Merge Rules] {#pmr}

Tous les segments prédictifs se verront attribuer le [!UICONTROL Profile Merge Rule] que vous avez sélectionné lors de la création du modèle. Le [!UICONTROL Profile Merge Rule] que vous choisissez est important pour les raisons suivantes :

* Il définit les périphériques et/ou les profils authentifiés à prendre en compte lorsque le modèle analyse l&#39;influent [!UICONTROL traits], au moment de classer un utilisateur dans une prévision [!UICONTROL segment].
* Il régit les types [!UICONTROL trait] (au niveau du périphérique ou au niveau de plusieurs périphériques) qui doivent être utilisés pendant l&#39;étape de formation du modèle et qui apparaissent comme influents [!UICONTROL traits]. Les [!UICONTROL segments] prédictifs sont des sous-ensembles de votre audience de cible.
   * Si l&#39;audience de cible est un segment, nous vous recommandons de sélectionner le même [!UICONTROL Profile Merge Rule] pour le modèle que celui affecté à votre audience de cible, ou un [!UICONTROL Profile Merge Rule] qui inclut le type de profil de votre audience de cible.
   * Si l&#39;audience de cible est une [!UICONTROL trait], nous vous recommandons de sélectionner une [!UICONTROL Profile Merge Rule] qui peut accéder au même type de données que la caractéristique d&#39;audience de cible (données de profil de périphérique ou données de profil sur plusieurs périphériques).
* [!UICONTROL Profile Merge Rules] l’utilisation des  [!UICONTROL Current Authenticated Profiles] options et  [!UICONTROL No Device Profile] des options n’est prise en charge que pour la classification des audiences en temps réel. Pour plus d&#39;informations, voir [Options de règles de fusion de Profils définies](../profile-merge-rules/merge-rule-definitions.md).

La sélection d&#39;un [!UICONTROL Profile Merge Rule] qui utilise à la fois les données de périphérique et les données inter-périphériques permet d&#39;augmenter le nombre de [!UICONTROL traits] qui pourraient être utilisés pour la formation du modèle et la classification des utilisateurs dans le [!UICONTROL segments] prédictif.

## [!UICONTROL Role-Based Access Controls] {#rbac}

Les caractéristiques et les segments que vous choisissez pour les personnages et la classification des audiences sont sujets à l&#39;Audience Manager [Contrôles d&#39;accès basés sur le rôle](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/administration/administration-overview.html).

Les utilisateurs d&#39;Audience Manager ne peuvent sélectionner que des caractéristiques ou des segments pour les personnes et les audiences de cible, qu&#39;ils ont [l&#39;autorisation de vue](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/administration/administration-overview.html#wild-card-permissions).
