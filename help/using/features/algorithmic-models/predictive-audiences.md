---
description: Les  prédictifs  vous aident à classer les de  inconnu en personnes distinctes en temps réel, à l’aide de la science des données.
seo-description: Les  prédictifs  vous aident à classer les de  inconnu en personnes distinctes en temps réel, à l’aide de la science des données.
seo-title: Aperçu du  de  prédictif
solution: Audience Manager
title: ' Gestionnaire de   Gestionnaire de  Prédictif'
translation-type: tm+mt
source-git-commit: 74a5de961b2f9ab6afa2caf998ba1100d40cc93a

---


# Aperçu du  de  prédictif {#predictive-audiences}

[!UICONTROL Predictive Audiences] vous permet de classer un inconnu en  distincts, en temps réel, à l’aide de techniques avancées de science des données.

>[!IMPORTANT]
>Cet article contient la documentation du produit destinée à vous guider tout au long de la configuration et de l’utilisation de cette fonctionnalité. Rien dans ce document n&#39;est un conseil juridique. Veuillez consulter votre propre conseiller juridique pour obtenir des conseils juridiques.

Dans un contexte de marketing, une personne est un segment   défini par les, les utilisateurs ou les acheteurs potentiels, qui partagent un ensemble spécifique de caractéristiques, telles que les caractéristiques démographiques, les habitudes de navigation, l’historique d’achat, etc.

[!UICONTROL Predictive Audiences] les modèles poussent ce concept un peu plus loin, en vous permettant d&#39;utiliser  capacités d&#39;apprentissage automatique de  Manager pour classer les inconnus en personnes distinctes.  Gestionnaire de  de vous aide à atteindre cet objectif en calculant la propension de votre  propriétaire inconnu pour un ensemble de propriétaires connus.

Lorsque vous créez un [!UICONTROL Predictive Audiences] modèle, la première étape consiste à choisir les caractéristiques ou les segments de ligne de base par lesquels vous souhaitez que votre  votre soit classé. Ces caractéristiques ou segments définissent vos personnalités.

Au cours de la phase d’évaluation, le modèle crée un nouveau [!UICONTROL Predictive Audiences] segment pour chaque caractéristique ou segment que vous avez défini comme ligne de base. La prochaine fois que  Gestionnaire  voit un de votre [!UICONTROL Predictive Audiences] derapports  qui n’est pas classé pour une personne (ne remplissait pas les critères de base ni pour vos segments), le modèle déterminera à quel segment prédictif le doit appartenir et ajoutera le à ce segment.

Vous pouvez identifier les segments prédictifs créés par le modèle, dans la [!UICONTROL Segments] page. Chaque [!UICONTROL Predictive Audiences] modèle possède son propre dossier sous le [!UICONTROL Predictive Audiences] dossier, et vous pouvez voir les segments de chaque modèle en cliquant sur le dossier du modèle.

![-segments de prédictif-](assets/predictive-audiences-segments.png)

## Cas d’utilisation {#use-cases}

Pour vous aider à mieux comprendre comment et quand vous pouvez utiliser [!UICONTROL Predictive Audiences], voici quelques cas d’utilisation que  clients de  Manager peuvent résoudre à l’aide de cette fonctionnalité.

### Cas d’utilisation 1

En tant que spécialiste du marketing dans un de commerce électronique, je souhaite classifier tous mes Web et mobiles en différents  dela marque, pour que je puisse personnaliser leur expérience utilisateur.

### Cas d’utilisation n° 2

En tant que spécialiste du marketing dans un  de média, je souhaite classer mes web et mobiles non authentifiés par genres favoris, afin de pouvoir leur suggérer un contenu personnalisé à travers tous les .

### Cas d’utilisation 3

En tant qu&#39;annonceur d&#39;un de compagnie aérienne, je veux m&#39;assurer de classer mes  de en fonction de leur intérêt pour les destinations de voyage, afin de pouvoir leur faire de la publicité en temps réel, dans une courte fenêtre de reciblage.

### Cas d’utilisation n° 4

En tant qu&#39;annonceur, je veux classer mon de premier  en temps réel, afin de pouvoir réagir rapidement aux informations de tendance.

### Cas d’utilisation n° 5

En tant que spécialiste du marketing, je veux prédire dans quelle phase de voyage des clients se trouvent mes de site Web, comme la découverte, l&#39;engagement, l&#39;achat ou la rétention, afin de pouvoir les  en conséquence.

### Cas d’utilisation 6

En tant que de médias, je veux classer mon  de, afin de pouvoir vendre mon espace publicitaire à des prix très élevés, tout en offrant à mes des publicités pertinentes.

## Fonctionnement des modèles   prédictifs

Lorsque vous créez un [!UICONTROL Predictive Audiences] modèle, vous effectuez trois étapes :

1. Tout d’abord, vous sélectionnez au moins deux caractéristiques ou deux segments qui définiront vos personnalités.
1. Ensuite, vous choisissez une caractéristique ou un segment qui définit le   à classifier.
1. Enfin, vous choisissez un nom pour le modèle et sélectionnez une source de données qui stockera les segments prédictifs.

### Critères de sélection pour les personnes {#selection-personas}

Vous pouvez choisir l’une de vos caractéristiques ou segments propriétaires pour définir vos personnalités. Cependant, pour des résultats optimaux, voici un ensemble de bonnes pratiques recommandées :

