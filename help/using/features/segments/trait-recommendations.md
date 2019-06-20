---
description: Avec Trait Recommendations, lorsque vous créez ou modifiez un segment dans Segment Builder, vous obtenez des recommandations sur les caractéristiques supplémentaires que vous pouvez inclure et qui sont similaires aux caractéristiques de la règle de segment. Ajoutez les caractéristiques recommandées à votre segment pour élargir votre audience cible.
seo-description: Obtenez des recommandations de caractéristiques dynamiques lorsque vous créez vos segments.
seo-title: Trait Recommendations
solution: Audience Manager
title: Trait Recommendations
uuid: null
translation-type: tm+mt
source-git-commit: e369038fbc83e28d10da24060699488faf783511

---


# Trait Recommendations

Obtenez des recommandations de caractéristiques dynamiques lorsque vous créez vos segments.

## Aperçu

[!UICONTROL Trait Recommendations], optimisé par [!DNL Adobe Sensei], apporte la science des données dans vos flux de travaux quotidiens d&#39;Audience Manager.
With [!UICONTROL Trait Recommendations], when you build or edit a segment in [Segment Builder](segment-builder.md), you get recommendations on additional traits you can include, that are similar to the traits in the segment rule. Ajoutez les caractéristiques recommandées à votre segment pour élargir votre audience cible.

![Présentation des recommandations de caractéristiques](assets/trait-recommendations-overview.png)

**En résumé :**

* Audience Manager affiche des caractéristiques propriétaires et des caractéristiques tierces des flux de données actuellement abonnés sous forme de caractéristiques recommandées.
* Audience Manager affiche au maximum cinquante caractéristiques similaires à celle de la règle de segment.
* Vous pouvez filtrer les sources de données à partir desquelles vous ne souhaitez pas voir de recommandations.
* When calculating similarities, Audience Manager considers [UUIDs](../../reference/ids-in-aam.md) that qualified for the trait during the last 30 days.
* Si le message d&#39;erreur « Aucune caractéristique similaire n&#39;est trouvée » s&#39;affiche. Les caractéristiques peuvent être trop nouvelles.  », cela signifie qu&#39;aucune activité pour cette caractéristique au cours des 30 derniers jours n&#39;a été effectuée ou qu&#39;Audience Manager n&#39;a pas encore mis à jour les recommandations pour cette caractéristique. Veuillez réessayer dans 24 heures.

## Cas d’utilisation

With [!UICONTROL Trait Recommendations], you can improve your workflows, depending on how you use Audience Manager:

* En tant que spécialiste du marketing, vous pouvez rapidement identifier les audiences intéressées par des produits complémentaires grâce à des caractéristiques similaires, afin que vous puissiez augmenter votre portée.
* If you use Audience Manager as a publisher, with [!UICONTROL Trait Recommendations], you can understand audience behavior and build better segments for ad sales or user acquisition.

## Différences entre les recommandations de caractéristiques et les modèles algorithmiques

### Modèles algorithmiques

[!UICONTROL Algorithmic Models] recherche non seulement les caractéristiques les plus influentes, mais aussi les utilisateurs en fonction de ces caractéristiques et affecte un score individuel à chaque utilisateur. Vous créez ensuite des caractéristiques algorithmiques pour cibler vos utilisateurs. With accuracy and reach controls in the [!UICONTROL Trait Builder], you can specify which users amongst all those who have the influential traits you want to target.

[!UICONTROL Algorithmic Models] vous permet de sélectionner des utilisateurs à différents niveaux de précision et de tester dans [!UICONTROL Audience Lab] quel groupe d&#39;utilisateurs sont convertis de manière optimale. See the detailed use case in [Compare Models in Audience Lab](../../features/audience-lab/audience-lab-use-cases.md#compare-models).

In [!UICONTROL Algorithmic Models], the model runs every 8 days and refreshes the users qualified for algorithmic traits.

### Trait Recommendations

[!UICONTROL Trait Recommendations] est un moyen rapide d&#39;obtenir des informations sur d&#39;autres caractéristiques similaires à celles que vous utilisez dans un segment.

You should use [!UICONTROL Trait Recommendations] when:

* Vous avez besoin d&#39;informations rapides lors de la création d&#39;un segment ;
* Vous utilisez les segments pour des campagnes courtes ou lorsque vous souhaitez rapidement supprimer le public qui effectue des conversions ;
* Vous tentez d&#39;optimiser la portée.

## Workflow

When building or editing a segment in [Segment Builder](segment-builder.md), you can explore traits similar to the traits in the segment rule. Le flux de travaux du créateur de segments est très similaire pour les segments nouveaux et existants :

### Nouveaux segments

1. In **Audience Data &gt; Segments**, select **Add New**.
1. In the **Traits** drop-down box, add at least one trait to the segment rule.
1. Vous pouvez maintenant voir les caractéristiques recommandées similaires aux caractéristiques que vous avez ajoutées à la règle de segment. Faites défiler la page vers le bas pour afficher toutes les caractéristiques recommandées.
1. (Optional) To exclude recommended traits from certain data sources, click the **X** symbol for the data sources you want to exclude.
   > [!NOTE]
   > 
   >Les sources de données exclues s&#39;affichent juste au-dessus de la liste des caractéristiques recommandées. Press **X** in the grey box to remove the exclusions and see results from the respective data sources again.
1. To add recommended traits to the segment rule, click the **+** symbol.

### Segments existants

