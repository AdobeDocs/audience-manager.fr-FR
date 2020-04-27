---
description: Les  prédictifs  vous aident à classer les de  inconnu en personnes distinctes en temps réel, à l’aide de la science des données.
seo-description: Les  prédictifs  vous aident à classer les de  inconnu en personnes distinctes en temps réel, à l’aide de la science des données.
seo-title: 'FAQ sur les  prédictifs '
solution: Audience Manager
title: ' Gestionnaire de   Gestionnaire de  Prédictif'
translation-type: tm+mt
source-git-commit: 8cf504fa811e4043f83d0b9f11754065efccf7bb

---


# FAQ sur les  prédictifs 

Foire aux questions sur [!UICONTROL Predictive Audiences].

 

**Quand devrais-je utiliser[!UICONTROL Predictive Audiences]plutôt que[!UICONTROL Look-alike modeling]?**

[!UICONTROL Predictive Audiences] et [!UICONTROL Look-alike modeling] servir différents cas d&#39;utilisation. Les principales différences entre les deux algorithmes sont les suivantes :

1. [!UICONTROL Look-alike modeling] prend un petit   en entrée et le développe. [!UICONTROL Predictive Audiences] prend un grand   en entrée et le divise en un plus petit de , défini par vos personnages.
1. Le nombre de segments de base est différent pour chaque algorithme. [!UICONTROL Predictive Audiences] requiert au moins deux lignes de base, tandis que [!UICONTROL Look-alike modeling] utilise une ligne de base au maximum.
1. [!UICONTROL Predictive Audiences] effectue une évaluation des segments en temps réel, mais [!UICONTROL Look-alike modeling] non.

Selon votre cas d&#39;utilisation, vous devez décider quel modèle sera le plus pertinent pour vous.

Vous pouvez imaginer construire un [!UICONTROL Predictive Audiences] modèle avec un certain nombre de niveaux de base comme l&#39;équivalent de construire le même nombre de modèles semblables, seulement sans l&#39;évaluation en temps réel, et avec une très forte probabilité d&#39;avoir des appartenant à plusieurs personnalités différentes, au lieu d&#39;une seule personne distincte.

 

**Combien de personnalités/modèles puis-je créer ?**

Vous pouvez créer jusqu’à 10 [!UICONTROL Predictive Audiences] modèles. Pour chaque modèle, vous pouvez définir jusqu’à 50 caractéristiques ou segments de base.

 

**Comment puis-je créer de nouveaux segments à partir d’un[!UICONTROL Predictive Audiences]segment ?**

Accédez à **[!UICONTROL Audience Data]** > **[!UICONTROL Segments]**, puis cliquez sur le **[!UICONTROL Predictive Audiences]** dossier. Recherchez le segment de votre choix, -le et modifiez-le selon vos besoins.

 

**Pourquoi certains de mes à bord ne sont-ils pas classifiés ?**

Actuellement,  classification  fonctionne uniquement pour les qualifications en temps réel, à l’exception des utilisateurs authentifiés définis comme faisant partie de [!UICONTROL Profile Merge Rules].

La prise en charge complète des données intégrées sera ajoutée dans une prochaine mise à jour.

 

**Quand puis-je voir les premiers résultats produits par mon modèle ?**

[!UICONTROL Predictive Audiences] les résultats du modèle sont disponibles dans les 24 heures suivant la création du modèle, si le modèle s’exécute correctement.

Si le modèle ne produit pas de résultats dans les 24 heures, contactez votre représentant Adobe.

 

**Pourquoi mon modèle ne produit-il pas de résultats ou n’affiche-t-il pas l’état d’avertissement ?**

[!UICONTROL Predictive Audiences] les modèles peuvent ne pas produire de résultats pour plusieurs raisons :

1. Aucune des caractéristiques/segments de personnalité/segment sélectionnés n’a suffisamment de  d’utilisateur. Nous vous recommandons de choisir vos caractéristiques ou segments afin que chaque personne dispose d’au moins quelques centaines de  d’utilisateurs.
1. Aucune des caractéristiques/segments de personnage sélectionnés n’a suffisamment de données dans les  d’utilisateur (caractéristiques à analyser insuffisantes).
1. Le    caractéristique/segment de n’avait aucun utilisateur actif ou intégré au cours des 30 derniers jours.
1. Le    les utilisateurs actifs ou embarqués au cours des 30 derniers jours n’ont pas suffisamment de données dans leurutilisateur (caractéristiques insuffisantes pour l’analyse).

Pour produire des résultats pertinents, l’ [!UICONTROL Predictive Audiences] algorithme évalue les réalisations de caractéristiques et de segments en fonction des utilisateur en temps réel  vus par le serveur de collecte de données. Si vous sélectionnez de nouvelles caractéristiques de base et de nouveaux segments qui n’ont pas encore assez d’utilisateurs, l’algorithme peut prendre quelques jours pour classer votre  .

Pour obtenir des résultats optimaux, suivez les lignes directrices suggérées dans les Critères de [sélection pour les personnes](../features/algorithmic-models/predictive-audiences.md#selection-personas) et les Critères de [sélection pour les  ](../features/algorithmic-models/predictive-audiences.md#selection-audience).

 

**Pourquoi mon modèle affiche-t-il l’état d’erreur ?**

Le modèle n&#39;a pas pu fonctionner. Dans ce cas, contactez votre représentant Adobe.

 

**Comment puis-je modifier la règle de fusion  pour un segment  prédictif ?**

 le [!UICONTROL Predictive Audiences] segment et modifiez [!UICONTROL Profile Merge Rule] le segment dupliqué.

 

**Un utilisateur de l&#39;   qui ne fait partie d&#39;aucune caractéristique personnelle / segment peut-il ne pas être classifié ?**

Oui, au cas où l&#39;utilisateur n&#39;aurait aucune caractéristique dans son . Dans ce cas, l’utilisateur obtiendra un score de correspondance de 0 pour toutes les caractéristiques/segments de la personne et ne sera donc classé dans aucun des segments prédictifs.

 

**Un utilisateur qui a été classé dans l’un des segments prédictifs peut-il être reclassifié dans un autre[!UICONTROL Predictive Audiences]segment ?**

Oui. Comme l’algorithme est formé quotidiennement, il applique les modifications pour chacun des personnages en termes de notation des caractéristiques. Si un utilisateur faisant partie d’un [!UICONTROL Predictive Audiences] segment est actif, les modifications de son score de caractéristique peuvent modifier la classification en fonction des 30 derniers jours  le .

 

**Puis-je voir les caractéristiques par lesquelles  classification  est effectuée ?**

Oui, vous pouvez voir toutes les caractéristiques influentes pour toutes les lignes de base dans la page de  du modèle. Voir Caractéristiques [influentes](../features/algorithmic-models/predictive-audiences-reporting.md#influential-traits).

 

**Qu’arrive-t-il au modèle si je modifie l’une de ses caractéristiques de base ou l’un de ses segments ?**

Le modèle évalue les caractéristiques ou les segments une fois par jour. Vous devriez voir la classification mise à jour le lendemain de votre mise à jour.

 

**Puis-je sélectionner les sources de données à partir desquelles le modèle apprendra ?**

Non, la sélection des sources de données n’est pas prise en charge. L’ [!UICONTROL Predictive Audiences] algorithme apprend de toutes vos caractéristiques propriétaires.