* Choisissez vos caractéristiques ou segments personnels de sorte que chaque personne dispose d’au moins quelques centaines d’ID de [périphérique](../../reference/ids-in-aam.md).
* Si vos caractéristiques sont basées sur des identifiants [](../../reference/ids-in-aam.md)inter-périphériques, vous pouvez les encapsuler dans des segments avec des règles [de fusion de](../profile-merge-rules/merge-rules-overview.md) qui utilisent des identifiants [de](../../reference/ids-in-aam.md)périphérique, comme [!UICONTROL Device Graph]par exemple. Cela permet de s’assurer qu’il y a suffisamment d’ID [de](../../reference/ids-in-aam.md) périphérique dont l’algorithme peut tirer des leçons.
* Nous vous recommandons de choisir des caractéristiques ou des segments simples pour vos personnes, composés de 1 à 3 caractéristiques.
* Choisissez des caractéristiques de ligne de base ou des segments qui présentent un chevauchement minimal.
* Assurez-vous de capturer des caractéristiques granulaires sur vos propriétés numériques.

### Critères de sélection pour   {#selection-audience}

Comme pour la sélection de personnes, vous devez choisir votre caractéristique ou segment qui définit votre   de de manière à ce qu’il dispose d’utilisateurs en temps réel avec des ensembles de caractéristiques riches, pour les classer dans la personne appropriée.

###  prédictive  phase de formation du modèle {#model-training}

Avant que l’algorithme puisse classifier vos  de premier niveau  en personnes appropriées, il doit s’entraîner à utiliser vos données.

Pour chaque personne que vous définissez, l’algorithme analyse ses  de  respectifs et évalue tout de caractéristiques en temps réel et/ou intégré pour ses utilisateurs au cours des 30 derniers jours.
Cette étape a lieu une fois toutes les 24 heures, afin de tenir compte des modifications apportées à votre  de  propriétaire.

###  prédictif  phase de classification du modèle {#model-classification}

Lorsqu’un qui fait partie de l’ de  de  est vu en temps réel, le modèle évalue si le fait partie des personnes définies. Pour chaque qui n’appartient à aucune personnalité, le modèle attribue un score de qualification personnelle.

Lors de l’évaluation de l’ de premier niveau et de l’attribution de scores, le modèle utilise la valeur par défaut **[!UICONTROL Profile Merge Rule]** définie dans votre compte. Enfin, le est classé dans la personne pour laquelle il a obtenu le score le plus élevé.

![-graphique-prédictif-](assets/predictive-audiences-graph.png)

## Considérations et limites {#considerations}

>[!IMPORTANT]
> Lisez attentivement cette section avant de passer à la phase de mise en oeuvre.

Lors de la configuration de vos [!UICONTROL Predictive Audiences] modèles, tenez compte des considérations et limites suivantes :

* Vous pouvez créer jusqu’à 10 [!UICONTROL Predictive Audiences] modèles.
* Pour chaque modèle, vous pouvez choisir jusqu’à 50 caractéristiques / segments de base.
* Les données tierces et secondaires ne sont actuellement pas prises en charge dans [!UICONTROL Predictive Audiences].
*  classification  est effectuée uniquement pour les de premier niveau en temps réel. La classification des  propriétaires internes peut être prise en charge dans une prochaine mise à jour.
   >[!IMPORTANT]
   > Actuellement, les segments [!UICONTROL Total Segment Population] prédictifs sont affichés sous la forme 0 et les transferts [de données sortantes par](../../integration/receiving-audience-data/batch-outbound-transfers/batch-outbound-overview.md) lot ne sont pas pris en charge pour les  de  prédictifs. Ce comportement changera dans une future mise à jour.
* [!UICONTROL Predictive Audiences] effectue   classification en fonction de vos caractéristiques propriétaires, à partir de toutes vos sources de données propriétaires.
* L’évaluation des segments pour [!UICONTROL Predictive Audiences] utilise la valeur par défaut **[!UICONTROL Profile Merge Rule]** que vous avez définie dans votre compte. Pour en savoir plus sur [!UICONTROL Profile Merge Rules] consultez la [documentation](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/profile-merge-rules/merge-rules-overview.html)dédiée.
* Certaines caractéristiques et certains segments ne sont pas pris en charge en tant que lignes de base ou  . [!UICONTROL Predictive Audiences] les modèles ne pourront pas être enregistrés lorsque vous choisirez l’un des éléments suivants comme lignes de base ou   de base :
   * Caractéristiques prédictives et segments créés avec des caractéristiques prédictives;
   * [Caractéristiques ou segments d’Adobe Experience Platform](../integration/../../integration/integration-aep/aam-aep-audience-sharing.md) ;
   * Caractéristiques algorithmiques;
   * Caractéristiques secondaires et tierces.

## Contrôles des exportations de données{#dec}

Les segments prédictifs créés par [!UICONTROL Predictive Audiences] les modèles héritent des contrôles [d’exportation des](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-export-controls.html) données des sources de données propriétaires suivantes :

1. Source de données propriétaires que vous choisissez lors de la création du modèle.
1. Les sources de données propriétaires de votre  . Plus précisément, les contrôles d’exportation des données des caractéristiques ou des segments qui composent votre   les  de l’.

Les caractéristiques et segments prédictifs nouvellement créés auront les mêmes restrictions de confidentialité que le   des sources de données propriétaires décrites ci-dessus.

Les caractéristiques comportant des restrictions supplémentaires qui ne font pas partie des restrictions de confidentialité des [!UICONTROL Predictive Audiences] segments seront exclues de la phase de formation et n’auront aucune influence sur le modèle.

##  basées sur les rôles{#rbac}

Les caractéristiques et les segments que vous choisissez pour les personnages et la classification   sont soumis à l’ [analyse de](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/administration/administration-overview.html)rôle du Gestionnaire de de   de  de de.

 les utilisateurs de   Manager ne peuvent sélectionner que des caractéristiques ou des segments pour les personnages et les  de l’, qu’ils ont l’ [autorisation d’effectuer une analyse de l’](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/administration/administration-overview.html#wild-card-permissions).
