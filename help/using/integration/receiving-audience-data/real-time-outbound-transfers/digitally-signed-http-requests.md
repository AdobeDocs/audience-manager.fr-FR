---
description: Audience Manager requiert que les demandes serveur HTTP soient signées numériquement pour validité. Ce document décrit la manière de signer des requêtes HTTP avec des clés privées.
seo-description: Audience Manager requiert que les demandes serveur HTTP soient signées numériquement pour validité. Ce document décrit la manière de signer des requêtes HTTP avec des clés privées.
seo-title: Requêtes HTTP avec signature numérique
solution: Audience Manager
title: Requêtes HTTP avec signature numérique
uuid: 1183 a 70 f -0 c 96-42 cf-a 4 f 5-37 a 83 ffa 1286
translation-type: tm+mt
source-git-commit: 9bf1f3771b6a4b9bb9a52149e812b37d1c8e27f8

---


# Digitally Signed `HTTP` Requests {#digitally-signed-http-requests}

Audience Manager requires the `HTTP` server-to-server requests to be digitally signed for validity. This document describes how you can sign `HTTP` requests with private keys.

## Aperçu {#overview}

<!-- digitally_signed_http_requests.xml -->

Using a private key provided by you and shared with [!DNL Audience Manager], we can digitally sign the `HTTP` requests that are sent between [IRIS](../../../reference/system-components/components-data-action.md#iris) and your HTTP server. Ceci garantit que :

* **Authenticité**: seul l'expéditeur qui possède la clé privée ([!UICONTROL IRIS]) peut envoyer `HTTP(S)` des messages valides au partenaire.
* **Intégrité des messages**: avec cette approche, même sur `HTTP`, vous êtes protégé contre un homme dans l'attaque intermédiaire où les messages sont déformés.

[!UICONTROL IRIS] comporte une prise en charge intégrée pour faire pivoter les clés dont le temps d'interruption est zéro, comme indiqué dans [la section Rotation de la clé](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#rotate-private-key) privée ci-dessous.

## Information you need to provide {#info-to-provide}

For an `HTTP` real-time server-to-server destination, contact your [!DNL Audience Manager] consultant and specify:

* Clé utilisée pour signer la requête.
* The name of the `HTTP` header that will hold the generated signature (X-Signature in the example header below).
* Facultatif : type de hachage utilisé pour la signature (md 5, sha 1, sha 256).

```
* Connected to partner.website.com (127.0.0.1) port 80 (#0)
> POST /webpage HTTP/1.1
> Host: partner.host.com
> Accept: */*
> Content-Type: application/json
> Content-Length: 20
> X-Signature: +wFdR/afZNoVqtGl8/e1KJ4ykPU=
POST message content
```

## How it works {#how-it-works}

1. [!UICONTROL IRIS] crée le `HTTP` message à envoyer au partenaire.
1. [!UICONTROL IRIS] crée une signature basée sur `HTTP` le message et la clé privée communiquée par le partenaire.
1. [!UICONTROL IRIS] envoie la `HTTP(S)` requête au partenaire. Ce message contient la signature et le message réel, comme le montre l'exemple ci-dessus.
1. The partner server receives the `HTTP(S)` request. It reads the message body and the signature received from [!UICONTROL IRIS].
1. En fonction du corps du message reçu et de la clé privée, le serveur partenaire recalcule la signature. See the [How to calculate the signature](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#calculate-signature) section just below on how to achieve this.
1. Compare the signature created on the partner server (receiver) with the one received from [!UICONTROL IRIS] (sender).
1. If the signatures match, then the **authenticity** and **message integrity** have been validated. Seul l'expéditeur, qui possède la clé privée, peut envoyer une signature valide (authenticité). De plus, un homme au milieu ne peut pas modifier le message et générer une signature valide, puisqu'il n'a pas la clé privée (intégrité des messages).

![](assets/iris-digitally-sign-http-request.png)

## How to calculate the signature {#calculate-signature}

[!DNL HMAC] (Code d'authentification de message basé sur un hachage) est la méthode utilisée pour [!UICONTROL IRIS] la signature de message. Les implémentations et les bibliothèques sont disponibles essentiellement dans chaque langage de programmation. [!DNL HMAC] ne comporte pas d'attaques d'extension connues. See an example in [!DNL Java] below:

```
// Message to be signed.
// For GET type HTTP destinations, the message used for signing will be the REQUEST_PATH + QUERY_STRING
// For POST type HTTP destinations, the message used for signing will be the REQUEST_BODY.
// String getData = "/from-aam-s2s?sids=1,2,3";
String postData = "POST message content";
// Algorithm used. Currently supported: HmacSHA1, HmacSHA256, HmacMD5.
String algorithm = "HmacSHA1";
// Private key shared between the partner and Adobe Audience Manager.
String key = "sample_partner_private_key";
  
// Perform signing.
SecretKeySpec signingKey = new SecretKeySpec(key.getBytes(), algorithm);
Mac mac = Mac.getInstance(algorithm);
mac.init(signingKey);
byte[] result = mac.doFinal(postData.getBytes());
  
String signature = Base64.encodeBase64String(result).trim(); 
// signature = +wFdR/afZNoVqtGl8/e1KJ4ykPU=
```

The RFC for the [!DNL HMAC] hash implementation is [https://www.ietf.org/rfc/rfc2104.txt](https://www.ietf.org/rfc/rfc2104.txt). A test site: [https://asecuritysite.com/encryption/hmac](https://asecuritysite.com/encryption/hmac) (note that you have to [convert](https://tomeko.net/online_tools/hex_to_base64.php?lang=en) the hex encoding to base64).

## Rotating the private key {#rotate-private-key}

Pour des raisons de sécurité, il est recommandé de faire pivoter régulièrement la clé privée. C'est à vous de décider de la clé privée et de la période de rotation. In order to achieve the key rotation with zero downtime, [!UICONTROL IRIS] supports adding multiple signature headers. Un en-tête contiendra la signature générée avec l'ancienne clé ; un autre en-tête contiendra la signature générée à l'aide de la nouvelle clé privée. Voir sous la procédure détaillée :

1. Partner communicates the new private key to [!DNL Adobe Audience Manager].
1. [!UICONTROL IRIS] commence à envoyer deux en-têtes de signature (l'un utilisant l'ancienne clé, l'autre utilisant la nouvelle clé).
1. Une fois que vous avez commencé à recevoir les deux en-têtes, vous pouvez ignorer l'ancienne clé et seulement la nouvelle signature.
1. The old key is removed from [!DNL Audience Manager] and [!UICONTROL IRIS] only sends the new signature header. Les clés ont été pivotées.

## Data used for signing {#data-signing}

For `GET` type destinations, the message used for signing will be the *REQUEST_PATH + QUERY STRING* (e.g. */from-aam-s2s?sids=1,2,3*). IRIS does not take into account the hostname or `HTTP` headers - these can be modified / misconfigured along the path or reported incorrectly.

For `POST` type destinations, the message used for signing is the *REQUEST BODY*. De nouveau, les en-têtes ou autres paramètres de requête sont ignorés.
