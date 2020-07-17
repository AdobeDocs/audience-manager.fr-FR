---
description: Un flux de données nécessite un nom, une description, une source de données et un type de plan. Les flux sont désactivés jusqu’à ce que vous enregistriez et activiez le flux. Configurez des flux de données publics ou privés dans Audience Marketplace > Mes données partagées. Disponible uniquement pour les vendeurs de données.
seo-description: Un flux de données nécessite un nom, une description, une source de données et un type de plan. Les flux sont désactivés jusqu’à ce que vous enregistriez et activiez le flux. Configurez des flux de données publics ou privés dans Audience Marketplace > Mes données partagées. Disponible uniquement pour les vendeurs de données.
seo-title: Création, tarification et gestion des flux de données
solution: Audience Manager
title: Création, tarification et gestion des flux de données
topic: DIL API
uuid: e28c20b3-33fc-4485-8ee9-8530d126f741
feature: Audience Marketplace
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1304'
ht-degree: 2%

---


# Création, tarification et gestion des flux de données {#create-price-and-manage-data-feeds}

## Création d’un flux de données public ou privé {#create-public-private-data-feed}

Un flux de données nécessite un nom, une description, une source de données et un type de plan. Les flux sont désactivés jusqu’à ce que vous enregistriez et activiez le flux. Configurez des flux de données publics ou privés dans **[!UICONTROL Audience Marketplace > My Shared Data]**. Disponible uniquement pour les vendeurs de données.

<!-- t_data_feed.xml -->

Vous devez disposer des droits d’administrateur pour créer un flux de données public ou privé.
Pour créer un flux de données :

1. Cliquez sur **[!UICONTROL New Data Feed]**.
1. Nommez le flux de données. Les acheteurs de données peuvent rechercher votre flux en fonction de son nom.
1. Fournissez une brève description (255 caractères maximum).

   Une bonne description doit décrire votre flux avec précision. Par exemple, vous pouvez inclure du texte pour les catégories marketing, les données démographiques et la couverture géographique (par exemple, [!DNL US] ou l’Amérique du Nord). Le texte de la description peut faire l’objet de recherches et aide les acheteurs à trouver ou à évaluer votre flux. Une bonne description est un élément important pour attirer les abonnés à votre flux de données.
1. Sélectionnez une source de données dans les **[!UICONTROL Data Source]** options. Les flux de données sont limités à une seule source de données. Vous ne pouvez pas affecter plusieurs sources de données au même flux de données.

   >[!IMPORTANT]
   >
   >Dans le cadre de ce flux, toutes les caractéristiques actuelles et futures appartenant à cette source de données seront partagées avec vos acheteurs de données.

1. Dans [!UICONTROL Plan Types], sélectionnez les options à utiliser, puis cliquez sur **[!UICONTROL Add Plan]**.

   Les flux peuvent contenir plusieurs plans. Les plans peuvent contenir plusieurs cas d&#39;utilisation. Pour plus d’informations, voir Types de [plan pour les flux](../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#plan-types)de données.

1. Cliquez sur **[!UICONTROL Save]** pour enregistrer votre flux de données *sans* l’activer.
1. Pour enregistrer et activer un flux de données :
   1. Déplacez le **[!UICONTROL Availability]** curseur vers **[!UICONTROL Active]**.
   1. Cliquez sur **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >* Les flux de données enregistrés et activés ne peuvent pas être supprimés.
   >* Les acheteurs ne voient que les flux actifs.


### Facultatif : Création d’un flux de données privé

Dans la [!UICONTROL Settings] section, déplacez le curseur vers :

* **[!UICONTROL Private]** et **[!UICONTROL Branded]**: La [!UICONTROL Marketplace] liste de l&#39;acheteur affiche le nom du vendeur dans la colonne Fournisseur et toutes les autres données sont masquées.

* **[!UICONTROL Private]** et **[!UICONTROL Unbranded]**: La [!UICONTROL Marketplace] liste de l’acheteur affiche uniquement le nom et la description du flux de données. Le nom du fournisseur de données s’affiche sous la forme [!UICONTROL Private Seller].

Pour savoir à quoi ressemble un flux privé pour les acheteurs, consultez la section Acheteurs dans Flux [de données](../../../features/audience-marketplace/marketplace-private-feeds.md)privés.

## Désactivation du flux de données d’un abonné {#deactivate-data-feed}

En tant que fournisseur [!UICONTROL Audience Marketplace] de données, vous pouvez révoquer l’accès de l’acheteur à un flux de données auquel vous êtes abonné. Vous pouvez supprimer un acheteur d’un flux pour des raisons telles que le paiement tardif/le non-paiement des frais ou s’il utilise incorrectement les données de caractéristiques.

<!-- marketplace-deactiva4te-subscribers.xml -->

