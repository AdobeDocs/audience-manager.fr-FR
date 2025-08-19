---
description: Le statut d’authentification du visiteur dans Audience Manager détermine si les nouvelles informations de caractéristiques sont écrites dans le profil authentifié du visiteur ou sur le profil de l’appareil à partir duquel les données ont été collectées. Audience Manager gère de la même manière les statuts d’authentification des identifiants visiteur UNKNOWN et LOGGED_OUT dans les appels d’événement.
keywords: dpm.demdex.net
seo-description: The visitor authentication status in Audience Manager determines if the new trait information is written to the visitor's authenticated profile or to the device profile, where the data was collected from. Audience Manager handles the visitor ID authentication statuses UNKNOWN and LOGGED_OUT in event calls in the same way.
seo-title: Visitor Authentication States in Audience Manager
solution: Audience Manager
title: États de l’authentification des visiteurs dans Audience Manager
uuid: d748c0c3-5833-4fb9-ab3e-793f5f252e47
feature: Reference
exl-id: 55aec28d-02f6-4e6d-9be1-4ce40deb8dc3
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 2%

---

# États de l’authentification des visiteurs dans Audience Manager{#visitor-authentication-states-in-audience-manager}

Le statut d’authentification du visiteur dans Audience Manager détermine si les nouvelles informations de caractéristiques sont écrites dans le profil authentifié du visiteur ou sur le profil de l’appareil à partir duquel les données ont été collectées. Audience Manager gère de la même manière les statuts d’authentification des identifiants visiteur UNKNOWN et LOGGED_OUT dans les appels d’événement.

À partir [!DNL Experience Cloud] service d’ID version 1.5+, la méthode `setCustomerID` inclut l’objet `AuthState` facultatif. `AuthState` identifie les visiteurs en fonction de leur [statut d&#39;authentification](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html). [!DNL Audience Manager] traite les caractéristiques réalisées différemment, selon le statut d’authentification transmis dans l’appel et la [règle de fusion de profil](../features/profile-merge-rules/merge-rules-dashboard.md) que vous utilisez pour la segmentation.

## Statut d’authentification : INCONNU {#auth-status-unknown}

| Valeur de la requête | Lire des informations à partir du profil authentifié | Écrire de nouvelles caractéristiques dans le profil authentifié |
|---|---|---|
| 0 | <ul><li>Oui, si le [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Last Authenticated Profiles].</li><li>Non, si le [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Current Authenticated Profiles] ou [!UICONTROL No Authenticated Profile].</li></ul> | Non, les données de caractéristique sont ajoutées au profil de l’appareil. |

Exemple d’appel (la valeur de requête correspondant au statut d’authentification est mise en surbrillance) :

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%010&d_sid=123456`

## Statut d’authentification : AUTHENTICATED {#auth-status-authenticated}

| Valeur de la requête | Lire des informations à partir du profil authentifié | Écrire de nouvelles caractéristiques dans le profil authentifié |
|---|---|---|
| 1 | <ul><li>Oui, si le [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Current Authenticated Profiles] ou [!UICONTROL Last Authenticated Profiles].</li><li>Non, si le [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL No Authenticated Profile].</li></ul> | Oui, les données de caractéristique sont ajoutées au profil authentifié. |

Exemple d’appel (la valeur de requête correspondant au statut d’authentification est mise en surbrillance) :

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%011&d_sid=123456`

## Statut d’authentification : LOGGED_OUT {#auth-status-logged-out}

| Valeur de la requête | Lire des informations à partir du profil authentifié | Écrire de nouvelles caractéristiques dans le profil authentifié |
|---|---|---|
| 2 | <ul><li>Oui, si le [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Last Authenticated Profiles].</li><li>Non, si le [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Current Authenticated Profiles] ou [!UICONTROL No Authenticated Profile].</li></ul> | Non, les données de caractéristique sont écrites dans le profil de l’appareil. |

Exemple d’appel (la valeur de requête correspondant au statut d’authentification est mise en surbrillance) :

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%012&d_sid=123456`

>[!NOTE]
>
>[!DNL Audience Manager] effectue une synchronisation des identifiants entre [CID et UUID](../reference/ids-in-aam.md) dans les trois cas.

>[!MORELIKETHIS]
>
>* [ID de client et états d’authentification](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html)
