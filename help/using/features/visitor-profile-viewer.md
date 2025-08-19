---
description: Utilisez la Visionneuse du profil du visiteur pour afficher l’état actuel d’un profil utilisateur pour le navigateur actuel, y compris ses caractéristiques et ses segments. Pour chaque caractéristique, vous pouvez afficher son SID, son nom, des détails sur la manière dont les caractéristiques du visiteur ont été réalisées (propriétaires ou tiers), la date de réalisation et la fréquence des réalisations. Pour chaque segment, vous pouvez afficher son SID, son nom et la date d’appartenance au segment. Vous pouvez également afficher le profil du visiteur pour un autre identifiant de profil Audience Manager (UUID). La visionneuse de profil du visiteur est utile pour résoudre les problèmes.
keywords: emplacement;paramètre d’emplacement
seo-description: Use the Visitor Profile Viewer to display the current state of a user profile for the current browser, including its traits and segments. For each trait, you can view its SID, name, details about how visitor traits were realized (first- or third-party), the realization date, and the frequency of realizations. For each segment, you can view its SID, name, and the segment membership date. You can also view the visitor profile for another Audience Manager profile ID (UUID). The Visitor Profile Viewer is helpful for troubleshooting purposes.
seo-title: Visitor Profile Viewer
solution: Audience Manager
title: Visionneuse du profil du visiteur
uuid: 77ffe134-e08f-41de-8fc4-15494847b1d0
feature: Traits
exl-id: 6c1ee14c-6f78-4e45-9b88-24ace8400079
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 0%

---

# Visionneuse du profil du visiteur {#visitor-profile-viewer}

Utilisez le [!UICONTROL Visitor Profile Viewer] pour afficher l’état actuel d’un profil utilisateur pour le navigateur actuel, y compris ses caractéristiques et ses segments. Pour chaque caractéristique, vous pouvez afficher son [!UICONTROL SID], son nom, les détails sur la manière dont les caractéristiques du visiteur ont été réalisées (propriétaires ou tiers), la date de réalisation et la fréquence des réalisations. Pour chaque segment, vous pouvez afficher son [!UICONTROL SID], son nom et la date d’appartenance au segment. Vous pouvez également afficher le profil du visiteur pour un autre identifiant de profil Audience Manager ([!UICONTROL UUID]). Le [!UICONTROL Visitor Profile Viewer] est utile à des fins de dépannage.

>[!NOTE]
>
>* L’accès nécessite des autorisations [!UICONTROL Administrator].
>* Un délai de 24 heures est nécessaire pour que les informations sur les segments réalisés et les caractéristiques intégrées s’affichent dans l’interface utilisateur.

<!-- 
Traits that are not part of a segment will not appear in the
<span class="wintitle"> Visitor Profile Viewer</span>.
-->

1. Cliquez sur **[!UICONTROL Tools]** > **[!UICONTROL Visitor Profile Viewer]**.

1. *(Facultatif)* Cliquez sur le nom de la caractéristique pour l’afficher dans le [!UICONTROL Trait Builder].

   Pour plus d’informations, voir [Caractéristiques](../features/traits/trait-details-page.md).

1. *(Facultatif)* Cliquez sur le nom du segment pour l’afficher dans le [!UICONTROL Segment Builder].

   Pour plus d’informations, voir [Segments](../features/segments/segments-purpose.md).

1. *(Conditionnel)* Dans la zone **[!UICONTROL UUID]**, spécifiez un autre identifiant de profil Audience Manager, puis cliquez sur **[!UICONTROL Refresh]** pour afficher les caractéristiques et les segments de cet utilisateur.
