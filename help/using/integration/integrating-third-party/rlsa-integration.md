---
description: Cette procédure requiert une liste de remarketing adwords, un code de pixels et une destination d'URL Audience Manager. On parle également de liste de remarketing pour l'intégration des publicités de recherche (RLSA). S'applique uniquement à la recherche payante.
seo-description: Cette procédure requiert une liste de remarketing adwords, un code de pixels et une destination d'URL Audience Manager. On parle également de liste de remarketing pour l'intégration des publicités de recherche (RLSA). S'applique uniquement à la recherche payante.
seo-title: Envoyer des segments à une liste de remarketing Google adwords
solution: Audience Manager
title: Envoyer des segments à une liste de remarketing Google adwords
uuid: 5 ad 821 c 6-48 b 4-42 c 0-b 912-1563331 e 93 a 2
translation-type: tm+mt
source-git-commit: f67ab906bfbd9900941649c4d9045ea94f1e7f4c

---


# Envoyer des segments à une liste de remarketing Google Publicités {#send-segments-to-a-google-adwords-remarketing-list}

Cette procédure requiert une [!DNL Google Ads] liste de remarketing, un code de pixels et [!DNL URL] une destination Audience Manager. On parle également de liste de remarketing pour l'intégration des publicités de recherche ([!DNL RLSA]). S'applique uniquement à la recherche payante.

>[!IMPORTANT]
>Veuillez noter qu'il ne s'agit pas d'une intégration productrice des deux systèmes.

Pour configurer une [!DNL Google Ads] liste de remarketing comme destination [!DNL Audience Manager] d'URL :

1. Dans votre [!DNL Google Ads] compte [, créez une liste de remarketing de site Web](https://support.google.com/adwords/answer/2454064?hl=en) et notez votre identifiant de conversion.
1. Utilisez l'URL suivante comme modèle pour l'URL de base et l'URL sécurisée. Remplacez la section xxxxxxxx par votre identifiant de conversion.

   ```
    //googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. Dans Audience Manager, [créez une destination d'URL](../../features/destinations/create-url-destination.md) ou modifiez une destination existante. Utilisez les paramètres suivants lors de la création de la destination :
   * Type : URL
   * Sérialiser : Activé
   * Délimiteur : Point-virgule (;)

1. Dans [!UICONTROL Segment Mappings] la section [!DNL URL] de votre destination, ajoutez le code de l'étape 2 aux champs [!DNL URL] et aux [!DNL Secure URL] champs. Préfixez le code avec `http:` et `https:` dans les [!DNL URL] champs et [!DNL Secure URL] , respectivement.

   >[!IMPORTANT]
   >
   >Remplacer les esperluettes codées `&` par des esperluettes non codées `&`

   Code non sécurisé [!DNL URL] :

   ```
    http://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

   Code sécurisé [!DNL URL] :

   ```
    https://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. Cliquez sur **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >Si vous travaillez avec plusieurs segments, obtenez un pixel pour chaque segment à mapper à une destination Google Publicités. Ainsi, les données sont appliquées à la liste de remarketing appropriée.

1. Lorsque vous mappez un nouveau segment à cette destination dans Audience Manager, définissez le mappage et `aam=segmentID` remplacez-le `segmentID` par l'identifiant de votre segment.
1. Lors de la définition d'un compartiment dans [!DNL Google Ads], créez une règle correspondant au mappage défini à l'étape 6.

Un mappage terminé peut ressembler à ceci :

![](../assets/rlsa_mapping.png)

>[!MORE_ LIKE_ THIS]
>
>* [Destinations](../../features/destinations/destinations.md)
>* [Création d'une destination d'URL](../../features/destinations/create-url-destination.md)
>* [A propos des listes de remarketing adwords](https://support.google.com/adwords/answer/2472738)
>* [Fonctionnement du remarketing adwords](https://support.google.com/adwords/answer/2454000)

