---
description: Questions et problèmes courants associés aux produits et aux fonctions.
keywords: audience manager cookies
seo-description: Common product and function-related questions and issues.
seo-title: Product Features and Functions FAQ
solution: Audience Manager
title: FAQ sur les fonctions et fonctionnalités de produit
uuid: da5f5089-24a8-4455-88a6-eb62d83939d2
feature: Overview
exl-id: b5884d26-0be1-4eaa-99a1-7247942bf6c9
TQID: https://experienceleague.adobe.com/gsJ4qXlNDpfWmTq0jjmtjfUWI60yRr7uBTxZjsF-pQE
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
  - id: c814092e-2730-45e8-a12d-e084529f52cb
  - id: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
subfeature_v2:
  - id: d3dfac44-e20d-492d-a806-0f4a4a495901
  - id: fa77d762-7e75-47b2-9bb4-e3fcf50d251d
topic_v2:
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: f2fdbb191013b0bcb9bdab0529e3b7f3c872fd54
workflow-type: tm+mt
source-wordcount: 428
ht-degree: 75%

---

# FAQ sur les fonctions et fonctionnalités de produit{#product-features-and-functions-faq}

Questions et problèmes courants associés aux produits et aux fonctions.

 

<!-- 

faq_features_functions.xml

 -->

**Quel est mon identifiant d’organisation et comment puis-je le trouver ?**

L’*`Organization ID`* est un identifiant unique qui identifie votre organisation pour [!DNL Audience Manager] et [!DNL Adobe Experience Cloud]. Il se compose d’une chaîne alphanumérique sensible à la casse de 24 caractères suivis d’un [!UICONTROL @AdobeOrg].

Par exemple, un *`Organization ID`* ressemble à ceci : `1FD6776A524453CC0A490D44@AdobeOrg`.

L’*`Organization ID`* est utilisé par l’API [DIL](../dil/dil-overview.md) d’Audience Manager, [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=fr), et d’autres solutions [!DNL Experience Cloud]. Les utilisateurs possédant des autorisations d’administrateur peuvent trouver l’*`Organization ID`* dans [!DNL Adobe Admin Console]. Voir la [FAQ Administration - Gestion des utilisateurs](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=fr).

 

**Puis-je créer des caractéristiques ou des destinations en bloc ?**

Oui. Voir [Outils de gestion en bloc](../reference/bulk-management-tools/bulk-management-intro.md).

>[!NOTE]
>
>Les outils [!UICONTROL Bulk Management Tools] *ne sont pas* pris en charge par [!DNL Audience Manager]. Ils sont fournis uniquement pour plus de commodité et à des fins de courtoisie. Pour les modifications en bloc, nous vous recommandons plutôt de travailler avec l’[API Audience Manager](../api/api.md).

 

**When performing a bulk ID export to a destination, some of the customer IDs are missing. Why does that happen?**

When a device ID ([AAM UUID](../reference/ids-in-aam.md)) is linked to multiple CRM IDs ([DPUUIDs](../reference/ids-in-aam.md)), only the latest mapping gets exported. This is why you may see a lower than expected number of device IDs being exported.

 

**[!DNL Audience Manager] peut-il réduire les besoins en balises ou en pixels tiers et améliorer les temps de chargement de page ?**

Si [!DNL Audience Manager] est intégré à votre partenaire de données de troisième niveau, vous pouvez remplacer leurs pixels et leurs balises avec un appel d’identifiant serveur à serveur à [!DNL Audience Manager]. Dans ce cas, [!DNL Audience Manager] déclencherait un appel d’identifiant unique la première fois que nous voyons un utilisateur et que nous synchronisons ces informations avec votre partenaire tiers. Cela évite d’avoir à passer plusieurs appels de pixel depuis chaque page. La réduction des appels de pixel peut améliorer les temps de chargement de la page.

 

**Je me suis abonné à un flux de données. Où ces données sont-elles stockées ?**

Votre flux de données et toutes les caractéristiques contenues dans les flux apparaissent en tant que sous-dossiers et caractéristiques dans [!DNL Audience Manager]. Rendez-vous dans **[!UICONTROL Audience Data > Traits]** et développez le dossier [!UICONTROL 3rd-Party Data] pour afficher vos caractéristiques ou créer des segments et des modèles avec ces données.

 

**Qu’est-ce que [!UICONTROL Tag Insertion Manager (TIM)] ?**

Audience Manager a utilisé [!UICONTROL Tag Insertion Manager] (TIM) pour créer et gérer [!UICONTROL data collection code (DIL)]. Cette fonction est obsolète et a été remplacée par [!UICONTROL Dynamic Tag Manager (DTM)], puis par [!DNL Adobe Experience Platform Tags]. For more information, see [Adobe Experience Platform Tags](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=fr).

 

**Y a-t-il une différence entre les segments Adobe Analytics et Audience Manager ?**

Oui, veuillez lire [Présentation des segments dans Analytics et Audience Manager](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html?lang=fr) pour une description approfondie des différences.
