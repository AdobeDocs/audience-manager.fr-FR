---
description: La page de détails d’une caractéristique individuelle fournit un aperçu des informations telles que le nom, l’identifiant, les mesures de performances, les expressions qui définissent la caractéristique, les segments auxquels elle appartient et le journal d’audit de la caractéristique. Pour afficher ces détails, accédez à Audience Data > Caractéristiques et cliquez sur le nom de la caractéristique que vous souhaitez utiliser.
seo-description: The details page for an individual trait provides overview of information like the trait name, ID, performance metrics, expressions that define the trait, segments it belongs to, and the trait audit log. To vew these details, go to Audience Data > Traits and click the name of the trait you want to work with.
seo-title: Trait Details Page
solution: Audience Manager
title: Page Détails des caractéristiques
uuid: 23301376-c1cc-4778-b8c4-9831f6739db9
keywords: ventilation de type d’identité, ventilation d’identité, rapport d’identité d’audience, multi-appareils, identifiant multi-appareils, identifiant d’appareil
feature: Traits
exl-id: c0b4791f-885e-4b14-b7e8-3c2d618fb80e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '616'
ht-degree: 0%

---

# [!UICONTROL Trait] Page Détails {#trait-details-page}

La page de détails d’un [!UICONTROL trait] fournit un aperçu des détails [!UICONTROL trait], tels que le nom [!UICONTROL trait], l’identifiant, les mesures de performances, les expressions qui définissent le [!UICONTROL trait], les segments auxquels il appartient et le journal d’audit [!UICONTROL trait]. Pour afficher ces détails, accédez à **[!UICONTROL Audience Data]** > **[!UICONTROL Traits]** et cliquez sur le nom du [!UICONTROL trait] que vous souhaitez utiliser.

## [!UICONTROL Trait] outils de gestion {#trait-management-tools}

La partie supérieure de la page de détails [!UICONTROL trait] héberge les outils que vous pouvez utiliser pour gérer votre [!UICONTROL traits] :

1. **[!UICONTROL Add New]** : utilisez cette option pour créer [!UICONTROL rule-based], [!UICONTROL algorithmic] ou [!UICONTROL onboarded traits].
2. **[!UICONTROL Edit]** : utilisez cette option pour modifier la configuration de la [!UICONTROL trait] active.
3. **[!UICONTROL Delete]** : utilisez cette option pour supprimer le [!UICONTROL trait] actuel de votre compte d’Audience Manager.
4. **[!UICONTROL Marketplace Recommendations]** : utilisez cette option pour trouver [!UICONTROL traits] similaire à celui que vous consultez, à partir des [!UICONTROL Audience Marketplace] frais de données auxquels vous n’êtes pas abonné. Voir [Audience Marketplace pour les acheteurs de données](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) pour savoir comment naviguer dans [!UICONTROL Marketplace] et trouver des caractéristiques similaires.

![basic-trait-information](assets/basic-trait-information.png)

## [!UICONTROL Trait] Information {#basics}

La section [!UICONTROL Trait Information] affiche des détails sur les champs obligatoires et facultatifs que vous avez remplis lors de la création de [!UICONTROL trait]. Cela inclut des éléments tels que le type [!UICONTROL trait], l’ID [!UICONTROL trait], la description, [!UICONTROL data source] et d’autres métadonnées. Ces détails varient selon le type [!UICONTROL trait] ([!UICONTROL folder], [!UICONTROL onboarded] ou [!UICONTROL rule-based]).

## [!UICONTROL Trait Graph] {#trait-graph}

[!UICONTROL Trait Graph] fournit des mesures de performances en un coup d’oeil pour les [!UICONTROL trait] sélectionnés. Placez le curseur sur une ligne de tendance pour afficher des données supplémentaires pour le [!UICONTROL trait] sélectionné.

[!UICONTROL Unique Trait Realizations] représente un nombre d’utilisateurs uniques qui ont ajouté cet [!UICONTROL trait] à leur profil au cours de la période donnée. [!UICONTROL Total Trait Population] indique le nombre d’utilisateurs uniques actuellement qualifiés pour cet [!UICONTROL trait].

Pour [!UICONTROL rule-based traits], la qualification [!UICONTROL trait] se produit en temps réel, car les utilisateurs sont qualifiés pour un [!UICONTROL trait] dans leur navigateur.

