---
description: Une requête en bloc renvoie des données que vous pouvez utiliser avec les différents en-têtes des feuilles de calcul Mettre à jour, Créer, Estimer et Supprimer.
seo-description: Une requête en bloc renvoie des données que vous pouvez utiliser avec les différents en-têtes des feuilles de calcul Mettre à jour, Créer, Estimer et Supprimer.
seo-title: Demandes en bloc
solution: Audience Manager
title: Demandes en bloc
uuid: 0192d26a-4cea-4e12-9fea-388b92b382f1
feature: BAAAM
exl-id: a0597bf4-79c8-404d-ba3b-a92c6b5c9c06
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 3%

---

# Demandes en bloc{#bulk-requests}

Une requête en bloc renvoie des données que vous pouvez utiliser avec les différents en-têtes des feuilles de calcul Mettre à jour, Créer, Estimer et Supprimer.

<!-- 

t_bulk_requests.xml

 -->

>[!NOTE]
>
>[Les ](../../features/administration/administration-overview.md) autorisations de groupe RBAC attribuées dans l’ [!DNL Audience Manager] interface utilisateur sont respectées dans le  [!UICONTROL Bulk Management Tools].

La feuille de calcul [!UICONTROL Request] ne comporte pas son propre jeu d&#39;en-têtes de colonne et vous n&#39;avez pas besoin de copier des ID dans aucune des colonnes. Elle renvoie plutôt des données en fonction du bouton d’action sur lequel vous cliquez dans la barre d’outils. En outre, une fonction de rapports facultative renvoie un nombre de fréquences pour les incendies de pixels et un nombre d’utilisateurs uniques pour plusieurs intervalles de temps fixes.

Pour effectuer des requêtes en masse, ouvrez la feuille de calcul [!UICONTROL Bulk Management Tools] et :

1. Cliquez sur l&#39;onglet **[!UICONTROL Request]**.
2. Dans la barre d&#39;outils située en haut de la feuille de calcul, cliquez sur un bouton de requête correspondant aux données à utiliser. Vous pouvez demander :

   * Modèles algorithmiques
   * Sources de données
   * Signaux dérivés
   * Mappages de destination
   * Caractéristiques algorithmiques, basées sur des règles et intégrées
   * Segments 
   * ID des dossiers de caractéristiques et de segments

   L&#39;API [!DNL Audience Manager] réécrit les données en vrac dans la feuille de calcul [!UICONTROL Request].

>[!NOTE]
>
>Dans vos résultats, les colonnes `createTime` et `updateTime` renvoient des données en notation exponentielle. Les horodatages sous-jacents sont enregistrés dans l’heure UTC UNIX. Actuellement, la feuille de calcul ne peut pas renvoyer des horodatages dans un format lisible.

Si votre mise à jour en masse renvoie une erreur ou échoue, voir [Résolution des problèmes liés aux outils de gestion en bloc](../../reference/bulk-management-tools/bulk-troubleshooting.md).
