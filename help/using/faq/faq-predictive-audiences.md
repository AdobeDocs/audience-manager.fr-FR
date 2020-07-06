---
description: Les audiences prédictives vous aident à classer les audiences inconnues en personas distinctes en temps réel à l’aide de la science des données.
seo-description: Les audiences prédictives vous aident à classer les audiences inconnues en personas distinctes en temps réel à l’aide de la science des données.
seo-title: FAQ sur les audiences prédictives
solution: Audience Manager
title: Audiences prédictives d’Audience Manager
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '773'
ht-degree: 100%

---


# FAQ sur les audiences prédictives

Questions fréquentes sur [!UICONTROL Predictive Audiences].

 

**Quand dois-je utiliser [!UICONTROL Predictive Audiences] plutôt que [!UICONTROL Look-alike modeling] ?**

[!UICONTROL Predictive Audiences] et [!UICONTROL Look-alike modeling] correspondent à des cas d’utilisation différents. Les principales différences entre les deux algorithmes sont les suivantes :

1. [!UICONTROL Look-alike modeling] prend une petite audience comme entrée et la développe. [!UICONTROL Predictive Audiences] prend une grande audience comme entrée et la divise en audiences distinctes plus petites, définies par vos personas.
1. Le nombre de segments de base est différent pour chaque algorithme. [!UICONTROL Predictive Audiences] nécessite au moins deux lignes de base, alors que [!UICONTROL Look-alike modeling] utilise au maximum une ligne de base.
1. [!UICONTROL Predictive Audiences] effectue une évaluation de segmentation en temps réel, contrairement à [!UICONTROL Look-alike modeling].

Vous devez choisir le modèle qui vous convient le mieux en fonction de votre cas d’utilisation.

Vous pouvez considérer la création d’un modèle [!UICONTROL Predictive Audiences] avec un certain nombre de lignes de base comme l’équivalent de la création d’un même nombre de modèles semblables, seulement sans l’évaluation en temps réel. Il est également très probable que les visiteurs appartiennent à plusieurs personas différentes, au lieu d’une seule persona distincte.

 

**Combien de personas/modèles suis-je autorisé à créer ?**

Vous pouvez créer jusqu’à 10 modèles [!UICONTROL Predictive Audiences]. Pour chaque modèle, vous pouvez définir jusqu’à 50 caractéristiques ou segments de ligne de base.

 

**Comment puis-je créer de nouveaux segments à partir d’un segment [!UICONTROL Predictive Audiences] ?**

Accédez à **[!UICONTROL Audience Data]** > **[!UICONTROL Segments]**, puis cliquez sur le dossier **[!UICONTROL Predictive Audiences]**. Recherchez le segment souhaité, dupliquez-le et modifiez-le en fonction de vos besoins.

 

**Pourquoi certains de mes visiteurs intégrés ne sont-ils pas classés ?**

Actuellement, la classification des audiences ne fonctionne que pour les qualifications en temps réel, à l’exception des utilisateurs authentifiés définis comme faisant partie de [!UICONTROL Profile Merge Rules].

La prise en charge complète des données intégrées sera ajoutée dans une prochaine mise à jour.

 

**Quand puis-je voir les premiers résultats produits par mon modèle ?**

Les résultats du modèle [!UICONTROL Predictive Audiences] sont disponibles dans les 24 heures suivant la création du modèle, si celui-ci fonctionne correctement.

Si le modèle ne produit pas de résultats dans les 24 heures, contactez votre représentant Adobe.

 

**Pourquoi mon modèle ne produit-il pas de résultats ou n’affiche-t-il pas l’état d’avertissement ?**

Les modèles [!UICONTROL Predictive Audiences] peuvent ne produire aucun résultat pour un certain nombre de raisons :

1. Aucun des segments/caractéristiques de persona sélectionnés ne dispose de suffisamment de profils utilisateur. Nous vous recommandons de choisir vos caractéristiques ou segments afin que chaque persona dispose d’au moins quelques centaines de profils utilisateur.
1. Aucun des segments/caractéristiques de persona sélectionnés ne contient suffisamment de données dans son profil utilisateur (caractéristiques insuffisantes pour l’analyse).
1. La caractéristique ou le segment de l’audience cible ne disposait d’aucun utilisateur actif ou intégré au cours des 30 derniers jours.
1. Les profils des utilisateurs de l’audience cible qui étaient actifs ou intégrés au cours des 30 derniers jours ne contiennent pas suffisamment de données (caractéristiques insuffisantes pour l’analyse).

Pour obtenir des résultats pertinents, l’algorithme [!UICONTROL Predictive Audiences] évalue les réalisations de caractéristiques et de segments en fonction de l’activité de l’utilisateur en temps réel observée par le serveur de collecte de données. Si vous sélectionnez de nouveaux segments et caractéristiques de base qui ne disposent pas encore de suffisamment d’utilisateurs, l’algorithme peut prendre quelques jours pour classer votre audience.

Pour obtenir des résultats optimaux, suivez les instructions proposées dans [Critères de sélection des personas](../features/algorithmic-models/predictive-audiences.md#selection-personas) et [Critères de sélection de l’audience cible](../features/algorithmic-models/predictive-audiences.md#selection-audience).

 

**Pourquoi mon modèle affiche-t-il l’état d’erreur ?**

L’exécution du modèle a échoué. Dans ce cas, contactez votre représentant Adobe.

 

**Comment puis-je modifier la stratégie de fusion de profils d’un segment d’audiences prédictives ?**

Dupliquez le segment [!UICONTROL Predictive Audiences] et modifiez la [!UICONTROL Profile Merge Rule] du segment dupliqué.

 

**Un utilisateur de l’audience cible qui ne fait partie d’aucun segment/caractéristique de persona peut-il ne pas être classé ?**

Oui, lorsque le profil de l’utilisateur ne contient aucune caractéristique. Dans ce cas, l’utilisateur obtient une note de correspondance de 0 pour tous les segments/caractéristiques de persona et n’est donc classé dans aucun des segments prédictifs.

 

**Un utilisateur qui a été classé dans l’un des segments prédictifs peut-il être reclassé dans un autre segment [!UICONTROL Predictive Audiences] ?**

Oui. Étant donné que l’algorithme est formé quotidiennement, il applique les modifications pour chacune des personas en termes de notation des caractéristiques. Si un utilisateur faisant partie d’un segment [!UICONTROL Predictive Audiences] est actif, les modifications apportées à sa notation des caractéristiques peuvent modifier la classification en fonction de l’activité des 30 derniers jours.

 

**Puis-je voir les caractéristiques utilisées pour la classification des audiences ?**

Oui, vous pouvez voir toutes les caractéristiques influentes pour toutes les lignes de base dans la page de rapports de modèle. Voir [Caractéristiques influentes](../features/algorithmic-models/predictive-audiences-reporting.md#influential-traits).

 

**Qu’advient-il du modèle si je modifie l’un de ses segments ou caractéristiques de ligne de base ?**

Le modèle évalue les caractéristiques ou les segments une fois par jour. Vous devriez voir la mise à jour de la classification le lendemain de votre mise à jour.

 

**Puis-je sélectionner les sources de données qui serviront à former le modèle ?**

Non, la sélection des sources de données n’est pas prise en charge. L’algorithme [!UICONTROL Predictive Audiences] est formé à partir de toutes vos caractéristiques propriétaires.