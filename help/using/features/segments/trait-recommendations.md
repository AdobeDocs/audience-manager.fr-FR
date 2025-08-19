---
description: Grâce aux recommandations de caractéristiques, lorsque vous créez ou modifiez un segment dans le créateur de segments, vous obtenez des recommandations sur les caractéristiques supplémentaires que vous pouvez inclure et qui sont similaires aux caractéristiques de la règle de segment. Ajoutez les caractéristiques recommandées à votre segment pour élargir votre audience cible.
seo-description: Get live trait recommendations as you build your segments.
seo-title: Trait Recommendations
solution: Audience Manager
title: Recommandations de caractéristiques
feature: Segments
exl-id: 7ef862a9-7354-49fb-9af0-925d827a5165
source-git-commit: 432b12c4d4fb567d1a0bcaa9d12baaac5e3ae0f7
workflow-type: tm+mt
source-wordcount: '1584'
ht-degree: 5%

---

# Recommandations de caractéristiques

Obtenez des recommandations de caractéristiques en direct à mesure que vous créez vos segments à partir de vos propres caractéristiques propriétaires et de vos flux de données [!UICONTROL Audience Marketplace].

## Démonstration vidéo

Commencez par regarder la vidéo [!UICONTROL Trait Recommendations] ci-dessous, puis poursuivez la lecture pour plus d’informations. La démonstration vidéo vous explique comment utiliser les recommandations de vos propres caractéristiques propriétaires, ainsi que les recommandations de caractéristiques de [!UICONTROL Audience Marketplace] flux de données auxquels *vous êtes déjà abonné*.

