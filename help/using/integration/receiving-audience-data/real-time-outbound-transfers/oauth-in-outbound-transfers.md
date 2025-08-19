---
description: Lors de la publication de segments vers la destination partenaire via une intégration serveur à serveur en temps réel, Audience Manager peut être configuré pour s’authentifier à l’aide d’OAuth 2.0 lors de l’exécution des requêtes. Cela permet d’émettre des requêtes authentifiées d’Audience Manager vers votre point d’entrée.
seo-description: When publishing segments to the partner destination via a realtime server-to-server integration, Audience Manager can be set up to authenticate using OAuth 2.0 when making the requests. This presents the ability to issue authenticated requests from Audience Manager to your endpoint.
seo-title: OAuth 2.0 Integration for Real-Time Outbound Transfers
solution: Audience Manager
title: Intégration OAuth 2.0 pour les transferts sortants en temps réel
uuid: a39e370c-b3bd-4b06-a1af-60a024ee7ee4
feature: Outbound Data Transfers
exl-id: eef3a3ae-1a3f-47e9-aab6-abf878e4cb77
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '450'
ht-degree: 0%

---

# Intégration [!DNL OAuth 2.0] pour les transferts sortants en temps réel{#oauth-integration-for-real-time-outbound-transfers}

Lors de la publication de segments vers la destination partenaire via une intégration serveur à serveur en temps réel, Audience Manager peut être configuré pour s’authentifier à l’aide de [!DNL OAuth 2.0] lors de l’exécution des requêtes. Cela permet d’émettre des requêtes authentifiées d’Audience Manager vers votre point d’entrée.

## Flux d’authentification {#auth-flow}

L’implémentation de l’authentification [!DNL Adobe Audience Manager] [OAuth 2.0](https://tools.ietf.org/html/rfc6749#section-4.4) repose sur le flux d’octroi des informations d’identification client et suit les étapes suivantes :

1. Vous devez nous fournir :
   * Point d’entrée [!DNL OAuth 2.0] qui génère le jeton d’authentification.
   * Informations d’identification utilisées pour générer un jeton.
1. Un consultant [!DNL Audience Manager] configure la [destination](../../../features/destinations/destinations.md) à l’aide des informations que vous avez fournies.
1. Une fois qu’un segment est mappé à cette destination, notre système de transfert de données en temps réel, [IRIS](../../../reference/system-components/components-data-action.md#iris), effectue une requête `POST` au point d’entrée du jeton pour échanger les informations d’identification contre un jeton porteur.
1. Pour chaque requête de publication de segment vers le point d’entrée du partenaire, [!UICONTROL IRIS] utilise le jeton porteur pour l’authentification.

![](assets/oauth2-iris.png)

## Exigences {#auth-requirements}

En tant que partenaire [!DNL Audience Manager], les points d’entrée suivants sont nécessaires pour recevoir des requêtes authentifiées :

### Point d&#39;entrée 1 utilisé par IRIS pour obtenir un jeton porteur

Ce point d’entrée accepte les informations d’identification fournies à l’étape 1 et génère un jeton porteur qui sera utilisé lors des requêtes suivantes.

* Le point d’entrée doit accepter les requêtes `HTTP POST`.
* Le point d’entrée doit accepter et examiner l’en-tête [!DNL Authorization]. La valeur de cet en-tête sera : `Basic <credentials_provided_by_partner>`.
* Le point d’entrée doit examiner l’en-tête [!DNL Content-type] et vérifier que sa valeur est `application/x-www-form-urlencoded ; charset=UTF-8`.
* Le corps de la requête sera `grant_type=client_credentials`.

### Exemple de requête envoyée par Audience Manager au point d’entrée du partenaire afin d’obtenir un jeton porteur

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

### Exemple de réponse à partir du point d’entrée du partenaire

```
HTTP/1.1 200 OK
Status: 200 OK
Content-Type: application/json; charset=utf-8
...
Content-Encoding: gzip
Content-Length: 121
  
{"token_type":"Bearer","access_token":"glIbBVohK8d86alDEnllPWi6IpjZvJC6kwBRuuawts6YMkw4tZkt84rEZYU2ZKHCQP3TT7PnzCQPI0yY"}
```

### Point d’entrée 2 utilisé par IRIS pour publier des segments à l’aide du jeton porteur

[!DNL Audience Manager] envoie des données à ce point d’entrée en temps quasi réel lorsque les utilisateurs remplissent les critères pour les segments. En outre, cette méthode peut envoyer des lots de données hors ligne ou intégrées aussi fréquemment que toutes les 24 heures.

Le jeton porteur généré par le point d’entrée 1 est utilisé pour envoyer des requêtes à ce point d’entrée. Le système de transfert de données en temps réel [!DNL Audience Manager], [IRIS](../../../reference/system-components/components-data-action.md#iris), crée une requête HTTPS normale et inclut un en-tête d’autorisation. La valeur de cet en-tête sera : `<bearer token from step 1>` du porteur.

### Exemple de réponse à partir du point d’entrée du partenaire

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
>Cette requête contient une payload standard (contenu de la requête).

## Points importants {#considerations}

### Les jetons sont des mots de passe

Les informations d’identification présentées par le partenaire et les jetons obtenus par [!DNL Audience Manager] lors de l’authentification à l’aide du flux [!DNL OAuth 2.0] sont des informations sensibles et ne doivent pas être partagés avec des tiers.

### [!DNL SSL] est obligatoire

[!DNL SSL] doit être utilisé afin de maintenir un processus d’authentification sécurisé. Toutes les requêtes, y compris celles utilisées pour obtenir et utiliser les jetons, doivent utiliser des points d’entrée `HTTPS`.
