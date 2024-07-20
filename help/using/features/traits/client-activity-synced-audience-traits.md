---
description: Il s’agit de caractéristiques spéciales utilisées par les audiences adressables. Les caractéristiques synchronisées d’audience et de Source de données actives sont situées dans Audience Data > Caractéristiques > Caractéristiques d’audience.
seo-description: These are special traits used by Addressable Audiences. Active Audience and Data Source Synced Traits are located in Audience Data > Traits > Audience Traits.
seo-title: Active Audience Traits and Data Source Synced Traits
solution: Audience Manager
title: Caractéristiques d’audience active et caractéristiques synchronisées de Data Source
uuid: b4f145ab-f343-4d71-86d1-5d03f7b03809
feature: Traits
exl-id: 8fa4ea24-1beb-40cb-bdec-540a3f7c2573
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 0%

---

# Caractéristiques d’audience active et caractéristiques synchronisées de Data Source {#active-audience-traits-and-data-source-synced-traits}

Il s’agit de caractéristiques spéciales utilisées par [!UICONTROL Addressable Audiences]. [!UICONTROL Active Audience] et [!UICONTROL Data Source Synced Traits] se trouvent dans [!UICONTROL Audience Data > Traits > Audience Traits].

>[!NOTE]
>
>L’accès nécessite des autorisations d’administrateur.

## Caractéristiques d’audience actives {#active-audience-traits}

Une caractéristique [!UICONTROL Active Audience] contient tous les appareils gérés dans votre compte [!DNL Audience Manager]. Vous pouvez utiliser un [!UICONTROL Active Audience Trait] comme d’autres caractéristiques lorsque vous créez ou modifiez des segments. En outre, [Audiences adressables](../../features/addressable-audiences.md) nécessite cette caractéristique pour générer des données de chevauchement. Par défaut, tous les comptes ont une caractéristique [!UICONTROL Active Audience]. Cette caractéristique ne peut pas être supprimée.

## Caractéristiques synchronisées de Data Source {#data-source-synced-traits}

[!UICONTROL Data Source Synced Traits] apparaît dans le dossier [!UICONTROL Audience Traits] lorsque vous [ créez ou modifiez une source de données ](../../features/manage-datasources.md#create-data-source) et que vous appliquez l’un de ces paramètres :

![](assets/datasource_synced.png)

[!UICONTROL Data Source Synced Traits] effectue le suivi de tous les utilisateurs associés à une source de données. Vous pouvez utiliser un [!UICONTROL Data Source Synched Trait] comme d’autres caractéristiques lorsque vous créez ou modifiez des segments. Lorsque vous créez un [!UICONTROL Data Source Synced Trait], le nom de la caractéristique correspond au nom utilisé par votre source de données. Modifiez la source de données pour modifier le nom de la caractéristique. Ces caractéristiques ne peuvent pas être supprimées.

>[!TIP]
>
>[!UICONTROL Data Source Synced Traits] est utile pour la résolution des problèmes. Cliquez sur le nom d’une caractéristique pour vérifier les mesures sur la page de résumé des caractéristiques. Si votre caractéristique sélectionnée renvoie des données, cela indique que le processus de synchronisation des identifiants est configuré correctement et que les données sont envoyées vers [!DNL Audience Manager].

>[!MORELIKETHIS]
>
>* [Audiences adressables](../../features/addressable-audiences.md)
