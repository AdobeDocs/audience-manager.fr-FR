---
description: Vous pouvez envoyer des segments qualifiés à Google Ad Manager par le biais d’une intégration côté client ou côté serveur. Les exigences et les informations connexes relatives aux deux méthodes sont répertoriées ci-dessous.
seo-description: You can send qualified segments to Google Ad Manager either through a client-side or through a server-side integration. Requirements and related information about both methods are listed below.
seo-title: Requirements and Methods of Sending Segments to Google Ad Manager Using Google Publisher Tags (GPT)
solution: Audience Manager
title: Conditions requises et méthodes d’envoi de segments à Google Ad Manager à l’aide de balises de l’éditeur Google (GPT)
uuid: 4b2ea81c-29bb-42d3-93d3-1d8e677790b6
feature: Third-party Integration
exl-id: 04bf6fb5-ce38-4de1-bf19-e130b7e47616
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 0%

---

# Conditions requises et méthodes d’envoi de segments à Google Ad Manager à l’aide des balises de l’éditeur Google (GPT) {#requirements-and-methods-of-sending-segments-to-dfp-using-google-publisher-tags-gpt}

Vous pouvez envoyer des segments qualifiés à [!DNL Google Ad Manager] (anciennement DFP) par le biais d’une intégration côté client ou côté serveur. Les exigences et les informations connexes relatives aux deux méthodes sont répertoriées ci-dessous.

## Intégration côté client {#client-side-integration}

Pour une intégration côté client, vous devez configurer une destination [!DNL GPT] dans Audience Manager. Tenez compte des points suivants lorsque vous souhaitez configurer [!DNL GPT] comme destination d’Audience Manager :

* **Ajoutez [!UICONTROL DIL] :** Déployez le code [!UICONTROL Data Integration Library (DIL)] sur toutes les pages que vous souhaitez cibler. [!UICONTROL DIL] écrit les données de segment d’Audience Manager et les identifiants d’utilisateur aux cookies utilisés par [!DNL GPT] pour le ciblage.

* **Créez une [!UICONTROL Cookie Destination] :** [!DNL GPT] doit être configuré en tant que destination basée sur les cookies dans Audience Manager.

* **Implémentez Cookie Checking Code :** Encapsulez la méthode d’API [!DNL GPT] `.setTargeting` dans notre [code de vérification de cookie](../../integration/gpt-aam-destination/gpt-aam-modify-api.md) recommandé. Ce code permet d’éviter les erreurs en recherchant des cookies AAM valides avant l’appel de la méthode `.setTargeting`.

* **Ajoutez la fonction `AamGpt` :** Le code `AamGpt` capture les données des cookies d’Audience Manager et les envoie à [!DNL GPT]. Placez le [code d’Audience Manager pour les balises de l’éditeur Google](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md) ( `AamGpt`) en haut de la page ou à l’intérieur du bloc de code `<head>`.

  >[!NOTE]
  >
  >La fonction `AamGpt` n’est pas requise si vous utilisez votre propre code pour lire les données de cookie d’Audience Manager.

* **Envoyer les logs de diffusion à l’Audience Manager :** Si vous souhaitez un rapport de diffusion de segment (facultatif), fournissez à l’Audience Manager un journal quotidien contenant des données de diffusion au niveau de l’impression. Les données peuvent être dans un format brut, mais chaque enregistrement doit contenir l’Audience Manager `UUID`. L&#39;Audience Manager peut les récupérer ou les recevoir via [!DNL FTP].

### Seuls les segments qualifiés sont envoyés à GPT

La quantité de données transmises à [!DNL GPT] dépend du nombre de segments pour lesquels un utilisateur particulier est admissible. Supposons, par exemple, que vous configuriez 100 segments d’Audience Manager. Si un visiteur du site est admissible pour cinq d’entre eux, seuls ces cinq segments sont envoyés à [!DNL GPT] (pas tous les 100).

>[!NOTE]
>
>Il n’existe aucune limite au nombre de valeurs de clé que vous pouvez envoyer, mais la requête [!DNL Google] [!DNL URL] a des limites au nombre de caractères qu’elle peut accepter. Voir [Définition du ciblage et des tailles avec GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1697712).

## Intégration côté serveur {#server-side-integration}

Si vous souhaitez configurer une intégration côté serveur avec [!DNL Google Ad Manager] à l’aide de [!DNL GPT], contactez votre conseiller en Audience Manager ou l’assistance clientèle. Vous devrez fournir votre ID réseau et l’ID de lien d’audience de votre compte [!DNL Google Ad Manager].

>[!IMPORTANT]
>
>Si vos pages web exécutent la bibliothèque [Accelerated Media Pages](https://www.ampproject.org/) ([!DNL AMP]), vous devez utiliser l’intégration côté serveur avec Audience Manager. Si vous utilisez [!DNL AMP] et que vous disposez d’une intégration côté client avec [!DNL AMP], vous devez migrer vers l’intégration côté serveur. Contactez votre conseiller en Audience Manager ou l’assistance clientèle pour discuter de la migration.

>[!MORELIKETHIS]
>
>* [Guide de référence de l’API GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1650154)
