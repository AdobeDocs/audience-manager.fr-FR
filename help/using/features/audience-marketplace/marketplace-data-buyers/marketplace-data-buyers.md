---
description: Présentation et flux de travail pour les acheteurs de données qui souhaitent acheter des données tierces à partir de l’Audience Manager
seo-description: Présentation et flux de travail pour les acheteurs de données qui souhaitent acheter des données tierces à partir de l’Audience Manager
seo-title: Audience Marketplace pour les acheteurs de données
solution: Audience Manager
title: Audience Marketplace pour les acheteurs de données
topic: DIL API
uuid: f505b5f4-4231-4e84-993a-cd64128b540f
translation-type: tm+mt
source-git-commit: 9a8c0650d3f00a95a8a1f05c248c21b420e727e0
workflow-type: tm+mt
source-wordcount: '748'
ht-degree: 1%

---


# [!UICONTROL Audience Marketplace] pour les acheteurs de données {#audience-marketplace-for-data-buyers}

Présentation et flux de travail pour les acheteurs de données qui souhaitent acheter des données tierces depuis [!DNL Audience Manager].

>[!NOTE]
>[Les autorisations](../../../reporting/reports-dashboard.md) basées sur les rôles contrôlent l’accès aux [!UICONTROL Audience Marketplace] fonctionnalités.
>
>* Les administrateurs peuvent créer des flux de données, gérer les abonnés et s’abonner à des flux de données.
>* Les utilisateurs peuvent uniquement rechercher et vue des flux.


## Le [!UICONTROL Marketplace]: A propos {#about-marketplace}

Cette [!UICONTROL Marketplace] [!DNL Audience Manager] fonctionnalité permet aux acheteurs de données de liste des flux de données auxquels vous pouvez vous abonner. Il liste des flux de données à taux fixe [!DNL CPM]et privés. Ces flux sont fournis par des fournisseurs tiers qui utilisent [!DNL Audience Manager] les données pour les vendre.

Dans la section [!UICONTROL Marketplace], les outils de rapports vous permettent de suivre l’utilisation des flux et le chevauchement entre votre [!UICONTROL traits] flux et ceux d’un flux de données abonné. Enfin, [!UICONTROL Audience Marketplace], [!DNL Adobe] prend en charge les factures et les paiements de frais (bien que vous deviez vous-même déclarer l’utilisation lors de votre abonnement à un [!DNL CPM] flux). Ces fonctionnalités vous permettent de trouver des sources de données efficaces sans perdre de temps à rechercher un fournisseur de données.

>[!TIP]
>
>Utilisez **[Adobe Audience Finder](https://www.adobe-audience-finder.com/)**pour trouver des flux de données de haute qualité auxquels vous pouvez vous abonner. Ensuite, revenez dans l’interface[!DNL Audience Manager]utilisateur ou utilisez l’API[Acheteur d’](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API)Audiences Marketplace pour vous abonner aux flux que vous avez trouvés.

![acheteur-marché-aperçu](assets/buyer-marketplace-overview.png)

La [!UICONTROL Marketplace] liste contient des informations que vous pouvez trier et rechercher pour trouver le flux de données qui vous convient. Les éléments de la liste de l&#39; [!UICONTROL Marketplace] acheteur sont les suivants :

* **[!UICONTROL Search]**: Recherchez les flux de données par nom ou par description textuelle.
* **[!UICONTROL Similar Traits]**: Indique le nombre de rapports similaires [!UICONTROL traits] provenant d’un flux de données. Cette colonne s’affiche une fois que vous avez entré un [!UICONTROL trait] filtre ou [!UICONTROL segment] pour le filtrer dans la **[!UICONTROL Similarity To]** section.
* **[!UICONTROL Name]**: Nom du flux de données.
* **[!UICONTROL Description]**: Informations relatives au contenu d’un flux de données.
* **[!UICONTROL Provider]**: Nom du fournisseur de données.
* **[!UICONTROL Traits]**: Nombre d’éléments [!UICONTROL traits] d’un flux de données.
* **[!UICONTROL 30 Day Provider Unique Users]**: Nombre d’utilisateurs uniques vus au cours des 30 derniers jours.
* **[!UICONTROL 30 Day Overlapped Uniques]**: Nombre d’utilisateurs de votre compte qui chevauchent les utilisateurs du compte du fournisseur.
* **[!UICONTROL Feed Overlap]**: La valeur unique de 30 jours chevauchée, affichée en pourcentages, calculée comme suit : Acheteur de données 30 jours de valeurs uniques chevauchées / Acheteur de données 30 jours de valeurs uniques) x 100.
* **[!UICONTROL Private Feeds]**: Voir Flux [de données](../../../features/audience-marketplace/marketplace-private-feeds.md)privés.
* **[!UICONTROL Currently Subscribed Plan Count]**: Nombre d’abonnements que vous avez avec un fournisseur de données.

 

