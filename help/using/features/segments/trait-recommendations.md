---
description: Avec Trait Recommendations, lorsque vous créez ou modifiez un segment dans Segment Builder, vous obtenez des recommandations sur les caractéristiques supplémentaires que vous pouvez inclure et qui sont similaires aux caractéristiques de la règle de segment. Ajoutez les caractéristiques recommandées à votre segment pour élargir votre audience cible.
seo-description: Obtenez des recommandations de caractéristiques en direct lorsque vous créez vos segments.
seo-title: Recommandations de caractéristiques
solution: Audience Manager
title: Recommandations de caractéristiques
feature: 'Segments '
exl-id: 7ef862a9-7354-49fb-9af0-925d827a5165
source-git-commit: 432b12c4d4fb567d1a0bcaa9d12baaac5e3ae0f7
workflow-type: tm+mt
source-wordcount: '1574'
ht-degree: 8%

---

# Recommandations de caractéristiques

Obtenez des recommandations de caractéristiques en direct lorsque vous créez vos segments à partir de vos propres caractéristiques propriétaires et de flux de données [!UICONTROL Audience Marketplace].

## Démonstration vidéo

Commencez par regarder la vidéo [!UICONTROL Trait Recommendations] ci-dessous, puis lisez la suite pour plus d’informations. La démonstration vidéo vous montre comment utiliser les recommandations de vos propres caractéristiques propriétaires, ainsi que les recommandations de caractéristiques provenant de flux de données [!UICONTROL Audience Marketplace] auxquels vous êtes déjà abonné *.*

