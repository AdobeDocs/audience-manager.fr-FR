---
description: Les API de serveur à serveur (S2S) fournissent du code et des méthodes qui vous permettent d’envoyer et de recevoir des données utilisateur DCS et de travailler avec ces informations sur vos propres systèmes ou applications.
seo-description: Les API de serveur à serveur (S2S) fournissent du code et des méthodes qui vous permettent d’envoyer et de recevoir des données utilisateur DCS et de travailler avec ces informations sur vos propres systèmes ou applications.
seo-title: API DCS pour les transferts de données serveur à serveur
solution: Audience Manager
title: API DCS pour les transferts de données serveur à serveur
uuid: 8c369166-c8a7-46b0-9913-4c027f5b1df9
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 0%

---


# API DCS pour les transferts de données serveur à serveur{#dcs-apis-for-server-to-server-data-transfers}

Les serveurs à serveur ([!UICONTROL S2S]) [!DNL API]fournissent le code et les méthodes qui vous permettent d’envoyer et de recevoir des données [!DNL DCS] utilisateur et de travailler avec ces informations dans vos propres systèmes ou applications.

## Cas d’utilisation courants {#common-use-cases}

[!UICONTROL Server-to-server] les transferts peuvent vous aider à personnaliser des landings page ou d’autres interactions en fonction des intérêts des visiteurs. Voici quelques cas d&#39;utilisation courants :

* Personnalisation sur site : Personnalisez l’expérience d’un visiteur sur votre site en ajoutant dynamiquement du contenu pertinent et des appels à l’action en fonction des segments auxquels ils appartiennent.
* Améliorer le service à la clientèle : Importez [!DNL Audience Manager] des segments dans un [!DNL CRM] système ou un autre système par le biais d’un transfert de données serveur à serveur. Ces données peuvent fournir aux opérateurs de service d&#39;appel ou de conversation en ligne des informations pertinentes et personnalisées sur un client.

## Conditions requises : ID utilisateur et noms de serveur régionaux {#requirements}

Les ID d’utilisateur et les ID de région [!UICONTROL DCS API] sont nécessaires pour valider et envoyer des requêtes de données.

* L’ID utilisateur est requis car vous devez associer des données à un visiteur particulier.
* L’identifiant de région est nécessaire pour lier les appels à un nom de serveur et parce que les données utilisateur sont stockées dans les centres de données qui sont géographiquement les plus proches des visiteurs du site.

## Prise en main {#getting-started}

Actuellement, ce guide traite de la façon suivante :

* Récupérez les identifiants d’utilisateur et de région à partir des fichiers [!DNL DCS] que vous recevez peut-être déjà en tant que [!DNL Audience Manager] client.

* Obtenez les identifiants d’utilisateur et de région si vous utilisez le [!DNL Visitor ID Service].
* Appelez le [!DNL DCS] client après avoir identifié l’utilisateur et l’identifiant de région.

Nous ajouterons de nouvelles méthodes dès qu&#39;elles seront disponibles. Consultez les sections suivantes pour commencer.

* [Obtention des ID utilisateur et des régions à partir d’une réponse DCS](dcs-aam-ids.md)
* [Obtenir les ID d&#39;utilisateur et les régions par l&#39;intermédiaire de l&#39;ID d&#39;Experience Cloud...](dcs-mcid-ids.md)
* [Exécution d’appels d’API DCS serveur à serveur](dcs-s2s-calls.md)

>[!MORELIKETHIS]
>
>* [Référence de l’API DCS](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

