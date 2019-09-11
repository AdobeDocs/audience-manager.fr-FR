---
description: La page Détails d'une caractéristique individuelle donne une vue d'ensemble des informations telles que le nom de la caractéristique, l'ID, les mesures de performances, les expressions qui définissent la caractéristique, les segments auxquels il appartient et le journal d'audit de la caractéristique. Pour les afficher, accédez à Données d'audience > Caractéristiques, puis cliquez sur le nom de la caractéristique avec laquelle vous souhaitez travailler.
seo-description: La page Détails d'une caractéristique individuelle donne une vue d'ensemble des informations telles que le nom de la caractéristique, l'ID, les mesures de performances, les expressions qui définissent la caractéristique, les segments auxquels il appartient et le journal d'audit de la caractéristique. Pour les afficher, accédez à Données d'audience > Caractéristiques, puis cliquez sur le nom de la caractéristique avec laquelle vous souhaitez travailler.
seo-title: Page Détails de la caractéristique
solution: Audience Manager
title: Page Détails de la caractéristique
uuid: 23301376-c 1 cc -4778-b 8 c 4-9831 f 6739 db 9
translation-type: tm+mt
source-git-commit: 76adee013246c68da7ad871cef57f6ef174a239c

---


# Page Détails de la caractéristique {#trait-details-page}

La page Détails d'une caractéristique individuelle donne une vue d'ensemble des informations telles que le nom de la caractéristique, l'ID, les mesures de performances, les expressions qui définissent la caractéristique, les segments auxquels il appartient et le journal d'audit de la caractéristique. Pour les afficher, cliquez [!UICONTROL Audience Data > Traits] sur le nom de la caractéristique avec laquelle vous souhaitez travailler.

## Informations fondamentales {#basics}

La [!UICONTROL Basic Information] section présente des détails sur les champs obligatoires et facultatifs que vous avez terminés lors de la création de la caractéristique. Cela inclut des éléments tels que le type de caractéristique, l'ID de caractéristique, la description, la source de données et d'autres métadonnées. Ces détails varient selon le type de caractéristique (dossier, emplacement intégré ou selon des règles).

![](assets/basicInfo.png)

## Graphique de caractéristiques {#trait-graph}

Vous [!UICONTROL Trait Graph] disposez ainsi des mesures de performances d'un coup d'œil pour la caractéristique sélectionnée. Maintenez votre curseur sur une ligne de tendance pour afficher d'autres données pour la caractéristique sélectionnée.

[!UICONTROL Unique Trait Realizations] représentent le nombre d'utilisateurs uniques qui ont ajouté cette caractéristique à leur profil au cours de la période donnée. Le [!UICONTROL Total Trait Population] nombre d'utilisateurs uniques actuellement qualifiés pour cette caractéristique.

* Pour les caractéristiques basées sur des règles, la qualification des caractéristiques se produit en temps réel, car les utilisateurs remplissent une caractéristique dans leur navigateur.
* Pour les caractéristiques intégrées, la qualification des caractéristiques survient après le traitement d'un fichier entrant, c'est-à-dire que le fichier entrant [est alimenté dans Audience Manager](../../faq/faq-inbound-data-ingestion.md) , c'est-à-dire lorsque la qualification de caractéristique se produit.
* **[!UICONTROL Unique Trait Realizations]**: Nombre d'utilisateurs uniques qui ont ajouté cette caractéristique à leur profil au cours de la période donnée.
* **[!UICONTROL Total Trait Population]**: Nombre d'utilisateurs uniques actuellement qualifiés pour cette caractéristique.

   ![caractéristique-graphique](assets/trait-summary.png)

* **[!UICONTROL Identity Type Breakdown]**: Les trois premières entrées montrent les trois principales sources de données inter-périphériques dont le nombre de populations est le plus élevé et qui est qualifié pour la caractéristique, dans l'ordre décroissant. La quatrième entrée indique la somme de tout l'autre [!DNL DPUUIDs] ([!DNL CRM IDs]) qui est qualifiée pour la caractéristique, à partir des sources de données inter-périphériques qui ne figurent pas dans les trois premières. Ce rapport s'affiche uniquement si vous sélectionnez l'option ID inter-périphériques dans le [!UICONTROL Show Results By] menu déroulant en haut à droite de la page. L'option déroulante par défaut est [!UICONTROL Device ID], où ce rapport ne s'affiche pas.

   ![caractéristique-graphique](assets/trait-identity.png)
   > [!NOTE]
   > Audience Manager affiche uniquement [!UICONTROL Identity Type Breakdown] le rapport si des ID interterminaux sont qualifiés pour la caractéristique.

   >[!VIDEO](https://video.tv.adobe.com/v/27977/?captions=fre_fr)

## Expression de caractéristique {#trait-expression}

La [!UICONTROL Trait Expression] section indique les critères que les utilisateurs doivent remplir pour remplir la caractéristique. Ces règles sont définies lorsque vous [créez ou modifiez une caractéristique](../../features/traits/about-trait-builder.md).

![](assets/traitExpression.png)

## Segments de caractéristique {#trait-segments}

La [!UICONTROL Segments with this Trait] section répertorie tous les segments auxquels la caractéristique sélectionnée appartient. Vous pouvez cliquer sur un nom de segment pour afficher des détails sur ce segment.

![](assets/traitSegments.png)

## Journal d'audit/historique des caractéristiques {#trait-audit-history}

Pour les caractéristiques basées sur des règles et intégrées, les [!UICONTROL Trait Expression Change History] dix dernières modifications apportées aux règles d'expression de caractéristique et à ceux qui les ont créées sont les suivantes. Si votre caractéristique comporte plus de 10 modifications, cliquez sur **[!UICONTROL Export to CSV]** pour télécharger le journal d'audit complet. Le journal d'audit n'est pas disponible pour les caractéristiques d'un dossier ou d'un algorithme.

>[!NOTE]
>
>[!UICONTROL Not Available] dans [!UICONTROL By User] la colonne signifie que le compte de cet utilisateur a été supprimé.

![](assets/traitHistory.png)