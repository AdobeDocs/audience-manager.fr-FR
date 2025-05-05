---
description: Questions et problèmes courants associés aux produits et aux fonctions.
keywords: cookies d’audience manager
seo-description: Common product and function-related questions and issues.
seo-title: Product Features and Functions FAQ
solution: Audience Manager
title: FAQ sur les fonctions et fonctionnalités de produit
uuid: da5f5089-24a8-4455-88a6-eb62d83939d2
feature: Overview
exl-id: b5884d26-0be1-4eaa-99a1-7247942bf6c9
source-git-commit: b0521682c6332d23e55d769e7421680337670fa4
workflow-type: tm+mt
source-wordcount: '574'
ht-degree: 87%

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

 

**Lors d’une exportation d’ID en bloc vers une destination, certains ID de client sont absents. Pourquoi cela se produit-il ?**

Lorsqu’un identifiant d’appareil ([AAM UUID](../reference/ids-in-aam.md)) est lié à plusieurs identifiants CRM ([DPUUIDs](../reference/ids-in-aam.md)), seul le dernier mappage est exporté. C’est pourquoi le nombre d’identifiants d’appareil exportés est peut-être inférieur à ce qui était prévu.

 

**[!DNL Audience Manager] peut-il réduire les besoins en balises ou en pixels tiers et améliorer les temps de chargement de page ?**

Si [!DNL Audience Manager] est intégré à votre partenaire de données de troisième niveau, vous pouvez remplacer leurs pixels et leurs balises avec un appel d’identifiant serveur à serveur à [!DNL Audience Manager]. Dans ce cas, [!DNL Audience Manager] déclencherait un appel d’identifiant unique la première fois que nous voyons un utilisateur et que nous synchronisons ces informations avec votre partenaire tiers. Cela évite d’avoir à passer plusieurs appels de pixel depuis chaque page. La réduction des appels de pixel peut améliorer les temps de chargement de la page.

 

**Je me suis abonné à un flux de données. Où ces données sont-elles stockées ?**

Votre flux de données et toutes les caractéristiques contenues dans les flux apparaissent en tant que sous-dossiers et caractéristiques dans [!DNL Audience Manager]. Rendez-vous dans **[!UICONTROL Audience Data > Traits]** et développez le dossier [!UICONTROL 3rd-Party Data] pour afficher vos caractéristiques ou créer des segments et des modèles avec ces données.

 

**Qu’est-ce que [!UICONTROL Tag Insertion Manager (TIM)] ?**

Audience Manager a utilisé [!UICONTROL Tag Insertion Manager] (TIM) pour créer et gérer [!UICONTROL data collection code (DIL)]. Cette fonction est obsolète et a été remplacée par [!UICONTROL Dynamic Tag Manager (DTM)], puis par [!DNL Adobe Experience Platform Tags]. Pour plus d’informations, voir [Balises Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=fr).

 

**Quelles sont les différences entre les modèles algorithmiques et les recommandations de caractéristiques ? Quand dois-je utiliser chacun d’eux ?**

**Modèles algorithmiques**

Les modèles algorithmiques trouvent non seulement les caractéristiques les plus influentes, mais ils notent aussi les utilisateurs en fonction de ces caractéristiques et attribuent une note individuelle à chaque utilisateur. Vous créez ensuite des caractéristiques algorithmiques pour cibler vos utilisateurs. Grâce aux contrôles de précision et de portée dans le générateur de caractéristiques, vous pouvez préciser les utilisateurs parmi ceux qui ont les caractéristiques les plus influentes que vous souhaitez cibler.

Les modèles algorithmiques vous permettent de sélectionner les utilisateurs à différents niveaux de précision et de tester dans Audience Lab les groupes d’utilisateurs qui se convertissent le mieux. Consultez les cas d’utilisation détaillés dans [Comparaison des modèles dans Audience Lab](../features/audience-lab/audience-lab-use-cases.md#compare-models).

Dans les modèles algorithmiques, le modèle s’exécute tous les 8 jours et actualise les utilisateurs éligibles aux caractéristiques algorithmiques.

**Recommandations de caractéristiques**

Les recommandations de caractéristiques sont un moyen rapide d’obtenir des insights sur d’autres caractéristiques qui sont similaires à celles que vous utilisez dans un segment.

Vous devez utiliser les recommandations de caractéristiques lorsque :

* vous avez besoin d’insights rapides en créant un segment ;
* vous utilisez les segments pour des campagnes courtes ou vous souhaitez supprimer rapidement des audiences qui se convertissent ;
* vous essayez de maximiser votre portée.

 

**Y a-t-il une différence entre les segments Adobe Analytics et Audience Manager ?**

Oui, veuillez lire [Présentation des segments dans Analytics et Audience Manager](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html?lang=fr) pour une description approfondie des différences.
