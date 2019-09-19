---
description: Questions fréquentes sur la fonction Audience Lab.
seo-description: Questions fréquentes sur la fonction Audience Lab.
seo-title: FAQ d’Audience Lab
solution: Audience Manager
title: FAQ d’Audience Lab
topic: API DIL
uuid: b1daf99d-af60-4f65-987d-794a6d45d566
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# FAQ d’Audience Lab{#audience-lab-faq}

Questions fréquentes sur la fonction Audience Lab.

<!-- 

audience-lab-faq.xml

 -->

<br> 

**Les segments de test créés dans les groupes de test ont-ils des ID de segment différents ? Comment faire correspondre les ID à différentes destinations ?**

Oui, les segments de test ont des ID de segment différents. Pour les destinations avec [!UICONTROL Auto-fill Destination Mapping] ou les segments envoyés [!DNL Google], [!UICONTROL Audience Lab] gérera les valeurs de mappage comme les destinations habituelles.

<br> 

**La même caractéristique de conversion peut-elle être associée à plusieurs groupes de tests ?**

Oui, c'est permis. Pensez à un cas d’un test utilisant un segment mâle associé à la conversion X et d’un test utilisant un segment femelle associé à la conversion X. Peu importe que les deux tests génèrent des conversions puisqu’ils testent deux audiences différentes.

<br> 

**Supposons qu’un groupe de test utilise un profil authentifié pour le fractionnement du segment de test. Le profil authentifié est lié à 4 UUID[Audience Manager](../reference/ids-in-aam.md). Lorsque le visiteur présente une caractéristique de conversion de l’un des quatre UUID, est-ce que cela[!UICONTROL Audience Lab]compte comme une ou quatre conversions ?**

Dans ce cas, [!UICONTROL Audience Lab] seule une conversion est comptabilisée.

<br> 

**Que se passe-t-il si le visiteur du cas ci-dessus présente d’abord la caractéristique de conversion de l’un des quatre UUID liés à son profil authentifié, puis également la caractéristique de conversion de deux autres UUID liés au profil authentifié ? Ce cas compte-t-il comme une ou trois conversions ?**

Dans ce cas, [!UICONTROL Audience Lab] compte trois conversions, une pour chaque périphérique présentant la caractéristique d’authentification.

<br> 

**Un utilisateur peut-il avoir[!UICONTROL Segment: Read-Only]accès, mais aussi[!UICONTROL Audience Lab]tester l’accès à la création de segments ?**

Voir [Création d’un groupe](../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) de tests de segment pour en savoir plus sur la manière d’utiliser [!UICONTROL Audience Lab] [!UICONTROL RBAC] les privilèges.

**Puis-je utiliser[!UICONTROL Audience Lab]conjointement avec les graphiques des périphériques[!UICONTROL Profile Link Device Graph]et externes ([Adobe Experience Cloud Device Co-op](https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-overview.html), Tapad Device Graph, Liveramp Device Graph) ?**

Pour l’instant, [!UICONTROL Audience Lab] vous ne pouvez diviser les populations de segments que par les périphériques connectés à un périphérique éligible, lors de l’utilisation du [!UICONTROL Profile Link Device Graph]. Nous travaillons sur l'ajout de la prise en charge dans [!UICONTROL Audience Lab] les autres graphiques de périphériques et vous avertirons lorsque nous le ferons.
