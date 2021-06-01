---
description: Les audiences prédictives vous aident à classer les audiences inconnues en personas distinctes en temps réel à l’aide de la science des données.
seo-description: Les audiences prédictives vous aident à classer les audiences inconnues en personas distinctes en temps réel à l’aide de la science des données.
seo-title: FAQ sur les audiences prédictives
solution: Audience Manager
title: FAQ sur les audiences prédictives
feature: Modèles algorithmiques
exl-id: 21073970-8457-470b-89fc-724a118a18d2
source-git-commit: 03f039a1317576c7979a5cb4c3cffc543e3bd656
workflow-type: tm+mt
source-wordcount: '969'
ht-degree: 59%

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

 

**Quand puis-je voir les premiers résultats produits par mon modèle ?**

Les résultats du modèle [!UICONTROL Predictive Audiences] sont disponibles dans les 24 heures suivant la création du modèle, si celui-ci fonctionne correctement.

Si le modèle ne produit pas de résultats dans les 24 heures, contactez votre représentant Adobe.

 

**Pourquoi mon modèle ne produit-il pas de résultats ou n’affiche-t-il pas l’état d’avertissement ?**

Les modèles [!UICONTROL Predictive Audiences] peuvent ne produire aucun résultat pour un certain nombre de raisons :

1. Aucun des personnages sélectionnés [!UICONTROL traits] / [!UICONTROL segments] ne dispose de suffisamment de profils utilisateur. Nous vous recommandons de choisir vos [!UICONTROL traits] ou [!UICONTROL segments] afin que chaque persona dispose d’au moins quelques centaines de profils utilisateur.
1. Aucun des personnages sélectionnés [!UICONTROL traits] / [!UICONTROL segments] ne dispose de suffisamment de données dans leurs profils utilisateur (caractéristiques insuffisantes pour l’analyse).
1. La caractéristique ou le segment de l’audience cible ne comporte aucun utilisateur principal ou intégré.
1. Les profils des utilisateurs de l’audience cible qui étaient actifs ou intégrés au cours des 30 derniers jours ne contiennent pas suffisamment de données (caractéristiques insuffisantes pour l’analyse).
1. Le segment d’audience cible utilise une [!UICONTROL Profile Merge Rule] différente de celle que vous avez choisie pour le modèle.
1. La source de données de vos caractéristiques d’audience cible peut ne pas être incluse dans la balise [!UICONTROL Profile Merge Rule] que vous avez choisie pour le modèle.

Pour obtenir des résultats optimaux, suivez les instructions proposées dans [Critères de sélection des personas](../features/algorithmic-models/predictive-audiences.md#selection-personas) et [Critères de sélection de l’audience cible](../features/algorithmic-models/predictive-audiences.md#selection-audience).

 

**Pourquoi mon modèle affiche-t-il l’ [!UICONTROL Error] état ?**

L’exécution du modèle a échoué. Dans ce cas, contactez votre représentant [!DNL Adobe].

 

**Comment puis-je modifier le  [!UICONTROL Profile Merge Rule] pour un  [!UICONTROL Predictive Audiences] [!UICONTROL segment]?**

Créez un modèle en sélectionnant les mêmes personnes et l’audience cible que votre modèle précédent. Lors de la création du modèle, affectez un [!UICONTROL Profile Merge Rule] différent.

>[!WARNING]
> Vous pouvez également utiliser [Créateur de segments](../features/segments/segment-builder.md) pour créer manuellement une balise [!UICONTROL segment] avec un [!UICONTROL trait] prédictif existant et lui affecter une balise [!UICONTROL Profile Merge Rule] de votre choix.
> 
> Cependant, nous ne recommandons pas cette pratique, car la [!UICONTROL traits] prédictive hérite automatiquement de la [!UICONTROL Profile Merge Rule] du modèle auquel elle appartient et est construite à partir de la [!UICONTROL traits] influente qui est conforme à la [!UICONTROL Profile Merge Rule] du modèle.

 

**Que  [!UICONTROL Profile Merge Rule] devrais-je choisir ?**

Lorsque vous choisissez la balise [!UICONTROL Profile Merge Rule] pour votre modèle, analysez attentivement votre cas d’utilisation.

Supposons que votre audience cible [!UICONTROL segment] utilise une balise [!UICONTROL Profile Merge Rule] basée sur les profils authentifiés + [!DNL Device Graph] et que vous sélectionniez la même balise [!UICONTROL Profile Merge Rule] pour la [!UICONTROL segments] prédictive. Dans ce cas, les niveaux appareil et multi-appareils [!UICONTROL traits] seront utilisés pour entraîner le modèle et pour placer l’utilisateur dans une [!UICONTROL segment] prédictive.

Si, toutefois, vous sélectionnez une balise [!UICONTROL Profile Merge Rule] en fonction des profils d’appareil, aucun de vos [!UICONTROL traits] multi-appareils ne deviendra influent et ne contribuera pas au placement des utilisateurs dans une [!UICONTROL segment] prédictive. Cela peut avoir une incidence négative sur la précision et la portée du modèle.

Analysez soigneusement votre cas d’utilisation et décidez des [!UICONTROL trait] types à partir desquels vous souhaitez que le modèle apprenne et du type de données que vous souhaitez que le modèle utilise pour la classification.

**Un utilisateur de l’audience cible qui ne fait partie d’aucun segment/caractéristique de persona peut-il ne pas être classé ?**

Oui, lorsque le profil de l’utilisateur ne contient aucune caractéristique. Dans ce cas, l’utilisateur obtient une note de correspondance de 0 pour tous les segments/caractéristiques de persona et n’est donc classé dans aucun des segments prédictifs.

 

**Un utilisateur qui a été classé dans l’un des segments prédictifs peut-il être reclassé dans un autre segment [!UICONTROL Predictive Audiences] ?**

Oui. Étant donné que l’algorithme est formé quotidiennement, il applique les modifications pour chacune des personas en termes de notation des caractéristiques. Si un utilisateur faisant partie d’un segment [!UICONTROL Predictive Audiences] est actif, les modifications apportées à sa notation des caractéristiques peuvent modifier la classification en fonction de l’activité des 30 derniers jours.

 

**Puis-je voir les caractéristiques utilisées pour la classification des audiences ?**

Oui, vous pouvez voir toutes les caractéristiques influentes pour toutes les lignes de base dans la page de rapports de modèle. Voir [Caractéristiques influentes](../features/algorithmic-models/predictive-audiences-reporting.md#influential-traits).

 

**Puis-je modifier la durée de vie (TTL) des caractéristiques prédictives ?**

La durée de vie prédictive de la caractéristique est définie sur 0 (durée de vie) et ne peut pas être modifiée. [!UICONTROL Predictive Audiences] ne peuvent dissocier les utilisateurs des segments prédictifs que s’ils remplissent les critères du segment de base ou s’ils sont reclassés dans un autre segment prédictif.

Si nécessaire, vous pouvez contourner cette fonctionnalité en créant un nouveau segment qui contient à la fois une caractéristique prédictive et une caractéristique d’activité avec une durée de vie spécifiée.

 


**Qu’advient-il du modèle si je modifie l’un de ses segments ou caractéristiques de ligne de base ?**

Le modèle évalue les caractéristiques ou les segments une fois par jour. Vous devriez voir la mise à jour de la classification le lendemain de votre mise à jour.

 

**Puis-je sélectionner les sources de données qui serviront à former le modèle ?**

Non, la sélection des sources de données n’est pas prise en charge. L’algorithme [!UICONTROL Predictive Audiences] est formé à partir de toutes vos caractéristiques propriétaires.
