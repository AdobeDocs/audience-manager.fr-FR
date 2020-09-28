---
description: Les audiences prédictives vous aident à classer les audiences inconnues en personas distinctes en temps réel à l’aide de la science des données.
seo-description: Les audiences prédictives vous aident à classer les audiences inconnues en personas distinctes en temps réel à l’aide de la science des données.
seo-title: Présentation des audiences prédictives
solution: Audience Manager
title: Audiences prédictives d’Audience Manager
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: 1df6e8a76e5eae85483820926474ebc8633d5591
workflow-type: tm+mt
source-wordcount: '1551'
ht-degree: 7%

---


# [!UICONTROL Predictive Audiences] Présentation {#predictive-audiences}

[!UICONTROL Predictive Audiences] permet de classer une audience inconnue en différentes personnes, en temps réel, à l’aide de techniques avancées de science des données.

>[!IMPORTANT]
>Cet article contient la documentation du produit destinée à vous guider tout au long de la configuration et de l’utilisation de cette fonction. Rien dans ce document n&#39;est un conseil juridique. Veuillez consulter votre propre conseiller juridique pour obtenir des conseils juridiques.

Dans un contexte marketing, une persona est un segment d’audience défini par des visiteurs, des utilisateurs ou des acheteurs potentiels qui partagent un ensemble spécifique de caractéristiques comme des données démographiques, des habitudes de navigation, un historique des achats, etc.

Les modèles de [!UICONTROL Predictive Audiences] approfondissent encore ce concept en vous permettant d’utiliser les capacités d’apprentissage automatique d’Audience Manager pour classer les audiences inconnues en différentes personas. Pour ce faire, Audience Manager calcule la propension de votre audience propriétaire inconnue pour un ensemble d’audiences propriétaires connues.

Lorsque vous créez un [!UICONTROL Predictive Audiences] modèle, la première étape consiste à choisir les caractéristiques ou segments de base par lesquels votre audience de cible doit être classée. Ces caractéristiques ou segments définissent vos personnages.

Au cours de la phase d’évaluation, le modèle crée un nouveau [!UICONTROL Predictive Audiences] segment pour chaque caractéristique ou segment que vous avez défini comme ligne de base. La prochaine fois que l’Audience Manager voit un visiteur de votre audience de cible qui n’est pas classé pour une personne (qui ne correspond à aucun de vos traits ou segments de base), le modèle détermine à quel segment de prévision le visiteur doit appartenir et ajoute le visiteur à ce segment. [!UICONTROL Predictive Audiences]

Vous pouvez identifier les segments prédictifs créés par le modèle dans la [!UICONTROL Segments] page. Chaque [!UICONTROL Predictive Audiences] modèle comporte son propre dossier sous le [!UICONTROL Predictive Audiences] dossier et vous pouvez afficher les segments de chaque modèle en cliquant sur le dossier du modèle.

![audiences-prédictives-segments](assets/predictive-audiences-segments.png)

## Cas d’utilisation {#use-cases}

Pour vous aider à mieux comprendre comment et quand vous pouvez utiliser [!UICONTROL Predictive Audiences], voici quelques cas d&#39;utilisation que les clients d&#39;Audience Manager peuvent résoudre en utilisant cette fonctionnalité.

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

Lorsque vous créez un [!UICONTROL Predictive Audiences] modèle, vous suivez trois étapes :

1. Tout d’abord, vous sélectionnez au moins deux caractéristiques ou deux segments qui définiront vos personnages.
1. Ensuite, vous choisissez une caractéristique ou un segment qui définit l’audience de cible à classifier.
1. Enfin, vous choisissez un nom pour le modèle, une source de données qui stockera les segments prédictifs et un nom [!UICONTROL Profile Merge Rule] pour le modèle.

### Critères de sélection pour les personnes {#selection-personas}

Vous pouvez choisir l’une de vos caractéristiques ou segments propriétaires pour définir vos personnalités. Cependant, pour des résultats optimaux, voici un ensemble de bonnes pratiques recommandées :

