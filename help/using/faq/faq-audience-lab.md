---
description: Questions fréquentes sur la fonctionnalité Audience Lab.
seo-description: Questions fréquentes sur la fonctionnalité Audience Lab.
seo-title: FAQ sur Audience Lab
solution: Audience Manager
title: FAQ sur Audience Lab
topic: DIL API
uuid: b1daf99d-af60-4f65-987d-794a6d45d566
feature: Audience Lab
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# FAQ sur Audience Lab {#audience-lab-faq}

Questions fréquentes sur la fonctionnalité Audience Lab.

<!-- 

audience-lab-faq.xml

 -->

<br> 

**Les segments de test créés dans les groupes de test ont-ils des identifiants de segment différents ? Comment mapper les identifiants à différentes destinations ?**

Oui, les segments de test ont des identifiants de segment différents. Pour les destinations avec [!UICONTROL Auto-fill Destination Mapping] ou les segments envoyés à [!DNL Google], la gestion des valeurs de mappage par [!UICONTROL Audience Lab] est identique à celle qu’effectuent les destinations en temps normal.

<br> 

**Une même caractéristique de conversion peut-elle être associée à plusieurs groupes de test ?**

Oui, cela est possible. Supposons qu’un test utilisant un segment masculin soit associé à la conversion X, et qu’un test utilisant un segment féminin soit associé à la conversion X. Le fait que les deux tests génèrent des conversions importe peu, puisqu’ils testent deux audiences différentes.

<br> 

**Supposons qu’un groupe de test utilise un profil authentifié pour fractionner le segment de test. Le profil authentifié est lié à 4 [UUID Audience Manager](../reference/ids-in-aam.md). Lorsque le visiteur présente une caractéristique de conversion provenant de l’un des quatre UUID, [!UICONTROL Audience Lab] comptabilise-t-il cette caractéristique en tant qu’une ou quatre conversions ?**

Dans ce cas, [!UICONTROL Audience Lab] comptabilise une seule conversion.

<br> 

**Que se passe-t-il si le visiteur du cas ci-dessus présente d’abord une caractéristique de conversion provenant de l’un des quatre UUID liés à son profil authentifié, puis présente également une caractéristique de conversion provenant de deux autres UUID liés au profil authentifié ? Ce cas est-il comptabilisé en tant qu’une ou trois conversions ?**

Dans ce cas, [!UICONTROL Audience Lab] comptabilise trois conversions : une pour chaque appareil présentant la caractéristique d’authentification.

<br> 

**Un utilisateur peut-il avoir accès à [!UICONTROL Segment: Read-Only], mais aussi accès à la création de segments d’[!UICONTROL Audience Lab] ?**

Reportez-vous à la [Création d’un groupe de test de segments](../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) pour en savoir plus sur la manière d’utiliser [!UICONTROL Audience Lab] avec des privilèges [!UICONTROL RBAC].

**Puis-je utiliser [!UICONTROL Audience Lab] avec [!UICONTROL Profile Link Device Graph] et les représentations graphiques externes des appareils ([Adobe Experience Cloud Device Co-op](https://docs.adobe.com/content/help/fr-FR/device-co-op/using/home.html), Tapad Device Graph, Liveramp Device Graph) ?**

Pour l’instant, [!UICONTROL Audience Lab] peut uniquement fractionner les populations de segments selon les appareils connectés à un appareil qualifié, en utilisant le [!UICONTROL Profile Link Device Graph]. L’ajout de la prise en charge d’autres représentations graphiques des appareils par [!UICONTROL Audience Lab] est en cours ; vous serez informé dès qu’elle sera disponible.
