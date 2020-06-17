---
description: Les Audiences prédictives vous aident à classer les audiences inconnues en différentes personnes en temps réel, en utilisant la science des données.
seo-description: Les Audiences prédictives vous aident à classer les audiences inconnues en différentes personnes en temps réel, en utilisant la science des données.
seo-title: Présentation des Audiences prédictives
solution: Audience Manager
title: Audiences prédictives Audience Manager
translation-type: tm+mt
source-git-commit: 4df2a7536155d42133c0873ed4e3376eb24cba1a
workflow-type: tm+mt
source-wordcount: '1275'
ht-degree: 0%

---


# [!UICONTROL Predictive Audiences] Aperçu {#predictive-audiences}

[!UICONTROL Predictive Audiences] permet de classer une audience inconnue en différentes personnes, en temps réel, à l’aide de techniques avancées de science des données.

>[!IMPORTANT]
>Cet article contient la documentation du produit destinée à vous guider tout au long de la configuration et de l’utilisation de cette fonction. Rien dans ce document n&#39;est un conseil juridique. Veuillez consulter votre propre conseiller juridique pour obtenir des conseils juridiques.

Dans un contexte marketing, une personne est un segment d’audience défini par des visiteurs, des utilisateurs ou des acheteurs potentiels, qui partagent un ensemble spécifique de caractéristiques, telles que la démographie, les habitudes de navigation, l’historique des achats, etc.

[!UICONTROL Predictive Audiences] les modèles poussent ce concept encore plus loin, en vous permettant d’utiliser les capacités d’apprentissage automatique des Audiences Manager pour classer les audiences inconnues en personnes distinctes. L’Audience Manager vous permet d’y parvenir en calculant la propension de votre audience propriétaire inconnue pour un ensemble d’audiences propriétaires connues.

Lorsque vous créez un [!UICONTROL Predictive Audiences] modèle, la première étape consiste à choisir les caractéristiques ou segments de base par lesquels votre audience de cible doit être classée. Ces caractéristiques ou segments définissent vos personnages.

Pendant la phase d’évaluation, le modèle crée un nouveau [!UICONTROL Predictive Audiences] segment pour chaque caractéristique ou segment que vous avez défini comme ligne de base. La prochaine fois que l’Audience Manager voit un visiteur de votre audience de cible qui n’est pas classé pour une personne (qui ne correspond à aucun de vos traits ou segments de base), le modèle détermine à quel segment de prévision le visiteur doit appartenir et ajoute le visiteur à ce segment. [!UICONTROL Predictive Audiences]

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

## Fonctionnement des modèles d’Audiences prédictives

Lorsque vous créez un [!UICONTROL Predictive Audiences] modèle, vous suivez trois étapes :

1. Tout d’abord, vous sélectionnez au moins deux caractéristiques ou deux segments qui définiront vos personnages.
1. Ensuite, vous choisissez une caractéristique ou un segment qui définit l’audience de cible à classifier.
1. Enfin, vous choisissez un nom pour le modèle et sélectionnez une source de données qui stockera les segments prédictifs.

### Critères de sélection pour les personnes {#selection-personas}

Vous pouvez choisir l’une de vos caractéristiques ou segments propriétaires pour définir vos personnalités. Cependant, pour des résultats optimaux, voici un ensemble de bonnes pratiques recommandées :

* Choisissez vos caractéristiques ou segments de personnage de sorte que chaque personne dispose d’au moins quelques centaines d’ID [de](../../reference/ids-in-aam.md)périphérique.
* Si vos caractéristiques sont basées sur des identifiants [](../../reference/ids-in-aam.md)inter-périphériques, vous pouvez les encapsuler dans des segments avec des règles [de fusion de](../profile-merge-rules/merge-rules-overview.md) Profils qui utilisent des identifiants [de](../../reference/ids-in-aam.md)périphérique, tels que [!UICONTROL Device Graph]. Cela permet de s’assurer qu’il y a suffisamment d’ID [de](../../reference/ids-in-aam.md) périphérique dont l’algorithme peut tirer des leçons.
* Nous vous recommandons de choisir des caractéristiques ou des segments simples pour vos personnes, composés de 1 à 3 caractéristiques.
* Choisissez des caractéristiques ou des segments de base qui présentent un chevauchement minimal.
* Assurez-vous de capturer des caractéristiques granulaires sur vos propriétés numériques.

### Critères de sélection pour l&#39;Audience des Cibles {#selection-audience}

De la même manière que pour la sélection de personnes, vous devez choisir la caractéristique ou le segment qui définit votre audience de cible de telle sorte qu’il y ait des utilisateurs en temps réel avec de riches ensembles de caractéristiques, pour la classification dans la personne appropriée.

### Phase de formation du modèle d&#39;Audiences prédictives {#model-training}

Avant que l’algorithme puisse classifier votre audience propriétaire en personnes appropriées, il doit s’entraîner sur vos données.