1. Go to **[!UICONTROL Audience Data]&gt;[!UICONTROL Segments]**, select the segment you want to edit and press ![Edit](assets/edit-button.png).
1. Scroll down to the [!UICONTROL Traits] drop-down box.
1. Vous pouvez voir les caractéristiques recommandées, similaires aux caractéristiques déjà présentes dans la règle de segment. Faites défiler la page vers le bas pour afficher toutes les caractéristiques recommandées.
1. (Optional) To exclude recommended traits from certain data sources, click the **X** symbol for the data sources you want to exclude.
   > [!NOTE]
   > 
   >Les sources de données exclues s&#39;affichent juste au-dessus de la liste des caractéristiques recommandées. Press **X** in the grey box to remove the exclusions and see results from the respective data sources again.
1. To add recommended traits to the segment rule, click the **+** symbol.

Lorsque vous créez ou modifiez un segment et que vous ajoutez une caractéristique à la règle de segment, un maximum de cinquante caractéristiques recommandées est affiché, semblable à celui que vous avez ajouté. Si la règle de segment contient plusieurs caractéristiques, Audience Manager utilise une méthode ronde en double pour montrer la meilleure correspondance pour chaque caractéristique, puis la deuxième correspondance meilleure pour chaque caractéristique, et ainsi de suite, pour les cinquante caractéristiques les plus importantes par population, dans la règle de segment.

![Trois caractéristiques de base](assets/three-base-traits.png)

Par exemple, lorsqu&#39;il existe trois caractéristiques dans la règle de segment, comme illustré ci-dessous, les caractéristiques recommandées sont les suivantes :

1. Meilleure correspondance pour la caractéristique 3 (caractéristique avec la plus grande population) ;
2. Meilleure correspondance pour la caractéristique 1 ;
3. Meilleure correspondance pour la caractéristique 2 ;
4. Correspondance second meilleure pour la caractéristique 3 ;
5. Correspondance second meilleure pour caractéristique 1, etc. jusqu&#39;à cinquante caractéristiques.

Pour obtenir des recommandations pour une caractéristique spécifique, vous pouvez cliquer sur les caractéristiques dans la règle de segment (1) ou dans la vue des caractéristiques recommandées (2).

![](assets/three-base-traits-numbered.png)

Cliquez sur une caractéristique pour ouvrir une fenêtre contextuelle, comme illustré dans l&#39;image ci-dessous. If the recommended traits are not part of the segment, you can add them to the segment by pressing **+**.

![](assets/add_to_segments.png)

> [!TIP]
>
>Les sources de données exclues issues de la page principale sont prises en compte lors de la génération des recommandations dans la fenêtre contextuelle d&#39;informations sur la caractéristique. Et, si vous excluez les sources de données dans cette vue, les exclusions s&#39;appliquent à la page principale.

> [!NOTE]
>
> Les caractéristiques recommandées peuvent être vos caractéristiques propriétaires ou tierces à partir des flux auxquels vous êtes abonné.

## Fonctionnement

To produce trait recommendations, Audience Manager computes the [Jaccard similarity](https://en.wikipedia.org/wiki/Jaccard_index) between the target trait and every other trait that your account has access to, including third-party data. Audience Manager affiche ensuite jusqu&#39;à cinquante caractéristiques dont la similarité est la plus élevée.

## Score de similarité de caractéristique

Audience Manager calculate the [!UICONTROL Trait Similarity Score] between two traits by computing the intersection and union in terms of the number of [!UICONTROL UUID]s and then divide the two. Pour deux caractéristiques A et B, le calcul ressemble à ceci :

![](assets/jaccard_similarity.png)

Voir également les deux exemples ci-dessous.

### Exemple 1 - Score de similarité faible trait

Given two traits A and B, let&#39;s say each of the traits has a population of 1,000,000 [!UICONTROL UUID]s, 25,000 [!UICONTROL UUID]s of which qualify for both traits.
Using the formula above, this will result in: 25,000 / 1,975,000 = 0.012. This is a low [!UICONTROL Trait Similarity Score], the two traits are very dissimilar.

![](assets/Trait-Recommendations-Low-overlap.png)

### Exemple 2 - Score de similarité de caractéristique

If the same traits A and B had 400,000 [!UICONTRL UUID]s that qualify for both traits, the [!UICONTROL Trait Similarity Score] is much higher:
400,000 / 1,600,000 = 0.25

![](assets/Trait-Recommendations-High-overlap.png)

### Interprétation du score de similarité de caractéristique

Utilisez le tableau ci-dessous comme guide brut pour la similarité des caractéristiques. Ce guide repose sur les scores de similarité observés à la majorité des caractéristiques.

| [!UICONTROL Trait Similarity Score] | Signification |
---------|----------|
| 0,1 et plus | Similarité élevée entre caractéristiques |
| 0.03 - 0.1 | Similarité moyenne entre caractéristiques |
| 0.01 - 0.03 | Similarité faible entre les caractéristiques |
| 0 - 0.01 | Similarité très faible entre les caractéristiques |

## RBAC (Role-Based Access Control)

For companies using [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]), you need to have permission to create and edit segments in order to see recommended traits. And, the recommended traits you see are only the ones from data sources that you have access to via [!UICONTROL RBAC]. Read more about [!UICONTROL RBAC] controls [here](../administration/administration-overview.md).

## Limites

* Actuellement, Audience Manager n&#39;affiche pas les caractéristiques de dossier comme caractéristiques recommandées. Read more about folder traits [here](../traits/manage-folder-traits.md).
* When displaying Trait Recommendations, Audience Manager does not take into account [!DNL Boolean] operators ([!DNL AND], [!DNL OR], [!DNL NOT]) in segment rules.