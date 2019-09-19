---
description: Les API de serveur à serveur (S2S) fournissent le code et les méthodes qui vous permettent d’envoyer et de recevoir des données utilisateur DCS et de travailler avec ces informations dans vos propres systèmes ou applications.
seo-description: Les API de serveur à serveur (S2S) fournissent le code et les méthodes qui vous permettent d’envoyer et de recevoir des données utilisateur DCS et de travailler avec ces informations dans vos propres systèmes ou applications.
seo-title: API DCS pour les transferts de données serveur à serveur
solution: Audience Manager
title: API DCS pour les transferts de données serveur à serveur
uuid: 8c369166-c8a7-46b0-9913-4c027f5b1df9
translation-type: tm+mt
source-git-commit: 6169e8aefc4c215c83d6229be7378f90453f19e9

---


# API DCS pour les transferts de données serveur à serveur{#dcs-apis-for-server-to-server-data-transfers}

Les serveurs à serveur ([!UICONTROL S2S]) [!DNL API]fournissent le code et les méthodes qui vous permettent d’envoyer et de recevoir des données [!UICONTROL DCS] utilisateur et de travailler avec ces informations dans vos propres systèmes ou applications.

## Cas d’utilisation courants {#common-use-cases}

[!UICONTROL Server-to-server] transferts peuvent vous aider à personnaliser les pages d’entrée ou d’autres interactions en fonction des intérêts des visiteurs. Voici quelques exemples d’utilisation courants :

* Personnalisation sur site : Adaptez l’expérience d’un visiteur sur votre site en ajoutant dynamiquement du contenu pertinent et des appels à l’action en fonction des segments auxquels il appartient.
* Améliorer le service à la clientèle : Importez [!DNL Audience Manager] des segments dans un système [!DNL CRM] ou un autre système par le biais d’un transfert de données serveur à serveur. Ces données peuvent fournir aux opérateurs de service d’appel ou de conversation en ligne des informations pertinentes et personnalisées sur un client.

## Conditions requises : ID utilisateur et noms de serveur régionaux {#requirements}

Les ID utilisateur et les ID de région [!UICONTROL DCS API] sont nécessaires pour valider et effectuer des requêtes de données.

* L’ID utilisateur est requis car vous devez associer des données à un visiteur particulier.
* L’identifiant de région est nécessaire pour lier les appels à un nom de serveur et parce que les données utilisateur sont stockées dans des centres de données qui sont géographiquement les plus proches des visiteurs du site.

## Prise en main {#getting-started}

Actuellement, ce guide décrit comment :

* Récupérez les ID d’utilisateur et de région des [!UICONTROL DCS] fichiers que vous recevez peut-être déjà en tant que [!DNL Audience Manager] client.

* Obtenez les identifiants d’utilisateur et de région si vous utilisez le [!DNL Visitor ID Service].
* Appelez le [!UICONTROL DCS] client après avoir obtenu l’utilisateur et l’ID de région.

Nous ajouterons de nouvelles méthodes dès qu'elles seront disponibles. Reportez-vous aux sections suivantes pour commencer.

* [Obtention des ID utilisateur et des régions à partir d’une réponse DCS](dcs-aam-ids.md)
* [Obtention des ID utilisateur et des régions via l’ID Experience Cloud...](dcs-mcid-ids.md)
* [Réalisation d’appels d’API DCS de serveur à serveur](dcs-s2s-calls.md)

>[!MORE_LIKE_This]
>
>* [Référence de l’API DCS](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

