---
description: Questions et problèmes liés aux produits et aux fonctions courants.
keywords: cookies Audience Manager
seo-description: Questions et problèmes liés aux produits et aux fonctions courants.
seo-title: FAQ sur les fonctions et fonctions du produit
solution: Audience Manager
title: FAQ sur les fonctions et fonctions du produit
uuid: da 5 f 5089-24 a 8-4455-88 a 6-eb 62 d 83939 d 2
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Product Features and Functions FAQ{#product-features-and-functions-faq}

Questions et problèmes liés aux produits et aux fonctions courants.

<br> 

<!-- 

faq_features_functions.xml

 -->

**Quel est mon ID d&#39;organisation et comment le trouver ?**

The *`Organization ID`* is a unique ID that identifies your organization to [!DNL Audience Manager] and the [!DNL Adobe Experience Cloud]. It consists of a case-sensitive, 24-character alphanumeric string followed by [!UICONTROL @AdobeOrg].

For example, an *`Organization ID`* looks like this: `1FD6776A524453CC0A490D44@AdobeOrg`.

The *`Organization ID`* is used by Audience Manager&#39;s [DIL](../dil/dil-overview.md) API, the [Experience Cloud ID service](https://marketing.adobe.com/resources/help/en_US/mcvid/), and other [!DNL Experience Cloud] solutions. Users with Administrator permissions can find the *`Organization ID`* on the [!DNL Adobe Admin Console]. See the [Administration - User Management FAQ](https://marketing.adobe.com/resources/help/en_US/mcloud/admin_getting_started.html).

<br> 

**Puis-je créer des caractéristiques ou des destinations en bloc ?**

Oui. See [Bulk Management Tools](../reference/bulk-management-tools/bulk-management-intro.md).

>[!NOTE]
>
>The [!UICONTROL Bulk Management Tools] tools *are not* supported by [!DNL Audience Manager]. Ils sont fournis à titre de commodité uniquement. For bulk changes, we recommend you work with the [Audience Manager APIs](../api/api.md) instead.

<br> 

**Peut[!DNL Audience Manager]-on réduire le besoin de balises ou de pixels tiers et améliorer les temps de chargement des pages ?**

If [!DNL Audience Manager] is integrated with your third-party data partner, you can replace their pixels and tags with a server-to-server ID call to [!DNL Audience Manager]. In this case, [!DNL Audience Manager] would fire a single ID call the first time we see a user and synchronize that information with your third-party partner. Cela évite d&#39;appeler plusieurs pixels à partir de chaque page. La réduction des appels de pixels peut améliorer les temps de chargement des pages.

<br> 

**Je me suis abonné à un flux de données. Where is that data stored?**

Your data feed and all the traits contained in the feed appear as subfolders and traits in [!DNL Audience Manager]. Go to **[!UICONTROL Audience Data > Traits]** and expand the [!UICONTROL 3rd-Party Data] folder to view your traits or create segments and models with this data.

<br> 

**Qu’est-ce que[!UICONTROL Tag Insertion Manager (TIM)]?**

Audience Manager used [!UICONTROL Tag Insertion Manager] (TIM) to create and manage [!UICONTROL data collection code (DIL)]. This feature is obsolete and has been replaced first by [!UICONTROL Dynamic Tag Manager (DTM)], and later by [!DNL Adobe Launch]. For more information, see [Adobe Launch](https://docs.adobelaunch.com/) and [Dynamic Tag Management](https://marketing.adobe.com/resources/help/en_US/dtm/).

<br> 

**Quelles sont les différences entre les modèles algorithmiques et les recommandations de caractéristiques ? When should I use each of them?**

**Modèles algorithmiques**

Les modèles algorithmiques détectent non seulement les caractéristiques les plus influentes, mais aussi les utilisateurs en fonction de ces caractéristiques et affecte un score individuel à chaque utilisateur. Vous créez ensuite des caractéristiques algorithmiques pour cibler vos utilisateurs. Avec les commandes de précision et de portée dans le créateur de caractéristiques, vous pouvez spécifier les utilisateurs parmi tous ceux qui possèdent les caractéristiques influentes que vous souhaitez cibler.

Les modèles algorithmiques vous permettent de sélectionner des utilisateurs à différents niveaux et à différents tests dans Audience Lab, quel groupe d&#39;utilisateurs effectue le plus de conversions. See the detailed use case in [Compare Models in Audience Lab](../features/audience-lab/audience-lab-use-cases.md#compare-models).

Dans les modèles algorithmiques, le modèle s&#39;exécute tous les 8 jours et actualise les utilisateurs qualifiés pour les caractéristiques algorithmiques.

**Trait Recommendations**

Recommandations est un moyen rapide d&#39;obtenir des informations sur d&#39;autres caractéristiques similaires à celles que vous utilisez dans un segment.

Utilisez les recommandations de caractéristique lorsque :

* Vous avez besoin d&#39;informations rapides lors de la création d&#39;un segment ;
* Vous utilisez les segments pour des campagnes courtes ou lorsque vous souhaitez rapidement supprimer le public qui effectue des conversions ;
* Vous tentez d&#39;optimiser la portée.

<br> 

**Existe-t-il une différence entre les segments Adobe Analytics et Audience Manager ?**

Yes, please read [Understanding Segments in Analytics and Audience Manager](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/aam-analytics-segments.html) for an in-depth description of the differences.
