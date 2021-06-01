---
description: Présentation et workflow pour les acheteurs de données qui souhaitent acheter des données tierces dans Audience Manager
seo-description: Présentation et workflow pour les acheteurs de données qui souhaitent acheter des données tierces dans Audience Manager
seo-title: Audience Marketplace pour les acheteurs de données
solution: Audience Manager
title: Audience Marketplace pour les acheteurs de données
uuid: f505b5f4-4231-4e84-993a-cd64128b540f
feature: Audience Marketplace
exl-id: 9d6a7fda-f79f-41ad-9654-3ebcf9028cc2
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '750'
ht-degree: 3%

---

# [!UICONTROL Audience Marketplace] pour les acheteurs de données  {#audience-marketplace-for-data-buyers}

Présentation et workflow pour les acheteurs de données qui souhaitent acheter des données tierces dans [!DNL Audience Manager].

>[!NOTE]
>[Autorisations basées sur les rôles](../../../reporting/reports-dashboard.md) contrôler l’accès aux fonctionnalités [!UICONTROL Audience Marketplace].
>
>* Les administrateurs peuvent créer des flux de données, gérer les abonnés et s’abonner aux flux de données.
>* Les utilisateurs peuvent uniquement rechercher et afficher des flux.


## Le [!UICONTROL Marketplace] : À propos de {#about-marketplace}

[!UICONTROL Marketplace] est une fonction [!DNL Audience Manager] destinée aux acheteurs de données qui répertorie les flux de données auxquels vous pouvez vous abonner. Il répertorie les flux de données privés, [!DNL CPM] et de taux plate. Ces flux sont fournis par des fournisseurs tiers qui utilisent [!DNL Audience Manager] pour vendre des données.

Dans la section [!UICONTROL Marketplace], les outils de création de rapports vous permettent de suivre l’utilisation des flux et le chevauchement entre vos [!UICONTROL traits] et ceux d’un flux de données abonné. Enfin, avec [!UICONTROL Audience Marketplace], [!DNL Adobe] s’occupe des factures et des paiements de frais (bien que vous ayez à autodéclarer l’utilisation lorsque vous vous abonnez à un flux [!DNL CPM]). Ces fonctionnalités vous permettent de trouver des sources de données efficaces sans perdre de temps à rechercher un fournisseur de données.

>[!TIP]
>
>Utilisez **[Adobe d’Audience Finder](https://www.adobe-audience-finder.com/)** pour trouver des flux de données de haute qualité auxquels vous pouvez vous abonner. Ensuite, revenez dans l’interface utilisateur [!DNL Audience Manager] ou utilisez l’ [API Audience Marketplace Buyer](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API) pour vous abonner aux flux que vous avez trouvés.

![customer-marketplace-overview](assets/buyer-marketplace-overview.png)

La liste [!UICONTROL Marketplace] contient des informations que vous pouvez trier et rechercher pour trouver le flux de données qui vous convient. Les articles de la [!UICONTROL Marketplace] liste d&#39;acheteurs incluent :

* **[!UICONTROL Search]**: Recherchez les flux de données par nom ou par description textuelle.
* **[!UICONTROL Similar Traits]**: Indique le nombre de données similaires  [!UICONTROL traits] provenant d’un flux de données. Cette colonne s’affiche une fois que vous avez entré [!UICONTROL trait] ou [!UICONTROL segment] pour filtrer selon dans la section **[!UICONTROL Similarity To]**.
* **[!UICONTROL Name]**: Nom du flux de données.
* **[!UICONTROL Description]**: Informations sur le contenu d’un flux de données.
* **[!UICONTROL Provider]**: Nom du fournisseur de données.
* **[!UICONTROL Traits]**: Nombre de  [!UICONTROL traits] dans un flux de données.
* **[!UICONTROL 30 Day Provider Unique Users]**: Nombre d’utilisateurs uniques vus au cours des 30 derniers jours.
* **[!UICONTROL 30 Day Overlapped Uniques]**: Nombre d’utilisateurs de votre compte qui chevauchent les utilisateurs du compte du fournisseur.
* **[!UICONTROL Feed Overlap]**: La valeur unique de 30 jours chevauchée, affichée en pourcentages, calculée comme suit : Valeurs uniques de 30 jours pour l’acheteur de données/Valeurs uniques de 30 jours pour l’acheteur de données) x 100.
* **[!UICONTROL Private Feeds]**: Voir Flux de données  [privés](../../../features/audience-marketplace/marketplace-private-feeds.md).
* **[!UICONTROL Currently Subscribed Plan Count]**: Le nombre d’abonnements que vous avez avec un fournisseur de données.

 