>[!VIDEO](https://video.tv.adobe.com/v/40839?captions=fre_fr)

La vidéo suivante décrit le workflow de [!UICONTROL Marketplace Recommendations] et vous montre comment ajouter des caractéristiques à vos segments, en fonction des recommandations des flux de données dans [!UICONTROL Audience Marketplace]. Ces recommandations sont basées sur des flux de données auxquels *vous n’êtes pas abonné*.

>[!VIDEO](https://video.tv.adobe.com/v/33197?captions=fre_fr)

## Présentation

[!UICONTROL Trait Recommendations], optimisé par [!DNL Adobe Sensei], vous apporte des informations essentielles pour vos workflows Audience Manager quotidiens.
Avec [!UICONTROL Trait Recommendations], lorsque vous créez ou modifiez un segment dans le [créateur de segments](segment-builder.md), vous obtenez des recommandations sur les caractéristiques supplémentaires que vous pouvez inclure, qui sont similaires aux caractéristiques de la règle de segment.

Audience Manager vous présente les recommandations de caractéristiques à la fois à partir de vos caractéristiques propriétaires, dans la section **[!UICONTROL Recommendations]** , et à partir de **[!UICONTROL Audience Marketplace]**, dans la section **[!UICONTROL Recommendations from Marketplace]** .

Ajoutez les caractéristiques recommandées à votre segment pour élargir votre audience cible.

![Présentation des recommandations de caractéristiques](assets/trait-recommendations-overview-full.png)

**En résumé :**

* Audience Manager affiche les caractéristiques propriétaires dans la section [!UICONTROL Recommendations] . Les recommandations de marché provenant de flux publics et privés auxquels vous n’êtes pas abonné sont visibles dans la section [!UICONTROL Recommendations from Marketplace] . Cliquez sur le nom du flux pour accéder à [!UICONTROL Audience Marketplace] et vous abonner.
* Audience Manager affiche un maximum de cinquante caractéristiques similaires à celle de la règle de segment.
* Vous pouvez filtrer les sources de données à partir desquelles vous ne souhaitez pas afficher de recommandations.
* Lors du calcul des similitudes, Audience Manager prend en compte les [UUID](../../reference/ids-in-aam.md) qualifiés pour la caractéristique au cours des 30 derniers jours.
* Si le message d’erreur suivant s’affiche : « Aucune caractéristique similaire trouvée. Caractéristique(s) peut(ent) être trop nouvelle(s). », cela signifie qu’il n’y a eu aucune activité pour cette caractéristique au cours des 30 derniers jours ou qu’Audience Manager n’a pas encore mis à jour les recommandations pour cette caractéristique. Réessayez dans 24 heures.

## Cas d’utilisation

Avec [!UICONTROL Trait Recommendations], vous pouvez améliorer vos workflows, selon la manière dont vous utilisez Audience Manager :

* En tant que spécialiste marketing, vous pouvez rapidement trouver des audiences intéressées par des produits complémentaires à l’aide de caractéristiques similaires, afin d’augmenter votre portée.
* Si vous utilisez Audience Manager en tant qu’éditeur, avec [!UICONTROL Trait Recommendations], vous pouvez comprendre le comportement de l’audience et créer de meilleurs segments pour les ventes d’annonces publicitaires ou l’acquisition d’utilisateurs.
* En tant qu’acheteur de données [!UICONTROL Audience Marketplace], je souhaite découvrir des données tierces pertinentes sans avoir à parcourir un grand nombre de flux.
* En tant que fournisseur de données [!UICONTROL Audience Marketplace], je souhaite recommander des données pertinentes aux acheteurs afin que je puisse bénéficier d’abonnements optimaux et pertinents.

## Différences entre les recommandations de caractéristiques et les modèles algorithmiques

### Modèles algorithmiques

[!UICONTROL Algorithmic Models] ne trouve pas seulement les caractéristiques les plus influentes, mais note également les utilisateurs en fonction de ces caractéristiques et attribue à chaque utilisateur une note individuelle. Vous créez ensuite des caractéristiques algorithmiques pour cibler vos utilisateurs. Grâce aux contrôles de précision et de portée de la [!UICONTROL Trait Builder], vous pouvez spécifier les utilisateurs parmi tous ceux qui disposent des caractéristiques influentes que vous souhaitez cibler.

[!UICONTROL Algorithmic Models] vous permet de sélectionner des utilisateurs avec différents niveaux de précision et de tester dans [!UICONTROL Audience Lab] quel groupe d’utilisateurs effectue la meilleure conversion. Consultez les cas d’utilisation détaillés dans [Comparaison des modèles dans Audience Lab](../../features/audience-lab/audience-lab-use-cases.md#compare-models).

En [!UICONTROL Algorithmic Models], le modèle s’exécute tous les 8 jours et actualise les utilisateurs qualifiés pour les caractéristiques algorithmiques.

### Recommandations de caractéristiques

[!UICONTROL Trait Recommendations] est un moyen rapide d’obtenir des informations sur d’autres caractéristiques similaires à celles que vous utilisez dans un segment.

Vous devez utiliser [!UICONTROL Trait Recommendations] dans les cas suivants :

* vous avez besoin d’insights rapides en créant un segment ;
* vous utilisez les segments pour des campagnes courtes ou vous souhaitez supprimer rapidement des audiences qui se convertissent ;
* vous essayez de maximiser votre portée.

## Workflow

Lors de la création ou de la modification d’un segment dans [Créateur de segments](segment-builder.md), vous pouvez explorer des caractéristiques similaires à celles de la règle de segment. Le workflow [Créateur de segments](segment-builder.md) est très similaire pour les segments nouveaux et existants :

### Nouveaux Segments

1. Accédez à **Données d’audience > Segments**, puis cliquez sur **Ajouter**.
1. Dans la liste déroulante **Caractéristiques**, ajoutez au moins une caractéristique à la règle de segment.
1. Vous pouvez voir les caractéristiques recommandées propriétaires et les recommandations de caractéristiques [!UICONTROL Audience Marketplace] à partir des flux auxquels vous êtes abonné, dans la section **[!UICONTROL Recommendations]** . La section **[!UICONTROL Recommendations from Marketplace]** vous présente les recommandations de caractéristiques des flux auxquels vous n’êtes pas abonné. Toutes ces recommandations sont similaires aux caractéristiques que vous avez ajoutées à la règle de segment. Faites défiler la page vers le bas pour afficher toutes les caractéristiques recommandées.
1. (Facultatif) Pour exclure les caractéristiques propriétaires recommandées de certaines sources de données, cliquez sur le symbole **X** pour les sources de données à exclure.

   >[!NOTE]
   >
   >Les sources de données exclues sont affichées juste au-dessus de la liste des caractéristiques recommandées. Cliquez sur **X** dans la zone grise pour supprimer les exclusions et afficher à nouveau les résultats des sources de données respectives.
1. Pour ajouter des caractéristiques recommandées à la règle de segment, cliquez sur le symbole **+**.

>[!IMPORTANT]
>
>Lors de l’ajout de caractéristiques [!UICONTROL Marketplace] à un segment, les caractéristiques ne sont utilisées que pour l’estimation du segment, jusqu’à ce que vous vous abonniez au flux de données correspondant. Les caractéristiques provenant de flux de données auxquels vous n’êtes pas abonné sont marquées d’une icône de panier dans la liste des caractéristiques. Cliquez sur le nom de la caractéristique pour accéder à la page du flux de données et vous y abonner.
>
>![marketplace-not-subscribed](assets/trait-recommendations-marketplace.png)
>
>Vous ne pouvez enregistrer un segment avec des caractéristiques tierces qu’après vous être abonné aux flux de données correspondants.

### Segments existants

1. Accédez à **[!UICONTROL Audience Data]>[!UICONTROL Segments]**, sélectionnez le segment à modifier et cliquez sur ![Modifier](assets/edit-button.png).
1. Faites défiler l’écran jusqu’à la zone de liste déroulante [!UICONTROL Traits] .
1. Vous pouvez voir les caractéristiques recommandées, qui sont similaires aux caractéristiques déjà présentes dans la règle de segment. Faites défiler la page vers le bas pour afficher toutes les caractéristiques recommandées.
1. (Facultatif) Pour exclure les caractéristiques recommandées de certaines sources de données, cliquez sur le symbole **X** correspondant aux sources de données à exclure.

   >[!NOTE]
   >
   >Les sources de données exclues sont affichées juste au-dessus de la liste des caractéristiques recommandées. Cliquez sur **X** dans la zone grise pour supprimer les exclusions et afficher à nouveau les résultats des sources de données respectives.
1. Pour ajouter des caractéristiques recommandées à la règle de segment, cliquez sur le symbole **+**.

Lorsque vous créez ou modifiez un segment et ajoutez une caractéristique à la règle de segment, vous voyez un maximum de cinquante caractéristiques recommandées, similaires à celle que vous avez ajoutée. Si la règle de segment contient plusieurs caractéristiques, Audience Manager utilise une méthode circulaire pour afficher la meilleure correspondance pour chaque caractéristique, puis la deuxième meilleure correspondance pour chaque caractéristique, et ainsi de suite pour les cinquante caractéristiques les plus importantes par population, dans la règle de segment.

![trois caractéristiques de base](assets/three-base-traits.png)

Par exemple, lorsque la règle de segment comporte trois caractéristiques, comme illustré ci-dessous, les caractéristiques recommandées sont les suivantes :

1. Meilleure correspondance pour le trait 3 (le trait avec la plus grande population);
1. Meilleure correspondance pour la caractéristique 1 ;
1. Meilleure correspondance pour la caractéristique 2 ;
1. Deuxième meilleure correspondance pour le caractère 3 ;
1. Deuxième meilleure correspondance pour le trait 1, et ainsi de suite jusqu&#39;à ce que vous arriviez à cinquante traits.

Pour obtenir des recommandations relatives à une caractéristique spécifique, vous pouvez cliquer sur les caractéristiques dans la règle de segment (1) ou dans la vue des caractéristiques recommandées (2).

![base-traits-example](assets/three-base-traits-numbered.png)

Cliquez sur une caractéristique propriétaire pour ouvrir une fenêtre pop-up, comme illustré dans l’image ci-dessous. Si les caractéristiques recommandées ne font pas partie du segment, vous pouvez les ajouter au segment en appuyant sur **+**.

![ajout à un segment](assets/add_to_segments.png)

>[!TIP]
>
>Les sources de données exclues de la page principale sont prises en compte lors de la génération de recommandations dans la fenêtre pop-up d’informations sur les caractéristiques. De plus, si vous excluez des sources de données dans cette vue, les exclusions s’appliquent à la page principale.

>[!NOTE]
>
>Les caractéristiques recommandées peuvent être vos caractéristiques propriétaires ou des caractéristiques tierces provenant des flux de données auxquels vous êtes abonné dans [!UICONTROL Audience Marketplace].

## Fonctionnement

Pour produire des recommandations de caractéristiques, Audience Manager calcule la [similarité Jaccard](https://en.wikipedia.org/wiki/Jaccard_index) entre la caractéristique cible et toutes les autres caractéristiques auxquelles votre compte a accès, y compris les données tierces. Audience Manager affiche ensuite jusqu’à cinquante caractéristiques ayant la similarité la plus élevée.

## Score de similarité des caractéristiques {#trait-similarity-score}

Audience Manager calcule la [!UICONTROL Trait Similarity Score] entre deux caractéristiques en calculant l’intersection et l’union en termes de nombre de [!UICONTROL UUID], puis divise les deux. Pour deux caractéristiques A et B, le calcul est le suivant :

![jaccard-similarity](assets/jaccard_similarity.png)

Voir aussi les deux exemples ci-dessous.

### Exemple 1 - Score De Similarité De Faible Caractéristique

Si l’on considère deux caractéristiques A et B, supposons que chacune d’elles ait une population de 1 000 000 [!UICONTROL UUID], dont 25 000 [!UICONTROL UUID] sont éligibles pour les deux caractéristiques.
En utilisant la formule ci-dessus, cela donnera : 25 000 / 1 975 000 = 0,012. C&#39;est un [!UICONTROL Trait Similarity Score] faible, les deux traits sont très différents.

![caractéristique-recommendations-low-overlap](assets/Trait-Recommendations-Low-overlap.png)

### Exemple 2 - Score De Similarité Des Caractéristiques

Si les mêmes caractéristiques A et B avaient 400 000 [!UICONTROL UUID]s qui remplissent les critères pour les deux caractéristiques, la [!UICONTROL Trait Similarity Score] est beaucoup plus élevée :
400 000 / 1 600 000 = 0,25

![trait-recommendations-high-overlap](assets/Trait-Recommendations-High-overlap.png)

### Comment interpréter le score de similarité des caractéristiques

Utilisez le tableau ci-dessous comme guide grossier pour la similarité des caractéristiques. Ce guide est basé sur les scores de similarité observés pour la majorité des caractéristiques.

| [!UICONTROL Trait Similarity Score] | Significativité |
|---------|----------|
| 0.1 et versions ultérieures | Similarité élevée entre les caractéristiques |
| 0,03 - 0,1 | Similarité Medium entre les caractéristiques |
| 0,01 - 0,03 | Faible similarité entre les caractéristiques |
| 0 - 0,01 | Très faible similarité entre les caractéristiques |

## Contrôle d’accès en fonction du rôle (RBAC)

Pour les sociétés qui utilisent [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]), vous devez disposer des autorisations nécessaires pour créer et modifier des segments afin d’afficher les caractéristiques recommandées. Les recommandations de caractéristiques que vous voyez ne sont que celles des sources de données auxquelles vous avez accès via [!UICONTROL RBAC].

>[!IMPORTANT]
>
>Pour ajouter des [!UICONTROL Marketplace Recommendations] à un segment, les utilisateurs doivent d’abord s’abonner aux flux de données correspondants. Seuls les utilisateurs disposant de droits d’administrateur peuvent s’abonner aux flux de données [!UICONTROL Audience Marketplace].

En savoir plus sur [!UICONTROL RBAC] contrôles [ici](../administration/administration-overview.md).

## Limites

* Actuellement, Audience Manager n’affiche pas les caractéristiques de dossier comme caractéristiques recommandées. En savoir plus sur les caractéristiques de dossier [ici](../traits/manage-folder-traits.md).
* Lors de l’affichage des recommandations de caractéristiques, Audience Manager ne prend pas en compte les opérateurs [!DNL Boolean] ([!DNL AND], [!DNL OR], [!DNL NOT]) dans les règles de segment.
