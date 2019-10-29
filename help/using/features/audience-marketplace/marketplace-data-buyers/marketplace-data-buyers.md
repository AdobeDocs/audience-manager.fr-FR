---
description: Présentation et flux de travail pour les acheteurs de données qui souhaitent acheter des données tierces à partir d’Audience Manager
seo-description: Présentation et flux de travail pour les acheteurs de données qui souhaitent acheter des données tierces à partir d’Audience Manager
seo-title: Audience Marketplace pour les acheteurs de données
solution: Audience Manager
title: Audience Marketplace pour les acheteurs de données
topic: API DIL
uuid: f505b5f4-4231-4e84-993a-cd64128b540f
translation-type: tm+mt
source-git-commit: d9a4244f68e95c872d3686da10ee3a774250fbfe

---


# Audience Marketplace pour les acheteurs de données {#audience-marketplace-for-data-buyers}

Présentation et flux de travail pour les acheteurs de données qui souhaitent acheter des données tierces depuis l’intérieur [!DNL Audience Manager].

>[!NOTE]
>[Les autorisations](../../../reporting/reports-dashboard.md) basées sur les rôles contrôlent l’accès aux [!UICONTROL Audience Marketplace] fonctionnalités.
>
>* Les administrateurs peuvent créer des flux de données, gérer les abonnés et s’abonner aux flux de données.
>* Les utilisateurs peuvent uniquement rechercher et afficher des flux.


## Le Marché : À propos de {#about-marketplace}

<!-- c_marketplace_about.xml -->

Cette [!UICONTROL Marketplace] [!DNL Audience Manager] fonctionnalité permet aux acheteurs de données de répertorier les flux de données auxquels vous pouvez vous abonner. Il répertorie les flux de données à taux fixe [!DNL CPM]et privés. Ces flux sont fournis par des fournisseurs tiers qui utilisent les données [!DNL Audience Manager] pour les vendre.

Dans la [!UICONTROL Marketplace]section, les outils de création de rapports vous permettent de suivre l’utilisation des flux et le chevauchement entre vos caractéristiques et celles d’un flux de données abonné. Enfin, [!UICONTROL Audience Marketplace], [!DNL Adobe] prend en charge les factures et les paiements de frais (bien que vous deviez vous-même déclarer l’utilisation lorsque vous vous abonnez à un [!DNL CPM] flux). Ces fonctionnalités vous permettent de trouver des sources de données efficaces sans perdre de temps à rechercher un fournisseur de données.

