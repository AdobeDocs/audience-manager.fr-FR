---
description: La page de détails d’une caractéristique individuelle donne un aperçu des informations telles que le nom de la caractéristique, l’identifiant, les mesures de performances, les expressions qui définissent la caractéristique, les segments auxquels elle appartient et le journal d’audit de la caractéristique. Pour afficher ces détails, accédez à Données d’audience > Caractéristiques et cliquez sur le nom de la caractéristique que vous souhaitez utiliser.
seo-description: The details page for an individual trait provides overview of information like the trait name, ID, performance metrics, expressions that define the trait, segments it belongs to, and the trait audit log. To vew these details, go to Audience Data > Traits and click the name of the trait you want to work with.
seo-title: Trait Details Page
solution: Audience Manager
title: Page de détails des caractéristiques
uuid: 23301376-c1cc-4778-b8c4-9831f6739db9
keywords: répartition des types d’identité, répartition des identités, rapports d’identité d’audience, entre appareils, ID entre appareils, ID d’appareil
feature: Traits
exl-id: c0b4791f-885e-4b14-b7e8-3c2d618fb80e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '616'
ht-degree: 0%

---

# Page [!UICONTROL Trait] détails de l’application {#trait-details-page}

La page de détails d’un [!UICONTROL trait] individuel fournit un aperçu des détails du [!UICONTROL trait], tels que le nom du [!UICONTROL trait], l’identifiant, les mesures de performances, les expressions qui définissent le [!UICONTROL trait], les segments auxquels il appartient et le journal d’audit [!UICONTROL trait]. Pour afficher ces détails, accédez à **[!UICONTROL Audience Data]** > **[!UICONTROL Traits]** et cliquez sur le nom du [!UICONTROL trait] avec lequel vous souhaitez travailler.

## Outils de gestion des [!UICONTROL Trait] {#trait-management-tools}

La partie supérieure de la page des détails du [!UICONTROL trait] héberge les outils que vous pouvez utiliser pour gérer vos [!UICONTROL traits] :

1. **[!UICONTROL Add New]** : utilisez cette option pour créer des [!UICONTROL rule-based], des [!UICONTROL algorithmic] ou des [!UICONTROL onboarded traits].
2. **[!UICONTROL Edit]** : utilisez cette option pour modifier la configuration du [!UICONTROL trait] actif.
3. **[!UICONTROL Delete]** : utilisez cette option pour supprimer le [!UICONTROL trait] actuel de votre compte Audience Manager.
4. **[!UICONTROL Marketplace Recommendations]** : utilisez cette option pour trouver des [!UICONTROL traits] similaires à celles que vous consultez, parmi [!UICONTROL Audience Marketplace] frais de données auxquels vous n&#39;êtes pas abonné. Consultez [Audience Marketplace pour les acheteurs de données](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) pour savoir comment naviguer dans le [!UICONTROL Marketplace] et trouver des caractéristiques similaires.

![informations-caractéristiques de base](assets/basic-trait-information.png)

## Informations [!UICONTROL Trait] {#basics}

La section [!UICONTROL Trait Information] affiche des détails sur les champs obligatoires et facultatifs que vous avez renseignés lors de la création du [!UICONTROL trait]. Cela inclut des éléments tels que le type de [!UICONTROL trait], l’ID de [!UICONTROL trait], la description, la [!UICONTROL data source] et d’autres métadonnées. Ces détails varient en fonction du type de [!UICONTROL trait] ([!UICONTROL folder], [!UICONTROL onboarded] ou [!UICONTROL rule-based]).

## [!UICONTROL Trait Graph] {#trait-graph}

Le [!UICONTROL Trait Graph] fournit des mesures de performances en un coup d’œil pour les [!UICONTROL trait] sélectionnés. Placez le curseur sur une ligne de tendance pour afficher des données supplémentaires pour le [!UICONTROL trait] sélectionné.

[!UICONTROL Unique Trait Realizations] représente le nombre d’utilisateurs uniques qui ont ajouté ce [!UICONTROL trait] à leur profil au cours de la période donnée. La [!UICONTROL Total Trait Population] indique le nombre d’utilisateurs uniques actuellement qualifiés pour ce [!UICONTROL trait].

Par [!UICONTROL rule-based traits], [!UICONTROL trait] qualification se produit en temps réel, car les utilisateurs remplissent les critères d’une [!UICONTROL trait] dans leur navigateur.

