---
description: Une requête en masse renvoie des données que vous pouvez utiliser avec les différents en-têtes des feuilles de calcul Mettre à jour, Créer, Estimer et Supprimer.
seo-description: Une requête en masse renvoie des données que vous pouvez utiliser avec les différents en-têtes des feuilles de calcul Mettre à jour, Créer, Estimer et Supprimer.
seo-title: Demandes en bloc
solution: Audience Manager
title: Demandes en bloc
uuid: 0192d26a-4cea-4e12-9fea-388b92b382f1
translation-type: tm+mt
source-git-commit: 8cc3d9d629536c48b7013ffede16c0b112704c89

---


# Demandes en bloc{#bulk-requests}

Une requête en masse renvoie des données que vous pouvez utiliser avec les différents en-têtes des feuilles de calcul Mettre à jour, Créer, Estimer et Supprimer.

<!-- 

t_bulk_requests.xml

 -->

>[!NOTE]
>
>[Les autorisations](../../features/administration/administration-overview.md) de groupe RBAC attribuées dans l’ [!DNL Audience Manager] interface utilisateur sont respectées dans le [!UICONTROL Bulk Management Tools].

La [!UICONTROL Request] feuille de calcul ne comporte pas son propre jeu d&#39;en-têtes de colonne et vous n&#39;avez pas besoin de copier des ID dans aucune des colonnes. Il renvoie plutôt des données en fonction du bouton d’action sur lequel vous cliquez dans la barre d’outils. Et une fonctionnalité facultative de  de renvoie un nombre de fréquence pour les incendies de pixels et un nombre d’utilisateurs uniques pour plusieurs intervalles de temps fixes.

Pour effectuer des requêtes en masse, ouvrez la [!UICONTROL Bulk Management Tools] feuille de calcul et procédez comme suit :

1. Click the **[!UICONTROL Request]** tab.
2. Dans la barre d&#39;outils située en haut de la feuille de calcul, cliquez sur un bouton de requête correspondant aux données que vous souhaitez utiliser. Vous pouvez demander :

   * Modèles algorithmiques
   * Sources de données
   * Signaux dérivés
   * Mappages de destination
   * Caractéristiques algorithmiques, basées sur des règles et intégrées
   * Segments
   * ID de dossier de caractéristiques et de segments
   L’ [!DNL Audience Manager] API réécrit les données en masse dans la [!UICONTROL Request] feuille de calcul.

>[!NOTE]
>
>Dans vos résultats, les `createTime` colonnes et `updateTime` les colonnes renvoient des données en notation exponentielle. Les horodatages sous-jacents sont enregistrés dans l’heure UTC UNIX. Actuellement, la feuille de calcul ne peut pas renvoyer de tampons de date/heure dans un format lisible.

Si votre mise à jour en masse renvoie une erreur ou échoue, reportez-vous à la section [Dépannage des outils](../../reference/bulk-management-tools/bulk-troubleshooting.md)de gestion en bloc.