* Choisissez vos caractéristiques ou segments de personnage de sorte que chaque personne dispose d’au moins quelques centaines d’ID [de](../../reference/ids-in-aam.md)périphérique.
* Si vos caractéristiques sont basées sur des identifiants [](../../reference/ids-in-aam.md)inter-périphériques, vous pouvez les encapsuler dans des segments avec des règles [de fusion de](../profile-merge-rules/merge-rules-overview.md) Profils qui utilisent des identifiants [de](../../reference/ids-in-aam.md)périphérique, tels que [!UICONTROL Device Graph]. Cela permet de s’assurer qu’il y a suffisamment d’ID [de](../../reference/ids-in-aam.md) périphérique dont l’algorithme peut tirer des leçons.
* Nous vous recommandons de choisir des caractéristiques ou des segments simples pour vos personnages, composés de 1 à 3 caractéristiques.
* Choisissez des caractéristiques ou des segments de base qui présentent un chevauchement minimal.
* Assurez-vous de capturer des caractéristiques granulaires sur vos propriétés numériques.

### Critères de sélection pour l&#39;Audience des Cibles {#selection-audience}

Comme pour la sélection de personnes, vous devez choisir votre ou [!UICONTROL trait] celui qui définit votre audience de cible de telle sorte qu’il dispose d’utilisateurs en temps réel avec de riches ensembles de [!UICONTROL segment] [!UICONTROL traits]données, pour la classification dans la personne appropriée.

Lors de la sélection de l’audience de cible, analysez votre cas d’utilisation et décidez quels types d’ID vous souhaitez classer : [!UICONTROL device IDs] ou [!UICONTROL cross-device IDs]. Le [!UICONTROL Profile Merge Rule] que vous sélectionnez lors de la création du modèle définit les données qui seront utilisées pour placer chaque utilisateur dans le prédictif [!UICONTROL segments].

En règle générale, il est recommandé de choisir un [!UICONTROL Profile Merge Rule] qui a la même configuration que votre audience de cible [!UICONTROL Profile Merge Rule], ou un qui inclut le type de profil (profil de périphérique ou profil authentifié) de votre audience de cible.

### [!UICONTROL Predictive Audiences] Phase de formation du modèle {#model-training}

Avant que l’algorithme puisse classifier votre audience propriétaire en personnes appropriées, il doit s’entraîner sur vos données.

Pour chaque personne que vous définissez, l’algorithme analyse son audience respective et évalue toute activité de caractéristiques en temps réel et/ou intégrée pour ses utilisateurs au cours des 30 derniers jours.
Cette étape a lieu une fois toutes les 24 heures, afin de tenir compte des modifications apportées à votre audience propriétaire.

### [!UICONTROL Predictive Audiences] Phase de classification du modèle {#model-classification}

Lorsqu’un visiteur qui fait partie de l’audience de cible est vu en temps réel, le modèle évalue si le visiteur fait partie des personnes définies. Pour chaque visiteur qui n&#39;appartient à aucune personnalité, le modèle attribue un score de qualification personnelle.

Lors de l’évaluation des audiences propriétaires et de l’attribution de scores, le modèle utilise la valeur par défaut **[!UICONTROL Profile Merge Rule]** définie dans votre compte. Enfin, le visiteur est classé dans la personne pour laquelle il a obtenu le score le plus élevé.

![graphique à audiences prédictives](assets/predictive-audiences-graph.png)

## Considérations et limites {#considerations}

>[!IMPORTANT]
> Lisez attentivement cette section avant de passer à la phase de mise en oeuvre.

Lors de la configuration de vos [!UICONTROL Predictive Audiences] modèles, gardez à l’esprit les considérations et limitations suivantes :

* Vous pouvez créer jusqu’à 10 modèles [!UICONTROL Predictive Audiences]. 
* Pour chaque modèle, vous pouvez choisir jusqu’à 50 caractéristiques / segments de base.
* Actuellement, les données tierces et secondaires ne sont pas prises en charge dans [!UICONTROL Predictive Audiences].
* La classification des Audiences est effectuée uniquement pour les audiences propriétaires en temps réel. La classification des audiences propriétaires intégrée peut être prise en charge dans une prochaine mise à jour.
   >[!IMPORTANT]
   > Si vous ajoutez une caractéristique prédictive à un segment normal, elle devient un segment prédictif. Par conséquent, tous les profils associés ne sont pas segmentés.

   >[!IMPORTANT]
   > Actuellement, les segments prédictifs ne peuvent être activés que dans les destinations en temps réel. Les segments prédictifs [!UICONTROL Total Segment Population] et [!UICONTROL Addressable Audience] sont affichés sous la forme 0 et les transferts [de données sortantes](../../integration/receiving-audience-data/batch-outbound-transfers/batch-outbound-overview.md) par lot ne sont pas pris en charge pour [!UICONTROL Predictive Audiences]. Ce comportement changera dans une prochaine mise à jour.
