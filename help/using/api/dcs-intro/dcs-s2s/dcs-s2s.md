---
description: Les API de serveur à serveur (S 2 S) fournissent du code et des méthodes qui vous permettent d'envoyer et de recevoir des données utilisateur DCS et de travailler avec ces informations dans vos propres systèmes ou applications.
seo-description: Les API de serveur à serveur (S 2 S) fournissent du code et des méthodes qui vous permettent d'envoyer et de recevoir des données utilisateur DCS et de travailler avec ces informations dans vos propres systèmes ou applications.
seo-title: API DCS pour les transferts de données serveur à serveur
solution: Audience Manager
title: API DCS pour les transferts de données serveur à serveur
uuid: 8 c 369166-c 8 a 7-46 b 0-9913-4 c 027 f 5 b 1 df 9
translation-type: tm+mt
source-git-commit: 6169e8aefc4c215c83d6229be7378f90453f19e9

---


# DCS APIs for Server-to-Server Data Transfers{#dcs-apis-for-server-to-server-data-transfers}

Server-to-server ([!UICONTROL S2S]) [!DNL API]s provide code and methods that let you send and receive [!UICONTROL DCS] user data and work with this information in your own systems or applications.

## Common Use Cases {#common-use-cases}

[!UICONTROL Server-to-server] les transferts peuvent vous aider à personnaliser les pages d&#39;entrée ou d&#39;autres interactions en fonction des intérêts des visiteurs. Voici quelques cas d&#39;utilisation courants :

* Personnalisation sur site : Personnalisez l&#39;expérience d&#39;un visiteur sur votre site en ajoutant dynamiquement le contenu pertinent et les appels à l&#39;action en fonction des segments auxquels ils appartiennent.
* Improve customer service: Import [!DNL Audience Manager] segments into a [!DNL CRM] or other system through a server-to-server data transfer. Ces données peuvent fournir un service d&#39;appel ou des opérateurs de messagerie instantanée avec des informations pertinentes et personnalisées sur un client.

## Requirements: User IDs and Regional Server Names {#requirements}

The [!UICONTROL DCS API] requires user IDs and region IDs to validate and make data requests.

* L&#39;utilisateur - id est requis car vous devez associer des données à un visiteur particulier.
* L&#39;ID de région est nécessaire pour lier les appels à un nom de serveur et parce que les données utilisateur sont stockées dans des centres de données qui sont le plus proche des visiteurs du site.

## Prise en main {#getting-started}

Actuellement, ce guide explique comment effectuer les opérations suivantes :

* Get the user and region IDs from the [!UICONTROL DCS] files you may already receive as an [!DNL Audience Manager] customer.

* Get the user and region IDs if you use the [!DNL Visitor ID Service].
* Make calls to the [!UICONTROL DCS] after you have the user and region ID.

Nous ajouterons de nouvelles méthodes dès qu&#39;elles seront disponibles. Pour commencer, reportez-vous aux sections suivantes.

* [Obtention de l&#39;utilisateur - Identifiants et régions à partir d&#39;une réponse DCS](dcs-aam-ids.md)
* [Obtenir l&#39;utilisateur - Identifiants et régions via l&#39;ID d&#39;expérience…](dcs-mcid-ids.md)
* [Création d&#39;appels d&#39;API serveur à serveur](dcs-s2s-calls.md)

>[!MORE_ LIKE_ THIS]
>
>* [Référence de l&#39;API DCS](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