Pour révoquer un abonné :

1. Dans [!UICONTROL My Shared Data], recherchez le flux utilisé par l’abonné.

   >[!NOTE]
   >
   >Les flux de données avec des comptes en retard sont signalés par un triangle/point d’exclamation.

1. Dans la [!UICONTROL Subscribers] colonne, cliquez sur le chiffre bleu qui comptabilise les abonnés pour ce flux. La page Détails de l’abonnement s’ouvre alors.
1. Déplacez le **[!UICONTROL Subscription]** curseur vers **[!UICONTROL Off]**. Cette opération ouvre une boîte de dialogue de confirmation.
1. Dans la [!UICONTROL Confirmation] fenêtre contextuelle, cliquez sur **[!UICONTROL Yes]** pour désactiver un abonnement ou **[!UICONTROL Cancel]** pour quitter sans modifier l’abonnement.

### Que se passe-t-il après la désactivation d’un abonné ?

Le fait de révoquer l’accès à un flux de données envoie un courrier électronique de notification à tous les utilisateurs administrateurs du compte de l’acheteur de données. Le courrier électronique contient une pièce jointe qui liste les caractéristiques révoquées. Cette liste aide les abonnés à rechercher et à supprimer les caractéristiques désactivées de leurs segments et modèles.

### Facturation et désactivation des flux

Une fois que vous avez supprimé l’accès à un flux de données, les abonnés sont responsables des frais pour le mois précédent ou en cours, selon le moment où vous avez désactivé le flux.

## Types de plan pour les flux de données {#plan-types}

[!DNL Plan types] sont des composants essentiels d’un flux de [!UICONTROL Audience Marketplace] données. En tant que fournisseur de données, ils vous permettent de créer plusieurs cas d’utilisation et options de prix pour vos flux. En outre, il peut s’avérer judicieux de créer quelques plans pour chaque flux de données. Les acheteurs ont ainsi différentes options à choisir lorsqu&#39;ils recherchent des données à modéliser ou à envoyer à une destination.