Pour [!UICONTROL onboarded traits], la qualification [!UICONTROL trait] se produit après le traitement d&#39;un fichier entrant, c&#39;est-à-dire que le fichier entrant est [alimenté en Audience Manager](../../faq/faq-inbound-data-ingestion.md) et que c&#39;est à ce moment que la qualification [!UICONTROL trait] se produit.

Le [!UICONTROL Trait Graph] vous montre les informations suivantes :

* **[!UICONTROL Show results by]**
   * **[!UICONTROL Cross-Device ID]** : sélectionnez cette option pour afficher les résultats de [!UICONTROL traits] qui collectent des données pour les profils authentifiés. Lorsque vous sélectionnez cette option, seules les données du rapport [!UICONTROL Cross-Device ID] s’affichent, et aucune donnée ne sera présente sous le rapport [!UICONTROL Device ID].
   * **[!UICONTROL Device ID]** : sélectionnez cette option pour afficher les résultats de [!UICONTROL traits] qui collectent des données pour les profils d’appareil. Lorsque vous sélectionnez cette option, seules les données du rapport [!UICONTROL Device ID] s’affichent, et aucune donnée ne sera présente sous le rapport [!UICONTROL Cross-Device ID].

     ![trait-graph](assets/trait-summary.gif)

* **[!UICONTROL Unique Trait Realizations]** : nombre d’utilisateurs uniques qui ont ajouté cet [!UICONTROL trait] à leur profil au cours de la période donnée.
* **[!UICONTROL Total Trait Population]** : nombre d’utilisateurs uniques actuellement qualifiés pour cet [!UICONTROL trait].

* **[!UICONTROL Identity Type Breakdown]** : les trois premières entrées affichent les trois premières [!UICONTROL cross-device data sources] avec le plus grand nombre de population qualifiée pour [!UICONTROL trait], dans l’ordre décroissant. La quatrième entrée affiche la somme de tous les autres [!DNL DPUUIDs] ([!DNL CRM IDs]) qualifiés pour [!UICONTROL trait], des [!UICONTROL cross-device data sources] qui ne figurent pas dans les trois premiers. Ce rapport s’affiche uniquement si vous sélectionnez [!UICONTROL Cross-device ID] dans le menu déroulant [!UICONTROL Show Results By] en haut à droite de la page. L’option de liste déroulante par défaut est [!UICONTROL Device ID], où ce rapport n’est pas affiché.

  ![trait-graph](assets/trait-identity.png)

  >[!NOTE]
  >
  >L’Audience Manager n’affiche le rapport [!UICONTROL Identity Type Breakdown] que si [!UICONTROL cross-device] ID sont qualifiés pour [!UICONTROL trait].

  >[!VIDEO](https://video.tv.adobe.com/v/27977/)

## [!UICONTROL Trait] Expression {#trait-expression}

La section [!UICONTROL Trait Expression] vous montre les critères que les utilisateurs doivent remplir pour être éligibles à [!UICONTROL trait]. Ces règles sont définies lorsque vous [créez ou modifiez une caractéristique](../../features/traits/about-trait-builder.md).

![](assets/traitExpression.png)

## [!UICONTROL Trait] Segments {#trait-segments}

La section [!UICONTROL Segments with this Trait] répertorie tous les segments auxquels le [!UICONTROL trait] sélectionné appartient. Vous pouvez cliquer sur le nom d’un segment pour en afficher les détails.

![](assets/traitSegments.png)

## [!UICONTROL Trait] Journal d’audit/d’historique {#trait-audit-history}

Pour [!UICONTROL rule-based] et [!UICONTROL onboarded traits], le [!UICONTROL Trait Expression Change History] vous montre les 10 dernières modifications apportées aux règles d’expression [!UICONTROL trait] et qui les a effectuées. Si votre [!UICONTROL trait] comporte plus de 10 modifications, cliquez sur **[!UICONTROL Export to CSV]** pour télécharger le journal d’audit entier. Le journal d’audit n’est pas disponible pour [!UICONTROL folder] ou [!UICONTROL algorithmic traits].

>[!NOTE]
>
>[!UICONTROL Not Available] dans la colonne [!UICONTROL By User] signifie que le compte de cet utilisateur a été supprimé.

![](assets/traitHistory.png)
