---
description: Audience Lab permet plusieurs cas d’utilisation en vous permettant d’utiliser des segments de base pour créer des groupes de test. Vous pouvez diviser les groupes de test en plusieurs segments de test mutuellement exclusifs, les mapper à différentes destinations, puis déterminer les segments les plus efficaces pour générer des conversions.
seo-description: Audience Lab enables several use cases by allowing you to use baseline segments for creating test groups. You can divide test groups into several mutually exclusive test segments, map these to different destinations and then determine which of the segments are most effective in driving conversions.
seo-title: Audience Lab Use Cases
solution: Audience Manager
title: Cas d’utilisation d’Audience Lab
uuid: 727bec8a-df9a-40cc-b8a7-e1980d146a84
feature: Audience Lab
exl-id: b68f48bd-0d5d-4b72-84f3-a6f3acea6c49
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '585'
ht-degree: 0%

---

# Cas d’utilisation d’Audience Lab {#audience-lab-use-cases}

[!UICONTROL Audience Lab] permet plusieurs cas d’utilisation en vous permettant d’utiliser des segments de base pour créer des groupes de test. Vous pouvez diviser les groupes de test en plusieurs segments de test mutuellement exclusifs, les mapper à différentes destinations, puis déterminer les segments les plus efficaces pour générer des conversions.

## Comparaison de modèles dans Audience Lab {#compare-models}

Vous pouvez utiliser plusieurs types et sources de modèles différents dans [!DNL Audience Manager]. [!UICONTROL Audience Lab] offre un moyen facile de comparer les taux de conversion de vos clients, sur l’ensemble de vos modèles actifs.

<!-- audience-lab-compare-models.xml -->

Dans ce cas pratique, vous comparez différents modèles. Vous pouvez utiliser des modèles créés par le biais d’un entrepôt de données interne et les importer dans [!DNL Audience Manager] en tant que [ caractéristiques intégrées](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) ou utiliser la fonction [Modèles algorithmiques](../../features/algorithmic-models/understanding-models.md) dans [!DNL Audience Manager].

1. Créez deux modèles, soit dans le [créateur de modèles](../../features/algorithmic-models/create-model.md), soit via une plateforme externe.
1. Créez des [caractéristiques algorithmiques](../../features/traits/create-algorithmic-traits.md) à partir du modèle algorithmique ou importez vos propres modèles en tant que caractéristiques intégrées.
1. Créez des segments mutuellement exclusifs afin que les utilisateurs des deux modèles ne se chevauchent pas :

   * Créez un *segment de modèle 1* et un *segment de modèle 2*.
   * Faites en sorte que la règle de segment de *segment du modèle 1* soit la caractéristique 1 du modèle [!DNL AND NOT] modèle 2, et vice versa pour le *segment du modèle 2*.

1. [ Créez deux groupes de test de segment ](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) dans [!UICONTROL Audience Lab], l’un avec *Segment de modèle 1* comme ligne de base, l’autre avec *Segment de modèle 2* comme ligne de base.

   * Conservez les mêmes variables pour les deux groupes de test : les mêmes destinations, les mêmes caractéristiques créatives et de conversion.
   * Assurez-vous que les segments de test ont un nombre d’utilisateurs similaire (par exemple, 1,6 million et 1,8 million sont corrects, 1,6 million et 16 millions ne le sont pas).
   * Réservez un segment de contrôle dans chaque groupe de test de segment de test. Ainsi, vous pouvez mettre de côté une petite partie de chaque segment et ne pas les cibler explicitement dans le test.

1. Examinez les résultats :

   * La [vue de création de rapports d’Audience Lab](../../features/audience-lab/audience-lab-reporting-view.md) indique le nombre de conversions générées par chaque modèle. Pour les campagnes basées sur les conversions, le segment de test qui génère le plus de conversions correspond au modèle le plus performant.
   * Comme vous disposez de segments de contrôle, vous pouvez également évaluer la manière dont le modèle s’est comporté par rapport au &quot;ciblage standard&quot;. Vous testez non seulement un modèle par rapport à un autre, mais vous vous demandez si ce modèle a fait mieux que les pratiques normales.

## Test de créatifs sur plusieurs destinations {#testing-creatives}

<!-- audience-lab-creatives-across-destinations.xml -->

Utilisez [!UICONTROL Audience Lab] pour mesurer le nombre de conversions qu’un créatif génère entre différentes destinations. Ce cas pratique vous permet également de mesurer les conversions du créatif par rapport aux conversions naturelles.

1. [Créez un groupe de test de segment](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups), en sélectionnant le segment sur lequel vous souhaitez tester le créatif comme segment de base.
1. Fractionner le segment de ligne de base en segments de test et en segments de contrôle.
1. Mappez les segments de test aux différentes destinations que vous souhaitez tester.
1. Le segment de contrôle peut être masqué et n’être mappé à aucune destination. Le segment de contrôle ne doit pas être ciblé par l’élément créatif du test pour définir une ligne de base de résultats pour les conversions naturelles.
1. Spécifiez une date de début et une date de fin pour le test.
1. Configurez le segment et le contenu créatif dans les destinations.
1. La [vue de création de rapports d’Audience Lab](../../features/audience-lab/audience-lab-reporting-view.md) indiquera le nombre de conversions générées par le créatif à travers les destinations.
1. Parce que vous avez créé un segment de contrôle, vous pouvez également évaluer comment le créatif s’est comporté par rapport aux conversions naturelles. Vous testez la question : &quot;Ce créatif a-t-il généré un taux de conversion plus élevé que les pratiques normales ?&quot;