>[!TIP]
>
>Utilisez **[Adobe Audience Finder](https://www.adobe-audience-finder.com/)** pour rechercher des flux de données de haute qualité auxquels vous pouvez vous abonner. Revenez ensuite dans l’interface utilisateur d’Audience Manager ou utilisez l’API [d’achat d’](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API) Audience Marketplace pour vous abonner aux flux que vous avez trouvés.

![acheteur-marché-aperçu](assets/buyer-marketplace-overview.png)

La [!UICONTROL Marketplace] liste contient des informations que vous pouvez trier et rechercher pour trouver le flux de données qui vous convient. Les éléments de la liste des [!UICONTROL Marketplace] acheteurs sont les suivants :

* **[!UICONTROL Search]**: Recherchez les flux de données par nom ou par description de texte.
* **[!UICONTROL Similar Traits]**: Indique le nombre de caractéristiques similaires d’un flux de données. Cette colonne s’affiche une fois que vous avez saisi une caractéristique ou un segment par lequel filtrer dans la **[!UICONTROL Similarity To]** section.
* **[!UICONTROL Name]**: Nom du flux de données.
* **[!UICONTROL Description]**: Informations sur le contenu d’un flux de données.
* **[!UICONTROL Provider]**: Nom du fournisseur de données.
* **[!UICONTROL Traits]**: Nombre de caractéristiques dans un flux de données.
* **[!UICONTROL 30 Day Provider Unique Users]**: Nombre d’utilisateurs uniques vus au cours des 30 derniers jours.
* **[!UICONTROL 30 Day Overlapped Uniques]**: Nombre d’utilisateurs de votre compte qui chevauchent les utilisateurs du compte du fournisseur.
* **[!UICONTROL Feed Overlap]**: Valeur unique superposée de 30 jours, affichée en pourcentage, calculée comme suit : L’acheteur de données a chevauché une valeur unique de 30 jours / L’acheteur de données 30 jours (valeur unique de 30 jours) x 100.
* **[!UICONTROL Private Feeds]**: Voir Flux [de données](../../../features/audience-marketplace/marketplace-private-feeds.md)privés.
* **[!UICONTROL Currently Subscribed Plan Count]**: Nombre d’abonnements avec un fournisseur de données.

Pour trouver facilement les meilleurs flux de données en fonction de vos besoins, utilisez les filtres suivants disponibles sur le côté gauche de la [!UICONTROL Marketplace] page :

* **[!UICONTROL Similarity To]**: Filtrez les flux de données en fonction de leur similarité avec une caractéristique ou un segment de votre choix. Lorsque vous saisissez la caractéristique ou le segment à comparer, vous pouvez utiliser l’ID de caractéristique ou de segment ou leurs noms respectifs.
* **[!UICONTROL Similarity Cutoff]**: Faites glisser le curseur pour filtrer les flux de données en fonction de la similarité de leurs caractéristiques avec la caractéristique ou le segment sélectionné.
* **[!UICONTROL Subscription Status]**: Filtrez les flux de données en fonction de l’état de votre abonnement.
* **[!UICONTROL Plan Use Case]**: Filtrez les flux de données en fonction de leurs cas d’utilisation pris en charge : **[!UICONTROL Activation]**, **[!UICONTROL Segments and Overlap]** et **[!UICONTROL Modelling]**.
* **[!UICONTROL Plan Unit]**: Filtrez les flux de données en fonction de leur type de tarification.

Regardez la vidéo ci-dessous pour savoir comment utiliser ces filtres.

## Trouver des caractéristiques similaires {#finding-similar-traits}

[!UICONTROL Audience Marketplace] vous permet de rechercher des caractéristiques de différents flux de données, en fonction de leur similarité avec vos caractéristiques ou segments existants. Voici comment procéder :

1. Accédez à **[!UICONTROL Audience Marketplace]** &gt; **[!UICONTROL Marketplace]**.
2. Utilisez le **[!UICONTROL Similarity To]** sélecteur pour choisir entre le filtrage basé sur une caractéristique ou un segment. Vous pouvez filtrer en fonction de l’ID ou du nom de caractéristique/segment. La zone de recherche affiche automatiquement les suggestions pertinentes en fonction de vos entrées.
3. Une fois que vous avez identifié la caractéristique ou le segment par lequel vous souhaitez filtrer, cliquez dessus dans la liste des suggestions.
4. Pour réduire les résultats, utilisez le **[!UICONTROL Similarity Cutoff]** curseur pour passer de caractéristiques moins similaires à des caractéristiques plus similaires.

Une fois le filtrage terminé, une nouvelle colonne s’affiche dans la page de résultats : **[!UICONTROL Similar Traits]**. Cette colonne indique le nombre de caractéristiques similaires à celles par lesquelles vous avez filtré, pour chaque flux de données qui répond aux critères de filtrage.

Pour afficher la liste complète des caractéristiques similaires, cliquez sur le nombre dans la **[!UICONTROL Similar Traits]** colonne.

>[!NOTE]
>
> Audience Marketplace affiche les 500 principaux résultats de caractéristiques similaires provenant des différents flux de données.

Regardez la vidéo ci-dessous pour un aperçu complet de la façon de trouver des traits similaires.

>[!VIDEO](https://video.tv.adobe.com/v/29370/?captions=fre_fr)


## Flux de données privés {#private-data-feeds}

Dans la [!UICONTROL Marketplace] liste, le nom du fournisseur et les données de caractéristiques sont parfois marqués comme étant privés. Indique un flux [de données](../../../features/audience-marketplace/marketplace-private-feeds.md)privé. Un flux de données privé permet aux vendeurs de limiter l’accès des acheteurs à leurs données. Les vendeurs peuvent rendre les flux privés lorsqu’ils proposent des offres spéciales, des remises ou lorsque la confidentialité et le contrôle d’accès sont importants pour eux. En tant qu’acheteur, vous devez envoyer une demande d’abonnement au vendeur si vous souhaitez accéder à un flux privé. Voir [S’abonner à un flux](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) de données privé pour plus d’informations.

>[!MORE_LIKE_This]
>
>* [Présentation de la page des détails de la formule d’Audience Marketplace](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details) (en anglais)
>* [Remises pour les acheteurs de données](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)

