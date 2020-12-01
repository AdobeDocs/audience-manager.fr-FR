---
description: Pour plus d'informations sur la façon de demander une réponse DCS dans un appel /événement, consultez la section. Cette section comprend un exemple de réponse et des définitions pour les éléments de données courants dans une réponse.
seo-description: Pour plus d'informations sur la façon de demander une réponse DCS dans un appel /événement, consultez la section. Cette section comprend un exemple de réponse et des définitions pour les éléments de données courants dans une réponse.
seo-title: Réception de données du DCS
solution: Audience Manager
title: Réception de données du DCS
uuid: fbb77197-8530-48a8-b708-d785f7214494
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 5%

---


# Réception de données du DCS {#receive-data-from-the-dcs}

Pour plus d&#39;informations sur la façon de demander une réponse [!DNL DCS] dans un appel `/event`, reportez-vous à la section suivante. Cette section comprend un exemple de réponse et des définitions pour les éléments de données courants dans une réponse.

Avant de passer en revue ce contenu, voir [Envoyer des données au serveur de collecte de données](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md).

## Paramètres de réponse DCS : Une révision {#dcs-response-parameters}

Votre demande [!DNL DCS] doit inclure `d_rtbd=json` si vous souhaitez recevoir une réponse de la part de [!DNL DCS]. [!DNL DCS] ne renvoie pas de données si vous omettez ce paramètre. Un appel de base à [!DNL DCS] pour demander des données utilise la syntaxe suivante :

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

## Exemple de réponse {#sample-response}

Rappelez-vous que dans la documentation [Envoyer des données au serveur de collecte de données](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md), la société fictive [!DNL Acme, Inc.] a effectué cet appel :

`https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback`

Comme cet appel inclut le paramètre de réponse requis, l&#39;[!DNL DCS] a renvoyé l&#39;objet [!DNL JSON] illustré ci-dessous. Les vôtres peuvent être semblables ou plus complexes.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## Paramètres de réponse {#response-parameters}

Le tableau ci-dessous liste et définit les paramètres les plus courants que vous pouvez voir dans une réponse de [!DNL DCS]. Cela s&#39;applique aux appels de événement ou à d&#39;autres requêtes [!DNL DCS] [!DNL API] qui renvoient des données.

| Paramètre | Description |
|--- |--- |
| `c` | URL définie comme destination [URL](../../../features/destinations/create-url-destination.md). |
| `cn` | Nom ou ID défini dans le champ Nom du cookie d’une destination de cookie [](../../../features/destinations/create-cookie-destination.md). |
| `cv` | Les valeurs envoyées à la destination définie par le paramètre &quot;cn&quot;:&quot; nom de destination. |
| `dcs_region` | Appels [serveur-serveur DCS](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md). |
| `dests` | Cet objet contient des informations pour toutes les destinations URL configurées dans l’interface utilisateur. La liste de cet objet est dynamique en fonction des actions de l’utilisateur. |
| `dmn` | Il s’agit du domaine spécifié dans le champ Domaine du cookie pour une destination de cookie. Voir [Paramètres facultatifs pour les destinations de cookies](../../../features/destinations/cookie-destination-options.md).  Pour les intégrations de serveur à serveur, nous vous recommandons d’utiliser un domaine tel que `aam-api.com`. |
| `e` | URL sécurisée définie dans une destination d’URL. |
| `stuff` | Cet objet contient des informations pour toutes les destinations de cookie. La liste de cet objet est dynamique en fonction des actions de l’utilisateur. |
| `tid` | ID de transaction, qui est un identifiant unique de 12 caractères utilisé à des fins de débogage. Chaque appel /événement au serveur de collecte de données reçoit un appel que vous pouvez référencer dans les demandes d&#39;assistance pour obtenir une réponse plus rapide et plus efficace. |
| `ttl` | Valeur de durée de vie du cookie en jours. |
| `u` et `uuid` | ID utilisateur unique attribué par Audience Manager. Ceci est nécessaire si vous effectuez des appels DCS [serveur à serveur ](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md). |
| `y` | Type de destination, iFrame (`iframe`) ou image (`img`). |

>[!MORELIKETHIS]
>
>* [Préfixes et variables de valeur de clé pris en charge par le serveur de collecte de données](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)

