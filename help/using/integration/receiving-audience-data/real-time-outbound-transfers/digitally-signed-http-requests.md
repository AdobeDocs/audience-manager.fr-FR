---
description: L’Audience Manager requiert que les requêtes HTTP(S) serveur à serveur soient numériquement signées pour être valides. Ce document décrit comment signer des requêtes HTTP à l’aide de clés privées.
seo-description: L’Audience Manager requiert que les requêtes HTTP(S) serveur à serveur soient numériquement signées pour être valides. Ce document décrit comment signer des requêtes HTTP(S) avec des clés privées.
seo-title: Requêtes HTTP(S) Signées Numériquement
solution: Audience Manager
title: Requêtes HTTP(S) Signées Numériquement
uuid: 1183a70f-0c96-42cf-a4f5-37a83ffa1286
feature: Outbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '637'
ht-degree: 0%

---


# Demandes `HTTP(S)` signées numériquement {#digitally-signed-http-requests}

L’Audience Manager requiert que les requêtes `HTTP(S)` serveur à serveur soient numériquement signées pour être valides. Ce document décrit comment signer `HTTP(S)` des requêtes à l’aide de clés privées.

## Aperçu {#overview}

<!-- digitally_signed_http_requests.xml -->

En utilisant une clé privée que vous avez fournie et partagée avec [!DNL Audience Manager], nous pouvons signer numériquement les `HTTP(S)` requêtes envoyées entre [IRIS](../../../reference/system-components/components-data-action.md#iris) et votre serveur HTTP(S). Cela garantit :

* **Authenticité**: seul l&#39;expéditeur disposant de la clé privée ([!UICONTROL IRIS]) peut envoyer `HTTP(S)` des messages valides au partenaire.
* **Intégrité** du message : avec cette approche, même `HTTP`sur, vous êtes protégé d&#39;un homme dans l&#39;attaque médiane où les messages sont déformés.

[!UICONTROL IRIS] prend en charge la rotation des clés sans temps d’arrêt, comme le montre la section [Rotation de la clé](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#rotate-private-key) privée ci-dessous.

## Informations à fournir {#info-to-provide}

Pour une destination serveur à serveur en `HTTP(S)` temps réel, contactez votre [!DNL Audience Manager] consultant et spécifiez :

* Clé utilisée pour signer la demande.
* Nom de l’ `HTTP(S)` en-tête qui contiendra la signature générée (X-Signature dans l’exemple d’en-tête ci-dessous).
* Facultatif : type de hachage utilisé pour la signature (md5, sha1, sha256).

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

1. [!UICONTROL IRIS] crée le `HTTP(S)` message à envoyer au partenaire.
1. [!UICONTROL IRIS] crée une signature basée sur le `HTTP(S)` message et la clé privée communiqué par le partenaire.
1. [!UICONTROL IRIS] envoie la `HTTP(S)` demande au partenaire. Ce message contient la signature et le message réel, comme indiqué dans l’exemple ci-dessus.
1. Le serveur partenaire reçoit la `HTTP(S)` demande. Il lit le corps du message et la signature reçue de [!UICONTROL IRIS].
1. En fonction du corps du message reçu et de la clé privée, le serveur partenaire recalcule la signature. Consultez la section [Comment calculer la signature](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#calculate-signature) juste ci-dessous pour savoir comment y parvenir.
1. Comparez la signature créée sur le serveur partenaire (destinataire) à celle reçue de [!UICONTROL IRIS] (expéditeur).
1. Si les signatures correspondent, l’ **authenticité** et l’intégrité **des** messages ont été validées. Seul l’expéditeur, qui possède la clé privée, peut envoyer une signature valide (authenticité). De plus, un homme au milieu ne peut pas modifier le message et générer une nouvelle signature valide, puisqu&#39;il n&#39;a pas la clé privée (intégrité du message).

![](assets/iris-digitally-sign-http-request.png)

## Comment calculer la signature {#calculate-signature}

[!DNL HMAC] (Code d’authentification de message basé sur le hachage) est la méthode utilisée [!UICONTROL IRIS] pour la signature de message. Les implémentations et les bibliothèques sont disponibles dans tous les langages de programmation. [!DNL HMAC] n&#39;a pas d&#39;attaques d&#39;extension connues. Reportez-vous à un exemple [!DNL Java] ci-dessous :

```
// Message to be signed.
// For GET type HTTP(S) destinations, the message used for signing will be the REQUEST_PATH + QUERY_STRING
// For POST type HTTP(S) destinations, the message used for signing will be the REQUEST_BODY.
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

La RFC pour l’implémentation du [!DNL HMAC] hachage est [https://www.ietf.org/rfc/rfc2104.txt](https://www.ietf.org/rfc/rfc2104.txt). Un site de test : [https://asecuritysite.com/encryption/hmac](https://asecuritysite.com/encryption/hmac) (notez que vous devez [convertir](https://tomeko.net/online_tools/hex_to_base64.php?lang=en) l’encodage hexadécimal en base64).

## Rotation de la clé privée {#rotate-private-key}

Pour des raisons de sécurité, il est recommandé de faire pivoter périodiquement la clé privée. C&#39;est à vous de décider de la clé privée et de la période de rotation. Afin d’atteindre la rotation de clés avec un temps d’inactivité nul, [!UICONTROL IRIS] prend en charge l’ajout de plusieurs en-têtes de signature. Un en-tête contient la signature générée avec l’ancienne clé, un autre contient la signature générée à l’aide de la nouvelle clé privée. Reportez-vous aux étapes détaillées ci-dessous :

1. Le partenaire communique la nouvelle clé privée à [!DNL Adobe Audience Manager].
1. L’ancienne clé est supprimée [!DNL Audience Manager] et [!UICONTROL IRIS] envoie uniquement le nouvel en-tête de signature. Les clés ont été tournées.

## Données utilisées pour la signature {#data-signing}

Pour les destinations de `GET` type, le message utilisé pour la signature sera la chaîne *de REQUÊTE* REQUEST_PATH +  (ex. */from-aam-s2s?sids=1,2,3*). IRIS ne prend pas en compte le nom d&#39;hôte ou les `HTTP(S)` en-têtes - ceux-ci peuvent être modifiés/mal configurés le long du chemin d&#39;accès ou signalés de manière incorrecte.

Pour les destinations `POST` de type, le message utilisé pour la signature est le *CORPS* DE REQUÊTE. Là encore, les en-têtes ou les autres paramètres de requête sont ignorés.
