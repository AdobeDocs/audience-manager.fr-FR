---
description: Pour plus d’informations sur la manière de demander une réponse DCS dans un appel /event, voir la page suivante. Cette section comprend un exemple de réponse et des définitions des éléments de données courants dans une réponse.
seo-description: Pour plus d’informations sur la manière de demander une réponse DCS dans un appel /event, voir la page suivante. Cette section comprend un exemple de réponse et des définitions des éléments de données courants dans une réponse.
seo-title: Réception de données du DCS
solution: Audience Manager
title: Réception de données du DCS
uuid: fbb77197-8530-48a8-b708-d785f7214494
feature: DCS
exl-id: c6a87e5a-63cc-44d7-b6f0-ac8ee845fd00
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 5%

---

# Réception de données du DCS {#receive-data-from-the-dcs}

Continuez ici pour plus d’informations sur la manière de demander une réponse [!DNL DCS] dans un appel `/event`. Cette section comprend un exemple de réponse et des définitions des éléments de données courants dans une réponse.

Avant de passer en revue ce contenu, voir [Envoi de données au DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md).

## Paramètres de réponse DCS : Une révision {#dcs-response-parameters}

Votre requête [!DNL DCS] doit inclure `d_rtbd=json` si vous souhaitez recevoir une réponse de [!DNL DCS]. [!DNL DCS] ne renvoie pas de données si vous omettez ce paramètre. Un appel de base à [!DNL DCS] pour demander des données utilise la syntaxe suivante :

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

## Exemple de réponse {#sample-response}

Rappelez-vous que dans la documentation [Envoyer les données au DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md), la société fictive [!DNL Acme, Inc.] a effectué cet appel :

`https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback`

Comme cet appel inclut le paramètre de réponse requis, le [!DNL DCS] renvoyé l’objet [!DNL JSON] illustré ci-dessous. Les vôtres peuvent être similaires ou plus complexes.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## Paramètres de réponse {#response-parameters}

Le tableau ci-dessous répertorie et définit les paramètres les plus courants que vous pouvez voir dans une réponse de [!DNL DCS]. Cela s’applique aux appels d’événement ou à d’autres requêtes [!DNL DCS] [!DNL API] qui renvoient des données.

| Paramètre | Description |
|--- |--- |
| `c` | URL définie comme destination [URL](../../../features/destinations/create-url-destination.md). |
| `cn` | Nom ou ID défini dans le champ nom du cookie d’une [destination du cookie](../../../features/destinations/create-cookie-destination.md). |
| `cv` | Les valeurs envoyées à la destination définie par le paramètre &quot;cn&quot;:&quot; nom de destination. |
| `dcs_region` | Les [appels DCS serveur à serveur](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md). |
| `dests` | Cet objet contient des informations pour toutes les destinations d’URL configurées dans l’interface utilisateur. La liste de cet objet est dynamique en fonction des actions de l’utilisateur. |
| `dmn` | Il s’agit du domaine spécifié dans le champ Domaine du cookie pour une destination de cookie. Voir [Paramètres facultatifs pour les destinations de cookie](../../../features/destinations/cookie-destination-options.md).  Pour les intégrations Serveur à Serveur , nous vous recommandons d’utiliser un domaine du type `aam-api.com`. |
| `e` | URL sécurisée qui a été définie dans une destination d’URL. |
| `stuff` | Cet objet contient des informations pour toutes les destinations de cookie. La liste de cet objet est dynamique en fonction des actions de l’utilisateur. |
| `tid` | ID de transaction, qui est un identifiant unique de 12 caractères utilisé à des fins de débogage. Chaque appel /event au serveur de collecte de données reçoit une demande que vous pouvez référencer dans les demandes d’assistance pour une réponse plus rapide et plus efficace. |
| `ttl` | Valeur de durée de vie du cookie en jours. |
| `u` et `uuid` | Identifiant utilisateur unique attribué par Audience Manager. Cela est requis si vous effectuez des [appels DCS serveur à serveur](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md). |
| `y` | Type de destination, iFrame (`iframe`) ou image (`img`). |

>[!MORELIKETHIS]
>
>* [Préfixes et variables clé-valeur pris en charge par le serveur de collecte de données](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)

