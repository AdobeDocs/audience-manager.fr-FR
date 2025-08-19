---
description: Audience Lab permet plusieurs cas d’utilisation en vous permettant d’utiliser des segments de base pour créer des groupes de test. Vous pouvez diviser des groupes de test en plusieurs segments de test qui s’excluent mutuellement, les mapper à différentes destinations, puis déterminer lequel des segments est le plus efficace pour générer des conversions.
seo-description: Audience Lab enables several use cases by allowing you to use baseline segments for creating test groups. You can divide test groups into several mutually exclusive test segments, map these to different destinations and then determine which of the segments are most effective in driving conversions.
seo-title: Audience Lab Use Cases
solution: Audience Manager
title: Cas D’Utilisation Audience Lab
uuid: 727bec8a-df9a-40cc-b8a7-e1980d146a84
feature: Audience Lab
exl-id: b68f48bd-0d5d-4b72-84f3-a6f3acea6c49
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '585'
ht-degree: 0%

---

# Cas D’Utilisation Audience Lab {#audience-lab-use-cases}

[!UICONTROL Audience Lab] permet plusieurs cas d’utilisation en vous permettant d’utiliser des segments de base pour créer des groupes de test. Vous pouvez diviser des groupes de test en plusieurs segments de test qui s’excluent mutuellement, les mapper à différentes destinations, puis déterminer lequel des segments est le plus efficace pour générer des conversions.

## Comparer les modèles dans Audience Lab {#compare-models}

Vous pouvez utiliser plusieurs types et sources de modèles différents dans [!DNL Audience Manager]. [!UICONTROL Audience Lab] offre un moyen facile de comparer les taux de conversion de vos clients sur l’ensemble de vos modèles actifs.

<!-- audience-lab-compare-models.xml -->

Dans ce cas d’utilisation, vous comparez différents modèles. Vous pouvez utiliser des modèles créés via un entrepôt de données interne et les importer dans [!DNL Audience Manager] en tant que [Caractéristiques intégrées](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) ou vous pouvez utiliser la fonctionnalité [Modèles algorithmiques](../../features/algorithmic-models/understanding-models.md) dans [!DNL Audience Manager].

1. Créez deux modèles, soit dans le [Model Builder](../../features/algorithmic-models/create-model.md), soit via une plateforme externe.
1. Créez des [caractéristiques algorithmiques](../../features/traits/create-algorithmic-traits.md) à partir du modèle algorithmique ou importez vos propres modèles en tant que caractéristiques intégrées.
1. Créez des segments s’excluant mutuellement afin que les utilisateurs des deux modèles ne se chevauchent pas :

   * Créez un *segment Modèle 1* et un *segment Modèle 2*.
   * La règle de segment pour *Segment du modèle 1* doit être modèle 1 [!DNL AND NOT] caractéristique du modèle 2, et vice versa pour *Segment du modèle 2*.

1. [Créez deux groupes de test de segment](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) en [!UICONTROL Audience Lab], l’un avec *Segment Modèle 1* comme ligne de base, l’autre avec *Segment Modèle 2* comme ligne de base.

   * Conservez les mêmes variables pour les deux groupes de test : mêmes destinations, même contenu créatif, caractéristiques de conversion.
   * Assurez-vous que les segments de test ont un nombre d’utilisateurs similaire (par exemple, 1,6 million et 1,8 million sont corrects, 1,6 million et 16 millions ne le sont pas).
   * Réservez un segment témoin dans chaque groupe de test de segment de test. Ainsi, vous pouvez réserver une petite partie de chaque segment et ne pas le cibler explicitement dans le test.

1. Examinez les résultats :

   * La [vue de rapport Audience Lab](../../features/audience-lab/audience-lab-reporting-view.md) affichera le nombre de conversions pilotées par chaque modèle. Pour les campagnes basées sur la conversion, le segment de test qui génère le plus de conversions signifie le modèle qui a les meilleures performances.
   * Grâce aux segments de contrôle, vous pouvez également évaluer l’efficacité du modèle par rapport au « ciblage standard ». Vous testez non seulement un modèle par rapport à l’autre, mais vous testez également la question suivante : « Ce modèle a-t-il donné de meilleurs résultats que les pratiques normales ? »

## Test des contenus publicitaires sur plusieurs destinations {#testing-creatives}

<!-- audience-lab-creatives-across-destinations.xml -->

Utilisez [!UICONTROL Audience Lab] pour mesurer le nombre de conversions générées par un contenu créatif sur différentes destinations. Ce cas d’utilisation vous permet également de mesurer les conversions du contenu créatif par rapport aux conversions survenant naturellement.

1. [Créez un groupe de test de segment](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups), en sélectionnant le segment en fonction duquel vous souhaitez tester les créations comme segment de base.
1. Divisez le segment de base en segments de test et en segments de contrôle.
1. Mappez les segments de test aux différentes destinations que vous souhaitez tester.
1. Le segment de contrôle peut être conservé et non mappé à une destination. Le segment de contrôle ne doit pas être ciblé par le contenu créatif de test afin de définir une ligne de base de résultats pour les conversions naturelles.
1. Spécifiez une date de début et une date de fin pour le test.
1. Configurez le segment et le contenu créatif dans les destinations.
1. La [vue de compte rendu des performances d’Audience Lab](../../features/audience-lab/audience-lab-reporting-view.md) affichera le nombre de conversions générées par le contenu créatif sur les destinations.
1. Étant donné que vous avez créé un segment de contrôle, vous pouvez également évaluer la performance du contenu créatif par rapport aux conversions naturelles. Vous testez la question suivante : « Cette création a-t-elle généré un taux de conversion supérieur aux pratiques normales ? »