* [!UICONTROL Predictive Audiences] effectue une classification des audiences en fonction de vos caractéristiques propriétaires, à partir de toutes vos sources de données propriétaires.
* L’évaluation des segments pour [!UICONTROL Predictive Audiences] utilise la **[!UICONTROL Profile Merge Rule]** méthode choisie lors de la création du modèle. Pour en savoir plus sur [!UICONTROL Profile Merge Rules] consultez la [documentation](../profile-merge-rules/merge-rules-overview.md)qui vous est consacrée.
* Certaines caractéristiques et certains segments ne sont pas pris en charge en tant que lignes de base ou audiences de cible. [!UICONTROL Predictive Audiences] les modèles ne peuvent pas être enregistrés lorsque vous sélectionnez l&#39;une des audiences suivantes comme lignes de base ou cible :
   * Caractéristiques prédictives et segments créés avec des caractéristiques prédictives ;
   * [Caractéristiques ou segments de Adobe Experience Platform](../integration/../../integration/integration-aep/aam-aep-audience-sharing.md) ;
   * Caractéristiques algorithmiques ;
   * Caractéristiques des deuxième et troisième parties.

## [!UICONTROL Data Export Controls] {#dec}

Les segments prédictifs créés par [!UICONTROL Predictive Audiences] des modèles héritent des contrôles [d’exportation des](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-export-controls.html) données à partir des sources de données propriétaires suivantes :

1. Source de données propriétaire que vous choisissez lors de la création du modèle.
1. Sources de données propriétaires de votre audience de cible. Plus précisément, les contrôles d’exportation des données du ou [!UICONTROL traits] [!UICONTROL segments] qui constituent votre audience de cible.
1. Contrôles [](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-export-controls.html) d&#39;exportation de données du [!UICONTROL Profile Merge Rule] modèle sélectionné.

Le nouveau prédictif [!UICONTROL traits] et [!UICONTROL segments] aura les mêmes restrictions de confidentialité que l’union des sources de données propriétaires décrites ci-dessus.

Les caractéristiques qui comportent des restrictions supplémentaires qui ne font pas partie des restrictions de confidentialité des [!UICONTROL Predictive Audiences] segments seront exclues de la phase de formation et n’auront pas d’influence sur le modèle.

## [!UICONTROL Profile Merge Rules] {#pmr}

Tous les segments prédictifs se verront attribuer la valeur [!UICONTROL Profile Merge Rule] sélectionnée lors de la création du modèle. Le [!UICONTROL Profile Merge Rule] choix que vous choisissez est important pour les raisons suivantes :

* Il définit les périphériques et/ou les profils authentifiés à prendre en compte lorsque le modèle analyse l’influent [!UICONTROL traits], au moment de classer un utilisateur dans une prévision [!UICONTROL segment].
* Il détermine quels [!UICONTROL trait] types (au niveau du périphérique ou au niveau de plusieurs périphériques) doivent être utilisés au cours de l&#39;étape de formation du modèle et sont apparus comme influents [!UICONTROL traits]. Les prédictifs [!UICONTROL segments] sont des sous-ensembles de votre audience de cible.
   * Si l&#39;audience de cible est un segment, nous vous recommandons de sélectionner le même [!UICONTROL Profile Merge Rule] pour le modèle que celui affecté à votre audience de cible, ou un [!UICONTROL Profile Merge Rule] qui inclut le type de profil de votre audience de cible.
   * Si l&#39;audience de cible est une [!UICONTROL trait], nous vous recommandons de sélectionner une [!UICONTROL Profile Merge Rule] qui peut accéder au même type de données que la caractéristique d&#39;audience de cible (données de profil de périphérique ou données de profil sur plusieurs périphériques).

La sélection d’un [!UICONTROL Profile Merge Rule] périphérique qui utilise à la fois les données de périphérique et les données inter-périphériques permet d’augmenter le nombre de [!UICONTROL traits] modèles pouvant être utilisés pour la formation au modèle et la classification des utilisateurs dans la prévision [!UICONTROL segments].

## [!UICONTROL Role-Based Access Controls] {#rbac}

Les caractéristiques et les segments que vous choisissez pour les personnages et la classification des audiences sont soumis à des Contrôles d&#39;accès [basés sur les](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/administration/administration-overview.html)rôles d’Audience Manager.

Les utilisateurs d’Audience Manager ne peuvent sélectionner que des caractéristiques ou des segments pour les personnes et les audiences de cible, qu’ils ont l’ [autorisation de vue](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/administration/administration-overview.html#wild-card-permissions).
