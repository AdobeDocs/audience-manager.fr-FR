---
description: Vous pouvez envoyer des segments qualifiés au DFP soit par le biais d’une intégration côté client, soit par le biais d’une intégration côté serveur. Les exigences et les informations connexes sur les deux méthodes sont énumérées ci-dessous.
seo-description: Vous pouvez envoyer des segments qualifiés au DFP soit par le biais d’une intégration côté client, soit par le biais d’une intégration côté serveur. Les exigences et les informations connexes sur les deux méthodes sont énumérées ci-dessous.
seo-title: Conditions requises et méthodes d’envoi de segments à DFP à l’aide de balises Google Publisher Tag (GPT)
solution: Audience Manager
title: Conditions requises et méthodes d’envoi de segments à DFP à l’aide de balises Google Publisher Tag (GPT)
uuid: 4b2ea81c-29bb-42d3-93d3-1d8e67790b6
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Conditions requises et méthodes d’envoi de segments à DFP à l’aide de balises Google Publisher Tag (GPT) {#requirements-and-methods-of-sending-segments-to-dfp-using-google-publisher-tags-gpt}

Vous pouvez envoyer des segments qualifiés vers [!DNL DFP] un client ou via une intégration côté serveur. Les exigences et les informations connexes sur les deux méthodes sont énumérées ci-dessous.

## Intégration côté client {#client-side-integration}

Pour une intégration côté client, vous devez configurer une [!DNL GPT] destination dans Audience Manager. Tenez compte des points suivants lorsque vous souhaitez configurer une destination [!DNL GPT] Audience Manager :

* **[!UICONTROL DIL]Ajouter**: Déployez [!UICONTROL Data Integration Library (DIL)] le code sur toutes les pages que vous souhaitez cibler. [!UICONTROL DIL] écrit les données de segment et les ID d’utilisateur d’Audience Manager sur les cookies utilisés par [!DNL GPT] le ciblage.

* **[!UICONTROL Cookie Destination]Créez un**: doit [!DNL GPT] être configuré en tant que destination basée sur des cookies dans Audience Manager.

* **** Mise en oeuvre du code de vérification des cookies : Encapsulez la méthode [!DNL GPT]`.setTargeting` API dans le code [de vérification des](../../integration/gpt-aam-destination/gpt-aam-modify-api.md)cookies recommandé. Ce code permet d’éviter les erreurs en recherchant des cookies AAM valides avant l’appel de la `.setTargeting` méthode.

* **`AamGpt`Ajouter la** fonction : Le `AamGpt` code capture les données des cookies d’Audience Manager et les envoie à [!DNL GPT]. Placez le code [Audience Manager pour les balises](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md) Google Publisher ( `AamGpt`) en haut de la page ou à l’intérieur du bloc de `<head>` code.

   >[!NOTE]
   >
   >La `AamGpt` fonction n’est pas requise si vous utilisez votre propre code pour lire les données de cookie d’Audience Manager.

* **** Envoyer les journaux de remise à Audience Manager : Si vous souhaitez un rapport de diffusion de segments (facultatif), fournissez à Audience Manager un journal quotidien contenant des données de diffusion au niveau de l’impression. Les données peuvent être au format brut, mais chaque enregistrement doit contenir Audience Manager `UUID`. Audience Manager peut les récupérer ou les recevoir via [!DNL FTP].

### Seuls les segments qualifiés sont envoyés au GPT

La quantité de données transmises à [!DNL GPT] dépend du nombre de segments pour lesquels un utilisateur particulier est admissible. Supposons, par exemple, que vous configuriez 100 segments d’Audience Manager. Si un visiteur du site est admissible pour cinq d’entre eux, seuls ces cinq segments sont envoyés vers [!DNL GPT] (pas tous les 100).

>[!NOTE]
>
>Il n’existe aucune limite au nombre de valeurs de clé que vous pouvez envoyer, mais la [!DNL Google] requête [!DNL URL] ne contient aucune limite au nombre de caractères qu’elle peut accepter. Voir [Définition du ciblage et des tailles avec GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&answer=1697712).

## Intégration côté serveur {#server-side-integration}

Contactez votre conseiller Audience Manager ou le service à la clientèle si vous souhaitez configurer une intégration côté serveur avec [!DNL DFP], à l’aide de [!DNL GPT]. Vous devrez fournir l’ID réseau et l’ID de lien d’audience de votre [!DNL DFP] compte.

>[!IMPORTANT]
>
>Si vos pages Web exécutent la bibliothèque [Accélération des pages](https://www.ampproject.org/) multimédia ([!DNL AMP]), vous devez utiliser l’intégration côté serveur avec Audience Manager. Si vous vous trouvez [!DNL AMP] et avez une intégration côté client avec [!DNL AMP], vous devez migrer vers l’intégration côté serveur. Contactez votre consultant Audience Manager ou le service à la clientèle pour discuter de la migration.

>[!MORE_LIKE_This]
>
>* [Guide de référence des API GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&answer=1650154)

