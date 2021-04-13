---
description: Présentation et flux de travail pour les acheteurs de données qui souhaitent acheter des données tierces à partir de l’Audience Manager
seo-description: Présentation et flux de travail pour les acheteurs de données qui souhaitent acheter des données tierces à partir de l’Audience Manager
seo-title: Audience Marketplace pour les acheteurs de données
solution: Audience Manager
title: Audience Marketplace pour les acheteurs de données
uuid: f505b5f4-4231-4e84-993a-cd64128b540f
feature: Audience Marketplace
exl-id: 9d6a7fda-f79f-41ad-9654-3ebcf9028cc2
translation-type: tm+mt
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '750'
ht-degree: 3%

---

# [!UICONTROL Audience Marketplace] pour les acheteurs de données  {#audience-marketplace-for-data-buyers}

Présentation et flux de travail pour les acheteurs de données qui souhaitent acheter des données tierces à partir de [!DNL Audience Manager].

>[!NOTE]
>[Les autorisations basées sur le rôle ](../../../reporting/reports-dashboard.md) contrôlent l&#39;accès aux fonctionnalités [!UICONTROL Audience Marketplace].
>
>* Les administrateurs peuvent créer des flux de données, gérer les abonnés et s’abonner à des flux de données.
>* Les utilisateurs peuvent uniquement rechercher et vue des flux.


## Le [!UICONTROL Marketplace] : À propos de {#about-marketplace}

[!UICONTROL Marketplace] est une fonction [!DNL Audience Manager] destinée aux acheteurs de données qui liste les flux de données auxquels vous pouvez vous abonner. Il liste des flux de données privés à débit fixe, [!DNL CPM]. Ces flux sont fournis par des fournisseurs tiers qui utilisent [!DNL Audience Manager] pour vendre des données.

