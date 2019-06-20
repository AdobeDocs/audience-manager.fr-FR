---
description: Questions fréquentes sur la fonction Audience Lab.
seo-description: Questions fréquentes sur la fonction Audience Lab.
seo-title: FAQ sur Audience Lab
solution: Audience Manager
title: FAQ sur Audience Lab
topic: API DIL
uuid: b 1 daf 99 d-af 60-4 f 65-987 d -794 a 6 d 45 d 566
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Audience Lab FAQ{#audience-lab-faq}

Questions fréquentes sur la fonction Audience Lab.

<!-- 

audience-lab-faq.xml

 -->

<br> 

**Les segments de test créés dans les groupes de test ont-ils des ID de segment différents ? How do I map the IDs to different destinations?**

Oui, les segments de test comportent différents ID de segment. For destinations with [!UICONTROL Auto-fill Destination Mapping] or segments sent to [!DNL Google], [!UICONTROL Audience Lab] will handle the mapping values just like the destinations normally would.

<br> 

**La même caractéristique de conversion peut-elle être associée à plusieurs groupes de test ?**

Oui, cela est autorisé. Considérez un cas d&#39;un test à l&#39;aide d&#39;un segment masculin associé à la conversion X et un test à l&#39;aide d&#39;un segment féminin associé à la conversion X. Cela n&#39;a pas d&#39;importance que les deux tests génèrent des conversions puisqu&#39;ils testent deux audiences différentes.

<br> 

**Imaginons qu&#39;un groupe de test utilise un profil authentifié pour le fractionnement du segment de test. The authenticated profile is linked to 4[Audience Manager UUIDs](../reference/ids-in-aam.md). When the visitor exhibits a conversion trait from one of the four UUIDs, does[!UICONTROL Audience Lab]count this as one or four conversions?**

In this case, [!UICONTROL Audience Lab] only counts one conversion.

<br> 

**Que se passe-t-il si le visiteur du dossier ci-dessus présente la caractéristique de conversion de l&#39;un des quatre UUID liés à son profil authentifié, puis qu&#39;il affiche également la caractéristique de conversion de deux autres UUID liés au profil authentifié ? Does this case count as one or three conversions?**

In this case, [!UICONTROL Audience Lab] counts three conversions, one for each device that has exhibited the authentication trait.

<br> 

**Un utilisateur peut[!UICONTROL Segment: Read-Only]-il avoir accès, mais[!UICONTROL Audience Lab]aussi tester l&#39;accès à la création de segments ?**

See [Create Segment Test Group](../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) for information on how to use [!UICONTROL Audience Lab] with [!UICONTROL RBAC] privileges.

**Puis-je utiliser[!UICONTROL Audience Lab]conjointement les[!UICONTROL Profile Link Device Graph]graphiques des périphériques externes ([Adobe Experience Cloud Device Co-op](https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-overview.html), Filad Device Graph, Liveramp Device Graph) ?**

For now, [!UICONTROL Audience Lab] can only split out segment populations by the devices connected to a qualifying device, when using the [!UICONTROL Profile Link Device Graph]. We are working on adding support in [!UICONTROL Audience Lab] for the other device graphs and will let you know when we do so.
