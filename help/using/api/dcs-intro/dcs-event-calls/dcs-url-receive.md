---
description: Continuez ici pour plus d’informations sur la manière de demander une réponse DCS dans un appel /event. Cette section comprend un exemple de réponse et des définitions pour les éléments de données courants d’une réponse.
seo-description: Continue here for information about how to request a DCS response in a /event call. This section includes a response example and definitions for common data elements in a response.
seo-title: Receive Data From the DCS
solution: Audience Manager
title: Recevoir des données du serveur de collecte de données
uuid: fbb77197-8530-48a8-b708-d785f7214494
feature: DCS
exl-id: c6a87e5a-63cc-44d7-b6f0-ac8ee845fd00
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 1%

---

# Recevoir des données du serveur de collecte de données {#receive-data-from-the-dcs}

Continuez ici pour plus d’informations sur la manière de demander une réponse [!DNL DCS] dans un appel `/event`. Cette section comprend un exemple de réponse et des définitions pour les éléments de données courants d’une réponse.

Avant de passer en revue ce contenu, voir [Envoi de données au serveur de collecte de données](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md).

## Paramètres de réponse DCS : examen {#dcs-response-parameters}

Votre demande de [!DNL DCS] doit inclure `d_rtbd=json` si vous souhaitez recevoir une réponse de la [!DNL DCS]. L’[!DNL DCS] ne renvoie pas de données si vous omettez ce paramètre. Un appel de base au [!DNL DCS] pour demander des données utilise la syntaxe suivante :

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

## Exemple de réponse {#sample-response}

Rappelez-vous que dans la documentation [Envoyer les données au serveur de collecte de données](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md), l’entreprise fictive [!DNL Acme, Inc.] a effectué cet appel :

`https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback`

Comme cet appel inclut le paramètre de réponse obligatoire, l’[!DNL DCS] a renvoyé l’objet [!DNL JSON] illustré ci-dessous. La vôtre peut être similaire ou plus complexe.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## Paramètres de réponse {#response-parameters}

Le tableau ci-dessous répertorie et définit les paramètres les plus courants que vous pouvez voir dans une réponse du [!DNL DCS]. Cela s’applique aux appels d’événement ou à d’autres requêtes [!DNL DCS] [!DNL API] qui renvoient des données.

| Paramètre | Description |
|--- |--- |
| `c` | Une URL qui a été définie comme [destination URL](../../../features/destinations/create-url-destination.md). |
| `cn` | Nom ou ID défini dans le champ nom du cookie d’une [ destination de cookie ](../../../features/destinations/create-cookie-destination.md). |
| `cv` | Les valeurs envoyées à la destination définie par le paramètre « cn »:« nom de destination ». |
| `dcs_region` | Les [appels DCS serveur à serveur](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md). |
| `dests` | Cet objet contient des informations pour toutes les destinations d’URL configurées dans l’interface utilisateur. La liste de cet objet est dynamique en fonction des actions de l’utilisateur. |
| `dmn` | Il s’agit du domaine spécifié dans le champ Domaine du cookie pour une destination de cookie. Voir [Paramètres facultatifs pour les destinations de cookie](../../../features/destinations/cookie-destination-options.md).  Pour les intégrations serveur à serveur, il est recommandé d’utiliser un domaine tel que `aam-api.com`. |
| `e` | L’URL sécurisée qui a été définie dans une destination URL. |
| `stuff` | Cet objet contient des informations pour toutes les destinations de cookie. La liste de cet objet est dynamique en fonction des actions de l’utilisateur. |
| `tid` | Identifiant de transaction, qui est un identifiant unique de 12 caractères utilisé à des fins de débogage. Chaque appel /event au serveur de collecte de données reçoit un tid que vous pouvez référencer dans les demandes d’assistance pour une réponse meilleure et plus rapide. |
| `ttl` | Valeur de durée de vie du cookie en jours. |
| `u` et `uuid` | ID d’utilisateur unique attribué par Audience Manager. Cela est nécessaire si vous effectuez des [appels DCS serveur à serveur](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md). |
| `y` | Type de destination, iFrame (`iframe`) ou image (`img`). |

>[!MORELIKETHIS]
>
>* [Préfixes et variables clé-valeur pris en charge par le serveur de collecte de données](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)
