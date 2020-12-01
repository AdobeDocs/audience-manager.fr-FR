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

Lors de la publication de segments vers la destination partenaire via une intégration serveur à serveur en temps réel, l’Audience Manager peut être configurée pour s’authentifier à l’aide de [!DNL OAuth 2.0] lors de l’exécution des requêtes. Cela permet d’émettre des requêtes authentifiées d’Audience Manager en point de terminaison.

## Flux d’authentification {#auth-flow}

L&#39;implémentation de l&#39;authentification [!DNL Adobe Audience Manager] [OAuth 2.0](https://tools.ietf.org/html/rfc6749#section-4.4) est basée sur le flux d&#39;octroi des informations d&#39;identification client et suit les étapes suivantes :

1. Vous devez nous fournir :
   * Point de terminaison [!DNL OAuth 2.0] qui génère le jeton d’authentification.
   * Informations d’identification utilisées pour générer un jeton.
1. Un consultant [!DNL Audience Manager] configure la [destination](../../../features/destinations/destinations.md) à l&#39;aide des informations que vous avez fournies.
1. Une fois qu’un segment est mappé à cette destination, notre système de transfert de données en temps réel, [IRIS](../../../reference/system-components/components-data-action.md#iris), envoie une requête `POST` au point de terminaison du jeton pour échanger les informations d’identification pour un jeton porteur.
1. Pour chaque demande de publication de segment au point de terminaison partenaire, [!UICONTROL IRIS] utilise le jeton porteur pour l’authentification.

![](assets/oauth2-iris.png)

## Exigences {#auth-requirements}

En tant que partenaire [!DNL Audience Manager], les points de terminaison suivants sont nécessaires pour recevoir des demandes authentifiées :

### Point de terminaison 1 utilisé par IRIS pour obtenir un jeton porteur

Ce point de terminaison accepte les informations d’identification fournies à l’étape 1 et génère un jeton porteur qui sera utilisé pour les demandes ultérieures.

* Le point de terminaison doit accepter les demandes `HTTP POST`.
* Le point de terminaison doit accepter et consulter l&#39;en-tête [!DNL Authorization]. La valeur de cet en-tête sera : `Basic <credentials_provided_by_partner>`.
* Le point de terminaison doit examiner l&#39;en-tête [!DNL Content-type] et vérifier que sa valeur est `application/x-www-form-urlencoded ; charset=UTF-8`.
* Le corps de la requête sera `grant_type=client_credentials`.

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

Le jeton porteur généré par le point de terminaison 1 est utilisé pour envoyer des requêtes à ce point de terminaison. Le [!DNL Audience Manager] système de transfert de données en temps réel, [IRIS](../../../reference/system-components/components-data-action.md#iris), construit une requête HTTPS normale et inclut un en-tête Autorisation. La valeur de cet en-tête sera : Porteur `<bearer token from step 1>`.

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

Les informations d&#39;identification présentées par le partenaire et les jetons obtenus par [!DNL Audience Manager] lors de l&#39;authentification à l&#39;aide du flux [!DNL OAuth 2.0] sont des informations sensibles et ne doivent pas être partagées avec des tiers.

### [!DNL SSL] est requis

[!DNL SSL] doit être utilisé pour maintenir un processus d&#39;authentification sécurisé. Toutes les requêtes, y compris celles utilisées pour obtenir et utiliser les jetons, doivent utiliser des points de terminaison `HTTPS`.