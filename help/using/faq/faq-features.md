---
description: Questions et problèmes communs liés aux produits et aux fonctions.
keywords: audience manager cookies
seo-description: Questions et problèmes communs liés aux produits et aux fonctions.
seo-title: FAQ sur les fonctionnalités et les fonctionnalités du produit
solution: Audience Manager
title: FAQ sur les fonctionnalités et les fonctionnalités du produit
uuid: da5f5089-24a8-4455-88a6-eb62d83939d2
feature: Overview
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '619'
ht-degree: 1%

---


# FAQ sur les fonctionnalités et les fonctionnalités du produit{#product-features-and-functions-faq}

Questions et problèmes communs liés aux produits et aux fonctions.

 

<!-- 

faq_features_functions.xml

 -->

**Quel est mon ID d’organisation et comment puis-je le trouver ?**

Il *`Organization ID`* s’agit d’un identifiant unique qui identifie votre organisation [!DNL Audience Manager] et le [!DNL Adobe Experience Cloud]. Il se compose d’une chaîne alphanumérique de 24 caractères, sensible à la casse, suivie par [!UICONTROL @AdobeOrg].

Par exemple, voici à quoi ressemble un *`Organization ID`* exemple : `1FD6776A524453CC0A490D44@AdobeOrg`.

L&#39; *`Organization ID`* API [DIL](../dil/dil-overview.md) de l&#39;Audience Manager est utilisée, le service [d&#39;identité de l&#39;](https://docs.adobe.com/content/help/en/id-service/using/home.html)Adobe Experience Platform et d&#39;autres [!DNL Experience Cloud] solutions. Les utilisateurs dotés d’autorisations d’administrateur peuvent trouver le *`Organization ID`* sur le [!DNL Adobe Admin Console]. Voir la FAQ [](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html)Administration - Gestion des utilisateurs (en anglais).

 

**Puis-je créer des caractéristiques ou des destinations en vrac ?**

Oui. Voir Outils [de gestion](../reference/bulk-management-tools/bulk-management-intro.md)en masse.

>[!NOTE]
>
>Les [!UICONTROL Bulk Management Tools] outils ne *sont pas* pris en charge par [!DNL Audience Manager]le logiciel. Elles sont fournies pour commodité et uniquement à titre gracieux. Pour les modifications en masse, nous vous recommandons plutôt d’utiliser les API [](../api/api.md) d’Audience Manager.

 

**Lors d’une exportation d’ID en vrac vers une destination, certains identifiants de client sont absents. Why does that happen?**

Lorsqu’un ID de périphérique (UUID[](../reference/ids-in-aam.md)AAM) est lié à plusieurs ID de gestion de la relation client ([DPUUID](../reference/ids-in-aam.md)), seul le dernier mappage est exporté. C’est pourquoi le nombre d’ID de périphérique exportés est peut-être inférieur à ce qui était prévu.

 

**Peut-[!DNL Audience Manager]on réduire le besoin de balises tierces ou de pixels et améliorer les délais de chargement des pages ?**

Si [!DNL Audience Manager] est intégré à votre partenaire de données tiers, vous pouvez remplacer leurs pixels et balises par un appel d’ID serveur à serveur [!DNL Audience Manager]. Dans ce cas, [!DNL Audience Manager] déclencherait un appel d’identifiant unique lors de la première consultation d’un utilisateur et synchroniserait ces informations avec votre partenaire tiers. Cela évite d’appeler plusieurs pixels à partir de chaque page. La réduction des appels de pixels peut améliorer les temps de chargement des pages.

 

**Je me suis abonné à un flux de données. Où sont stockées ces données ?**

Votre flux de données et toutes les caractéristiques qu’il contient apparaissent sous la forme de sous-dossiers et de caractéristiques dans [!DNL Audience Manager]. Accédez à **[!UICONTROL Audience Data > Traits]** et développez le [!UICONTROL 3rd-Party Data] dossier pour vue vos caractéristiques ou créez des segments et des modèles à l’aide de ces données.

 

**Qu’est-ce que[!UICONTROL Tag Insertion Manager (TIM)]?**

Audience Manager utilisée [!UICONTROL Tag Insertion Manager] (TIM) pour créer et gérer [!UICONTROL data collection code (DIL)]. This feature is obsolete and has been replaced first by [!UICONTROL Dynamic Tag Manager (DTM)], and later by [!DNL Adobe Experience Platform Launch]. For more information, see [Adobe Experience Platform Launch](https://docs.adobelaunch.com/) and [Dynamic Tag Management](https://docs.adobe.com/content/help/en/dtm/using/dtm-home.html).

 

**Quelles sont les différences entre les modèles algorithmiques et les recommandations de caractéristiques ? Quand dois-je les utiliser ?**

**Modèles algorithmiques**

Les modèles algorithmiques trouvent non seulement les caractéristiques les plus influentes, mais notent également les utilisateurs en fonction de ces caractéristiques et attribuent à chaque utilisateur un score individuel. Vous créez ensuite des caractéristiques algorithmiques pour cible vos utilisateurs. Grâce aux contrôles de précision et de portée du créateur de caractéristiques, vous pouvez spécifier les utilisateurs parmi tous ceux qui possèdent les caractéristiques influentes que vous souhaitez cible.

Les modèles algorithmiques vous permettent de sélectionner des utilisateurs à différents niveaux de précision et de tester dans Audience Lab quel groupe d&#39;utilisateurs effectue le meilleur taux de conversion. Consultez le cas d&#39;utilisation détaillé dans [Comparaison de modèles dans Audience Lab](../features/audience-lab/audience-lab-use-cases.md#compare-models).

Dans les modèles algorithmiques, le modèle s’exécute tous les 8 jours et actualise les utilisateurs qualifiés pour les caractéristiques algorithmiques.

**Trait Recommendations**

Les recommandations de caractéristiques constituent un moyen rapide d’obtenir des informations sur d’autres caractéristiques similaires à celles que vous utilisez dans un segment.

Vous devez utiliser les recommandations de caractéristiques lorsque :

* Vous avez besoin d’informations rapides lors de la création d’un segment ;
* Vous utilisez les segments pour les campagnes courtes ou lorsque vous souhaitez supprimer rapidement les audiences qui convertissent ;
* Vous essayez de maximiser la portée.

 

**Existe-t-il une différence entre les segments Adobe et Audience Manager ?**

Oui, veuillez lire [Comprendre les segments en Analytics et en Audience Manager](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html) pour obtenir une description détaillée des différences.
