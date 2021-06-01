---
description: Les API de serveur à serveur (S2S) fournissent du code et des méthodes qui vous permettent d’envoyer et de recevoir des données utilisateur DCS et de travailler avec ces informations dans vos propres systèmes ou applications.
seo-description: Les API de serveur à serveur (S2S) fournissent du code et des méthodes qui vous permettent d’envoyer et de recevoir des données utilisateur DCS et de travailler avec ces informations dans vos propres systèmes ou applications.
seo-title: API DCS pour les transferts de données de serveur à serveur
solution: Audience Manager
title: API DCS pour les transferts de données de serveur à serveur
uuid: 8c369166-c8a7-46b0-9913-4c027f5b1df9
feature: DCS
exl-id: fd23d5e2-b74e-47ff-a4aa-3a4b2c7d39c5
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 11%

---

# API DCS pour les transferts de données de serveur à serveur{#dcs-apis-for-server-to-server-data-transfers}

Les serveurs vers serveur ([!UICONTROL S2S]) [!DNL API]fournissent du code et des méthodes qui vous permettent d’envoyer et de recevoir des [!DNL DCS] données utilisateur et de travailler avec ces informations dans vos propres systèmes ou applications.

## Cas d’utilisation courants {#common-use-cases}

[!UICONTROL Server-to-server] les transferts peuvent vous aider à personnaliser les landing pages ou d’autres interactions en fonction des centres d’intérêt des visiteurs. Voici quelques cas d’utilisation courants :

* Personnalisation sur site : Personnalisez l’expérience d’un visiteur sur votre site en ajoutant dynamiquement du contenu et des appels à l’action pertinents en fonction des segments auxquels ils appartiennent.
* Améliorer le service à la clientèle : Importez des segments [!DNL Audience Manager] dans un [!DNL CRM] ou un autre système par le biais d’un transfert de données serveur à serveur. Ces données peuvent fournir aux opérateurs de service d’appel ou de chat en ligne des informations pertinentes et personnalisées sur un client.

## Conditions requises : ID utilisateur et noms de serveur régionaux {#requirements}

[!UICONTROL DCS API] nécessite des identifiants d’utilisateur et de région pour valider et effectuer des requêtes de données.

* L’identifiant utilisateur est requis car vous devez associer des données à un visiteur particulier.
* L’identifiant de région est nécessaire pour relier les appels à un nom de serveur, car les données utilisateur sont stockées dans des centres de données qui sont géographiquement les plus proches des visiteurs du site.

## Prise en main {#getting-started}

Actuellement, ce guide explique comment :

* Récupérez les identifiants d’utilisateur et de région à partir des fichiers [!DNL DCS] que vous pouvez déjà recevoir en tant que client [!DNL Audience Manager].

* Obtenez les identifiants d’utilisateur et de région si vous utilisez la balise [!DNL Visitor ID Service].
* Appelez [!DNL DCS] une fois que vous disposez de l’ID utilisateur et de région.

Nous ajouterons de nouvelles méthodes dès qu&#39;elles seront disponibles. Consultez les sections suivantes pour commencer.

* [Obtention des identifiants et des régions à partir d’une réponse DCS](dcs-aam-ids.md)
* [Obtention des identifiants de région et d’utilisateur via l’identifiant Experience Cloud...](dcs-mcid-ids.md)
* [Lancement d’appels d’API DCS serveur à serveur](dcs-s2s-calls.md)

>[!MORELIKETHIS]
>
>* [Référence d’API DCS ](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

