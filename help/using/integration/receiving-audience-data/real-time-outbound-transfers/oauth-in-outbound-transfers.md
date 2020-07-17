---
description: Lors de la publication de segments vers la destination partenaire via une intégration serveur à serveur en temps réel, l’Audience Manager peut être configurée pour s’authentifier à l’aide d’OAuth 2.0 lors de l’exécution des requêtes. Cela permet d’émettre des requêtes authentifiées d’Audience Manager en point de terminaison.
seo-description: Lors de la publication de segments vers la destination partenaire via une intégration serveur à serveur en temps réel, l’Audience Manager peut être configurée pour s’authentifier à l’aide d’OAuth 2.0 lors de l’exécution des requêtes. Cela permet d’émettre des requêtes authentifiées d’Audience Manager en point de terminaison.
seo-title: Intégration OAuth 2.0 pour les transferts sortants en temps réel
solution: Audience Manager
title: Intégration OAuth 2.0 pour les transferts sortants en temps réel
uuid: a39e370c-b3bd-4b06-a1af-60a024ee7ee4
feature: Outbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 2%

---


# [!DNL OAuth 2.0] Intégration pour les transferts sortants en temps réel{#oauth-integration-for-real-time-outbound-transfers}

Lors de la publication de segments vers la destination partenaire via une intégration serveur à serveur en temps réel, l’Audience Manager peut être configurée pour s’authentifier à l’aide [!DNL OAuth 2.0] des requêtes. Cela permet d’émettre des requêtes authentifiées d’Audience Manager en point de terminaison.

## Flux d’authentification {#auth-flow}

L’implémentation de l’authentification [!DNL Adobe Audience Manager] OAuth 2.0 [](https://tools.ietf.org/html/rfc6749#section-4.4) repose sur le flux de subvention des informations d’identification du client et suit les étapes suivantes :

1. Vous devez nous fournir :
   * Point de [!DNL OAuth 2.0] terminaison qui génère le jeton d’authentification.
   * Informations d’identification utilisées pour générer un jeton.
1. Un [!DNL Audience Manager] consultant configure la [destination](../../../features/destinations/destinations.md) à l’aide des informations que vous avez fournies.
1. Une fois qu’un segment est mappé à cette destination, notre système de transfert de données en temps réel, [IRIS](../../../reference/system-components/components-data-action.md#iris), envoie une `POST` demande au point de terminaison du jeton pour échanger les informations d’identification pour un jeton porteur.
1. Pour chaque demande de publication de segment adressée au point de terminaison partenaire, [!UICONTROL IRIS] utilise le jeton porteur pour l’authentification.

![](assets/oauth2-iris.png)

## Exigences {#auth-requirements}

En tant que [!DNL Audience Manager] partenaire, les points de terminaison suivants sont nécessaires pour recevoir les demandes authentifiées :

### Point de terminaison 1 utilisé par IRIS pour obtenir un jeton porteur

Ce point de terminaison accepte les informations d’identification fournies à l’étape 1 et génère un jeton porteur qui sera utilisé pour les demandes ultérieures.

* Le point de terminaison doit accepter `HTTP POST` les requêtes.
* Le point de terminaison doit accepter et consulter l’en-tête. [!DNL Authorization] La valeur de cet en-tête sera : `Basic <credentials_provided_by_partner>`.
* Le point de terminaison doit examiner l’ [!DNL Content-type] en-tête et vérifier qu’il a une valeur `application/x-www-form-urlencoded ; charset=UTF-8`.
* Le corps de la demande sera `grant_type=client_credentials`indiqué.

### Exemple de demande d’Audience Manager au point de terminaison partenaire pour obtenir un jeton porteur

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

### Exemple de réponse du point de terminaison partenaire

```
HTTP/1.1 200 OK
Status: 200 OK
Content-Type: application/json; charset=utf-8
...
Content-Encoding: gzip
Content-Length: 121
  
{"token_type":"Bearer","access_token":"glIbBVohK8d86alDEnllPWi6IpjZvJC6kwBRuuawts6YMkw4tZkt84rEZYU2ZKHCQP3TT7PnzCQPI0yY"}
```

### Point de terminaison 2 utilisé par IRIS pour publier des segments à l’aide du jeton porteur

[!DNL Audience Manager] envoie des données à ce point de terminaison en temps quasi réel, car les utilisateurs remplissent les conditions requises pour les segments. De plus, cette méthode peut envoyer des lots de données hors ligne ou intégrées aussi souvent que toutes les 24 heures.

Le jeton porteur généré par le point de terminaison 1 est utilisé pour envoyer des requêtes à ce point de terminaison. Le système de transfert de données en [!DNL Audience Manager] temps réel, [IRIS](../../../reference/system-components/components-data-action.md#iris), construit une requête HTTPS normale et inclut un en-tête Autorisation. La valeur de cet en-tête sera : Porteur `<bearer token from step 1>`.

### Exemple de réponse du point de terminaison partenaire

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
>Cette requête contient une charge utile standard (contenu de la requête).

## Considérations importantes {#considerations}

### Les jetons sont des mots de passe

Les informations d’identification présentées par le partenaire et les jetons obtenus lors de [!DNL Audience Manager] [!DNL OAuth 2.0] l’authentification à l’aide du flux sont des informations sensibles et ne doivent pas être partagées avec des tiers.

### [!DNL SSL] est requis

[!DNL SSL] doit être utilisé pour maintenir un processus d&#39;authentification sécurisé. Toutes les requêtes, y compris celles utilisées pour obtenir et utiliser les jetons, doivent utiliser des `HTTPS` points de terminaison.