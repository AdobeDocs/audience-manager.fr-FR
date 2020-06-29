---
description: Cette procédure nécessite une liste de remarketing AdWords, un code de pixel et une destination URL d’Audience Manager. Elle est également connue sous le nom de liste de marketing de relance pour l’intégration des annonces de recherche (RLSA). S’applique uniquement à la recherche payante.
seo-description: Cette procédure nécessite une liste de remarketing AdWords, un code de pixel et une destination URL d’Audience Manager. Elle est également connue sous le nom de liste de marketing de relance pour l’intégration des annonces de recherche (RLSA). S’applique uniquement à la recherche payante.
seo-title: Envoyer des segments à une Liste de remarketing Google AdWords
solution: Audience Manager
title: Envoyer des segments à une Liste de remarketing Google AdWords
uuid: 5ad821c6-48b4-42c0-b912-1563331e93a2
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 0%

---


# Envoyer des segments à une Liste de remarketing publicitaire Google {#send-segments-to-a-google-adwords-remarketing-list}

Cette procédure nécessite une liste [!DNL Google Ads] de marketing de relance, du code de pixel et une Audience Manager [!DNL URL][!DNL destination]. Elle est également connue sous le nom de liste de marketing de relance pour l’intégration des publicités de recherche ([!DNL RLSA]). S’applique uniquement à la recherche payante.

>[!IMPORTANT]
>Veuillez noter qu&#39;il ne s&#39;agit pas d&#39;une intégration productive des deux systèmes.

Pour configurer une liste de [!DNL Google Ads] marketing de relance en tant que [!DNL Audience Manager][!DNL URL destination]:

1. Dans votre [!DNL Google Ads] compte, [créez une liste](https://support.google.com/adwords/answer/2454064?hl=en) de marketing de relance de site Web et notez votre identifiant de conversion.
1. Utilisez l’URL suivante comme modèle pour l’URL de base et l’URL sécurisée. Remplacez la section xxxxxxxx par votre ID de conversion.

   ```
    //googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. Dans Audience Manager, [créez une [ !destination URL DNL]](../../features/destinations/create-url-destination.md) ou modifiez une [!DNL destination]URL existante. Utilisez les paramètres suivants lors de la création du [!DNL destination]:
   * Type : URL
   * Sérialiser : Activé
   * Délimiteur : Point-virgule (;)

1. Dans la [!UICONTROL Segment Mappings] section de votre [!DNL URL][!DNL destination]formulaire, ajoutez le code de l’étape 2 aux [!DNL URL] champs et [!DNL Secure URL] . Préfixez le code avec `http:` et `https:` dans les [!DNL URL] et [!DNL Secure URL] champs, respectivement.

   >[!IMPORTANT]
   >
   >Remplace les esperluettes codées `&` par des esperluettes non codées. `&`

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
   >Si vous travaillez sur plusieurs segments, obtenez un nouveau pixel pour chaque segment que vous souhaitez mapper à un [!DNL Google Ads][!DNL destination]. Ainsi, les données sont appliquées à la liste de marketing de relance appropriée.

1. Lors du mappage d’un nouveau segment sur celui-ci [!DNL destination] dans l’Audience Manager, définissez le mappage `aam=segmentID` et remplacez-le `segmentID` par l’identifiant de votre segment.
1. Lors de la définition d&#39;un compartiment dans [!DNL Google Ads], créez une règle correspondant au mappage défini à l&#39;étape 6.

Un mappage terminé peut ressembler à ceci :

![](../assets/rlsa_mapping.png)

>[!MORELIKETHIS]
>
>* [[ !Destinations DNL]](../../features/destinations/destinations.md)
>* [Créer une [ !destination URL DNL]](../../features/destinations/create-url-destination.md)
>* [A propos des Listes de remarketing AdWords](https://support.google.com/adwords/answer/2472738)
>* [Fonctionnement du remarketing AdWords](https://support.google.com/adwords/answer/2454000)

