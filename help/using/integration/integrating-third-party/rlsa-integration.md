---
description: Cette procédure requiert une liste de remarketing adwords, un code de pixels et une destination d'URL Audience Manager. On parle également de liste de remarketing pour l'intégration des publicités de recherche (RLSA). S'applique uniquement à la recherche payante.
seo-description: Cette procédure requiert une liste de remarketing adwords, un code de pixels et une destination d'URL Audience Manager. On parle également de liste de remarketing pour l'intégration des publicités de recherche (RLSA). S'applique uniquement à la recherche payante.
seo-title: Envoyer des segments à une liste de remarketing Google adwords
solution: Audience Manager
title: Envoyer des segments à une liste de remarketing Google adwords
uuid: 5 ad 821 c 6-48 b 4-42 c 0-b 912-1563331 e 93 a 2
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Send Segments to a Google Ads Remarketing List {#send-segments-to-a-google-adwords-remarketing-list}

This procedure requires a [!DNL Google Ads] remarketing list, pixel code, and an Audience Manager [!DNL URL] destination. It is also known as a remarketing list for search ads ([!DNL RLSA]) integration. S'applique uniquement à la recherche payante.

>[!IMPORTANT]
>Veuillez noter qu'il ne s'agit pas d'une intégration productrice des deux systèmes.

To set up a [!DNL Google Ads] remarketing list as an [!DNL Audience Manager] URL destination:

1. In your [!DNL Google Ads] account, [create a website re-marketing list](https://support.google.com/adwords/answer/2454064?hl=en) and write down your conversion ID.
1. Utilisez l'URL suivante comme modèle pour l'URL de base et l'URL sécurisée. Remplacez la section xxxxxxxx par votre identifiant de conversion.

   ```
    //googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. In Audience Manager, [Create a URL destination](../../features/destinations/manage-destinations.md#configure-url-destination) or edit an existing destination. Utilisez les paramètres suivants lors de la création de la destination :
   * Type : URL
   * Sérialiser : Activé
   * Délimiteur : Point-virgule (;)

1. In the [!UICONTROL Segment Mappings] section of your [!DNL URL] destination, add the code from step 2 to the [!DNL URL] and [!DNL Secure URL] fields. Prefix the code with `http:` and `https:` in the [!DNL URL] and [!DNL Secure URL] fields, respectively.

   >[!IMPORTANT]
   >
   >Replace encoded ampersands `&` with un-encoded ampersands `&`

   Unsecure [!DNL URL] code:

   ```
    http://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

   Secure [!DNL URL] code:

   ```
    https://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. Cliquez sur **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >Si vous travaillez avec plusieurs segments, obtenez un pixel pour chaque segment à mapper à une destination Google Publicités. Ainsi, les données sont appliquées à la liste de remarketing appropriée.

1. When mapping a new segment to this destination in Audience Manager, define the mapping as `aam=segmentID` and replace `segmentID` with the ID of your segment.
1. When defining a bucket in [!DNL Google Ads], create a rule that matches the mapping defined at step 6.

Un mappage terminé peut ressembler à ceci :

![](../assets/rlsa_mapping.png)

>[!MORE_ LIKE_ THIS]
>
>* [Destinations](../../features/destinations/destinations.md)
>* [Création d'une destination d'URL](../../features/destinations/manage-destinations.md#configure-url-destination)
>* [A propos des listes de remarketing adwords](https://support.google.com/adwords/answer/2472738)
>* [Fonctionnement du remarketing adwords](https://support.google.com/adwords/answer/2454000)

