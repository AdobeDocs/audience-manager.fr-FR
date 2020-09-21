---
description: L’état d’authentification du visiteur dans l’Audience Manager détermine si les informations de nouvelle caractéristique sont écrites au profil authentifié du visiteur ou au profil du périphérique, à partir duquel les données ont été collectées. L’Audience Manager gère de la même manière les états d’authentification de l’ID de visiteur INCONNU et LOGGED_OUT dans les appels de événement.
keywords: dpm.demdex.net
seo-description: L’état d’authentification du visiteur dans l’Audience Manager détermine si les informations de nouvelle caractéristique sont écrites au profil authentifié du visiteur ou au profil du périphérique, à partir duquel les données ont été collectées. L’Audience Manager gère de la même manière les états d’authentification de l’ID de visiteur INCONNU et LOGGED_OUT dans les appels de événement.
seo-title: États d’authentification du visiteur dans Audience Manager
solution: Audience Manager
title: États d’authentification du visiteur dans Audience Manager
uuid: d748c0c3-5833-4fb9-ab3e-793f5f252e47
feature: reference
translation-type: tm+mt
source-git-commit: a41f0beffba686f283a2933ad7066cb124e4d380
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 5%

---


# États d’authentification du visiteur dans Audience Manager{#visitor-authentication-states-in-audience-manager}

L’état d’authentification du visiteur dans l’Audience Manager détermine si les informations de nouvelle caractéristique sont écrites au profil authentifié du visiteur ou au profil du périphérique, à partir duquel les données ont été collectées. L’Audience Manager gère de la même manière les états d’authentification de l’ID de visiteur INCONNU et LOGGED_OUT dans les appels de événement.

À partir de la version 1.5 du service [!DNL Experience Cloud] d’ID, la `setCustomerID` méthode inclut l’objet `AuthState` facultatif. `AuthState` identifie les visiteurs en fonction de leur état [d’](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html)authentification. [!DNL Audience Manager] gère différemment les caractéristiques réalisées, en fonction de l’état d’authentification transmis dans l’appel et de la règle [de fusion](../features/profile-merge-rules/merge-rules-dashboard.md) de Profil que vous utilisez pour la segmentation.

## État de l&#39;authentification : INCONNU {#auth-status-unknown}

| Valeur de requête | **Lire** les informations du profil authentifié | **Écrire** de nouvelles caractéristiques au profil authentifié |
---------|----------|---------
| 0 | <ul><li>Oui, si la règle de fusion des options authentifiées = &quot;Derniers Profils authentifiés&quot;.</li><li>Non, si la règle de fusion des options authentifiées = &quot;Profils authentifiés actuels&quot; ou &quot;Aucun Profil authentifié&quot;.</li></ul> | Non, les données de caractéristiques sont ajoutées au profil du périphérique. |


Exemple d’appel (la valeur de requête correspondant à l’état d’authentification est mise en surbrillance) :

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%010&d_sid=123456`

## État de l&#39;authentification : AUTHENTIFIÉ {#auth-status-authenticated}

| Valeur de requête | **Lire** les informations du profil authentifié | **Écrire** de nouvelles caractéristiques au profil authentifié |
---------|----------|---------
| 1 | <ul><li>Oui, si la règle de fusion des options authentifiées = &quot;Profils authentifiés actuels&quot; ou &quot;Derniers Profils authentifiés&quot;.</li><li>Non, si la règle de fusion des options authentifiées = &quot;Aucun Profil authentifié&quot;.</li></ul> | Oui, les données de caractéristiques sont ajoutées au profil authentifié. |

Exemple d’appel (la valeur de requête correspondant à l’état d’authentification est mise en surbrillance) :

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%011&d_sid=123456`

## État de l&#39;authentification : LOGGED_OUT {#auth-status-logged-out}

| Valeur de requête | **Lire** les informations du profil authentifié | **Écrire** de nouvelles caractéristiques au profil authentifié |
---------|----------|---------
| 2 | <ul><li>Oui, si la règle de fusion des options authentifiées = &quot;Derniers Profils authentifiés&quot;</li><li>Non, si la règle de fusion des options authentifiées = &quot;Profils authentifiés actuels&quot; ou &quot;Aucun Profil authentifié&quot;</li></ul> | Non, les données de caractéristiques sont écrites sur le profil du périphérique. |

Exemple d’appel (la valeur de requête correspondant à l’état d’authentification est mise en surbrillance) :

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%012&d_sid=123456`

>[!NOTE]
>
>[!DNL Audience Manager] effectue une synchronisation des identifiants entre [CID et UUID](../reference/ids-in-aam.md) dans les trois cas.

>[!MORELIKETHIS]
>
>* [ID de client et états d’authentification](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html)

