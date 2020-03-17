---
description: Questions et problèmes courants liés aux produits et aux fonctions.
keywords: audience manager cookies
seo-description: Questions et problèmes courants liés aux produits et aux fonctions.
seo-title: FAQ sur les fonctionnalités et les fonctionnalités du produit
solution: Audience Manager
title: FAQ sur les fonctionnalités et les fonctionnalités du produit
uuid: da5f5089-24a8-4455-88a6-eb62d83939d2
translation-type: tm+mt
source-git-commit: 7f9c7b74150682e8e8b839148dcae72f53d3b4ae

---


# FAQ sur les fonctionnalités et les fonctionnalités du produit{#product-features-and-functions-faq}

Questions et problèmes courants liés aux produits et aux fonctions.

<br> 

<!-- 

faq_features_functions.xml

 -->

**Quel est mon ID d’organisation et comment le trouver ?**

Il *`Organization ID`* s’agit d’un identifiant unique qui identifie votre entreprise [!DNL Audience Manager] et le [!DNL Adobe Experience Cloud]. Il se compose d’une chaîne alphanumérique de 24 caractères, sensible à la casse, suivie par [!UICONTROL @AdobeOrg].

Par exemple, une *`Organization ID`* figure se présente comme suit : `1FD6776A524453CC0A490D44@AdobeOrg`.

Le *`Organization ID`* logiciel est utilisé par  API [DIL](../dil/dil-overview.md) de  Manager, le service [d’identité](https://marketing.adobe.com/resources/help/en_US/mcvid/)Adobe Experience Platform et d’autres [!DNL Experience Cloud] solutions. Les utilisateurs disposant d’autorisations d’administrateur peuvent trouver le *`Organization ID`* sur le [!DNL Adobe Admin Console]. Voir le FAQ [Administration - Gestion des utilisateurs](https://marketing.adobe.com/resources/help/en_US/mcloud/admin_getting_started.html).

<br> 

**Puis-je créer des caractéristiques ou des destinations en bloc ?**

Oui. Voir Outils [de gestion](../reference/bulk-management-tools/bulk-management-intro.md)en masse.

>[!NOTE]
>
>Les [!UICONTROL Bulk Management Tools] outils ne *sont pas* pris en charge par [!DNL Audience Manager]. Elles sont fournies à titre de commodité et uniquement à titre gracieux. Pour les modifications en masse, nous vous recommandons de travailler avec les API [Gestionnaire de](../api/api.md) à la place.

<br> 

**Peut-[!DNL Audience Manager]il réduire le besoin de balises tierces ou de pixels et améliorer les temps de chargement des pages ?**

Si [!DNL Audience Manager] est intégré à votre partenaire de données tiers, vous pouvez remplacer leurs pixels et balises par un appel d’ID serveur à serveur [!DNL Audience Manager]. Dans ce cas, [!DNL Audience Manager] déclencherait un appel d’ID unique lors de la première consultation d’un utilisateur et synchroniserait ces informations avec votre partenaire tiers. Cela évite d’effectuer des appels de plusieurs pixels à partir de chaque page. La réduction des appels de pixels peut améliorer les temps de chargement des pages.

<br> 

**Je me suis abonné à un flux de données. Où sont stockées ces données ?**

Votre flux de données et toutes les caractéristiques contenues dans le flux apparaissent sous la forme de sous-dossiers et de caractéristiques dans [!DNL Audience Manager]. Accédez au **[!UICONTROL Audience Data > Traits]** dossier [!UICONTROL 3rd-Party Data] et développez-le pour vos caractéristiques ou créez des segments et des modèles à l’aide de ces données.

<br> 

**Qu’est-ce que[!UICONTROL Tag Insertion Manager (TIM)]?**

 Gestionnaire de  de a utilisé [!UICONTROL Tag Insertion Manager] (TIM) pour créer et gérer [!UICONTROL data collection code (DIL)]. This feature is obsolete and has been replaced first by [!UICONTROL Dynamic Tag Manager (DTM)], and later by [!DNL Adobe Experience Platform Launch]. For more information, see [Adobe Experience Platform Launch](https://docs.adobelaunch.com/) and [Dynamic Tag Management](https://marketing.adobe.com/resources/help/en_US/dtm/).

<br> 

**Quelles sont les différences entre les modèles algorithmiques et les recommandations de caractéristiques ? Quand devrais-je les utiliser ?**

**Modèles algorithmiques**

Les modèles algorithmiques trouvent non seulement les caractéristiques les plus influentes, mais notent également les utilisateurs en fonction de ces caractéristiques et attribuent à chaque utilisateur un score individuel. Vous créez ensuite des caractéristiques algorithmiques pour vos utilisateurs. Grâce aux commandes de précision et de portée du créateur de caractéristiques, vous pouvez spécifier les utilisateurs parmi tous ceux qui possèdent les caractéristiques influentes que vous souhaitez .

Les modèles algorithmiques vous permettent de sélectionner des utilisateurs à différents niveaux de précision et de tester dans   Lab le groupe d&#39;utilisateurs qui se convertit le mieux. Voir le cas d&#39;utilisation détaillé dans [Comparaison de modèles dans   Lab](../features/audience-lab/audience-lab-use-cases.md#compare-models).

Dans les modèles algorithmiques, le modèle s’exécute tous les 8 jours et actualise les utilisateurs qualifiés pour les caractéristiques algorithmiques.

**Trait Recommendations**

Les recommandations de caractéristiques constituent un moyen rapide d’obtenir des informations sur d’autres caractéristiques similaires à celles que vous utilisez dans un segment.

Utilisez les recommandations de caractéristiques lorsque :

* Vous avez besoin d’informations rapides lors de la création d’un segment ;
* Vous utilisez les segments pour des campagnes courtes ou lorsque vous souhaitez supprimer rapidement   qui convertit ;
* Vous essayez de maximiser la portée.

<br> 

**Existe-t-il une différence entre les segments Adobe Analytics et   Manager ?**

Oui, veuillez lire [Présentation des segments dans Analytics et  Gestionnaire de](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/aam-analytics-segments.html) de pour obtenir une description détaillée des différences.
