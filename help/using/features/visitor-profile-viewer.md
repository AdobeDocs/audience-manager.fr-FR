---
description: Utilisez le lecteur de Profil du Visiteur pour afficher l’état actuel d’un profil d’utilisateur pour le navigateur actuel, y compris ses caractéristiques et segments. Pour chaque caractéristique, vous pouvez vue son SID, son nom, des détails sur la façon dont les caractéristiques du visiteur ont été réalisées (première ou troisième partie), la date de réalisation et la fréquence des reconnaissances. Pour chaque segment, vous pouvez vue son SID, son nom et la date d’adhésion du segment. Vous pouvez également vue le profil du visiteur pour un autre identifiant de profil d’Audience Manager (UUID). Le lecteur de Profil du Visiteur est utile pour la résolution des problèmes.
keywords: emplacement ; paramètre location
seo-description: Utilisez le lecteur de Profil du Visiteur pour afficher l’état actuel d’un profil d’utilisateur pour le navigateur actuel, y compris ses caractéristiques et segments. Pour chaque caractéristique, vous pouvez vue son SID, son nom, des détails sur la façon dont les caractéristiques du visiteur ont été réalisées (première ou troisième partie), la date de réalisation et la fréquence des reconnaissances. Pour chaque segment, vous pouvez vue son SID, son nom et la date d’adhésion du segment. Vous pouvez également vue le profil du visiteur pour un autre identifiant de profil d’Audience Manager (UUID). Le lecteur de Profil du Visiteur est utile pour la résolution des problèmes.
seo-title: Visionneuse de profil du visiteur
solution: Audience Manager
title: Visionneuse de profil du visiteur
uuid: 77ffe134-e08f-41de-8fc4-15494847b1d0
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '339'
ht-degree: 2%

---


# Visionneuse de profil du visiteur {#visitor-profile-viewer}

Utilisez [!UICONTROL Visitor Profile Viewer] pour afficher l’état actuel d’un profil utilisateur pour le navigateur actuel, y compris ses caractéristiques et segments. Pour chaque caractéristique, vous pouvez vue son [!UICONTROL SID] nom, détails sur la façon dont les traits visiteurs ont été réalisés (premier ou tiers), la date de réalisation et la fréquence des reconnaissances. Pour chaque segment, vous pouvez vue son [!UICONTROL SID] nom et la date d’adhésion du segment. Vous pouvez également vue le profil du visiteur pour un autre ID de profil d’Audience Manager ([!UICONTROL UUID]). Le [!UICONTROL Visitor Profile Viewer] est utile à des fins de dépannage.

>[!NOTE]
>
>* L&#39;accès nécessite des autorisations [!UICONTROL Administrator].
>* Il y a un délai de 24 heures avant que les informations sur les segments réalisés et les caractéristiques intégrées ne s’affichent dans l’interface utilisateur.


<!-- 
Traits that are not part of a segment will not appear in the
<span class="wintitle"> Visitor Profile Viewer</span>.
-->

1. Cliquez sur **[!UICONTROL Tools]** > **[!UICONTROL Visitor Profile Viewer]**.

1. *(Facultatif)* Cliquez sur le nom de la caractéristique pour l’afficher dans le  [!UICONTROL Trait Builder].

   Pour plus d&#39;informations, voir [Caractéristiques](../features/traits/trait-details-page.md).

1. *(Facultatif)* Cliquez sur le nom du segment pour afficher ce segment dans le  [!UICONTROL Segment Builder].

   Pour plus d’informations, voir [Segments](../features/segments/segments-purpose.md).

1. *(Conditionnel)* Dans la  **[!UICONTROL UUID]** zone, indiquez un autre ID de profil d’Audience Manager, puis cliquez sur  **[!UICONTROL Refresh]** pour vue les caractéristiques et les segments de cet utilisateur.