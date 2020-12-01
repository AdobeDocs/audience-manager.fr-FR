---
description: Avec Trait Recommendations, lorsque vous créez ou modifiez un segment dans Segment Builder, vous obtenez des recommandations sur les caractéristiques supplémentaires que vous pouvez inclure et qui sont similaires aux caractéristiques de la règle de segment. Ajoutez les caractéristiques recommandées à votre segment pour élargir votre audience cible.
seo-description: Bénéficiez de recommandations de caractéristiques dynamiques lorsque vous créez vos segments.
seo-title: Recommandations de caractéristiques
solution: Audience Manager
title: Recommandations de caractéristiques
feature: Segments
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1573'
ht-degree: 8%

---


# Recommandations de caractéristiques

Bénéficiez de recommandations de caractéristiques dynamiques lorsque vous créez vos segments, à partir de vos propres caractéristiques propriétaires et de flux de données [!UICONTROL Audience Marketplace].

## Démonstration vidéo

Début en regardant la vidéo [!UICONTROL Trait Recommendations] ci-dessous, puis en lisant pour plus d&#39;informations. La démonstration vidéo vous montre comment utiliser les recommandations issues de vos propres caractéristiques propriétaires, ainsi que les recommandations de caractéristiques provenant de flux de données [!UICONTROL Audience Marketplace] auxquels *vous êtes déjà abonné*.

