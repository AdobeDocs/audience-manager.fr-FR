---
description: Les audiences prédictives vous aident à classer les audiences inconnues en personas distinctes en temps réel à l’aide de la science des données.
seo-description: Les audiences prédictives vous aident à classer les audiences inconnues en personas distinctes en temps réel à l’aide de la science des données.
seo-title: FAQ sur les audiences prédictives
solution: Audience Manager
title: Audiences prédictives d’Audience Manager
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '895'
ht-degree: 64%

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

1. None of the selected persona [!UICONTROL traits] / [!UICONTROL segments] have enough user profiles. We recommend choosing your [!UICONTROL traits] or [!UICONTROL segments] so that each persona has at least a few hundred user profiles.
1. None of the selected persona [!UICONTROL traits] / [!UICONTROL segments] have enough data in their user profiles (not enough traits to analyze).
1. La caractéristique / le segment d’audience de cible n’a aucun utilisateur principal ou intégré.
1. Les profils des utilisateurs de l’audience cible qui étaient actifs ou intégrés au cours des 30 derniers jours ne contiennent pas suffisamment de données (caractéristiques insuffisantes pour l’analyse).
1. Le segment audience de cible utilise un autre segment [!UICONTROL Profile Merge Rule] que celui que vous avez choisi pour le modèle.
1. Il est possible que la source de données de vos caractéristiques d&#39;audience de cible ne soit pas incluse dans le modèle [!UICONTROL Profile Merge Rule] que vous avez choisi.

Pour obtenir des résultats optimaux, suivez les instructions proposées dans [Critères de sélection des personas](../features/algorithmic-models/predictive-audiences.md#selection-personas) et [Critères de sélection de l’audience cible](../features/algorithmic-models/predictive-audiences.md#selection-audience).

 

**Pourquoi mon modèle affiche-t-il le [!UICONTROL Error] statut ?**

L’exécution du modèle a échoué. In such cases, please reach out to your [!DNL Adobe] representative.

 

**Comment puis-je changer le [!UICONTROL Profile Merge Rule] pour un [!UICONTROL Predictive Audiences] [!UICONTROL segment]?**

Créez un modèle en sélectionnant les mêmes personnes et audience de cible que votre modèle précédent. Au cours de la création du modèle, affectez un autre [!UICONTROL Profile Merge Rule]modèle.

>[!WARNING]
> Vous pouvez également utiliser le créateur [de](../features/segments/segment-builder.md) segments pour créer manuellement une variable [!UICONTROL segment] avec une prévision existante [!UICONTROL trait] et lui affecter une [!UICONTROL Profile Merge Rule] valeur de votre choix.
> 
> Cependant, nous ne recommandons pas cette pratique, puisque la prédiction [!UICONTROL traits] hérite automatiquement [!UICONTROL Profile Merge Rule] du modèle auquel ils appartiennent, et ils sont construits à partir d&#39;éléments influents [!UICONTROL traits] qui sont conformes à la [!UICONTROL Profile Merge Rule] du modèle.

 

**Que [!UICONTROL Profile Merge Rule] devrais-je choisir ?**

Lorsque vous choisissez le modèle [!UICONTROL Profile Merge Rule] pour votre modèle, analysez attentivement votre cas d’utilisation.

Supposons que votre audience de cible [!UICONTROL segment] utilise une [!UICONTROL Profile Merge Rule] base de profils et de profils authentifiés, et que vous en sélectionniez la même [!DNL Device Graph] pour la prévision [!UICONTROL Profile Merge Rule] [!UICONTROL segments]. Dans ce cas, le niveau du périphérique et le niveau de l&#39;ensemble des périphériques [!UICONTROL traits] seront utilisés pour former le modèle et pour placer l&#39;utilisateur dans une prévision [!UICONTROL segment].

Si, en revanche, vous sélectionnez un périphérique [!UICONTROL Profile Merge Rule] basé uniquement sur les profils du périphérique, aucun de vos périphériques croisés n’ [!UICONTROL traits] aura d’influence et ne contribuera pas à placer les utilisateurs dans une prévision [!UICONTROL segment]. Cela peut nuire à la précision et à la portée du modèle.

Analysez soigneusement votre cas d&#39;utilisation et décidez des [!UICONTROL trait] types dont vous souhaitez que le modèle tire des enseignements et du type de données que vous souhaitez que le modèle utilise pour la classification.

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