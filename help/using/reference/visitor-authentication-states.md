---
description: L’état d’authentification du visiteur dans l’Audience Manager détermine si les informations de nouvelle caractéristique sont écrites au profil authentifié du visiteur ou au profil du périphérique, à partir duquel les données ont été collectées. L’Audience Manager gère de la même manière les états d’authentification de l’ID de visiteur INCONNU et LOGGED_OUT dans les appels de événement.
keywords: dpm.demdex.net
seo-description: L’état d’authentification du visiteur dans l’Audience Manager détermine si les informations de nouvelle caractéristique sont écrites au profil authentifié du visiteur ou au profil du périphérique, à partir duquel les données ont été collectées. L’Audience Manager gère de la même manière les états d’authentification de l’ID de visiteur INCONNU et LOGGED_OUT dans les appels de événement.
seo-title: États d’authentification du visiteur dans Audience Manager
solution: Audience Manager
title: États d’authentification du visiteur dans Audience Manager
uuid: d748c0c3-5833-4fb9-ab3e-793f5f252e47
feature: 'Référence '
exl-id: 55aec28d-02f6-4e6d-9be1-4ce40deb8dc3
translation-type: tm+mt
source-git-commit: c3c829ef1335d1e073b719f8252103fa578bb4e6
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 7%

---

# États d’authentification du visiteur dans Audience Manager{#visitor-authentication-states-in-audience-manager}

L’état d’authentification du visiteur dans l’Audience Manager détermine si les informations de nouvelle caractéristique sont écrites au profil authentifié du visiteur ou au profil du périphérique, à partir duquel les données ont été collectées. L’Audience Manager gère de la même manière les états d’authentification de l’ID de visiteur INCONNU et LOGGED_OUT dans les appels de événement.

À partir de [!DNL Experience Cloud] service d’ID v1.5+, la méthode `setCustomerID` comprend l’objet facultatif `AuthState`. `AuthState` identifie les visiteurs en fonction de leur état [ d’](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html)authentification. [!DNL Audience Manager] gère différemment les caractéristiques réalisées, en fonction de l’état d’authentification transmis dans l’appel et de la  [règle de fusion du ](../features/profile-merge-rules/merge-rules-dashboard.md) Profil que vous utilisez pour la segmentation.

## État de l&#39;authentification : INCONNU {#auth-status-unknown}

| Valeur de requête | Lire les informations du profil authentifié | Écrire de nouvelles caractéristiques au profil authentifié |
|---|---|---|
| 0 | <ul><li>Oui, si [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Last Authenticated Profiles].</li><li>Non, si [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Current Authenticated Profiles] ou [!UICONTROL No Authenticated Profile].</li></ul> | Non, les données de caractéristiques sont ajoutées au profil du périphérique. |

Exemple d’appel (la valeur de requête correspondant à l’état d’authentification est mise en surbrillance) :

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%010&d_sid=123456`

## État de l&#39;authentification : AUTHENTIFIÉ {#auth-status-authenticated}

| Valeur de requête | Lire les informations du profil authentifié | Écrire de nouvelles caractéristiques au profil authentifié |
|---|---|---|
| 1 | <ul><li>Oui, si [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Current Authenticated Profiles] ou [!UICONTROL Last Authenticated Profiles].</li><li>Non, si [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL No Authenticated Profile].</li></ul> | Oui, les données de caractéristiques sont ajoutées au profil authentifié. |

Exemple d’appel (la valeur de requête correspondant à l’état d’authentification est mise en surbrillance) :

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%011&d_sid=123456`

## État de l&#39;authentification : LOGGED_OUT {#auth-status-logged-out}

| Valeur de requête | Lire les informations du profil authentifié | Écrire de nouvelles caractéristiques au profil authentifié |
|---|---|---|
| 2 | <ul><li>Oui, si [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Last Authenticated Profiles].</li><li>Non, si [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Current Authenticated Profiles] ou [!UICONTROL No Authenticated Profile].</li></ul> | Non, les données de caractéristiques sont écrites sur le profil du périphérique. |

Exemple d’appel (la valeur de requête correspondant à l’état d’authentification est mise en surbrillance) :

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%012&d_sid=123456`

>[!NOTE]
>
>[!DNL Audience Manager] effectue une synchronisation des identifiants entre  [CID et ](../reference/ids-in-aam.md) UUID dans les trois cas.

>[!MORELIKETHIS]
>
>* [ID de client et états d’authentification](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html)

