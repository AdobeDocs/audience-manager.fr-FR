---
description: Une requête en bloc renvoie les données que vous pouvez utiliser avec les différents en-têtes des feuilles de calcul Mettre à jour, Créer, Estimer et Supprimer.
seo-description: A bulk request returns data you can use with the different headers in the Update, Create, Estimate, and Delete worksheets.
seo-title: Bulk Requests
solution: Audience Manager
title: Demandes en bloc
uuid: 0192d26a-4cea-4e12-9fea-388b92b382f1
feature: BAAAM
exl-id: a0597bf4-79c8-404d-ba3b-a92c6b5c9c06
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 0%

---

# Demandes en bloc{#bulk-requests}

Une requête en bloc renvoie les données que vous pouvez utiliser avec les différents en-têtes des feuilles de calcul Mettre à jour, Créer, Estimer et Supprimer.

>[!IMPORTANT]
>
>Les outils de gestion en bloc ne sont pas une offre d’Adobe officiellement prise en charge. Le dépannage et l’assistance par l’intermédiaire de l’assistance clientèle seront gérés au cas par cas.

<!-- 

t_bulk_requests.xml

 -->

>[!NOTE]
>
>[Les autorisations de groupe RBAC ](../../features/administration/administration-overview.md) attribuées dans l’interface utilisateur de [!DNL Audience Manager] sont honorées dans le [!UICONTROL Bulk Management Tools].

La feuille de calcul [!UICONTROL Request] ne dispose pas de son propre jeu d’en-têtes de colonne et vous n’avez pas besoin de copier des identifiants dans aucune des colonnes. Elle renvoie plutôt des données en fonction du bouton d’action sur lequel vous cliquez dans la barre d’outils. De plus, une fonction de création de rapports facultative renvoie un nombre de fréquence pour les incendies de pixels et un nombre d’utilisateurs unique pour plusieurs intervalles de temps fixes.

Pour effectuer des requêtes en bloc, ouvrez la feuille de calcul [!UICONTROL Bulk Management Tools] et :

1. Cliquez sur l’onglet **[!UICONTROL Request]** .
2. Dans la barre d’outils située en haut de la feuille de calcul, cliquez sur un bouton de requête correspondant aux données que vous souhaitez utiliser. Vous pouvez demander :

   * Modèles algorithmiques
   * Sources de données
   * Signaux dérivés
   * Mappages des destinations
   * Caractéristiques algorithmiques, basées sur des règles et intégrées
   * Segments
   * ID de dossier de caractéristiques et de segments

   L’API [!DNL Audience Manager] réécrit les données en bloc dans la feuille de calcul [!UICONTROL Request].

>[!NOTE]
>
>Dans vos résultats, les colonnes `createTime` et `updateTime` renvoient des données en notation exponentielle. Les horodatages sous-jacents sont enregistrés en heure UTC UNIX. Actuellement, la feuille de calcul ne peut pas renvoyer les horodatages dans un format lisible.

Si votre mise à jour en masse renvoie une erreur ou échoue, reportez-vous à la section [Dépannage des outils de gestion en bloc](../../reference/bulk-management-tools/bulk-troubleshooting.md).
