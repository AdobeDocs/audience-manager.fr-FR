---
description: Lors de la publication de segments vers la destination du partenaire via une intégration serveur à serveur, Audience Manager peut être configuré pour s'authentifier à l'aide d'oauth 2.0 lors de la création des requêtes. Ceci permet de délivrer des requêtes authentifiées d'Audience Manager vers votre endpoint de fin.
seo-description: Lors de la publication de segments vers la destination du partenaire via une intégration serveur à serveur, Audience Manager peut être configuré pour s'authentifier à l'aide d'oauth 2.0 lors de la création des requêtes. Ceci permet de délivrer des requêtes authentifiées d'Audience Manager vers votre endpoint de fin.
seo-title: Intégration oauth 2.0 pour Real - Temps de transfert sortant
solution: Audience Manager
title: Intégration oauth 2.0 pour Real - Temps de transfert sortant
uuid: a 39 e 370 c-b 3 bd -4 b 06-a 1 af -60 a 024 ee 7 ee 4
translation-type: tm+mt
source-git-commit: 1cc8afd25331528fd67922183b6550288b9939bc

---


# [!DNL OAuth 2.0] Intégration pour Real - Temps de transfert sortant{#oauth-integration-for-real-time-outbound-transfers}

When publishing segments to the partner destination via a realtime server-to-server integration, Audience Manager can be set up to authenticate using [!DNL OAuth 2.0] when making the requests. Ceci permet de délivrer des requêtes authentifiées d'Audience Manager vers votre endpoint de fin.

## Authentication Flow {#auth-flow}

The [!DNL Adobe Audience Manager] [OAuth 2.0](https://tools.ietf.org/html/rfc6749#section-4.4) authentication implementation is based on the Client Credentials grant flow and follows these steps:

1. Vous devez nous fournir les éléments suivants :
   * [!DNL OAuth 2.0] Point de terminaison qui génère le jeton d'authentification.
   * Informations d'identification utilisées pour générer un jeton.
1. An [!DNL Audience Manager] consultant sets up the [destination](../../../features/destinations/destinations.md) using the information you provided.
1. Once a segment is mapped to this destination, our real-time data transfer system, [IRIS](../../../reference/system-components/components-data-action.md#iris), makes a `POST` request to the token endpoint to exchange the credentials for a bearer token.
1. For each segment publishing request to the partner endpoint, [!UICONTROL IRIS] uses the bearer token to authenticate.

![](assets/oauth2-iris.png)

## Conditions requises {#auth-requirements}

As an [!DNL Audience Manager] partner, the following endpoints are needed to receive authenticated requests:

### Point de terminaison 1 utilisé par IRIS pour obtenir un jeton de porteur

Ce point de fin accepte les informations d'identification fournies à l'étape 1 et génère un jeton porteur qui sera utilisé lors des demandes suivantes.

* The endpoint must accept `HTTP POST` requests.
* The endpoint must accept and look at the [!DNL Authorization] header. The value for this header will be: `Basic <credentials_provided_by_partner>`.
* The endpoint must look at the [!DNL Content-type] header and validate that its value is `application/x-www-form-urlencoded ; charset=UTF-8`.
* The body of the request will be `grant_type=client_credentials`.

### Exemple de requête effectuée par Audience Manager au endpoint de fin du partenaire pour obtenir un jeton porteur

```
POST /oauth2/token HTTP/1.1
Host: api.partner.com
User-Agent: Adobe Audience Manager Iris
Authorization: Basic zq2LOO1CcYGrODS5nXiNHpEz97eCpVHAoMF8pAgCntXAzxp5uRV7DTAE2qtPLjhMQwrEX3O6MHV4S
Content-Type: application/x-www-form-urlencoded;charset=UTF-8
Content-Length: 29
Accept-Encoding: gzip
  
grant_type=client_credentials
```

### Exemple de réponse du point de fin partenaire

```
HTTP/1.1 200 OK
Status: 200 OK
Content-Type: application/json; charset=utf-8
...
Content-Encoding: gzip
Content-Length: 121
  
{"token_type":"Bearer","access_token":"glIbBVohK8d86alDEnllPWi6IpjZvJC6kwBRuuawts6YMkw4tZkt84rEZYU2ZKHCQP3TT7PnzCQPI0yY"}
```

### Point de terminaison 2 utilisé par IRIS pour publier des segments à l'aide du jeton porteur

[!DNL Audience Manager] envoie des données à ce point de fin en temps quasi réel, car les utilisateurs remplissent les critères des segments. De plus, cette méthode peut envoyer des lots de données hors ligne ou intégrées aussi fréquemment que toutes les 24 heures.

Le jeton porteur généré par le point de fin 1 est utilisé pour envoyer des requêtes à ce point de fin. The [!DNL Audience Manager] real-time data transfer system, [IRIS](../../../reference/system-components/components-data-action.md#iris), constructs a normal HTTPS request and includes an Authorization header. The value for this header will be: Bearer `<bearer token from step 1>`.

### Exemple de réponse du point de fin partenaire

```
GET /segments/aam HTTP/1.1
Host: api.partner.com
User-Agent: Adobe Audience Manager Iris
Authorization: Bearer glIbBVohK8d86alDEnllPWi6IpjZvJC6kwBRuuawts6YMkw4tZkt84rEZYU2ZKHCQP3TT7PnzCQPI0yY
Content-Type: application/json
Accept-Encoding: gzip
   
{
"ProcessTime": "Wed Jul 27 16:17:42 UTC 2016",
"User_DPID": "12345",
"Client_ID": "74323",
"AAM_Destination_Id": "423",
"User_count": "2",
"Users": [{
   "AAM_UUID": "19393572368547369350319949416899715727",
   "DataPartner_UUID": "4250948725049857",
   "Segments": [{
            "Segment_ID": "14356",
            "Status": "1",
            "DateTime": "Wed Jul 27 16:17:22 UTC 2016"
         }
      ]
   }]
}
```

>[!NOTE]
>
>Cette demande contient une charge utile standard (contenu de demande).

## Important Considerations {#considerations}

### Les jetons sont des mots de passe

The credentials presented by the partner and the tokens obtained by [!DNL Audience Manager] when authenticating using the [!DNL OAuth 2.0] flow, are sensitive information and must not be shared with third parties.

### [!DNL SSL] est requis

[!DNL SSL] doit être utilisé pour assurer un processus d'authentification sécurisé. All requests, including the ones used to obtain and use the tokens must use `HTTPS` endpoints.