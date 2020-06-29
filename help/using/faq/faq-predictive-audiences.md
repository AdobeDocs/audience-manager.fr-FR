---
description: Les Audiences prédictives vous aident à classer les audiences inconnues en différentes personnes en temps réel, en utilisant la science des données.
seo-description: Les Audiences prédictives vous aident à classer les audiences inconnues en différentes personnes en temps réel, en utilisant la science des données.
seo-title: FAQ sur les Audiences prédictives
solution: Audience Manager
title: Audiences prédictives Audience Manager
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '773'
ht-degree: 0%

---


# FAQ sur les Audiences prédictives

Questions fréquentes sur [!UICONTROL Predictive Audiences].

 

**Quand dois-je utiliser[!UICONTROL Predictive Audiences]plutôt que[!UICONTROL Look-alike modeling]?**

[!UICONTROL Predictive Audiences] et [!UICONTROL Look-alike modeling] répondent à différents cas d’utilisation. Les principales différences entre les deux algorithmes sont les suivantes :

1. [!UICONTROL Look-alike modeling] prend une petite audience comme entrée et la développe. [!UICONTROL Predictive Audiences] prend une grande audience comme entrée et la divise en audiences distinctes plus petites, définies par vos personnages.
1. Le nombre de segments de base est différent pour chaque algorithme. [!UICONTROL Predictive Audiences] nécessite au moins deux lignes de base, alors que [!UICONTROL Look-alike modeling] l&#39;on utilise une ligne de base au maximum.
1. [!UICONTROL Predictive Audiences] effectue une évaluation des segments en temps réel, mais [!UICONTROL Look-alike modeling] non.

En fonction de votre cas d’utilisation, vous devez décider quel modèle sera le plus pertinent pour vous.

Vous pouvez imaginer construire un [!UICONTROL Predictive Audiences] modèle avec un certain nombre de lignes de base comme l&#39;équivalent de construire le même nombre de modèles semblables, seulement sans l&#39;évaluation en temps réel, et avec une très forte probabilité d&#39;avoir des visiteurs appartenant à plusieurs personnalités différentes, au lieu d&#39;une seule personne distincte.

 

**Combien de personnages/modèles suis-je autorisé à créer ?**

Vous pouvez créer jusqu’à 10 [!UICONTROL Predictive Audiences] modèles. Pour chaque modèle, vous pouvez définir jusqu’à 50 caractéristiques ou segments de base.

 

**Comment puis-je créer de nouveaux segments à partir d’un[!UICONTROL Predictive Audiences]segment ?**

Accédez à **[!UICONTROL Audience Data]** > **[!UICONTROL Segments]**, puis cliquez sur le **[!UICONTROL Predictive Audiences]** dossier. Recherchez le segment de votre choix, duplicata-le et modifiez-le selon vos besoins.

 

**Pourquoi certains de mes visiteurs embarqués ne sont-ils pas classifiés ?**

Actuellement, la classification des audiences ne fonctionne que pour les qualifications en temps réel, à l’exception des utilisateurs authentifiés définis comme faisant partie de [!UICONTROL Profile Merge Rules].

La prise en charge complète des données intégrées sera ajoutée dans une prochaine mise à jour.

 

**Quand puis-je voir les premiers résultats produits par mon modèle ?**

[!UICONTROL Predictive Audiences] les résultats du modèle sont disponibles dans les 24 heures suivant la création du modèle, si le modèle s&#39;exécute correctement.

Si le modèle ne produit pas de résultats dans les 24 heures, contactez votre représentant Adobe.

 

**Pourquoi mon modèle ne produit-il pas de résultats ou n&#39;affiche-t-il pas l&#39;état Avertissement ?**

[!UICONTROL Predictive Audiences] les modèles peuvent ne pas produire de résultats pour plusieurs raisons :

1. Aucune des caractéristiques/segments de personnalité/segment sélectionnés n’a suffisamment de profils d’utilisateur. Nous vous recommandons de choisir vos caractéristiques ou segments afin que chaque personne dispose d’au moins quelques centaines de profils d’utilisateur.
1. Aucune des caractéristiques/segments de personnage sélectionnés n’a suffisamment de données dans son profil d’utilisateur (pas assez de caractéristiques pour être analysées).
1. La caractéristique / le segment de l’audience de cible n’avait aucun utilisateur actif ou intégré au cours des 30 derniers jours.
1. Les utilisateurs de l’audience de cible qui étaient actifs ou intégrés au cours des 30 derniers jours ne disposent pas de suffisamment de données dans leurs profils d’utilisateurs (caractéristiques insuffisantes pour l’analyse).

Pour obtenir des résultats pertinents, l’ [!UICONTROL Predictive Audiences] algorithme évalue les réalisations de caractéristiques et de segments en fonction de l’activité utilisateur en temps réel vue par le serveur de collecte de données. Si vous sélectionnez de nouvelles caractéristiques de base et de nouveaux segments qui n’ont pas encore suffisamment d’utilisateurs, l’algorithme peut prendre quelques jours pour classer votre audience.

Pour obtenir des résultats optimaux, suivez les lignes directrices proposées dans Critères de [sélection pour les personnes](../features/algorithmic-models/predictive-audiences.md#selection-personas) et Critères de [sélection pour l&#39;Audience](../features/algorithmic-models/predictive-audiences.md#selection-audience)des Cibles.

 

**Pourquoi mon modèle affiche-t-il l’état d’erreur ?**

Le modèle n&#39;a pas pu s&#39;exécuter. Dans ce cas, contactez votre représentant Adobe.

 

**Comment puis-je modifier la règle de fusion des Profils pour un segment Audiences prédictives ?**

Duplicata du [!UICONTROL Predictive Audiences] segment et modification [!UICONTROL Profile Merge Rule] du segment dupliqué.

 

**Un utilisateur de l&#39;audience de cible qui ne fait partie d&#39;aucune caractéristique/segment persona ne peut-il pas être classifié ?**

Oui, au cas où l&#39;utilisateur n&#39;aurait aucune caractéristique dans son profil. Dans ce cas, l’utilisateur obtient un score de correspondance de 0 pour toutes les caractéristiques/segments de personne et ne sera donc classé dans aucun des segments prédictifs.

 

**Un utilisateur qui a été classé dans l’un des segments prédictifs peut-il être reclassifié dans un autre[!UICONTROL Predictive Audiences]segment ?**

Oui. Puisque l’algorithme est formé quotidiennement, il applique les modifications pour chacun des personnages en termes de notation des caractéristiques. Si un utilisateur faisant partie d’un [!UICONTROL Predictive Audiences] segment est actif, les modifications apportées à son score de caractéristique peuvent modifier la classification en fonction des 30 derniers jours d’activité.

 

**Puis-je voir les caractéristiques de la classification des audiences ?**

Oui, vous pouvez voir toutes les caractéristiques influentes pour toutes les lignes de base dans la page de rapports de modèle. Voir Caractéristiques [](../features/algorithmic-models/predictive-audiences-reporting.md#influential-traits)influentes.

 

**Qu’advient-il du modèle si je modifie l’une de ses caractéristiques ou segments de base ?**

Le modèle évalue les caractéristiques ou les segments une fois par jour. Vous devriez voir la classification mise à jour le lendemain de votre mise à jour.

 

**Puis-je sélectionner les sources de données à partir desquelles le modèle apprendra ?**

Non, la sélection des sources de données n’est pas prise en charge. L’ [!UICONTROL Predictive Audiences] algorithme identifie toutes vos caractéristiques propriétaires.