Pour trouver facilement les meilleurs flux de données en fonction de vos besoins, utilisez les filtres suivants disponibles sur le côté gauche de la [!UICONTROL Marketplace] page :

* **[!UICONTROL Similarity To]**: Filtrez les flux de données en fonction de leur similarité avec un [!UICONTROL trait] ou [!UICONTROL segment] l’un de vos choix. Lorsque vous saisissez le segment [!UICONTROL trait] ou le segment à comparer, vous pouvez utiliser l’ [!UICONTROL trait] identifiant ou [!UICONTROL segment] l’identifiant ou leurs noms respectifs.
* **[!UICONTROL Similarity Cutoff]**: Faites glisser le curseur pour filtrer les flux de données en fonction de leur degré [!UICONTROL traits] de similitude avec votre sélection [!UICONTROL trait] ou [!UICONTROL segment]. Pour en savoir plus sur les scores de [!UICONTROL trait] [similarité, voir Score de similarité de caractéristiques](../../segments/trait-recommendations.md#trait-similarity-score)
* **[!UICONTROL Subscription Status]**: Filtrez les flux de données en fonction de l’état de votre abonnement.
* **[!UICONTROL Plan Use Case]**: Filtrez les flux de données en fonction de leurs cas d’utilisation pris en charge : **[!UICONTROL Activation]**, **[!UICONTROL Segments and Overlap]** et **[!UICONTROL Modelling]**.
* **[!UICONTROL Plan Unit]**: Filtrez les flux de données en fonction de leur type de tarification.

## Recherche similaire [!UICONTROL Traits] {#finding-similar-traits}

[!UICONTROL Audience Marketplace] vous permet de rechercher [!UICONTROL traits] à partir de divers flux de données, en fonction de leur similarité avec votre [!UICONTROL traits] ou vos segments existants. Voici comment procéder :

1. Accédez à **[!UICONTROL Audience Marketplace]** > **[!UICONTROL Marketplace]**.
2. Utilisez le **[!UICONTROL Similarity To]** sélecteur pour choisir entre le filtrage basé sur un [!UICONTROL trait] ou [!UICONTROL segment]. Vous pouvez filtrer en fonction de l’ [!UICONTROL trait]/[!UICONTROL segment] ID ou du nom. La zone de recherche affiche automatiquement les suggestions pertinentes en fonction de vos entrées.
3. Une fois que vous avez identifié la caractéristique ou le segment par lequel vous souhaitez filtrer, cliquez dessus dans la liste de suggestions.
4. Pour réduire les résultats, utilisez le **[!UICONTROL Similarity Cutoff]** curseur pour passer d’un résultat moins similaire [!UICONTROL traits]à un résultat plus similaire.

Une fois le filtrage terminé, une nouvelle colonne s’affiche dans la page de résultats : **[!UICONTROL Similar Traits]**. Cette colonne indique le nombre de flux de données similaires [!UICONTROL traits] à celui par lequel vous avez filtré, de chaque flux de données qui satisfait aux critères de filtrage.

Pour afficher la liste complète des caractéristiques similaires, cliquez sur le nombre dans la **[!UICONTROL Similar Traits]** colonne.

>[!NOTE]
>
> L’Audience Marketplace affiche les 500 premiers résultats similaires [!UICONTROL trait] provenant des différents flux de données.

Regardez la vidéo ci-dessous pour une vue d&#39;ensemble complète de la façon de trouver des [!UICONTROL traits]similaires.

>[!VIDEO](https://video.tv.adobe.com/v/29370/)

## Flux de données privés {#private-data-feeds}

Dans la [!UICONTROL Marketplace] liste, le nom et les [!UICONTROL trait] données du fournisseur sont parfois marqués comme privés. Ceci indique un flux [de données](../../../features/audience-marketplace/marketplace-private-feeds.md)privé. Un flux de données privé permet aux vendeurs de limiter l’accès des acheteurs à leurs données. Les vendeurs peuvent rendre les flux privés lorsqu&#39;ils proposent des offres spéciales, des rabais ou lorsque la confidentialité et le contrôle d&#39;accès sont importants pour eux. En tant qu&#39;acheteur, vous devez envoyer une demande d&#39;abonnement au vendeur si vous souhaitez accéder à un flux privé. Pour plus d’informations, voir [S’abonner à un flux](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) de données privé.

>[!MORELIKETHIS]
>
>* [Présentation de la page des détails de la formule d’Audience Marketplace](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details) (en anglais)
>* [Remises pour les acheteurs de données](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)

