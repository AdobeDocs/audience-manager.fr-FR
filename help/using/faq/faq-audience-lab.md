---
description: Questions fréquentes sur la fonction du laboratoire d'Audience.
seo-description: Questions fréquentes sur la fonction du laboratoire d'Audience.
seo-title: FAQ sur Audience Lab
solution: Audience Manager
title: FAQ sur Audience Lab
topic: DIL API
uuid: b1daf99d-af60-4f65-987d-794a6d45d566
feature: Audience Lab
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 0%

---


# FAQ sur Audience Lab{#audience-lab-faq}

Questions fréquentes sur la fonction du laboratoire d&#39;Audience.

<!-- 

audience-lab-faq.xml

 -->

<br> 

**Les segments de test créés dans les groupes de test ont-ils des ID de segment différents ? Comment puis-je mapper les identifiants à différentes destinations ?**

Oui, les segments de test ont des ID de segment différents. Pour les destinations avec [!UICONTROL Auto-fill Destination Mapping] ou segments envoyés à [!DNL Google], [!UICONTROL Audience Lab] gérera les valeurs de mappage comme les destinations normalement.

<br> 

**La même caractéristique de conversion peut-elle être associée à plusieurs groupes de tests ?**

Oui, c&#39;est permis. Imaginez un cas d&#39;un test utilisant un segment masculin associé à la conversion X et un test utilisant un segment féminin associé à la conversion X. Peu importe que les deux tests génèrent des conversions puisqu&#39;ils testent deux audiences différentes.

<br> 

**Supposons qu’un groupe de test utilise un profil authentifié pour le fractionnement du segment de test. Le profil authentifié est lié à 4 UUID[d’Audience Manager](../reference/ids-in-aam.md). Lorsque le visiteur présente une caractéristique de conversion de l’un des quatre UUID, est-ce qu’il[!UICONTROL Audience Lab]compte une ou quatre conversions ?**

Dans ce cas, [!UICONTROL Audience Lab] une seule conversion est comptabilisée.

<br> 

**Que se passe-t-il si le visiteur de l&#39;affaire ci-dessus présente d&#39;abord la caractéristique de conversion de l&#39;un des quatre UUID liés à son profil authentifié, puis également la caractéristique de conversion de deux autres UUID liés au profil authentifié ? Ce cas compte-t-il comme une ou trois conversions ?**

Dans ce cas, [!UICONTROL Audience Lab] compte trois conversions, une pour chaque périphérique présentant la caractéristique d’authentification.

<br> 

**Un utilisateur peut-il avoir[!UICONTROL Segment: Read-Only]accès, mais aussi[!UICONTROL Audience Lab]tester l’accès à la création de segments ?**

Voir [Création d’un groupe](../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) de tests de segments pour en savoir plus sur la manière d’utiliser [!UICONTROL Audience Lab] [!UICONTROL RBAC] les privilèges.

**Puis-je utiliser[!UICONTROL Audience Lab]conjointement avec les graphiques des périphériques[!UICONTROL Profile Link Device Graph]et externes ([Adobe Experience Cloud Device Co-op](https://docs.adobe.com/content/help/en/device-co-op/using/home.html), Tapad Device Graph, Liveramp Device Graph) ?**

Pour l’instant, [!UICONTROL Audience Lab] vous ne pouvez diviser les populations de segments que par les périphériques connectés à un périphérique éligible, lors de l’utilisation de la [!UICONTROL Profile Link Device Graph]. Nous travaillons sur l&#39;ajout de la prise en charge des autres graphiques [!UICONTROL Audience Lab] de périphériques et vous avertirons quand nous le ferons.