Pour chaque personne que vous définissez, l’algorithme analyse son audience respective et évalue toute activité de caractéristiques en temps réel et/ou intégrée pour ses utilisateurs au cours des 30 derniers jours.
Cette étape a lieu une fois toutes les 24 heures, afin de tenir compte des modifications apportées à votre audience propriétaire.

### Phase de classification du modèle d&#39;Audiences prédictives {#model-classification}

Lorsqu’un visiteur qui fait partie de l’audience de cible est vu en temps réel, le modèle évalue si le visiteur fait partie des personnes définies. Pour chaque visiteur qui n&#39;appartient à aucune personnalité, le modèle attribue un score de qualification personnelle.

Lors de l’évaluation des audiences propriétaires et de l’attribution de scores, le modèle utilise la valeur par défaut **[!UICONTROL Profile Merge Rule]** définie dans votre compte. Enfin, le visiteur est classé dans la personne pour laquelle il a obtenu le score le plus élevé.

![graphique à audiences prédictives](assets/predictive-audiences-graph.png)

## Considérations et limites {#considerations}

>[!IMPORTANT]
> Lisez attentivement cette section avant de passer à la phase de mise en oeuvre.

Lors de la configuration de vos [!UICONTROL Predictive Audiences] modèles, gardez à l’esprit les considérations et limitations suivantes :

* Vous pouvez créer jusqu’à 10 [!UICONTROL Predictive Audiences] modèles.
* Pour chaque modèle, vous pouvez choisir jusqu’à 50 caractéristiques / segments de base.
* Actuellement, les données tierces et secondaires ne sont pas prises en charge dans [!UICONTROL Predictive Audiences].
* La classification des Audiences est effectuée uniquement pour les audiences propriétaires en temps réel. La classification des audiences propriétaires intégrée peut être prise en charge dans une prochaine mise à jour.
   >[!IMPORTANT]
   > Actuellement, les segments [!UICONTROL Total Segment Population] prédictifs sont affichés sous la forme 0 et les transferts [de données sortantes](../../integration/receiving-audience-data/batch-outbound-transfers/batch-outbound-overview.md) par lot ne sont pas pris en charge pour les Audiences prédictives. Ce comportement changera dans une prochaine mise à jour.
* [!UICONTROL Predictive Audiences] effectue une classification des audiences en fonction de vos caractéristiques propriétaires, à partir de toutes vos sources de données propriétaires.
* L’évaluation des segments pour [!UICONTROL Predictive Audiences] utilise la valeur par défaut **[!UICONTROL Profile Merge Rule]** que vous avez définie dans votre compte. Pour en savoir plus sur [!UICONTROL Profile Merge Rules] consultez la [documentation](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/profile-merge-rules/merge-rules-overview.html)qui vous est consacrée.
* Certaines caractéristiques et certains segments ne sont pas pris en charge en tant que lignes de base ou audiences de cible. [!UICONTROL Predictive Audiences] les modèles ne peuvent pas être enregistrés lorsque vous sélectionnez l&#39;une des audiences suivantes comme lignes de base ou cible :
   * Caractéristiques prédictives et segments créés avec des caractéristiques prédictives ;
   * [caractéristiques ou segments d&#39;Adobe Experience Platform](../integration/../../integration/integration-aep/aam-aep-audience-sharing.md) ;
   * Caractéristiques algorithmiques ;
   * Caractéristiques des deuxième et troisième parties.

## Contrôles des exportations de données{#dec}

Les segments prédictifs créés par [!UICONTROL Predictive Audiences] des modèles héritent des contrôles [d’exportation des](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-export-controls.html) données à partir des sources de données propriétaires suivantes :

1. Source de données propriétaire que vous choisissez lors de la création du modèle.
1. Sources de données propriétaires de votre audience de cible. Plus précisément, les contrôles d’exportation des données des caractéristiques ou segments qui constituent votre audience de cible.

Les caractéristiques et segments prédictifs nouvellement créés auront les mêmes restrictions de confidentialité que l’union des sources de données propriétaires décrites ci-dessus.

Les caractéristiques qui comportent des restrictions supplémentaires qui ne font pas partie des restrictions de confidentialité des [!UICONTROL Predictive Audiences] segments seront exclues de la phase de formation et n’auront pas d’influence sur le modèle.

## Contrôles d&#39;accès basés sur les rôles{#rbac}

Les caractéristiques et les segments que vous choisissez pour les personnages et la classification des audiences sont soumis à des Contrôles d&#39;accès [basés sur les](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/administration/administration-overview.html)rôles d’Audience Manager.

Les utilisateurs d’Audience Manager ne peuvent sélectionner que des caractéristiques ou des segments pour les personnes et les audiences de cible, qu’ils ont l’ [autorisation de vue](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/administration/administration-overview.html#wild-card-permissions).
