---
description: La page de détails d’une caractéristique individuelle fournit un aperçu des informations telles que le nom de la caractéristique, l’ID, les mesures de performances,  les  qui définissent la caractéristique, les segments auxquels elle appartient et le journal d’audit des caractéristiques. Pour afficher ces détails, accédez à Données  > Caractéristiques du et cliquez sur le nom de la caractéristique que vous souhaitez utiliser.
seo-description: La page de détails d’une caractéristique individuelle fournit un aperçu des informations telles que le nom de la caractéristique, l’ID, les mesures de performances,  les  qui définissent la caractéristique, les segments auxquels elle appartient et le journal d’audit des caractéristiques. Pour afficher ces détails, accédez à Données  > Caractéristiques du et cliquez sur le nom de la caractéristique que vous souhaitez utiliser.
seo-title: Page Détails du trait
solution: Audience Manager
title: Page Détails du trait
uuid: 23301376-c1cc-4778-b8c4-9831f6739db9
keywords: identity type breakdown, identity breakdown, audience identity reporting
translation-type: tm+mt
source-git-commit: 75fe1e0f7321107930a28e354ca2f4a256a477ac

---


# Page Détails du trait {#trait-details-page}

La page de détails d’une caractéristique individuelle fournit un aperçu des détails de la caractéristique, tels que le nom de la caractéristique, l’ID, les mesures de performances,   qui définissent la caractéristique, les segments auxquels elle appartient et le journal d’audit de la caractéristique. Pour  ces détails, cliquez sur **[!UICONTROL Audience Data]** > **[!UICONTROL Traits]** et cliquez sur le nom de la caractéristique que vous souhaitez utiliser.

## Outils de gestion des caractéristiques {#trait-management-tools}

La partie supérieure de la page des détails de la caractéristique héberge les outils que vous pouvez utiliser pour gérer vos caractéristiques :

1. **[!UICONTROL Add New]**: Utilisez cette option pour créer de nouvelles caractéristiques basées sur des règles, algorithmiques ou intégrées.
2. **[!UICONTROL Edit]**: Utilisez cette option pour modifier la configuration de la caractéristique actuelle.
3. **[!UICONTROL Delete]**: Utilisez cette option pour supprimer la caractéristique actuelle de votre compte  Manager .
4. **[!UICONTROL Marketplace Recommendations]**: Utilisez cette option pour trouver des caractéristiques similaires à celles que vous affichez, à partir des frais de [!UICONTROL Audience Marketplace] données auxquels vous n’êtes pas abonné. Voir [ Marketplace pour les acheteurs](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) de données pour savoir comment naviguer sur le Marketplace et trouver des caractéristiques similaires.

![basic-trait-information](assets/basic-trait-information.png)

## Informations sur les caractéristiques {#basics}

La [!UICONTROL Trait Information] section affiche des détails sur les champs obligatoires et facultatifs que vous avez remplis lors de la création de la caractéristique. Cela inclut des éléments tels que le type de caractéristique, l’ID de caractéristique, la description, la source de données et d’autres métadonnées. Ces détails varient en fonction du type de caractéristique (dossier, intégré ou basé sur des règles).

## Graphique de caractéristiques {#trait-graph}

Le [!UICONTROL Trait Graph] fournit des mesures de performances en un coup d’oeil pour votre caractéristique sélectionnée. Maintenez le curseur sur une ligne de tendance pour afficher des données supplémentaires pour la caractéristique sélectionnée.

[!UICONTROL Unique Trait Realizations] représentent le nombre d’utilisateurs uniques qui ont ajouté cette caractéristique à leur  de au cours d’une période donnée. Le [!UICONTROL Total Trait Population] indique le nombre d’utilisateurs uniques actuellement qualifiés pour cette caractéristique.

* Pour les caractéristiques basées sur des règles, la qualification des caractéristiques se produit en temps réel, car les utilisateurs remplissent les conditions requises pour une caractéristique dans leur navigateur.
* Pour les caractéristiques intégrées, la qualification des caractéristiques se produit après le traitement d’un fichier entrant, c’est-à-dire que le fichier entrant est [inséré dans  Gestionnaire](../../faq/faq-inbound-data-ingestion.md) de  et c’est-à-dire lorsque la qualification des caractéristiques se produit.
* **[!UICONTROL Unique Trait Realizations]**: Nombre d’utilisateurs uniques qui ont ajouté cette caractéristique à leur  sur une période donnée.
* **[!UICONTROL Total Trait Population]**: Nombre d’utilisateurs uniques actuellement qualifiés pour cette caractéristique.

   ![trait-graphique](assets/trait-summary.png)

* **[!UICONTROL Identity Type Breakdown]**: Les trois premières entrées montrent les trois principales sources de données inter-périphériques ayant le plus grand nombre de personnes qualifiées pour la caractéristique, dans l’ordre décroissant. La quatrième entrée indique la somme de tous les autres [!DNL DPUUIDs] ([!DNL CRM IDs]) qui ont qualifié la caractéristique, à partir des sources de données inter-périphériques qui ne figurent pas dans les trois premiers. Ce rapport s’affiche uniquement si vous sélectionnez ID inter-périphériques dans le menu [!UICONTROL Show Results By] déroulant en haut à droite de la page. L’option déroulante par défaut est [!UICONTROL Device ID], où ce rapport n’est pas affiché.

   ![trait-graphique](assets/trait-identity.png)

   >[!NOTE]
   >
   > Gestionnaire de  de affiche le [!UICONTROL Identity Type Breakdown] rapport uniquement si vous avez des ID de plusieurs périphériques qualifiés pour la caractéristique.

   >[!VIDEO](https://video.tv.adobe.com/v/27977/)

##  de caractéristiques {#trait-expression}

La [!UICONTROL Trait Expression] section présente les critères que les utilisateurs doivent respecter pour pouvoir bénéficier de la caractéristique. Ces règles sont définies lorsque vous [créez ou modifiez une caractéristique](../../features/traits/about-trait-builder.md).

![](assets/traitExpression.png)

## Segments de caractéristiques {#trait-segments}

Le de [!UICONTROL Segments with this Trait] section  tous les segments auxquels appartient la caractéristique sélectionnée. Vous pouvez cliquer sur le nom d’un segment pour afficher des détails sur ce segment.

![](assets/traitSegments.png)

## Journal d’audit/historique des caractéristiques {#trait-audit-history}

Pour les caractéristiques basées sur des règles et les caractéristiques intégrées, le [!UICONTROL Trait Expression Change History] montre les 10 dernières modifications apportées aux caractéristiques  les règles  et qui les a créées. Si votre caractéristique comporte plus de 10 modifications, cliquez sur **[!UICONTROL Export to CSV]** pour télécharger l’intégralité du journal d’audit. Le journal d’audit n’est pas disponible pour les caractéristiques de dossier ou d’algorithme.

>[!NOTE]
>
>[!UICONTROL Not Available] dans la [!UICONTROL By User] colonne signifie que le compte de cet utilisateur a été supprimé.

![](assets/traitHistory.png)