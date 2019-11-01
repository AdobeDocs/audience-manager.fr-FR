---
description: Pour plus d’informations sur la façon de demander une réponse DCS dans un appel /event, consultez la section suivante. Cette section comprend un exemple de réponse et des définitions pour les éléments de données courants dans une réponse.
seo-description: Pour plus d’informations sur la façon de demander une réponse DCS dans un appel /event, consultez la section suivante. Cette section comprend un exemple de réponse et des définitions pour les éléments de données courants dans une réponse.
seo-title: Recevoir des données du serveur de collecte de données
solution: Audience Manager
title: Recevoir des données du serveur de collecte de données
uuid: fbb77197-8530-48a8-b708-d785f7214494
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Recevoir des données du serveur de collecte de données {#receive-data-from-the-dcs}

Pour plus d'informations sur la façon de demander une [!UICONTROL DCS] réponse dans un `/event` appel, consultez la section. Cette section comprend un exemple de réponse et des définitions pour les éléments de données courants dans une réponse.

Avant de consulter ce contenu, voir [Envoyer des données au serveur de collecte de données](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md).

## Paramètres de réponse DCS : Une révision {#dcs-response-parameters}

Votre [!UICONTROL DCS] requête doit inclure `d_rtbd=json` si vous souhaitez recevoir une réponse de la [!UICONTROL DCS]. L’opérateur ne [!UICONTROL DCS] renvoie aucune donnée si vous omettez ce paramètre. Un appel de base à [!UICONTROL DCS] demander des données utilise la syntaxe suivante :

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

## Exemple de réponse {#sample-response}

Rappelez-vous que depuis la documentation [Send Data to DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md) , la société fictive [!DNL Acme, Inc.] a passé cet appel :

`https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback`

Comme cet appel inclut le paramètre de réponse requis, l’ [!UICONTROL DCS] objet [!DNL JSON] renvoyé est illustré ci-dessous. Le vôtre peut être similaire ou plus complexe.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## Paramètres de réponse {#response-parameters}

Le tableau ci-dessous répertorie et définit les paramètres les plus courants que vous pouvez voir dans une réponse de la [!UICONTROL DCS]. Cela s’applique aux appels d’événement ou à d’autres [!UICONTROL DCS] requêtes [!DNL API] qui renvoient des données.

| Paramètre | Description |
|--- |--- |
| `c` | URL définie comme destination [de l’](../../../features/destinations/create-url-destination.md)URL. |
| `cn` | Nom ou ID défini dans le champ Nom du cookie d’une destination [de](../../../features/destinations/create-cookie-destination.md)cookie. |
| `cv` | Valeurs envoyées à la destination définie par le paramètre "cn":" nom de destination. |
| `dcs_region` | Appels [DCS](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md)serveur à serveur. |
| `dests` | Cet objet contient des informations pour toutes les destinations URL configurées dans l’interface utilisateur. La liste de cet objet est dynamique en fonction des actions de l’utilisateur. |
| `dmn` | Domaine spécifié dans le champ Domaine du cookie pour une destination de cookie. Voir Paramètres [facultatifs pour les destinations](../../../features/destinations/cookie-destination-options.md)des cookies.  Pour les intégrations serveur à serveur, nous vous recommandons d’utiliser un domaine comme `aam-api.com`. |
| `e` | URL sécurisée définie dans une destination d’URL. |
| `stuff` | Cet objet contient des informations pour toutes les destinations de cookie. La liste de cet objet est dynamique en fonction des actions de l’utilisateur. |
| `tid` | ID de transaction, qui est un identifiant unique de 12 caractères utilisé à des fins de débogage. Chaque appel /event au serveur de collecte de données reçoit une notification à laquelle vous pouvez faire référence dans les demandes d’assistance pour obtenir une réponse plus rapide et plus efficace. |
| `ttl` | Valeur du temps de vie du cookie en jours. |
| `u` et `uuid` | ID utilisateur unique attribué par Audience Manager. Ceci est nécessaire si vous effectuez des appels [DCS](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md)serveur à serveur. |
| `y` | Type de destination, iFrame (`iframe`) ou image (`img`). |

>[!MORELIKETHIS]
>
>* [Préfixes et variables de valeur de clé pris en charge par le serveur de collecte de données](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)