>[!VIDEO](https://video.tv.adobe.com/v/26228/)

La vidéo suivante décrit le processus pour [!UICONTROL Marketplace Recommendations], qui vous montre comment ajouter des caractéristiques à vos segments, en fonction des recommandations provenant de flux de données dans [!UICONTROL Audience Marketplace]. Ces recommandations sont basées sur des flux de données auxquels *vous n’êtes pas abonné*.

>[!VIDEO](https://video.tv.adobe.com/v/29363/)

## Présentation

[!UICONTROL Trait Recommendations], optimisé par  [!DNL Adobe Sensei], vous apporte des informations essentielles dans vos workflows quotidiens d’Audience Manager.
Avec [!UICONTROL Trait Recommendations], lorsque vous créez ou modifiez un segment dans [Créateur de segments](segment-builder.md), vous obtenez des recommandations sur les caractéristiques supplémentaires que vous pouvez inclure et qui sont similaires aux caractéristiques de la règle de segment.

L’Audience Manager vous montre les recommandations de caractéristiques de votre premier niveau, dans la section **[!UICONTROL Recommendations]**, et de **[!UICONTROL Audience Marketplace]**, dans la section **[!UICONTROL Recommendations from Marketplace]**.

Ajoutez les caractéristiques recommandées à votre segment pour élargir votre audience cible.

![Présentation de Trait Recommendations](assets/trait-recommendations-overview-full.png)

**En un mot :**

* L’Audience Manager affiche les caractéristiques propriétaires dans la section [!UICONTROL Recommendations]. Les recommandations Marketplace provenant de flux publics et privés auxquels vous n’êtes pas abonné sont visibles dans la section [!UICONTROL Recommendations from Marketplace] . Cliquez sur le nom du flux pour accéder à [!UICONTROL Audience Marketplace] et vous abonner.
* L’Audience Manager affiche un maximum de cinquante caractéristiques similaires à celle de la règle de segment.
* Vous pouvez filtrer les sources de données à partir desquelles vous ne souhaitez afficher aucune recommandation.
* Lors du calcul des similitudes, l’Audience Manager prend en compte les [UUIDs](../../reference/ids-in-aam.md) qui ont rempli les critères de la caractéristique au cours des 30 derniers jours.
* Si le message d’erreur &quot;Aucune caractéristique similaire n’a été trouvée&quot; s’affiche. Les caractéristiques peuvent être trop nouvelles.&quot; Cela signifie qu’il n’y a eu aucune activité pour cette caractéristique au cours des 30 derniers jours ou que l’Audience Manager n’a pas encore mis à jour les recommandations pour cette caractéristique. Veuillez réessayer dans 24 heures.

## Cas d’utilisation

Avec [!UICONTROL Trait Recommendations], vous pouvez améliorer vos workflows en fonction de l’utilisation de l’Audience Manager :

* En tant que marketeur, vous pouvez rapidement trouver des audiences intéressées par des produits complémentaires à l’aide de caractéristiques similaires afin d’accroître votre portée.
* Si vous utilisez l’Audience Manager comme éditeur, avec [!UICONTROL Trait Recommendations], vous pouvez comprendre le comportement de l’audience et créer de meilleurs segments pour les ventes publicitaires ou l’acquisition d’utilisateurs.
* En tant qu’acheteur de données [!UICONTROL Audience Marketplace], je souhaite découvrir des données tierces pertinentes sans parcourir un grand nombre de flux.
* En tant que fournisseur de données [!UICONTROL Audience Marketplace], je souhaite recommander des données pertinentes aux acheteurs afin que je puisse bénéficier d’abonnements optimaux et pertinents.

## Différences entre le Recommendations des caractéristiques et les modèles algorithmiques

### Modèles algorithmiques

[!UICONTROL Algorithmic Models] non seulement trouve-t-on les caractéristiques les plus influentes, mais il note également les utilisateurs en fonction de ces caractéristiques et attribue à chaque utilisateur un score individuel. Vous créez ensuite des caractéristiques algorithmiques pour cibler vos utilisateurs. Grâce aux contrôles de précision et de portée dans la balise [!UICONTROL Trait Builder], vous pouvez spécifier les utilisateurs parmi tous ceux qui ont les caractéristiques d’influence à cibler.

[!UICONTROL Algorithmic Models] vous permet de sélectionner des utilisateurs à différents niveaux de précision et de tester  [!UICONTROL Audience Lab] quel groupe d’utilisateurs effectue la meilleure conversion. Consultez les cas d’utilisation détaillés dans [Comparaison des modèles dans Audience Lab](../../features/audience-lab/audience-lab-use-cases.md#compare-models).

Dans [!UICONTROL Algorithmic Models], le modèle s’exécute tous les 8 jours et actualise les utilisateurs qualifiés pour les caractéristiques algorithmiques.

### Recommandations de caractéristiques

[!UICONTROL Trait Recommendations] est un moyen rapide d’obtenir des informations sur d’autres caractéristiques similaires à celles que vous utilisez dans un segment.

Vous devez utiliser [!UICONTROL Trait Recommendations] lorsque :

* vous avez besoin d’insights rapides en créant un segment ;
* vous utilisez les segments pour des campagnes courtes ou vous souhaitez supprimer rapidement des audiences qui se convertissent ;
* vous essayez de maximiser votre portée.

## Workflow

Lors de la création ou de la modification d’un segment dans [le créateur de segments](segment-builder.md), vous pouvez explorer des caractéristiques similaires aux caractéristiques de la règle de segment. Le workflow [Créateur de segments](segment-builder.md) est très similaire pour les segments nouveaux et existants :

### Nouveaux segments

1. Accédez à **Données d’audience > Segments**, puis cliquez sur **Ajouter nouveau**.
1. Dans la liste déroulante **Caractéristiques** , ajoutez au moins une caractéristique à la règle de segment.
1. Vous pouvez afficher les caractéristiques recommandées propriétaires et les recommandations de caractéristiques [!UICONTROL Audience Marketplace] provenant de flux auxquels vous êtes abonné, dans la section **[!UICONTROL Recommendations]** . La section **[!UICONTROL Recommendations from Marketplace]** présente les recommandations de caractéristiques provenant de flux auxquels vous n’êtes pas abonné. Toutes ces recommandations sont similaires aux caractéristiques que vous avez ajoutées à la règle de segment. Faites défiler l’écran vers le bas pour afficher toutes les caractéristiques recommandées.
1. (Facultatif) Pour exclure les caractéristiques propriétaires recommandées de certaines sources de données, cliquez sur le symbole **X** correspondant aux sources de données à exclure.

   >[!NOTE]
   >
   >Les sources de données exclues s’affichent juste au-dessus de la liste des caractéristiques recommandées. Cliquez sur **X** dans la zone grise pour supprimer les exclusions et afficher à nouveau les résultats des sources de données respectives.
1. Pour ajouter des caractéristiques recommandées à la règle de segment, cliquez sur le symbole **+** .

>[!IMPORTANT]
>
>Lors de l’ajout de caractéristiques [!UICONTROL Marketplace] à un segment, les caractéristiques ne sont utilisées que pour l’estimation du segment, jusqu’à ce que vous vous abonniez au flux de données correspondant. Les caractéristiques provenant de flux de données auxquels vous n’êtes pas abonné sont marquées d’une icône de panier dans la liste des caractéristiques. Cliquez sur le nom de la caractéristique pour accéder à la page du flux de données et vous y abonner.
>
>![marketplace-not-subscribed](assets/trait-recommendations-marketplace.png)
>
>Vous ne pouvez enregistrer un segment avec des caractéristiques tierces qu’après vous être abonné aux flux de données correspondants.

### Segments existants

1. Accédez à **[!UICONTROL Audience Data]>[!UICONTROL Segments]**, sélectionnez le segment à modifier et cliquez sur ![Modifier](assets/edit-button.png).
1. Faites défiler l’écran jusqu’à la liste déroulante [!UICONTROL Traits].
1. Vous pouvez voir les caractéristiques recommandées, qui sont similaires aux caractéristiques déjà présentes dans la règle de segment. Faites défiler l’écran vers le bas pour afficher toutes les caractéristiques recommandées.
1. (Facultatif) Pour exclure les caractéristiques recommandées de certaines sources de données, cliquez sur le symbole **X** correspondant aux sources de données à exclure.

   >[!NOTE]
   >
   >Les sources de données exclues s’affichent juste au-dessus de la liste des caractéristiques recommandées. Cliquez sur **X** dans la zone grise pour supprimer les exclusions et afficher à nouveau les résultats des sources de données respectives.
1. Pour ajouter des caractéristiques recommandées à la règle de segment, cliquez sur le symbole **+** .

Lorsque vous créez ou modifiez un segment et ajoutez une caractéristique à la règle de segment, vous voyez un maximum de cinquante caractéristiques recommandées, semblables à celle que vous avez ajoutée. Si la règle de segment contient plusieurs caractéristiques, l’Audience Manager utilise une méthode de robot rond pour afficher la meilleure correspondance pour chaque caractéristique, puis la deuxième meilleure correspondance pour chaque caractéristique, et ainsi de suite, pour les cinquante plus grandes caractéristiques par population, dans la règle de segment.

![Trois caractéristiques de base](assets/three-base-traits.png)

Par exemple, lorsqu’il existe trois caractéristiques dans la règle de segment, comme illustré ci-dessous, les caractéristiques recommandées sont les suivantes :

1. la meilleure correspondance pour la caractéristique 3 (la caractéristique ayant la plus grande population) ;
1. Meilleure correspondance pour la caractéristique 1 ;
1. Correspondance la mieux adaptée à la caractéristique 2 ;
1. La deuxième meilleure correspondance pour la caractéristique 3 ;
1. La deuxième meilleure correspondance pour la caractéristique 1, et ainsi de suite jusqu’à ce que vous atteigniez cinquante caractéristiques.

Pour obtenir des recommandations pour une caractéristique spécifique, vous pouvez cliquer sur les caractéristiques de la règle de segment (1) ou de la vue des caractéristiques recommandées (2).

![base-traits-example](assets/three-base-traits-numbered.png)

Cliquer sur une caractéristique propriétaire ouvre une fenêtre contextuelle, comme illustré dans l’image ci-dessous. Si les caractéristiques recommandées ne font pas partie du segment, vous pouvez les ajouter au segment en appuyant sur **+**.

![ajouter à un segment](assets/add_to_segments.png)

>[!TIP]
>
>Les sources de données exclues de la page principale sont prises en compte lors de la génération de recommandations dans la fenêtre contextuelle d’informations sur les caractéristiques. Et, si vous excluez des sources de données dans cette vue, les exclusions s’appliquent à la page principale.

>[!NOTE]
>
>Les caractéristiques recommandées peuvent être vos caractéristiques propriétaires ou tierces à partir des flux de données auxquels vous êtes abonné dans [!UICONTROL Audience Marketplace].

## Fonctionnement

Pour générer des recommandations de caractéristiques, l’Audience Manager calcule la [similarité Jaccard](https://en.wikipedia.org/wiki/Jaccard_index) entre la caractéristique cible et toutes les autres caractéristiques auxquelles votre compte a accès, y compris les données tierces. L’Audience Manager affiche alors jusqu’à cinquante caractéristiques présentant la plus grande similarité.

## Score de similarité de caractéristiques {#trait-similarity-score}

L’Audience Manager calcule la [!UICONTROL Trait Similarity Score] entre deux caractéristiques en calculant l’intersection et l’union en termes du nombre de [!UICONTROL UUID]s, puis en divisant les deux. Pour deux caractéristiques A et B, le calcul ressemble à ceci :

![jaccard-similarité](assets/jaccard_similarity.png)

Voir également les deux exemples ci-dessous.

### Exemple 1 - Score de similarité de caractéristiques faible

Compte tenu de deux caractéristiques A et B, supposons que chacune des caractéristiques a une population de 1 000 000 [!UICONTROL UUID]s, 25 000 [!UICONTROL UUID]dont la population est admissible pour les deux caractéristiques.
En utilisant la formule ci-dessus, vous obtiendrez : 25 000 / 1 975 000 = 0,012. Il s’agit d’une valeur [!UICONTROL Trait Similarity Score] faible, les deux caractéristiques sont très différentes.

![trait-recommandations-faible-chevauchement](assets/Trait-Recommendations-Low-overlap.png)

### Exemple 2 - Score de similarité de caractéristiques

Si les mêmes caractéristiques A et B présentent 400 000 [!UICONTROL UUID]s qui répondent aux deux caractéristiques, la valeur [!UICONTROL Trait Similarity Score] est beaucoup plus élevée :
400 000 / 1 600 000 = 0,25

![trait-recommandations-haut-chevauchement](assets/Trait-Recommendations-High-overlap.png)

### Interprétation du score de similarité de caractéristiques

Utilisez le tableau ci-dessous comme guide approximatif de la similarité de caractéristiques. Ce guide repose sur les scores de similarité observés dans la majorité des caractéristiques.

| [!UICONTROL Trait Similarity Score] | Significativité |
|---------|----------|
| 0.1 et versions ultérieures | Forte similarité entre les caractéristiques |
| 0,03 à 0,1 | similarité moyenne entre les caractéristiques |
| 0,01 à 0,03 | Faible similarité entre les caractéristiques |
| 0 à 0,01 | Très faible similarité entre les caractéristiques |

## Contrôle d’accès en fonction du rôle (RBAC)

Pour les entreprises qui utilisent [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]), vous devez disposer des autorisations nécessaires pour créer et modifier des segments afin d’afficher les caractéristiques recommandées. Les recommandations de caractéristiques que vous voyez ne sont que celles provenant de sources de données auxquelles vous avez accès via [!UICONTROL RBAC].

>[!IMPORTANT]
>
>Pour ajouter [!UICONTROL Marketplace Recommendations] à un segment, les utilisateurs doivent d’abord s’abonner aux flux de données correspondants. Seuls les utilisateurs disposant de droits d’administrateur peuvent s’abonner à des flux de données [!UICONTROL Audience Marketplace].

Pour en savoir plus sur les [!UICONTROL RBAC] contrôles [ici](../administration/administration-overview.md).

## Limites

* Actuellement, l’Audience Manager n’affiche pas les caractéristiques de dossier comme caractéristiques recommandées. Pour en savoir plus sur les caractéristiques de dossier [ici](../traits/manage-folder-traits.md).
* Lors de l’affichage du Recommendations des caractéristiques, l’Audience Manager ne prend pas en compte les opérateurs [!DNL Boolean] ([!DNL AND], [!DNL OR], [!DNL NOT]) dans les règles de segment.
