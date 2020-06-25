---
description: Une requête en bloc renvoie des données que vous pouvez utiliser avec les différents en-têtes des feuilles de calcul Mettre à jour, Créer, Estimer et Supprimer.
seo-description: Une requête en bloc renvoie des données que vous pouvez utiliser avec les différents en-têtes des feuilles de calcul Mettre à jour, Créer, Estimer et Supprimer.
seo-title: Demandes en masse
solution: Audience Manager
title: Demandes en masse
uuid: 0192d26a-4cea-4e12-9fea-388b92b382f1
feature: baaam
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 0%

---


# Demandes en masse{#bulk-requests}

Une requête en bloc renvoie des données que vous pouvez utiliser avec les différents en-têtes des feuilles de calcul Mettre à jour, Créer, Estimer et Supprimer.

<!-- 

t_bulk_requests.xml

 -->

>[!NOTE]
>
>[Les autorisations](../../features/administration/administration-overview.md) de groupe RBAC attribuées dans l’ [!DNL Audience Manager] interface utilisateur sont respectées dans le [!UICONTROL Bulk Management Tools].

La [!UICONTROL Request] feuille de calcul ne comporte pas son propre jeu d&#39;en-têtes de colonne et vous n&#39;avez pas besoin de copier des ID dans aucune des colonnes. Elle renvoie plutôt des données en fonction du bouton d’action sur lequel vous cliquez dans la barre d’outils. En outre, une fonction de rapports facultative renvoie un nombre de fréquences pour les incendies de pixels et un nombre d’utilisateurs uniques pour plusieurs intervalles de temps fixes.

Pour effectuer des requêtes en masse, ouvrez la [!UICONTROL Bulk Management Tools] feuille de calcul et :

1. Click the **[!UICONTROL Request]** tab.
2. Dans la barre d&#39;outils située en haut de la feuille de calcul, cliquez sur un bouton de requête correspondant aux données à utiliser. Vous pouvez demander :

   * Modèles algorithmiques
   * Sources de données
   * Signaux dérivés
   * Mappages de destination
   * Caractéristiques algorithmiques, basées sur des règles et intégrées
   * Segments
   * ID des dossiers de caractéristiques et de segments
   L&#39; [!DNL Audience Manager] API réécrit les données en vrac dans la [!UICONTROL Request] feuille de calcul.

>[!NOTE]
>
>Dans vos résultats, les `createTime` colonnes et `updateTime` les colonnes renvoient des données en notation exponentielle. Les horodatages sous-jacents sont enregistrés dans l’heure UTC UNIX. Actuellement, la feuille de calcul ne peut pas renvoyer des horodatages dans un format lisible.

Si votre mise à jour en masse renvoie une erreur ou échoue, voir [Dépannage des outils](../../reference/bulk-management-tools/bulk-troubleshooting.md)de gestion en bloc.