Pour trouver facilement les meilleurs flux de données en fonction de vos besoins, utilisez les filtres suivants disponibles sur le côté gauche de la page [!UICONTROL Marketplace] :

* **[!UICONTROL Similarity To]**: Filtrez les flux de données en fonction de leur similarité avec un  [!UICONTROL trait] ou  [!UICONTROL segment] de votre choix. Lorsque vous saisissez le [!UICONTROL trait] ou le segment à comparer, vous pouvez utiliser l’ID [!UICONTROL trait] ou [!UICONTROL segment], ou leurs noms respectifs.
* **[!UICONTROL Similarity Cutoff]**: Faites glisser le curseur pour filtrer les flux de données en fonction de leur  [!UICONTROL traits] ressemblance avec votre  [!UICONTROL trait]  ou  [!UICONTROL segment]sélectionné(e). Pour en savoir plus sur les [!UICONTROL trait] scores de similarité, voir [Score de similarité de caractéristiques](../../segments/trait-recommendations.md#trait-similarity-score)
* **[!UICONTROL Subscription Status]**: Filtrez les flux de données en fonction de l’état de votre abonnement.
* **[!UICONTROL Plan Use Case]**: Filtrez les flux de données en fonction de leurs cas d’utilisation pris en charge :  **[!UICONTROL Activation]**,  **[!UICONTROL Segments and Overlap]** et  **[!UICONTROL Modelling]**.
* **[!UICONTROL Plan Unit]**: Filtrez les flux de données en fonction de leur type de tarification.

## Recherche de [!UICONTROL Traits] {#finding-similar-traits}

[!UICONTROL Audience Marketplace] vous donne la possibilité de rechercher  [!UICONTROL traits] à partir de divers flux de données, en fonction de leur similarité avec vos segments  [!UICONTROL traits] ou existants. Procédez comme suit :

1. Accédez à **[!UICONTROL Audience Marketplace]** > **[!UICONTROL Marketplace]**.
2. Utilisez le sélecteur **[!UICONTROL Similarity To]** pour choisir entre le filtrage basé sur un [!UICONTROL trait] ou [!UICONTROL segment]. Vous pouvez filtrer selon l’ID ou le nom [!UICONTROL trait]/[!UICONTROL segment]. La zone de recherche affiche automatiquement les suggestions pertinentes en fonction de votre saisie.
3. Une fois que vous avez identifié la caractéristique ou le segment par lequel vous souhaitez filtrer, cliquez dessus dans la liste de suggestions.
4. Pour réduire les résultats, utilisez le curseur **[!UICONTROL Similarity Cutoff]** pour passer de [!UICONTROL traits] moins similaire à des résultats plus similaires.

Une fois le filtrage terminé, une nouvelle colonne s’affiche dans la page des résultats : **[!UICONTROL Similar Traits]**. Cette colonne indique le nombre de [!UICONTROL traits] similaires à celui par lequel vous avez filtré, pour chaque flux de données répondant aux critères de filtrage.

Pour afficher la liste complète des caractéristiques similaires, cliquez sur le nombre dans la colonne **[!UICONTROL Similar Traits]**.

>[!NOTE]
>
> Audience Marketplace affiche les 500 premiers résultats similaires [!UICONTROL trait] provenant de l’ensemble des flux de données.

Regardez la vidéo ci-dessous pour un aperçu complet de la façon de trouver des [!UICONTROL traits] similaires.

>[!VIDEO](https://video.tv.adobe.com/v/29370/)

## Flux de données privés {#private-data-feeds}

Dans la liste [!UICONTROL Marketplace], le nom du fournisseur et les données [!UICONTROL trait] sont parfois marqués comme privés. Cela indique un [flux de données privé](../../../features/audience-marketplace/marketplace-private-feeds.md). Un flux de données privé permet aux vendeurs de limiter l’accès des acheteurs à leurs données. Les vendeurs peuvent rendre les flux privés lorsqu’ils proposent des offres spéciales, des remises ou lorsque la confidentialité et le contrôle d’accès sont importants pour eux. En tant qu&#39;acheteur, vous devez envoyer une demande d&#39;abonnement au vendeur si vous souhaitez accéder à un flux privé. Voir [S’abonner à un flux de données privé](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) pour plus d’informations.

>[!MORELIKETHIS]
>
>* [Présentation de la page des détails de la formule d’Audience Marketplace (en anglais)](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)
* [Remises pour les acheteurs de données](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)

