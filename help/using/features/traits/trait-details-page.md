---
description: La page de détails d’une caractéristique individuelle fournit un aperçu des informations telles que le nom, l’identifiant, les mesures de performances, les expressions qui définissent la caractéristique, les segments auxquels elle appartient et le journal d’audit de la caractéristique. Pour afficher ces détails, accédez à Audience Data > Caractéristiques et cliquez sur le nom de la caractéristique que vous souhaitez utiliser.
seo-description: La page de détails d’une caractéristique individuelle fournit un aperçu des informations telles que le nom, l’identifiant, les mesures de performances, les expressions qui définissent la caractéristique, les segments auxquels elle appartient et le journal d’audit de la caractéristique. Pour afficher ces détails, accédez à Audience Data > Caractéristiques et cliquez sur le nom de la caractéristique que vous souhaitez utiliser.
seo-title: Page Détails des caractéristiques
solution: Audience Manager
title: Page Détails des caractéristiques
uuid: 23301376-c1cc-4778-b8c4-9831f6739db9
keywords: ventilation de type d’identité, ventilation d’identité, rapport d’identité d’audience, multi-appareils, identifiant multi-appareils, identifiant d’appareil
feature: 'Caractéristiques '
exl-id: c0b4791f-885e-4b14-b7e8-3c2d618fb80e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '671'
ht-degree: 1%

---

# [!UICONTROL Trait] Page Détails {#trait-details-page}

La page Détails d’une [!UICONTROL trait] individuelle fournit un aperçu des détails [!UICONTROL trait], tels que le nom [!UICONTROL trait], l’identifiant, les mesures de performances, les expressions qui définissent [!UICONTROL trait], les segments auxquels il appartient et le journal d’audit [!UICONTROL trait]. Pour afficher ces détails, accédez à **[!UICONTROL Audience Data]** > **[!UICONTROL Traits]** et cliquez sur le nom de la balise [!UICONTROL trait] que vous souhaitez utiliser.

## [!UICONTROL Trait] Outils de gestion {#trait-management-tools}

La partie supérieure de la page de détails [!UICONTROL trait] héberge les outils que vous pouvez utiliser pour gérer vos [!UICONTROL traits] :

1. **[!UICONTROL Add New]**: Utilisez cette option pour créer  [!UICONTROL rule-based],  [!UICONTROL algorithmic] ou  [!UICONTROL onboarded traits].
2. **[!UICONTROL Edit]**: Utilisez cette option pour modifier la configuration de la  [!UICONTROL trait]active.
3. **[!UICONTROL Delete]**: Utilisez cette option pour supprimer le  [!UICONTROL trait] de votre compte d’Audience Manager.
4. **[!UICONTROL Marketplace Recommendations]**: Utilisez cette option pour trouver  [!UICONTROL traits] la même chose que celle que vous consultez, à partir des frais de  [!UICONTROL Audience Marketplace] données auxquels vous n’êtes pas abonné. Voir [Audience Marketplace pour les acheteurs de données](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) pour savoir comment naviguer dans [!UICONTROL Marketplace] et trouver des caractéristiques similaires.

![basic-trait-information](assets/basic-trait-information.png)

## [!UICONTROL Trait] Informations {#basics}

La section [!UICONTROL Trait Information] affiche des détails sur les champs obligatoires et facultatifs que vous avez renseignés lors de la création de [!UICONTROL trait]. Cela inclut des éléments tels que le type [!UICONTROL trait], l’ID [!UICONTROL trait], la description, [!UICONTROL data source] et d’autres métadonnées. Ces détails varient selon le type [!UICONTROL trait] ([!UICONTROL folder], [!UICONTROL onboarded] ou [!UICONTROL rule-based]).

## [!UICONTROL Trait Graph] {#trait-graph}

[!UICONTROL Trait Graph] fournit des mesures de performances en un coup d’oeil pour la [!UICONTROL trait] sélectionnée. Placez le curseur sur une ligne de tendance pour afficher des données supplémentaires pour la [!UICONTROL trait] sélectionnée.

[!UICONTROL Unique Trait Realizations] représentent un nombre d’utilisateurs uniques qui ont ajouté ceci  [!UICONTROL trait] à leur profil au cours de la période donnée. [!UICONTROL Total Trait Population] indique le nombre d’utilisateurs uniques actuellement qualifiés pour cette [!UICONTROL trait].