Dans [!UICONTROL Marketplace], les outils de rapports vous permettent de suivre l’utilisation des flux et le chevauchement entre votre [!UICONTROL traits] et ceux d’un flux de données abonné. Enfin, avec [!UICONTROL Audience Marketplace], [!DNL Adobe] prend en charge les factures et les paiements de frais (bien que vous deviez vous auto-déclarer l&#39;utilisation lorsque vous vous abonnez à un flux [!DNL CPM]). Ces fonctionnalités vous permettent de trouver des sources de données efficaces sans perdre de temps à rechercher un fournisseur de données.

>[!TIP]
>
>Utilisez l’**[Adobe Audience Finder](https://www.adobe-audience-finder.com/)** pour trouver des flux de données de haute qualité auxquels vous pouvez vous abonner. Ensuite, revenez dans l&#39;interface utilisateur [!DNL Audience Manager] ou utilisez l&#39;[Audience Marketplace Buyer API](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API) pour vous abonner aux flux que vous avez trouvés.

![acheteur-marché-aperçu](assets/buyer-marketplace-overview.png)

La liste [!UICONTROL Marketplace] contient des informations que vous pouvez trier et rechercher pour trouver le flux de données qui vous convient. Les éléments de la liste de l&#39;acheteur [!UICONTROL Marketplace] sont les suivants :

* **[!UICONTROL Search]**: Recherchez les flux de données par nom ou par description de texte.
* **[!UICONTROL Similar Traits]**: Indique le nombre de rapports similaires  [!UICONTROL traits] provenant d’un flux de données. Cette colonne s’affiche après avoir saisi [!UICONTROL trait] ou [!UICONTROL segment] pour filtrer par dans la section **[!UICONTROL Similarity To]**.
* **[!UICONTROL Name]**: Nom du flux de données.
* **[!UICONTROL Description]**: Informations relatives au contenu d’un flux de données.
* **[!UICONTROL Provider]**: Nom du fournisseur de données.
* **[!UICONTROL Traits]**: Numéro d’un  [!UICONTROL traits] flux de données.
* **[!UICONTROL 30 Day Provider Unique Users]**: Nombre d’utilisateurs uniques vus au cours des 30 derniers jours.
* **[!UICONTROL 30 Day Overlapped Uniques]**: Nombre d’utilisateurs de votre compte qui chevauchent les utilisateurs du compte du fournisseur.
* **[!UICONTROL Feed Overlap]**: La valeur unique de 30 jours chevauchée, affichée en pourcentages, calculée comme suit : Acheteur de données 30 jours de valeurs uniques chevauchées / Acheteur de données 30 jours de valeurs uniques) x 100.
* **[!UICONTROL Private Feeds]**: Voir Flux [ de données ](../../../features/audience-marketplace/marketplace-private-feeds.md)privés.
* **[!UICONTROL Currently Subscribed Plan Count]**: Nombre d’abonnements que vous avez avec un fournisseur de données.

 

Pour trouver facilement les meilleurs flux de données en fonction de vos besoins, utilisez les filtres suivants disponibles sur le côté gauche de la page [!UICONTROL Marketplace] :

* **[!UICONTROL Similarity To]**: Filtrez les flux de données en fonction de leur similarité avec un  [!UICONTROL trait] ou  [!UICONTROL segment] l’un de vos choix. Lorsque vous entrez [!UICONTROL trait] ou le segment à comparer, vous pouvez utiliser l&#39;ID [!UICONTROL trait] ou [!UICONTROL segment], ou leurs noms respectifs.
* **[!UICONTROL Similarity Cutoff]**: Faites glisser le curseur pour filtrer les flux de données en fonction de leur degré de similitude  [!UICONTROL traits] avec votre sélection  [!UICONTROL trait] ou votre  [!UICONTROL segment]sélection. Pour en savoir plus sur les [!UICONTROL trait] scores de similarité, voir [Score de similarité de caractéristiques](../../segments/trait-recommendations.md#trait-similarity-score)
* **[!UICONTROL Subscription Status]**: Filtrez les flux de données en fonction de l’état de votre abonnement.
* **[!UICONTROL Plan Use Case]**: Filtrez les flux de données en fonction de leurs cas d’utilisation pris en charge :  **[!UICONTROL Activation]**,  **[!UICONTROL Segments and Overlap]** et  **[!UICONTROL Modelling]**.
* **[!UICONTROL Plan Unit]**: Filtrez les flux de données en fonction de leur type de tarification.

## Recherche de [!UICONTROL Traits] {#finding-similar-traits} similaires

[!UICONTROL Audience Marketplace] vous permet de rechercher  [!UICONTROL traits] à partir de divers flux de données, en fonction de leur similarité avec votre  [!UICONTROL traits] ou vos segments existants. Voici comment procéder :

1. Accédez à **[!UICONTROL Audience Marketplace]** > **[!UICONTROL Marketplace]**.
2. Utilisez le sélecteur **[!UICONTROL Similarity To]** pour choisir entre un filtrage basé sur [!UICONTROL trait] ou [!UICONTROL segment]. Vous pouvez filtrer en fonction de [!UICONTROL trait]/[!UICONTROL segment] ID ou nom. La zone de recherche affiche automatiquement les suggestions pertinentes en fonction de vos entrées.
3. Une fois que vous avez identifié la caractéristique ou le segment par lequel vous souhaitez filtrer, cliquez dessus dans la liste de suggestions.
4. Pour réduire les résultats, utilisez le curseur **[!UICONTROL Similarity Cutoff]** pour passer de [!UICONTROL traits] moins similaire à  à des résultats plus similaires.

Une fois le filtrage terminé, une nouvelle colonne s’affiche dans la page de résultats : **[!UICONTROL Similar Traits]**. Cette colonne indique le nombre de [!UICONTROL traits] similaires à celui par lequel vous avez filtré, pour chaque flux de données qui satisfait aux critères de filtrage.

Pour afficher la liste complète des caractéristiques similaires, cliquez sur le nombre dans la colonne **[!UICONTROL Similar Traits]**.

>[!NOTE]
>
> L’Audience Marketplace affiche les 500 premiers résultats similaires [!UICONTROL trait] provenant de l’ensemble des flux de données.

Regardez la vidéo ci-dessous pour un aperçu complet de la façon de trouver des [!UICONTROL traits] similaires.

>[!VIDEO](https://video.tv.adobe.com/v/29370/)

## Flux de données privés {#private-data-feeds}

Dans la liste [!UICONTROL Marketplace], le nom du fournisseur et les données [!UICONTROL trait] sont parfois marqués comme privés. Ceci indique un [flux de données privé](../../../features/audience-marketplace/marketplace-private-feeds.md). Un flux de données privé permet aux vendeurs de limiter l’accès des acheteurs à leurs données. Les vendeurs peuvent rendre les flux privés lorsqu&#39;ils proposent des offres spéciales, des rabais ou lorsque la confidentialité et le contrôle d&#39;accès sont importants pour eux. En tant qu&#39;acheteur, vous devez envoyer une demande d&#39;abonnement au vendeur si vous souhaitez accéder à un flux privé. Voir [S’abonner à un flux de données privé](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) pour plus d’informations.

>[!MORELIKETHIS]
>
>* [Présentation de la page des détails de la formule d’Audience Marketplace](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details) (en anglais)
>* [Remises pour les acheteurs de données](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)

