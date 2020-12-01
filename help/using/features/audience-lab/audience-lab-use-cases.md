---
description: Le laboratoire d'Audiences permet d'utiliser plusieurs cas d'utilisation en vous permettant d'utiliser des segments de base pour créer des groupes de tests. Vous pouvez diviser les groupes de tests en plusieurs segments de test mutuellement exclusifs, les mapper à différentes destinations, puis déterminer quels segments sont les plus efficaces pour générer des conversions.
seo-description: Le laboratoire d'Audiences permet d'utiliser plusieurs cas d'utilisation en vous permettant d'utiliser des segments de base pour créer des groupes de tests. Vous pouvez diviser les groupes de tests en plusieurs segments de test mutuellement exclusifs, les mapper à différentes destinations, puis déterminer quels segments sont les plus efficaces pour générer des conversions.
seo-title: Cas d’utilisation d’Audience Lab
solution: Audience Manager
title: Cas d’utilisation d’Audience Lab
topic: DIL API
uuid: 727bec8a-df9a-40cc-b8a7-e1980d146a84
feature: Audience Lab
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '623'
ht-degree: 1%

---


# Cas d’utilisation d’Audience Lab {#audience-lab-use-cases}

[!UICONTROL Audience Lab] permet d’utiliser plusieurs cas d’utilisation en vous permettant d’utiliser des segments de base pour créer des groupes de tests. Vous pouvez diviser les groupes de tests en plusieurs segments de test mutuellement exclusifs, les mapper à différentes destinations, puis déterminer quels segments sont les plus efficaces pour générer des conversions.

## Comparaison de modèles dans le laboratoire d&#39;Audience {#compare-models}

Vous pouvez utiliser plusieurs types et sources de modèles différents dans [!DNL Audience Manager]. [!UICONTROL Audience Lab] Les offres constituent un moyen facile de comparer les taux de conversion de vos clients, entre vos principaux modèles.

<!-- audience-lab-compare-models.xml -->

Dans ce cas d’utilisation, vous comparez différents modèles. Vous pouvez utiliser des modèles créés via un entrepôt de données interne et les importer dans [!DNL Audience Manager] en tant que [Caractéristiques intégrées](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) ou utiliser la fonction [Modèles algorithmiques](../../features/algorithmic-models/understanding-models.md) de [!DNL Audience Manager].

1. Créez deux modèles, soit dans le [Créateur de modèles](../../features/algorithmic-models/create-model.md), soit via une plateforme externe.
1. Créez [des caractéristiques algorithmiques](../../features/traits/create-algorithmic-traits.md) à partir du modèle algorithmique ou importez vos propres modèles sous forme de caractéristiques intégrées.
1. Créez des segments mutuellement exclusifs afin que les utilisateurs des deux modèles ne se chevauchent pas :

   * Créez un segment *Modèle 1* et un segment *Modèle 2*.
   * Demandez à la règle de segment *Segment du modèle 1* d&#39;être une caractéristique du modèle 1 [!DNL AND NOT] caractéristique du modèle 2 et vice versa pour *Segment du modèle 2*.

1. [Créez deux ](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) groupes de tests de segment  [!UICONTROL Audience Lab]: l&#39;un avec  *Segmentation du* modèle 1 comme ligne de base, l&#39;autre avec  ** Segmentation du modèle 2 comme ligne de base.

   * Conservez les variables identiques pour les deux groupes de tests : mêmes destinations, caractéristiques créatives, caractéristiques de conversion.
   * Assurez-vous que les segments de test ont un nombre similaire d&#39;utilisateurs (par exemple, 1,6 million et 1,8 million sont corrects, 1,6 million et 16 millions ne le sont pas).
   * Réservez un segment de contrôle dans chaque groupe de tests de segment de test. Ainsi, vous pouvez réserver une petite partie de chaque segment et ne pas les cible explicitement dans le test.

1. Examinez les résultats :

   * La vue de rapports [Audience Lab](../../features/audience-lab/audience-lab-reporting-view.md) montre le nombre de conversions que chaque modèle génère. Pour les campagnes basées sur les conversions, le segment de test qui génère le plus de conversions signifie le modèle le plus performant.
   * Comme vous disposez de segments de contrôle, vous pouvez également évaluer comment le modèle s’est comporté par rapport au &quot;ciblage standard&quot;. Vous testez non seulement un modèle par rapport à un autre, mais vous vous demandez si ce modèle a fait mieux que les pratiques normales.

## Test de créatifs entre les destinations {#testing-creatives}

<!-- audience-lab-creatives-across-destinations.xml -->

Utilisez [!UICONTROL Audience Lab] pour mesurer le nombre de conversions qu’un créatif effectue sur différentes destinations. Ce cas d’utilisation vous permet également de mesurer les conversions du créatif par rapport aux conversions naturelles.

1. [Créez un groupe](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) de test de segment, en sélectionnant le segment par rapport auquel vous souhaitez tester le créatif comme segment de base.
1. Fractionner le segment de base en segments de test et segments de contrôle.
1. Faites correspondre les segments de test aux différentes destinations que vous souhaitez tester.
1. Le segment de contrôle peut être masqué et non mappé à une destination. Le segment de contrôle ne doit pas être ciblé par l’élément créatif du test pour définir une base de résultats pour les conversions naturelles.
1. Indiquez une date de début et une date de fin pour le test.
1. Configurez le segment et la création dans les destinations.
1. La [vue de rapports du laboratoire d&#39;Audiences](../../features/audience-lab/audience-lab-reporting-view.md) montre le nombre de conversions effectuées par l&#39;élément créatif à travers les destinations.
1. Comme vous avez créé un segment de contrôle, vous pouvez également évaluer comment le créatif s’est comporté par rapport aux conversions naturelles. Vous testez la question : &quot;Ce créatif a-t-il généré un taux de conversion plus élevé que les pratiques habituelles ?&quot;