Pour [!UICONTROL rule-based traits], la qualification [!UICONTROL trait] se produit en temps réel, car les utilisateurs sont qualifiés pour une [!UICONTROL trait] dans leur navigateur.

Pour [!UICONTROL onboarded traits], la qualification [!UICONTROL trait] se produit après le traitement d’un fichier entrant, c’est-à-dire que le fichier entrant est [ajouté à l’Audience Manager](../../faq/faq-inbound-data-ingestion.md) et c’est lorsque la qualification [!UICONTROL trait] se produit.

La section [!UICONTROL Trait Graph] présente les informations suivantes :

* **[!UICONTROL Show results by]**
   * **[!UICONTROL Cross-Device ID]**: sélectionnez cette option pour afficher les résultats pour  [!UICONTROL traits] qui collectent des données pour les profils authentifiés. Lorsque vous sélectionnez cette option, seules les données du rapport [!UICONTROL Cross-Device ID] s’affichent, et aucune donnée ne sera présente sous le rapport [!UICONTROL Device ID].
   * **[!UICONTROL Device ID]**: sélectionnez cette option pour afficher les résultats pour  [!UICONTROL traits] qui collectent des données pour les profils d’appareil. Lorsque vous sélectionnez cette option, seules les données du rapport [!UICONTROL Device ID] s’affichent, et aucune donnée ne sera présente sous le rapport [!UICONTROL Cross-Device ID].

      ![trait-graph](assets/trait-summary.gif)

* **[!UICONTROL Unique Trait Realizations]**: Nombre d’utilisateurs uniques qui ont ajouté ceci  [!UICONTROL trait] à leur profil au cours de la période donnée.
* **[!UICONTROL Total Trait Population]**: Le nombre d’utilisateurs uniques actuellement qualifiés pour cela  [!UICONTROL trait].

* **[!UICONTROL Identity Type Breakdown]**: Les trois premières entrées montrent les trois premières  [!UICONTROL cross-device data sources] avec le plus grand nombre de personnes qualifiées pour  [!UICONTROL trait], dans l&#39;ordre décroissant. La quatrième entrée affiche la somme de tous les autres [!DNL DPUUIDs] ([!DNL CRM IDs]) qualifiés pour la [!UICONTROL trait], de la [!UICONTROL cross-device data sources] qui ne figurent pas dans les trois premiers. Ce rapport s’affiche uniquement si vous sélectionnez [!UICONTROL Cross-device ID] dans le menu déroulant [!UICONTROL Show Results By] en haut à droite de la page. L’option de liste déroulante par défaut est [!UICONTROL Device ID], où ce rapport n’est pas affiché.

   ![trait-graph](assets/trait-identity.png)

   >[!NOTE]
   >
   >L’Audience Manager n’affiche le rapport [!UICONTROL Identity Type Breakdown] que si [!UICONTROL cross-device] ID est qualifié pour la balise [!UICONTROL trait].

   >[!VIDEO](https://video.tv.adobe.com/v/27977/)

## [!UICONTROL Trait] Expression {#trait-expression}

La section [!UICONTROL Trait Expression] indique les critères que les utilisateurs doivent remplir pour être éligibles à la [!UICONTROL trait]. Ces règles sont définies lorsque vous [créez ou modifiez une caractéristique](../../features/traits/about-trait-builder.md).

![](assets/traitExpression.png)

## [!UICONTROL Trait]Segments  {#trait-segments}

La section [!UICONTROL Segments with this Trait] répertorie tous les segments auxquels la [!UICONTROL trait] sélectionnée appartient. Vous pouvez cliquer sur le nom d’un segment pour en afficher les détails.

![](assets/traitSegments.png)

## [!UICONTROL Trait] Journal d’audit/d’historique {#trait-audit-history}

Pour [!UICONTROL rule-based] et [!UICONTROL onboarded traits], la section [!UICONTROL Trait Expression Change History] présente les 10 dernières modifications apportées aux règles d’expression [!UICONTROL trait] et à leur auteur. Si votre [!UICONTROL trait] comporte plus de 10 modifications, cliquez sur **[!UICONTROL Export to CSV]** pour télécharger l’intégralité du journal d’audit. Le journal d’audit n’est pas disponible pour [!UICONTROL folder] ou [!UICONTROL algorithmic traits].

>[!NOTE]
>
>[!UICONTROL Not Available] dans la  [!UICONTROL By User] colonne , le compte de cet utilisateur a été supprimé.

![](assets/traitHistory.png)
