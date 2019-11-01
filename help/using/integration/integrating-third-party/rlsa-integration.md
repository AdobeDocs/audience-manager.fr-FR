---
description: Cette procédure nécessite une liste de remarketing AdWords, un code de pixel et une destination URL Audience Manager. Il s’agit également d’une liste de marketing de relance pour l’intégration des publicités de recherche (RLSA). S’applique uniquement à la recherche payante.
seo-description: Cette procédure nécessite une liste de remarketing AdWords, un code de pixel et une destination URL Audience Manager. Il s’agit également d’une liste de marketing de relance pour l’intégration des publicités de recherche (RLSA). S’applique uniquement à la recherche payante.
seo-title: Envoyer des segments à une liste de commentaires Google AdWords
solution: Audience Manager
title: Envoyer des segments à une liste de commentaires Google AdWords
uuid: 5ad821c6-48b4-42c0-b912-156331e93a2
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Envoyer des segments à une liste de remarketing publicitaire Google {#send-segments-to-a-google-adwords-remarketing-list}

Cette procédure nécessite une liste de [!DNL Google Ads] marketing de relance, un code de pixel et une destination Audience Manager [!DNL URL] . Elle est également connue sous le nom de liste de remarketing pour l’intégration des publicités de recherche ([!DNL RLSA]). S’applique uniquement à la recherche payante.

>[!IMPORTANT]
>Veuillez noter qu'il ne s'agit pas d'une intégration productive des deux systèmes.

Pour configurer une liste de [!DNL Google Ads] remarketing en tant que destination [!DNL Audience Manager] URL :

1. Dans votre [!DNL Google Ads] compte, [créez une liste](https://support.google.com/adwords/answer/2454064?hl=en) de marketing de relance et notez votre identifiant de conversion.
1. Utilisez l’URL suivante comme modèle pour l’URL de base et l’URL sécurisée. Remplacez la section xxxxxxxx par votre ID de conversion.

   ```
    //googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. Dans Audience Manager, [créez une destination](../../features/destinations/create-url-destination.md) URL ou modifiez une destination existante. Utilisez les paramètres suivants lors de la création de la destination :
   * Type :URL
   * Sérialiser : Activé
   * Délimiteur : Point-virgule (;)

1. Dans la [!UICONTROL Segment Mappings] section de votre [!DNL URL] destination, ajoutez le code de l’étape 2 aux [!DNL URL] champs et [!DNL Secure URL] . Préfixez le code avec `http:` et `https:` dans les champs [!DNL URL] et [!DNL Secure URL] , respectivement.

   >[!IMPORTANT]
   >
   >Remplacement des esperluettes codées `&` par des esperluettes non codées `&`

   Code non sécurisé [!DNL URL] :

   ```
    http://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

   Code [!DNL URL] sécurisé :

   ```
    https://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. Cliquez sur **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >Si vous travaillez sur plusieurs segments, obtenez un nouveau pixel pour chaque segment que vous souhaitez mapper à une destination Google Publicités. Ainsi, les données sont appliquées à la liste de remarketing appropriée.

1. Lors du mappage d’un nouveau segment sur cette destination dans Audience Manager, définissez le mappage comme `aam=segmentID` et remplacez-le `segmentID` par l’ID de votre segment.
1. Lors de la définition d’un compartiment dans [!DNL Google Ads], créez une règle qui correspond au mappage défini à l’étape 6.

Un mappage terminé peut ressembler à ceci :

![](../assets/rlsa_mapping.png)

>[!MORELIKETHIS]
>
>* [Destinations](../../features/destinations/destinations.md)
>* [Création d’une destination d’URL](../../features/destinations/create-url-destination.md)
>* [A propos des listes de remarketing AdWords](https://support.google.com/adwords/answer/2472738)
>* [Fonctionnement du remarketing AdWords](https://support.google.com/adwords/answer/2454000)