>[!VIDEO](https://video.tv.adobe.com/v/26228/)

La vidéo suivante décrit le flux de travaux de [!UICONTROL Marketplace Recommendations], qui montre comment ajouter des caractéristiques à vos segments, en fonction des recommandations issues de flux de données dans [!UICONTROL Audience Marketplace]. Ces recommandations sont basées sur des flux de données auxquels *vous n’êtes pas abonné*.

>[!VIDEO](https://video.tv.adobe.com/v/29363/)

## Présentation

[!UICONTROL Trait Recommendations], optimisé par  [!DNL Adobe Sensei], intègre la science des données dans vos workflows d&#39;Audience Manager quotidiens.
Avec [!UICONTROL Trait Recommendations], lorsque vous créez ou modifiez un segment dans [Créateur de segments](segment-builder.md), vous obtenez des recommandations sur les caractéristiques supplémentaires que vous pouvez inclure, qui sont similaires aux caractéristiques de la règle de segment.

L&#39;Audience Manager vous montre les recommandations de caractéristiques provenant à la fois de vos caractéristiques propriétaires, dans la section **[!UICONTROL Recommendations]** et de **[!UICONTROL Audience Marketplace]**, dans la section **[!UICONTROL Recommendations from Marketplace]**.

Ajoutez les caractéristiques recommandées à votre segment pour élargir votre audience cible.

![Présentation de Trait Recommendations](assets/trait-recommendations-overview-full.png)

**En un mot :**

* L’Audience Manager présente les caractéristiques de premier niveau dans la section [!UICONTROL Recommendations]. Les recommandations Marketplace provenant de flux publics et privés auxquels vous n’êtes pas abonné sont visibles dans la section [!UICONTROL Recommendations from Marketplace]. Cliquez sur le nom du flux pour accéder à [!UICONTROL Audience Marketplace] et vous abonner.
* L’Audience Manager affiche un maximum de cinquante caractéristiques similaires à celle de la règle de segment.
* Vous pouvez filtrer les sources de données à partir desquelles vous ne souhaitez afficher aucune recommandation.
* Lors du calcul des similitudes, l’Audience Manager prend en compte [UUIDs](../../reference/ids-in-aam.md) qui ont été qualifiés pour la caractéristique au cours des 30 derniers jours.
* Si vous voyez le message d&#39;erreur &quot;Aucune caractéristique similaire trouvée. Les caractéristiques peuvent être trop nouvelles.&quot;, cela signifie qu&#39;il n&#39;y a eu aucune activité pour cette caractéristique au cours des 30 derniers jours ou que l&#39;Audience Manager n&#39;a pas encore mis à jour les recommandations pour cette caractéristique. Veuillez réessayer dans 24 heures.

## Cas d’utilisation

Avec [!UICONTROL Trait Recommendations], vous pouvez améliorer vos workflows en fonction de la manière dont vous utilisez l&#39;Audience Manager :

* En tant que spécialiste du marketing, vous pouvez rapidement trouver des audiences intéressées par des produits complémentaires à l’aide de caractéristiques similaires, afin d’augmenter votre portée.
* Si vous utilisez l’Audience Manager en tant qu’éditeur, avec [!UICONTROL Trait Recommendations], vous pouvez comprendre le comportement des audiences et créer de meilleurs segments pour les ventes d’annonces ou l’acquisition d’utilisateurs.
* En tant qu’acheteur de données [!UICONTROL Audience Marketplace], je souhaite découvrir des données tierces pertinentes sans parcourir un grand nombre de flux.
* En tant que fournisseur de données [!UICONTROL Audience Marketplace], je souhaite recommander des données pertinentes aux acheteurs afin de pouvoir bénéficier d&#39;abonnements optimaux et pertinents.

## Différences entre Recommendations de caractéristiques et modèles algorithmiques

### Modèles algorithmiques

[!UICONTROL Algorithmic Models] non seulement trouve-t-on les caractéristiques les plus influentes, mais il note également les utilisateurs en fonction de ces caractéristiques et attribue à chaque utilisateur un score individuel. Vous créez ensuite des caractéristiques algorithmiques pour cibler vos utilisateurs. Grâce aux contrôles de précision et de portée de [!UICONTROL Trait Builder], vous pouvez spécifier les utilisateurs parmi tous ceux qui ont les caractéristiques influentes que vous souhaitez cible.

[!UICONTROL Algorithmic Models] vous permet de sélectionner des utilisateurs à différents niveaux de précision et de tester  [!UICONTROL Audience Lab] quel groupe d’utilisateurs effectue le plus de conversions. Consultez les cas d’utilisation détaillés dans [Comparaison des modèles dans Audience Lab](../../features/audience-lab/audience-lab-use-cases.md#compare-models).

Dans [!UICONTROL Algorithmic Models], le modèle s’exécute tous les 8 jours et actualise les utilisateurs qualifiés pour les caractéristiques algorithmiques.

### Recommandations de caractéristiques

[!UICONTROL Trait Recommendations] est un moyen rapide d’obtenir des informations sur d’autres caractéristiques similaires à celles que vous utilisez dans un segment.

Vous devez utiliser [!UICONTROL Trait Recommendations] lorsque :

* vous avez besoin d’insights rapides en créant un segment ;
* vous utilisez les segments pour des campagnes courtes ou vous souhaitez supprimer rapidement des audiences qui se convertissent ;
* vous essayez de maximiser votre portée.

## Workflow

Lors de la création ou de la modification d’un segment dans [Créateur de segments](segment-builder.md), vous pouvez explorer des caractéristiques similaires aux caractéristiques de la règle de segment. Le flux de travail du créateur de segments [](segment-builder.md) est très similaire pour les segments nouveaux et existants :

### Nouveaux segments

1. Accédez à **Données d’Audience > Segments**, puis cliquez sur **Ajouter nouveau**.
1. Dans la liste déroulante **Caractéristiques**, ajoutez au moins une caractéristique à la règle de segment.
1. Vous pouvez afficher les caractéristiques recommandées propriétaires et les recommandations de caractéristiques [!UICONTROL Audience Marketplace] des flux auxquels vous êtes abonné, dans la section **[!UICONTROL Recommendations]**. La section **[!UICONTROL Recommendations from Marketplace]** présente les recommandations de caractéristiques des flux auxquels vous n’êtes pas abonné. Toutes ces recommandations sont similaires aux caractéristiques que vous avez ajoutées à la règle de segmentation. Faites défiler la page vers le bas pour afficher toutes les caractéristiques recommandées.
1. (Facultatif) Pour exclure les caractéristiques propriétaires recommandées de certaines sources de données, cliquez sur le symbole **X** correspondant aux sources de données à exclure.

   >[!NOTE]
   >
   >Les sources de données exclues sont affichées juste au-dessus de la liste des caractéristiques recommandées. Cliquez sur **X** dans la zone grise pour supprimer les exclusions et afficher à nouveau les résultats des sources de données respectives.
1. Pour ajouter des caractéristiques recommandées à la règle de segment, cliquez sur le symbole **+**.

>[!IMPORTANT]
>
>Lors de l’ajout de caractéristiques [!UICONTROL Marketplace] à un segment, celles-ci ne sont utilisées que pour l’estimation des segments, jusqu’à ce que vous vous abonniez au flux de données correspondant. Les caractéristiques provenant de flux de données auxquels vous n’êtes pas abonné sont marquées par une icône de panier dans la liste de caractéristiques. Cliquez sur le nom de la caractéristique pour accéder à la page de flux de données et vous y abonner.
>
>![sans abonnement au marché](assets/trait-recommendations-marketplace.png)
>
>Vous ne pouvez enregistrer un segment avec des caractéristiques tierces qu’après avoir souscrit un abonnement aux flux de données correspondants.

### Segments existants

1. Accédez à **[!UICONTROL Audience Data]>[!UICONTROL Segments]**, sélectionnez le segment à modifier et cliquez sur ![Modifier](assets/edit-button.png).
1. Faites défiler l&#39;écran jusqu&#39;à la liste déroulante [!UICONTROL Traits].
1. Vous pouvez afficher les caractéristiques recommandées, qui sont similaires aux caractéristiques déjà présentes dans la règle de segmentation. Faites défiler la page vers le bas pour afficher toutes les caractéristiques recommandées.
1. (Facultatif) Pour exclure les caractéristiques recommandées de certaines sources de données, cliquez sur le symbole **X** correspondant aux sources de données à exclure.

   >[!NOTE]
   >
   >Les sources de données exclues sont affichées juste au-dessus de la liste des caractéristiques recommandées. Cliquez sur **X** dans la zone grise pour supprimer les exclusions et afficher à nouveau les résultats des sources de données respectives.
1. Pour ajouter des caractéristiques recommandées à la règle de segment, cliquez sur le symbole **+**.

Lorsque vous créez ou modifiez un segment et ajoutez une caractéristique à la règle de segment, vous obtenez un maximum de cinquante caractéristiques recommandées, semblables à celles que vous avez ajoutées. Si la règle de segmentation contient plusieurs caractéristiques, l’Audience Manager utilise une méthode de robot circulaire pour afficher la meilleure correspondance pour chaque caractéristique, puis la deuxième meilleure correspondance pour chaque caractéristique, et ainsi de suite, pour les cinquante caractéristiques les plus importantes par population, dans la règle de segment.

![Trois caractéristiques de base](assets/three-base-traits.png)

Par exemple, s’il existe trois caractéristiques dans la règle de segment, comme illustré ci-dessous, les caractéristiques recommandées sont les suivantes :

1. la meilleure correspondance pour le trait 3 (trait ayant la plus grande population);
1. Meilleure correspondance pour la caractéristique 1 ;
1. Meilleure correspondance pour la caractéristique 2 ;
1. Deuxième meilleure correspondance pour le trait 3 ;
1. Deuxième meilleure correspondance pour la caractéristique 1, et ainsi de suite jusqu&#39;à ce que vous atteigniez cinquante traits.

Pour obtenir des recommandations pour une caractéristique spécifique, vous pouvez cliquer sur les caractéristiques dans la règle de segmentation (1) ou dans la vue de caractéristiques recommandée (2).

![base-traits-exemple](assets/three-base-traits-numbered.png)

Cliquez sur une caractéristique propriétaire pour ouvrir une fenêtre contextuelle, comme illustré dans l’image ci-dessous. Si les caractéristiques recommandées ne font pas partie du segment, vous pouvez les ajouter au segment en appuyant sur **+**.

![ajouter à un segment](assets/add_to_segments.png)

>[!TIP]
>
>Les sources de données exclues de la page principale sont prises en compte lors de la génération de recommandations dans la fenêtre contextuelle d’informations sur la caractéristique. Et si vous excluez les sources de données dans cette vue, les exclusions s’appliquent à la page principale.

>[!NOTE]
>
>Les caractéristiques recommandées peuvent être vos caractéristiques propriétaires ou tierces à partir de flux de données auxquels vous êtes abonné dans [!UICONTROL Audience Marketplace].

## Fonctionnement

Pour générer des recommandations de caractéristiques, l’Audience Manager calcule la [similarité Jaccard](https://en.wikipedia.org/wiki/Jaccard_index) entre la caractéristique de cible et toutes les autres caractéristiques auxquelles votre compte a accès, y compris les données tierces. L’Audience Manager affiche ensuite jusqu’à cinquante caractéristiques présentant la plus grande similarité.

## Score de similarité de caractéristiques {#trait-similarity-score}

L&#39;Audience Manager calcule le [!UICONTROL Trait Similarity Score] entre deux caractéristiques en calculant l&#39;intersection et l&#39;union en termes de nombre de [!UICONTROL UUID]s, puis divise les deux. Pour deux caractéristiques A et B, le calcul ressemble à ceci :

![jaccard-similarité](assets/jaccard_similarity.png)

Voir également les deux exemples ci-dessous.

### Exemple 1 - Note de similarité de caractéristiques faible

Compte tenu de deux caractéristiques A et B, supposons que chacune d&#39;elles a une population de 1 000 000 [!UICONTROL UUID]s, dont 25 000 [!UICONTROL UUID]s qui répondent aux deux caractéristiques.
En utilisant la formule ci-dessus, vous obtenez : 25 000 / 1 975 000 = 0,012. Il s&#39;agit d&#39;un [!UICONTROL Trait Similarity Score] faible, les deux caractéristiques sont très dissemblables.

![trait-recommandations-faible-chevauchement](assets/Trait-Recommendations-Low-overlap.png)

### Exemple 2 - Note de similarité de caractéristiques

Si les mêmes caractéristiques A et B avaient 400 000 [!UICONTROL UUID]s qui répondent aux deux caractéristiques, le [!UICONTROL Trait Similarity Score] est beaucoup plus élevé :
400 000 / 1 600 000 = 0,25

![caractéristiques-recommandations-chevauchement élevé](assets/Trait-Recommendations-High-overlap.png)

### Comment interpréter la note de similarité de caractéristiques

Utilisez le tableau ci-dessous comme un guide sommaire de la similarité des caractéristiques. Ce guide est basé sur les scores de similitude observés dans la majorité des caractéristiques.

| [!UICONTROL Trait Similarity Score] | Signification |
---------|----------|
| 0.1 et ultérieure | Haute similarité entre les caractéristiques |
| 0,03 - 0,1 | similarité moyenne entre les caractéristiques |
| 0,01 - 0,03 | Faible similarité entre les caractéristiques |
| 0 - 0,01 | Très faible similarité entre les caractéristiques |

## Contrôle d&#39;accès basé sur les rôles (RBAC)

Pour les sociétés qui utilisent [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]), vous devez disposer des autorisations nécessaires pour créer et modifier des segments afin d’afficher les caractéristiques recommandées. Les recommandations de caractéristiques que vous voyez ne sont que celles provenant de sources de données auxquelles vous avez accès via [!UICONTROL RBAC].

>[!IMPORTANT]
>
>Pour ajouter [!UICONTROL Marketplace Recommendations] à un segment, les utilisateurs doivent d’abord s’abonner aux flux de données correspondants. Seuls les utilisateurs disposant de droits d’administrateur peuvent s’abonner aux flux de données [!UICONTROL Audience Marketplace].

Pour en savoir plus sur les contrôles [!UICONTROL RBAC] [ici](../administration/administration-overview.md).

## Limites

* Actuellement, l’Audience Manager n’affiche pas les caractéristiques de dossier comme caractéristiques recommandées. Pour en savoir plus sur les caractéristiques des dossiers [ici](../traits/manage-folder-traits.md).
* Lors de l’affichage de Trait Recommendations, l’Audience Manager ne prend pas en compte les opérateurs [!DNL Boolean] ([!DNL AND], [!DNL OR], [!DNL NOT]) dans les règles de segment.
