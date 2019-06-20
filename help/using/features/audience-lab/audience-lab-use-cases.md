---
description: Audience Lab active plusieurs cas d'utilisation en vous permettant d'utiliser des segments de base pour la création de groupes de test. Vous pouvez diviser les groupes de tests en plusieurs segments de test exclusifs, les mapper à différentes destinations, puis déterminer quels segments sont les plus efficaces pour générer des conversions.
seo-description: Audience Lab active plusieurs cas d'utilisation en vous permettant d'utiliser des segments de base pour la création de groupes de test. Vous pouvez diviser les groupes de tests en plusieurs segments de test exclusifs, les mapper à différentes destinations, puis déterminer quels segments sont les plus efficaces pour générer des conversions.
seo-title: Cas d'utilisation d'Audience Lab
solution: Audience Manager
title: Cas d'utilisation d'Audience Lab
topic: API DIL
uuid: 727 bec 8 a-df 9 a -40 cc-b 8 a 7-e 1980 d 146 a 84
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Audience Lab Use Cases {#audience-lab-use-cases}

[!UICONTROL Audience Lab] active plusieurs cas d&#39;utilisation en vous permettant d&#39;utiliser des segments de base pour la création de groupes de test. Vous pouvez diviser les groupes de tests en plusieurs segments de test exclusifs, les mapper à différentes destinations, puis déterminer quels segments sont les plus efficaces pour générer des conversions.

## Compare Models in Audience Lab {#compare-models}

You can use several different types and sources of models in [!DNL Audience Manager]. [!UICONTROL Audience Lab] offre un moyen facile de comparer les taux de conversion de vos clients à vos modèles actifs.

<!-- audience-lab-compare-models.xml -->

Dans ce cas d&#39;utilisation, vous comparez différents modèles. You can either use models created via an in-house data warehouse and import them in [!DNL Audience Manager] as [Onboarded Traits](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) or you can use the [Algorithmic Models](../../features/algorithmic-models/understanding-models.md) feature in [!DNL Audience Manager].

1. Create two models, either in the [Model Builder](../../features/algorithmic-models/create-model.md), or via an outside platform.
1. Create [algorithmic traits](../../features/traits/create-algorithmic-traits.md) from the algorithmic model or import your own models as onboarded traits.
1. Créer mutuellement - segments exclusifs de sorte que les utilisateurs des deux modèles ne chevauchent pas :

   * Create a *Model 1 Segment* and a *Model 2 Segment*.
   * Have the segment rule for *Model 1 Segment* be model 1 trait [!DNL AND NOT] model 2 trait, and vice-versa for *Model 2 Segment*.

1. [Créez deux groupes de test de segment](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) dans [!UICONTROL Audience Lab], un avec *Segment 1 Segment* comme ligne de base, l&#39;autre avec *le segment Modèle 2* comme ligne de base.

   * Conservez les variables de la même façon pour les deux groupes de test : même destinations, éléments créatifs, caractéristiques de conversion.
   * Assurez-vous que les segments de test comportent un nombre d&#39;utilisateurs similaire (par exemple, 1,6 million et 1,8 million d&#39;utilisateurs à droite, 1,6 million et 16 millions).
   * Réservez un segment de contrôle dans chaque groupe de test de segment de test. Ainsi, vous pouvez définir une petite partie de chaque segment et ne pas les cibler explicitement dans le test.

1. Examinez les résultats :

   * The [Audience Lab reporting view](../../features/audience-lab/audience-lab-reporting-view.md) will show the number of conversions each model is driving. Pour les campagnes basées sur les conversions, le segment de test qui génère le plus de conversions indique le modèle qui est le plus performant.
   * Comme vous avez des segments de contrôle, vous pouvez également évaluer la manière dont le modèle a eu lieu par rapport au ciblage standard.  » » Vous testez simplement un modèle par rapport à l&#39;autre, mais testez la question « ce modèle a-t-il été plus performant que les pratiques normales ? ».  » »

## Testing Creatives Across Destinations {#testing-creatives}

<!-- audience-lab-creatives-across-destinations.xml -->

Use [!UICONTROL Audience Lab] to measure the number of conversions a creative is driving across different destinations. Ce cas d&#39;utilisation vous permet également de mesurer les conversions de la création par rapport naturellement à des conversions survenant naturellement.

1. [Créez un groupe de test de segment](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups), en sélectionnant le segment que vous souhaitez tester comme segment de base.
1. Divisez le segment de base en segments de test et contrôlez les segments.
1. Faites correspondre les segments de test aux différentes destinations à tester.
1. Le segment de contrôle peut être conservé et non associé à une destination. Le segment de contrôle ne doit pas être ciblé par le créatif de test pour définir une ligne de base des résultats pour les conversions naturellement survenant.
1. Spécifiez une date de début et une date de fin pour le test.
1. Configurez le segment et le créatif des destinations.
1. The [Audience Lab reporting view](../../features/audience-lab/audience-lab-reporting-view.md) will show the number of conversions the creative is driving across the destinations.
1. Comme vous avez créé un segment de contrôle, vous pouvez également évaluer la manière dont le créatif a été comparé naturellement à des conversions survenant naturellement. Vous testez la question : « Ce créatif générait-il un taux de conversion plus élevé que les pratiques normales ?  » »