Par [!UICONTROL onboarded traits], [!UICONTROL trait] qualification se produit une fois qu’un fichier entrant est traité, c’est-à-dire que le fichier entrant est [introduit dans Audience Manager](../../faq/faq-inbound-data-ingestion.md) et c’est à ce moment que la qualification [!UICONTROL trait] se produit.

La [!UICONTROL Trait Graph] affiche les informations suivantes :

* **[!UICONTROL Show results by]**
   * **[!UICONTROL Cross-Device ID]** : sélectionnez cette option pour afficher les résultats des [!UICONTROL traits] qui collectent des données pour les profils authentifiés. Lorsque vous sélectionnez cette option, seules les données du rapport [!UICONTROL Cross-Device ID] s’affichent et aucune donnée n’est présente sous le rapport [!UICONTROL Device ID].
   * **[!UICONTROL Device ID]** : sélectionnez cette option pour afficher les résultats des [!UICONTROL traits] qui collectent des données pour les profils d’appareils. Lorsque vous sélectionnez cette option, seules les données du rapport [!UICONTROL Device ID] s’affichent et aucune donnée n’est présente sous le rapport [!UICONTROL Cross-Device ID].

     ![trait-graph](assets/trait-summary.gif)

* **[!UICONTROL Unique Trait Realizations]** : nombre d’utilisateurs uniques ayant ajouté ce [!UICONTROL trait] à leur profil au cours de la période donnée.
* **[!UICONTROL Total Trait Population]** : nombre d’utilisateurs uniques actuellement qualifiés pour ce [!UICONTROL trait].

* **[!UICONTROL Identity Type Breakdown]** : les trois premières entrées affichent, par ordre décroissant, les trois premières [!UICONTROL cross-device data sources] avec le nombre de population le plus élevé remplissant les critères de la [!UICONTROL trait]. La quatrième entrée affiche la somme de tous les autres [!DNL DPUUIDs] ([!DNL CRM IDs]) qui remplissent les critères de la [!UICONTROL trait], à partir des [!UICONTROL cross-device data sources] qui ne figurent pas dans les trois premiers. Ce rapport s’affiche uniquement si vous sélectionnez [!UICONTROL Cross-device ID] dans le menu déroulant [!UICONTROL Show Results By] en haut à droite de la page. L’option de liste déroulante par défaut est [!UICONTROL Device ID], où ce rapport n’est pas affiché.

  ![trait-graph](assets/trait-identity.png)

  >[!NOTE]
  >
  >Audience Manager n’affiche le rapport [!UICONTROL Identity Type Breakdown] que si vous disposez de [!UICONTROL cross-device] ID qualifiés pour le [!UICONTROL trait].

  >[!VIDEO](https://video.tv.adobe.com/v/32077?captions=fre_fr)

## Expression [!UICONTROL Trait] {#trait-expression}

La section [!UICONTROL Trait Expression] vous indique les critères que les utilisateurs doivent remplir pour pouvoir participer au [!UICONTROL trait]. Ces règles sont définies lorsque vous [créez ou modifiez une caractéristique](../../features/traits/about-trait-builder.md).

![](assets/traitExpression.png)

## [!UICONTROL Trait] Segments {#trait-segments}

La section [!UICONTROL Segments with this Trait] répertorie tous les segments auxquels appartient la [!UICONTROL trait] sélectionnée. Vous pouvez cliquer sur le nom d’un segment pour en afficher les détails.

![](assets/traitSegments.png)

## Journal d’audit/d’historique [!UICONTROL Trait] {#trait-audit-history}

Pour [!UICONTROL rule-based] et [!UICONTROL onboarded traits], la [!UICONTROL Trait Expression Change History] vous montre les 10 dernières modifications apportées aux règles d’expression [!UICONTROL trait] et qui les a effectuées. Si votre [!UICONTROL trait] comporte plus de 10 modifications, cliquez sur **[!UICONTROL Export to CSV]** pour télécharger l’intégralité du journal d’audit. Le journal d’audit n’est pas disponible pour [!UICONTROL folder] ou [!UICONTROL algorithmic traits].

>[!NOTE]
>
>[!UICONTROL Not Available] dans la colonne [!UICONTROL By User] signifie que le compte de cet utilisateur a été supprimé.

![](assets/traitHistory.png)
