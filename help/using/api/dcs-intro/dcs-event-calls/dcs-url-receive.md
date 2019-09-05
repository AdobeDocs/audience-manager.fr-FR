---
description: Pour plus d'informations sur la demande d'une réponse DCS dans un appel /event, procédez comme suit. Cette section comprend un exemple de réponse et des définitions pour les éléments de données courants dans une réponse.
seo-description: Pour plus d'informations sur la demande d'une réponse DCS dans un appel /event, procédez comme suit. Cette section comprend un exemple de réponse et des définitions pour les éléments de données courants dans une réponse.
seo-title: Réception de données du serveur de collecte de données
solution: Audience Manager
title: Réception de données du serveur de collecte de données
uuid: fbb 77197-8530-48 a 8-b 708-d 785 f 7214494
translation-type: tm+mt
source-git-commit: bc2a9364b771436fe0191f9d69a8c291563f9229

---


# Réception de données du serveur de collecte de données {#receive-data-from-the-dcs}

Pour plus d'informations sur la demande d' [!UICONTROL DCS] une réponse dans `/event` un appel, procédez comme suit. Cette section comprend un exemple de réponse et des définitions pour les éléments de données courants dans une réponse.

Avant de consulter ce contenu, reportez-vous à [la section Envoi de données au serveur de collecte de données](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md).

## Paramètres de réponse DCS : Révision {#dcs-response-parameters}

Votre [!UICONTROL DCS] demande doit inclure `d_rtbd=json` si vous souhaitez recevoir une réponse de [!UICONTROL DCS]la part de. Le [!UICONTROL DCS] paramètre ne renvoie aucune donnée si vous omettez ce paramètre. Un appel de base aux [!UICONTROL DCS] données de demande utilise cette syntaxe :

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

## Exemple de réponse {#sample-response}

Rappelez-vous que, dans la documentation [Envoyer les données vers DCS,](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md) la société fictive [!DNL Acme, Inc.] a effectué cet appel :

`https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback`

Comme cet appel inclut le paramètre de réponse requis, le [!UICONTROL DCS] retour de [!DNL JSON] l'objet illustré ci-dessous est renvoyé. La vôtre peut être similaire ou plus complexe.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## Paramètres de réponse {#response-parameters}

Le tableau ci-dessous répertorie et définit les paramètres les plus courants que [!UICONTROL DCS]vous pouvez voir dans une réponse. Cela s'applique aux appels d'événement ou aux autres [!UICONTROL DCS][!DNL API] requêtes renvoyant des données.

| Paramètre | Description |
|--- |--- |
| `c` | URL qui a été définie comme destination [d'URL](../../../features/destinations/create-url-destination.md). |
| `cn` | Nom ou identifiant défini dans le champ Nom du cookie d'une destination [de cookie](../../../features/destinations/create-cookie-destination.md). |
| `cv` | Valeurs envoyées à la destination définie par le « cn » : « destinaton name ». |
| `dcs_region` | Appels DCS [serveur à serveur](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md). |
| `dests` | Cet objet contient des informations pour toutes les destinations URL configurées dans l'interface utilisateur. La liste de cet objet est dynamique en fonction des actions de l'utilisateur. |
| `dmn` | Il s'agit du domaine spécifié dans le champ Domaine du cookie pour une destination de cookie. Voir [Paramètres facultatifs pour les destinations de cookie](../../../features/destinations/cookie-destination-options.md). Pour les intégrations Serveur/Serveur, nous recommandons d'utiliser un domaine comme `aam-api.com`. |
| `e` | URL sécurisée qui a été définie dans une destination d'URL. |
| `stuff` | Cet objet contient des informations pour toutes les destinations de cookie. La liste de cet objet est dynamique en fonction des actions de l'utilisateur. |
| `tid` | ID de transaction, identifiant de 12 caractères unique utilisé pour le débogage. Chaque /event appel au serveur de collecte de données reçoit un tid que vous pouvez référencer dans les demandes de support pour une réponse plus rapide et plus rapide. |
| `ttl` | Valeur de durée de vie du cookie en jours. |
| `u` et `uuid` | Utilisateur unique - id attribué par Audience Manager. Cela est nécessaire si vous effectuez [des appels](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md)serveur à serveur. |
| `y` | Type de destination, iframe (`iframe`) ou image (`img`). |

>[!MORE_ LIKE_ THIS]
>
>* [Préfixes de valeurs clés et variables prises en charge par le serveur de collecte de données](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)