[Créez un flux](../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#create-public-private-data-feed) de données à sélectionner [!UICONTROL Plan Types].

![](assets/plan_types.png)

## Types de plan et options de cas d&#39;utilisation {#plan-types-use-cases}

<!-- c_feed_options.xml -->

Les [!UICONTROL Use Case] paramètres permettent aux vendeurs de contrôler comment les acheteurs peuvent utiliser vos données.

### Segments et chevauchement

Un cas d’ **[!UICONTROL Segments and Overlap]** utilisation crée un plan qui permet aux acheteurs de comparer les données de caractéristiques dans un rapport [de chevauchement](../../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report)trait par trait. En outre, les acheteurs peuvent ajouter vos données aux segments et faire des comparaisons avec les rapports [segment à caractéristique](../../../reporting/dynamic-reports/segment-trait-overlap-report.md) et [segment à segment](../../../reporting/dynamic-reports/segment-segment-overlap-report.md) .

Chaque flux de données doit inclure au moins un cas d’ [!UICONTROL Segments and Overlap] utilisation. Les acheteurs ne peuvent pas s’abonner à d’autres plans dans un flux de données si le flux ne contient pas de cas d’ [!UICONTROL Segments and Overlap] utilisation, soit seul, soit en combinaison avec un autre cas d’utilisation.

Les comparaisons de chevauchement peuvent aider les acheteurs :

* **Étendre la portée de l&#39;audience :** Un chevauchement faible suggère que vos caractéristiques contiennent des utilisateurs que l&#39;acheteur n&#39;a jamais vus auparavant. Par conséquent, les acheteurs peuvent souhaiter que ces caractéristiques ajoutent de nouveaux utilisateurs à leurs segments d’audience.
* **Améliorer les audiences existantes :** Un chevauchement élevé suggère que vos caractéristiques contiennent des utilisateurs semblables à ceux qu&#39;un acheteur connaît déjà. Par conséquent, les acheteurs peuvent souhaiter que ces caractéristiques aident à apporter des améliorations ciblées et progressives aux audiences développées.

Mettez en valeur ce cas d&#39;utilisation comme suit :

* Unité de mesure : Tarif forfaitaire
* Prix : Gratuit (0,00 $)

### Modélisation

Un cas **[!UICONTROL Modeling]** d’utilisation crée un plan qui permet aux acheteurs de comparer leurs caractéristiques à la leur avec une modélisation [](../../../features/algorithmic-models/understanding-models.md#understanding-models)algorithmique. Les acheteurs examinent les résultats du modèle pour trouver de nouvelles audiences dans vos données qui partagent des attributs de conversion similaires à leurs propres. Mettez en valeur ce cas d&#39;utilisation comme suit :

* Unité de mesure : Tarif forfaitaire
* Prix : Prix actualisé ou prix du marché

### Activation

Un cas **[!UICONTROL Activation]** d’utilisation permet aux acheteurs d’envoyer des données vers une [destination](../../../features/destinations/destinations.md). Dans ce cas d’utilisation, les acheteurs ne peuvent pas comparer les données à un rapport de chevauchement ou à un modèle algorithmique. Mettez en valeur ce cas d&#39;utilisation comme suit :

* Unité de mesure : [!DNL CPM]
* Prix : [!DNL CPM] taux de marché

## Options de facturation et de prix {#billing}

Les options de facturation et de prix contrôlent comment les acheteurs paient pour vos données.

<table id="table_CCEAAF24295942EA82F20753827D1A23"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Option </th> 
   <th colname="col2" class="entry"> Description </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Cycle de facturation</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> Mensuellement en Arrières</span></b> est la seule option. Le cycle de facturation se termine le 10e jour de chaque mois. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Unité de mesure</span></b> </td> 
   <td colname="col2">Facturer les acheteurs de données sur un taux de CPM ou des frais fixes. 
    <ul id="ul_D5F125E0F7364C568D9F3107E090059D"> 
     <li id="li_A79F47FFC1DC4B9DADC014621A9C12A1"> Avec la tarification CPM, les acheteurs de données doivent déclarer eux-mêmes l'utilisation. </li> 
     <li id="li_DFED3194854A492F9DD0E7BA1A655E96">Avec le tarif forfaitaire, les acheteurs de données ne signalent pas l'utilisation car ils se voient facturer un tarif fixe. </li> 
    </ul> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Prix</span></b> </td>
   <td colname="col2"> Le montant qu'un vendeur facture à l'acheteur en tant que taux CPM ou prix forfaitaire, en dollars. </td>
  </tr> 
 </tbody> 
</table>

## Notes du plan {#plan-notes}

Dans le **[!UICONTROL Additional Notes]** champ, prenez le temps de décrire chaque plan de données d’un flux. Une brève description précise permet aux acheteurs de comprendre le contenu ou l’objectif de chaque plan dans un flux de données. Les acheteurs peuvent lire les descriptions des flux de données et des plans lorsqu’ils recherchent ou évaluent de nouvelles sources de données.

## Gérer les requêtes de flux de données privées {#manage-private-requests}

workflows du fournisseur pour la gestion des demandes d’alimentation privées des acheteurs.

Pour examiner, approuver ou rejeter des demandes d&#39;acheteur, accédez à [!UICONTROL My Shared Data] et :

<!-- t_private_feed_workflows.xml -->

1. Cliquez sur le nom du flux de données privé.
2. Cliquez sur **[!UICONTROL Access Requests]** pour consulter tous les acheteurs qui souhaitent accéder à votre flux de données.
3. Dans la [!UICONTROL Allow Access] section de chaque champ de requête, cochez la case pour approuver une requête ou le X pour refuser l’accès.
4. Confirmez ou annulez l’action sélectionnée dans la fenêtre contextuelle de confirmation.

## Remises pour les fournisseurs de données {#discounts}

Dans [!UICONTROL Audience Marketplace]le cas présent, les remises vous permettent de réduire le prix publié d’un flux de données pour les abonnés individuels. Vous pouvez offre des remises aux abonnés qui ont soumis une demande d’abonnement ou aux abonnés qui ont demandé des détails sur un flux de données. Les rabais s’appliquent aux flux [!DNL CPM] et aux flux à taux fixe. Les remises peuvent s&#39;avérer utiles lorsque vous souhaitez offrir des avantages d&#39;abonnement aux nouveaux clients ou pour récompenser la fidélité de vos clients.

## Appliquer des remises à un flux de données {#apply-discounts}

<!-- marketplace-seller-discounts.xml -->

Pour réduire un flux, ajoutez un montant de remise en % au champ de remise et confirmez vos modifications. Les fournisseurs de données peuvent réduire un flux de données dans [!UICONTROL Audience Marketplace] l’un des :

* **[!UICONTROL My Shared Data > Potential Subscribers]**
* **[!UICONTROL My Shared Data > Details Requests]**

Dans ces exemples, le vendeur a ajouté une remise de 10 % au flux de [!UICONTROL Software Audience] données.

![](assets/potential_subscribers.png)

![](assets/detail_requests.png)

## Vérification des flux actualisés {#review-discounted-feeds}

Les fournisseurs de données peuvent afficher tous leurs abonnés et flux à tarif réduit dans **[!UICONTROL Audience Marketplace > My Shared Data > Current Subscribers]**.

![](assets/subscribers.png)

>[!MORELIKETHIS]
>
>* [Flux de données privés](../../../features/audience-marketplace/marketplace-private-feeds.md)

