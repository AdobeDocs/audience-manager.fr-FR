---
description: Vous pouvez envoyer des segments qualifiés à Google Ad Manager par le biais d’une intégration côté client ou côté serveur. Les conditions requises et les informations associées concernant les deux méthodes sont répertoriées ci-dessous.
seo-description: You can send qualified segments to Google Ad Manager either through a client-side or through a server-side integration. Requirements and related information about both methods are listed below.
seo-title: Requirements and Methods of Sending Segments to Google Ad Manager Using Google Publisher Tags (GPT)
solution: Audience Manager
title: Exigences et méthodes relatives à l’envoi de segments à Google Ad Manager à l’aide de Google Publisher Tags (GPT)
uuid: 4b2ea81c-29bb-42d3-93d3-1d8e677790b6
feature: Third-party Integration
exl-id: 04bf6fb5-ce38-4de1-bf19-e130b7e47616
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 0%

---

# Exigences et méthodes relatives à l’envoi de segments à Google Ad Manager à l’aide de Google Publisher Tags ( GPT) {#requirements-and-methods-of-sending-segments-to-dfp-using-google-publisher-tags-gpt}

Vous pouvez envoyer des segments qualifiés à [!DNL Google Ad Manager] (anciennement DFP) par le biais d’une intégration côté client ou côté serveur. Les conditions requises et les informations associées concernant les deux méthodes sont répertoriées ci-dessous.

## Intégration Côté Client {#client-side-integration}

Pour une intégration côté client, vous devez configurer une destination [!DNL GPT] dans Audience Manager. Tenez compte des points suivants lorsque vous souhaitez configurer [!DNL GPT] en tant que destination Audience Manager :

* **Ajoutez des [!UICONTROL DIL] :** déployez [!UICONTROL Data Integration Library (DIL)] code sur toutes les pages que vous souhaitez cibler. [!UICONTROL DIL] écrit les données de segment et les identifiants d’utilisateur Audience Manager dans les cookies utilisés par [!DNL GPT] pour le ciblage.

* **Création d’une [!UICONTROL Cookie Destination] :** [!DNL GPT] doit être configuré en tant que destination basée sur des cookies dans Audience Manager.

* **Implémenter le code de vérification des cookies** Encapsulez la méthode d’API [!DNL GPT] `.setTargeting` dans notre [code de vérification des cookies](../../integration/gpt-aam-destination/gpt-aam-modify-api.md) recommandé. Ce code permet d’éviter les erreurs en recherchant les cookies AAM valides avant d’appeler la méthode `.setTargeting`.

* **Ajouter la fonction `AamGpt` :** le code `AamGpt` capture les données des cookies Audience Manager et les envoie à [!DNL GPT]. Placez le [code Audience Manager pour les balises de l’éditeur Google](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md) ( `AamGpt`) en haut de la page ou à l’intérieur du bloc de code `<head>`.

  >[!NOTE]
  >
  >La fonction `AamGpt` n’est pas requise si vous utilisez votre propre code pour lire les données de cookie Audience Manager.

* **Envoyer les journaux de diffusion à Audience Manager :** si vous souhaitez un rapport de diffusion de segment (facultatif), fournissez à Audience Manager un journal quotidien contenant les données de diffusion au niveau de l’impression. Les données peuvent être dans un format brut, mais chaque enregistrement doit contenir le `UUID` Audience Manager. Audience Manager peut les récupérer ou les recevoir via [!DNL FTP].

### Seuls les segments qualifiés sont envoyés au GPT

La quantité de données transmises à [!DNL GPT] dépend du nombre de segments pour lesquels un utilisateur particulier est qualifié. Supposons, par exemple, que vous ayez configuré 100 segments Audience Manager. Si un visiteur ou une visiteuse du site remplit les conditions de cinq d’entre eux, seuls ces cinq segments sont envoyés à [!DNL GPT] (pas les 100).

>[!NOTE]
>
>Le nombre de valeurs de clé que vous pouvez envoyer n’est pas limité, mais l’[!DNL Google] de requête [!DNL URL] n’a pas de limite quant au nombre de caractères qu’elle peut accepter. Voir [Définition du ciblage et des tailles avec le GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&answer=1697712).

## Intégration Côté Serveur {#server-side-integration}

Adressez-vous à votre consultant Audience Manager ou à l’assistance clientèle si vous souhaitez configurer une intégration côté serveur avec [!DNL Google Ad Manager], à l’aide de [!DNL GPT]. Vous devez fournir les identifiants réseau et de lien d’audience de votre compte [!DNL Google Ad Manager].

>[!IMPORTANT]
>
>Si vos pages web exécutent la bibliothèque [Accelerated Media Pages](https://www.ampproject.org/) ([!DNL AMP]) , vous devez utiliser l’intégration côté serveur à Audience Manager. Si vous êtes sur [!DNL AMP] et disposez d’une intégration côté client avec [!DNL AMP], vous devez migrer vers l’intégration côté serveur. Contactez votre consultant Audience Manager ou l’assistance clientèle pour discuter de la migration.

>[!MORELIKETHIS]
>
>* [&#x200B; Guide de référence de l’API GPT &#x200B;](https://support.google.com/dfp_premium/bin/answer.py?hl=en&answer=1650154)
