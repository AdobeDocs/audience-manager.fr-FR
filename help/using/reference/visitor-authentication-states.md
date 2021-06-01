---
description: L’état d’authentification du visiteur dans l’Audience Manager détermine si les nouvelles informations de caractéristique sont écrites dans le profil authentifié du visiteur ou dans le profil du périphérique à partir duquel les données ont été collectées. Audience Manager gère de la même manière les états d’authentification de l’identifiant visiteur UNKNOWN et LOGGED_OUT dans les appels d’événement.
keywords: dpm.demdex.net
seo-description: L’état d’authentification du visiteur dans l’Audience Manager détermine si les nouvelles informations de caractéristique sont écrites dans le profil authentifié du visiteur ou dans le profil du périphérique à partir duquel les données ont été collectées. Audience Manager gère de la même manière les états d’authentification de l’identifiant visiteur UNKNOWN et LOGGED_OUT dans les appels d’événement.
seo-title: États d’authentification du visiteur dans Audience Manager
solution: Audience Manager
title: États d’authentification du visiteur dans Audience Manager
uuid: d748c0c3-5833-4fb9-ab3e-793f5f252e47
feature: 'Référence '
exl-id: 55aec28d-02f6-4e6d-9be1-4ce40deb8dc3
source-git-commit: c3c829ef1335d1e073b719f8252103fa578bb4e6
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 7%

---

# États d’authentification du visiteur dans Audience Manager{#visitor-authentication-states-in-audience-manager}

L’état d’authentification du visiteur dans l’Audience Manager détermine si les nouvelles informations de caractéristique sont écrites dans le profil authentifié du visiteur ou dans le profil du périphérique à partir duquel les données ont été collectées. Audience Manager gère de la même manière les états d’authentification de l’identifiant visiteur UNKNOWN et LOGGED_OUT dans les appels d’événement.

En commençant par [!DNL Experience Cloud] Service d’ID v1.5+, la méthode `setCustomerID` inclut l’objet `AuthState` facultatif. `AuthState` identifie les visiteurs en fonction de leur état  [d’authentification](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html). [!DNL Audience Manager] gère différemment les caractéristiques réalisées, en fonction de l’état d’authentification transmis dans l’appel et de la  [règle de fusion des ](../features/profile-merge-rules/merge-rules-dashboard.md) profils que vous utilisez pour la segmentation.

## État d’authentification : INCONNU {#auth-status-unknown}

| Valeur de la requête | Lecture des informations du profil authentifié | Écrire de nouvelles caractéristiques au profil authentifié |
|---|---|---|
| 0 | <ul><li>Oui, si [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Last Authenticated Profiles].</li><li>Non, si [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Current Authenticated Profiles] ou [!UICONTROL No Authenticated Profile].</li></ul> | Non, les données de caractéristiques sont ajoutées au profil de l’appareil. |

Exemple d’appel (la valeur de requête correspondant à l’état d’authentification est mise en surbrillance) :

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%010&d_sid=123456`

## État d’authentification : AUTHENTIFIÉ {#auth-status-authenticated}

| Valeur de la requête | Lecture des informations du profil authentifié | Écrire de nouvelles caractéristiques au profil authentifié |
|---|---|---|
| 1 | <ul><li>Oui, si [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Current Authenticated Profiles] ou [!UICONTROL Last Authenticated Profiles].</li><li>Non, si [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL No Authenticated Profile].</li></ul> | Oui, les données de caractéristique sont ajoutées au profil authentifié. |

Exemple d’appel (la valeur de requête correspondant à l’état d’authentification est mise en surbrillance) :

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%011&d_sid=123456`

## État d’authentification : LOGGED_OUT {#auth-status-logged-out}

| Valeur de la requête | Lecture des informations du profil authentifié | Écrire de nouvelles caractéristiques au profil authentifié |
|---|---|---|
| 2 | <ul><li>Oui, si [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Last Authenticated Profiles].</li><li>Non, si [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Current Authenticated Profiles] ou [!UICONTROL No Authenticated Profile].</li></ul> | Non, les données de caractéristique sont écrites dans le profil de l’appareil. |

Exemple d’appel (la valeur de requête correspondant à l’état d’authentification est mise en surbrillance) :

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%012&d_sid=123456`

>[!NOTE]
>
>[!DNL Audience Manager] effectue une synchronisation des identifiants entre  [CID et ](../reference/ids-in-aam.md) UUID dans les trois cas.

>[!MORELIKETHIS]
>
>* [ID de client et états d’authentification](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html)

