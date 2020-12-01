---
description: Vous pouvez envoyer des segments qualifiés à Google Ad Manager soit par le biais d’une intégration côté client, soit par le biais d’une intégration côté serveur. Les exigences et les informations connexes sur les deux méthodes sont énumérées ci-dessous.
seo-description: Vous pouvez envoyer des segments qualifiés à Google Ad Manager soit par le biais d’une intégration côté client, soit par le biais d’une intégration côté serveur. Les exigences et les informations connexes sur les deux méthodes sont énumérées ci-dessous.
seo-title: Exigences et méthodes d’envoi de segments à Google Ad Manager à l’aide de balises Google Publisher (GPT)
solution: Audience Manager
title: Exigences et méthodes d’envoi de segments à Google Ad Manager à l’aide de balises Google Publisher (GPT)
uuid: 4b2ea81c-29bb-42d3-93d3-1d8e677790b6
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e007279d81998031d2d61d0e68fe911813cadf8e
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 0%

---


# Exigences et méthodes d’envoi de segments à Google Ad Manager à l’aide de balises Google Publisher ( GPT) {#requirements-and-methods-of-sending-segments-to-dfp-using-google-publisher-tags-gpt}

Vous pouvez envoyer des segments qualifiés à [!DNL Google Ad Manager] (anciennement DFP) soit par le biais d’une intégration côté client, soit par le biais d’une intégration côté serveur. Les exigences et les informations connexes sur les deux méthodes sont énumérées ci-dessous.

## Intégration côté client {#client-side-integration}

Pour une intégration côté client, vous devez configurer une destination [!DNL GPT] en Audience Manager. Tenez compte des points suivants lorsque vous souhaitez configurer [!DNL GPT] en tant que destination d’Audience Manager :

* **Ajoute  [!UICONTROL DIL]:** Déployez du  [!UICONTROL Data Integration Library (DIL)] code sur toutes les pages à cible. [!UICONTROL DIL] écrit les données de segment d’Audience Manager et les identifiants d’utilisateur sur les cookies qui sont utilisés par  [!DNL GPT] le ciblage.

* **Créez un  [!UICONTROL Cookie Destination]:** [!DNL GPT] doit être configuré en tant que destination basée sur un cookie en Audience Manager.

* **Mise en oeuvre du code de vérification des cookies :** Placez la méthode  [!DNL GPT] `.setTargeting` API dans le code [ de vérification des ](../../integration/gpt-aam-destination/gpt-aam-modify-api.md)cookies recommandé. Ce code permet d’éviter les erreurs en recherchant des cookies AAM valides avant l’appel de la méthode `.setTargeting`.

* **Ajoutez la  `AamGpt` fonction :** le  `AamGpt` code capture les données des cookies d’Audience Manager et les envoie à  [!DNL GPT]. Placez le [code d’Audience Manager pour les balises Google Publisher](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md) ( `AamGpt`) en haut de la page ou à l’intérieur du bloc de codes `<head>`.

   >[!NOTE]
   >
   >La fonction `AamGpt` n&#39;est pas requise si vous utilisez votre propre code pour lire les données des cookies d&#39;Audience Manager.

* **Envoyer des Logs de diffusion à l’Audience Manager :** si vous souhaitez un rapport de diffusion de segments (facultatif), fournissez à l’Audience Manager un journal quotidien contenant des données de diffusion au niveau de l’impression. Les données peuvent être au format brut, mais chaque enregistrement doit contenir l’Audience Manager `UUID`. L&#39;Audience Manager peut les récupérer ou les recevoir par [!DNL FTP].

### Seuls les segments qualifiés sont envoyés au GPT

La quantité de données transmises à [!DNL GPT] dépend du nombre de segments pour lesquels un utilisateur particulier est admissible. Supposons, par exemple, que vous configuriez 100 segments d’Audience Manager. Si un visiteur de site est admissible pour cinq d&#39;entre eux, seuls ces cinq segments sont envoyés à [!DNL GPT] (pas tous les 100).

>[!NOTE]
>
>Le nombre de valeurs-clés que vous pouvez envoyer n&#39;est pas limité, mais la requête [!DNL Google] [!DNL URL] contient des limites au nombre de caractères qu&#39;elle peut accepter. Voir [Définition du ciblage et des tailles avec GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1697712).

## Intégration côté serveur {#server-side-integration}

Si vous souhaitez configurer une intégration côté serveur avec [!DNL Google Ad Manager] à l’aide de [!DNL GPT], contactez votre conseiller en Audience Manager ou le service à la clientèle. Vous devrez fournir votre [!DNL Google Ad Manager] ID réseau et ID de lien d’Audience de votre compte.

>[!IMPORTANT]
>
>Si vos pages Web exécutent la bibliothèque [Accélération des pages multimédia](https://www.ampproject.org/) ([!DNL AMP]), vous devez utiliser l’intégration côté serveur avec l’Audience Manager. Si vous utilisez [!DNL AMP] et que vous disposez d’une intégration côté client avec [!DNL AMP], vous devez migrer vers l’intégration côté serveur. Contactez votre conseiller en Audience Manager ou le service à la clientèle pour discuter de la migration.

>[!MORELIKETHIS]
>
>* [Guide de référence d&#39;API GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1650154)

