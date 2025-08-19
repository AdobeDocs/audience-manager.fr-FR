---
description: Cette procédure nécessite une liste de remarketing AdWords, un code pixel et une destination d'URL Audience Manager. Il s’agit également d’une intégration de liste de remarketing pour les annonces de recherche (RLSA). S’applique uniquement au référencement payant.
seo-description: This procedure requires an AdWords remarketing list, pixel code, and an Audience Manager URL destination. It is also known as a remarketing list for search ads (RLSA) integration. Applies to paid search only.
seo-title: Send Segments to a Google AdWords Remarketing List
solution: Audience Manager
title: Envoyer des segments à une liste de remarketing AdWords Google
uuid: 5ad821c6-48b4-42c0-b912-1563331e93a2
feature: Third-party Integration
exl-id: 76676eae-de4f-4fee-8774-ee215525306a
source-git-commit: b8d65ef8c27100d174a997eb24a75f37b4e75d40
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 0%

---

# Envoyer des segments à une liste de remarketing Google Ads {#send-segments-to-a-google-adwords-remarketing-list}

Cette procédure nécessite une liste de remarketing [!DNL Google Ads], un code pixel et un [!DNL URL] de [!DNL destination] Audience Manager. Il s’agit également d’une liste de remarketing pour l’intégration des annonces de recherche ([!DNL RLSA]). S’applique uniquement au référencement payant.

>[!IMPORTANT]
>Notez qu’il ne s’agit pas d’une intégration personnalisée des deux systèmes.

Pour configurer une liste de remarketing [!DNL Google Ads] en tant que [!DNL Audience Manager] [!DNL URL destination] :

1. Dans votre compte [!DNL Google Ads], [créez une liste de remarketing de site web](https://support.google.com/tagmanager/answer/6106960?hl=en) et notez votre ID de conversion.
1. Utilisez l’URL suivante comme modèle pour l’URL de base et l’URL sécurisée. Remplacez la section xxxxxxxx par votre ID de conversion.

   ```
    //googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. Dans Audience Manager, [Créer un [!DNL URL destination]](../../features/destinations/create-url-destination.md) ou modifier un [!DNL destination] existant. Utilisez les paramètres suivants lors de la création du [!DNL destination] :
   * Type : URL
   * Sérialiser : activé
   * Délimiteur : point-virgule ( &semi; )

1. Dans la section [!UICONTROL Segment Mappings] de votre [!DNL URL] de [!DNL destination], ajoutez le code de l’étape 2 aux champs [!DNL URL] et [!DNL Secure URL]. Ajoutez le préfixe `http:` et `https:` au code dans les champs [!DNL URL] et [!DNL Secure URL], respectivement.

   >[!IMPORTANT]
   >
   >Remplacez les esperluettes codées `&` par des esperluettes non codées `&`

   Code [!DNL URL] non sécurisé :

   ```
    http://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

   Code [!DNL URL] sécurisé :

   ```
    https://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. Cliquez sur **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >Si vous utilisez plusieurs segments, obtenez un nouveau pixel pour chaque segment que vous souhaitez mapper à un [!DNL Google Ads] [!DNL destination]. Cela permet de s’assurer que les données sont appliquées à la liste de remarketing appropriée.

1. Lors du mappage d’un nouveau segment à ce [!DNL destination] dans Audience Manager, définissez le mappage comme `aam=segmentID` et remplacez `segmentID` par l’identifiant de votre segment.
1. Lors de la définition d’un intervalle dans [!DNL Google Ads], créez une règle qui correspond au mappage défini à l’étape 6.

Un mappage terminé pourrait ressembler à ceci :

![](../assets/rlsa_mapping.png)

>[!MORELIKETHIS]
>
>* [[!DNL Destinations]](../../features/destinations/destinations.md)
>* [Créer un [!DNL URL Destination]](../../features/destinations/create-url-destination.md)
>* [À propos des listes de remarketing AdWords](https://support.google.com/adwords/answer/2472738)
>* [Fonctionnement du remarketing AdWords](https://support.google.com/adwords/answer/2454000)
