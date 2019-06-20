---
description: Vous pouvez envoyer des segments qualifiés au DFP via un côté client ou via une intégration côté serveur. Les exigences et les informations associées au sujet des deux méthodes sont répertoriées ci-dessous.
seo-description: Vous pouvez envoyer des segments qualifiés au DFP via un côté client ou via une intégration côté serveur. Les exigences et les informations associées au sujet des deux méthodes sont répertoriées ci-dessous.
seo-title: Conditions requises et méthodes d’envoi de segments à DFP à l’aide de balises Google Publisher Tag (GPT)
solution: Audience Manager
title: Conditions requises et méthodes d’envoi de segments à DFP à l’aide de balises Google Publisher Tag (GPT)
uuid: 4 b 2 ea 81 c -29 bb -42 d 3-93 d 3-1 d 8 e 677790 b 6
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Conditions requises et méthodes d’envoi de segments à DFP à l’aide de balises Google Publisher Tag (GPT) {#requirements-and-methods-of-sending-segments-to-dfp-using-google-publisher-tags-gpt}

You can send qualified segments to [!DNL DFP] either through a client-side or through a server-side integration. Les exigences et les informations associées au sujet des deux méthodes sont répertoriées ci-dessous.

## Client-Side Integration {#client-side-integration}

For a client-side integration, you need to set up a [!DNL GPT] destination in Audience Manager. Consider the following points when you want to set up [!DNL GPT] as an Audience Manager destination:

* **Ajouter[!UICONTROL DIL]:** Déployez [!UICONTROL Data Integration Library (DIL)] le code sur toutes les pages à cibler. [!UICONTROL DIL] écrit les données de segment Audience Manager et l&#39;utilisateur - identifiants aux cookies utilisés [!DNL GPT] pour le ciblage.

* **Créer un[!UICONTROL Cookie Destination]:**[!DNL GPT] doit être configurée comme destination basée sur des cookies dans Audience Manager.

* **Implémentation du code de vérification des cookies :** Encapsulez la méthode [!DNL GPT]`.setTargeting` API dans le code de vérification [de cookie recommandé](../../integration/gpt-aam-destination/gpt-aam-modify-api.md). This code helps prevent errors by looking for valid AAM cookies before the `.setTargeting` method gets invoked.

* **Ajouter`AamGpt`la fonction :** `AamGpt` Le code capture les données des cookies Audience Manager et les envoie [!DNL GPT]. Place the [Audience Manager Code for Google Publisher Tags](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md) ( `AamGpt`) at the top of the page or inside the `<head>` code block.

   >[!NOTE]
   >
   >`AamGpt` La fonction n&#39;est pas requise si vous utilisez votre propre code pour lire les données du cookie Audience Manager.

* **Envoyer des journaux de diffusion à Audience Manager :** Si vous souhaitez un rapport de diffusion de segment (facultatif), fournissez à Audience Manager un journal quotidien contenant des données de diffusion au niveau d&#39;impression. The data can be in a raw format, but each record must contain the Audience Manager `UUID`. Audience Manager can pick up or receive these via [!DNL FTP].

### Seuls les segments qualifiés sont envoyés à GPT

The amount of data passed in to [!DNL GPT] depends on how many segments a particular user qualifies for. Par exemple, supposons que vous configurez 100 segments Audience Manager. If a site visitor qualifies for five of them, then only those five segments get sent to [!DNL GPT] (not all 100).

>[!NOTE]
>
>There are no limits to the number of key-values you can send, but the [!DNL Google] request [!DNL URL] does have limits to the number of characters it can accept. See [Setting targeting and sizes with GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&answer=1697712).

## Server-Side Integration {#server-side-integration}

Talk to your Audience Manager consultant or Customer Care if you want to set up a server-side integration with [!DNL DFP], using [!DNL GPT]. You&#39;ll need to provide your [!DNL DFP] account Network ID and Audience Link ID.

>[!IMPORTANT]
>
>If your web pages are running the [Accelerated Media Pages](https://www.ampproject.org/) ([!DNL AMP]) library, you must use the server-side integration with Audience Manager. If you are on [!DNL AMP] and have a client-side integration with [!DNL AMP], you must migrate to the server-side integration. Contactez votre consultant Audience Manager ou le service d&#39;assistance clientèle pour discuter de la migration.

>[!MORE_ LIKE_ THIS]
>
>* [Guide de référence de l&#39;API GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&answer=1650154)

