---
description: Pour plus d'informations sur la demande d'une réponse DCS dans un appel /event, procédez comme suit. Cette section comprend un exemple de réponse et des définitions pour les éléments de données courants dans une réponse.
seo-description: Pour plus d'informations sur la demande d'une réponse DCS dans un appel /event, procédez comme suit. Cette section comprend un exemple de réponse et des définitions pour les éléments de données courants dans une réponse.
seo-title: Réception de données du serveur de collecte de données
solution: Audience Manager
title: Réception de données du serveur de collecte de données
uuid: fbb 77197-8530-48 a 8-b 708-d 785 f 7214494
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Receive Data From the DCS {#receive-data-from-the-dcs}

Continue here for information about how to request a [!UICONTROL DCS] response in a `/event` call. Cette section comprend un exemple de réponse et des définitions pour les éléments de données courants dans une réponse.

Before reviewing this content, see [Send Data to the DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md).

## DCS Response Parameters: A Review {#dcs-response-parameters}

Your [!UICONTROL DCS] request must include `d_rtbd=json` if you want to receive a response from the [!UICONTROL DCS]. The [!UICONTROL DCS] will not return data if you omit this parameter. A basic call to the [!UICONTROL DCS] to request data uses this syntax:

<pre><code>https://domain alias.demdex.net/event<i></i>?<i>key 1</i>= <i>val 1</i>, &amp;<i>key 2</i>= <i>val 2</i>&amp; d_ dst = 1 &amp; d_ rtbd = json &amp; d_ cb =<i>callback</i></code>
</pre>

## Exemple de réponse {#sample-response}

Recall that from the [Send Data to the DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md) documentation, the fictional company [!DNL Acme, Inc.] made this call:

`https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback`

As this call includes the required response parameter, the [!UICONTROL DCS] sent back the [!DNL JSON] object shown below. La vôtre peut être similaire ou plus complexe.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## Paramètres de réponse {#response-parameters}

The table below lists and defines the more common parameters you may see in a response from the [!UICONTROL DCS]. This applies to event calls or other [!UICONTROL DCS] [!DNL API] queries that return data.

| Paramètre | Description |
|--- |--- |
| `c` | A URL that has been set as a [URL destination](../../../features/destinations/manage-destinations.md#configure-url-destination). |
| `cn` | The name or ID set in the cookie name field of a [cookie destination](../../../features/destinations/manage-destinations.md#create-cookie-destination). |
| `cv` | Valeurs envoyées à la destination définie par le « cn » : « destinaton name ». |
| `dcs_region` | The [server-to-server DCS calls](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md). |
| `dests` | Cet objet contient des informations pour toutes les destinations URL configurées dans l'interface utilisateur. La liste de cet objet est dynamique en fonction des actions de l'utilisateur. |
| `dmn` | Il s'agit du domaine spécifié dans le champ Domaine du cookie pour une destination de cookie. See [Optional Settings for Cookie Destinations](../../../features/destinations/manage-destinations.md#optional-settings-cookies).  For  Server to Server integrations we recommend using a domain like `aam-api.com`. |
| `e` | URL sécurisée qui a été définie dans une destination d'URL. |
| `stuff` | Cet objet contient des informations pour toutes les destinations de cookie. La liste de cet objet est dynamique en fonction des actions de l'utilisateur. |
| `tid` | ID de transaction, identifiant de 12 caractères unique utilisé pour le débogage. Chaque /event appel au serveur de collecte de données reçoit un tid que vous pouvez référencer dans les demandes de support pour une réponse plus rapide et plus rapide. |
| `ttl` | Valeur de durée de vie du cookie en jours. |
| `u` et `uuid` | Utilisateur unique - id attribué par Audience Manager. This is required if you're making [server-to-server DCS calls](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md). |
| `y` | Destination type,  iFrame (`iframe`) or image (`img`). |

>[!MORE_ LIKE_ THIS]
>
>* [Préfixes de valeurs clés et variables prises en charge par le serveur de collecte de données](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)

