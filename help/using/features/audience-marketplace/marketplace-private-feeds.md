---
description: Un flux de données privé est une option qui permet aux fournisseurs de limiter l’accès des acheteurs à leurs données. Les fournisseurs de données et les acheteurs doivent consulter ces informations avant de créer des flux de données privés et de s’y abonner.
seo-description: Un flux de données privé est une option qui permet aux fournisseurs de limiter l’accès des acheteurs à leurs données. Les fournisseurs de données et les acheteurs doivent consulter ces informations avant de créer des flux de données privés et de s’y abonner.
seo-title: Flux de données privés
solution: Audience Manager
title: Flux de données privés
uuid: e4ca59ca-bbc9-4897-9374-8f3d54b2beee
feature: Audience Marketplace
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1090'
ht-degree: 1%

---


# Flux de données privés {#private-data-feeds}

Un flux de données privé est une option qui permet aux fournisseurs de limiter l’accès des acheteurs à leurs données. Les fournisseurs de données et les acheteurs doivent consulter ces informations avant de créer des flux de données privés et de s’y abonner.

<!-- c_marketplace_privatefeed.xml -->

## Flux de données privés pour les fournisseurs {#private-data-feeds-providers}

En tant que fournisseur, vos flux de données peuvent être publics ou privés. Un flux de données privé vous permet de limiter l’accès des acheteurs à vos données, y compris le nom du vendeur de données. Vous pouvez créer un flux de données privé pour offre des offres spéciales, des remises ou lorsque la confidentialité et le contrôle d&#39;accès sont importants. Avec un flux de données privé, vous pouvez examiner et approuver les demandes d’achat. Après avoir approuvé une demande, le flux ressemble à un flux de données public destiné à l’acheteur. Vous pouvez vue et gérer tous vos flux dans **[!UICONTROL Audience Marketplace > My Shared Data]**. Comme illustré ci-dessous, ce type de flux est marqué &quot;Privé&quot; dans la colonne d’état.

![](assets/my_shared_data.png)

### Gestion des requêtes de flux

Cliquez sur le nom d’un flux de données privé à partir de [!UICONTROL My Shared Data] pour accéder à une page qui contient plusieurs onglets. Cliquez sur un onglet pour gérer vos requêtes de flux de données privées.

![](assets/shared_data_tabs.png)

Le tableau suivant définit le ou les rôles fournis par chaque onglet d’action.

<table id="table_AFB429CA52A34658859448D9A5215F9F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tabulation </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Abonnés actuels</span></b> </p> </td> 
   <td colname="col2"> <p>Les listes ont approuvé les acheteurs qui se sont abonnés à un flux de données privé. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Abonnés potentiels</span></b> </p> </td> 
   <td colname="col2"> <p>Liste a approuvé les acheteurs qui ne se sont pas abonnés à un flux de données privé. </p> <p>Une approbation permet aux acheteurs de vue d’un flux de données comme s’il était public. Cela leur permet de consulter et d’évaluer vos flux avant de s’abonner. Vous pouvez également offre des remises sur les flux de données aux acheteurs répertoriés comme abonnés potentiels. Une fois que l'acheteur s'est abonné, son profil passe à <b><span class="uicontrol"> Abonnés actuels</span></b>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Demandes d’accès</span></b> </p> </td>
   <td colname="col2"> <p>Liste les nouvelles demandes d’abonnement pour un flux de données privé. Cliquez sur cet onglet pour examiner, approuver ou rejeter les demandes d'acheteur. </p>
    <ul id="ul_BE0A835A90B14C05B3F63226B79D052D"> 
     <li id="li_2C5686CEB6F4430BA18AED5AD75C330A">Les acheteurs approuvés passent à <b><span class="uicontrol"> Abonnés potentiels</span></b>. </li>
     <li id="li_929591FCF81E43A3881813BDBD3AC278">Les acheteurs refusés passent à <b><span class="uicontrol"> Accès refusé</span></b>. </li>
    </ul> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Demandes de détails</span></b> </p> </td>
   <td colname="col2"> <p>Les listes ont approuvé les acheteurs qui ne se sont pas encore abonnés à un flux de données et ont demandé plus d’informations sur vos flux. </p> <p>Une approbation permet aux acheteurs de vue d’un flux de données comme s’il était public. Cela leur permet de consulter et d’évaluer vos flux avant de s’abonner. Vous pouvez également offre des remises sur les flux de données aux acheteurs qui demandent l’accès. La réponse à une demande de détails supprime le profil acheteur de cet onglet. S'ils ne se sont pas abonnés, le profil acheteur est toujours dans <b><span class="uicontrol"> Abonnés potentiels</span></b>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Accès refusé</span></b> </p> </td> 
   <td colname="col2"> <p>Les listes ont rejeté les demandes d’abonnement pour un flux de données privé. </p> <p>Pour réapprouver les acheteurs refusés, remplacez <span class="wintitle"> Statut de rejet</span> par <b><span class="uicontrol"> Autoriser</span></b>. L'acheteur est ainsi dirigé vers <b><span class="uicontrol"> Abonnés potentiels</span></b>. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Étapes suivantes

La documentation suivante peut vous aider à commencer à utiliser des flux de données privés.

* [Création d’un flux de données public ou privé](../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#create-public-private-data-feed)
* [Révision, approbation ou rejet de demandes de flux privés](../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#manage-private-requests)
* [Flux de données privés pour les acheteurs](../../features/audience-marketplace/marketplace-private-feeds.md#private-data-feeds-for-buyers)

## Flux de données privés pour les acheteurs {#private-data-feeds-for-buyers}

En tant qu’acheteur, les flux de données privés apparaissent dans le [Marché](../../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md#about-marketplace) comme toute autre offre. Cependant, dans ce cas, la liste de flux n’affiche pas d’informations récapitulatives sur les caractéristiques, les utilisateurs uniques et les chevauchements d’utilisateurs. En outre, le vendeur de données peut afficher ou masquer son nom dans la colonne [!UICONTROL Provider] de la liste [!UICONTROL Marketplace]. Une fois que le vendeur a approuvé votre demande d’abonnement, toutes les données d’un flux privé sont mises à votre disposition (il fonctionne comme un flux public). L&#39;exemple [!UICONTROL Marketplace] ci-dessous liste les 3 différents types de flux disponibles en tant qu&#39;acheteur.

![](assets/buyer_marketplace.png)

Les types de flux sont les suivants :

Le tableau décrit comment ces différents types de flux affichent ou masquent les données.

<table id="table_41D4A798ACF548A3A03ACB427CA4652D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type de flux  </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Public</span></b> </p> </td> 
   <td colname="col2"> <p>Le nom, la caractéristique et les données uniques du fournisseur apparaissent dans la liste. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Privé sans marque</span></b> </p> </td> 
   <td colname="col2"> <p>Le nom du fournisseur est défini sur "Vendeur privé" et vous ne pouvez pas afficher le nombre de caractéristiques, les données uniques et les données de chevauchement de caractéristiques. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Privé avec marque</span></b> </p> </td> 
   <td colname="col2"> <p>Le nom du fournisseur s’affiche dans la liste mais vous ne pouvez pas afficher le nombre de caractéristiques, les données uniques et les données de chevauchement de caractéristiques. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Étapes suivantes

Voir  [Abonnez-vous à un ](../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) flux de données privé pour demander un accès.

## Comment configurer la relation de partage entre le fournisseur de données et l&#39;acheteur de données {#set-up-sharing-relationship}

### Étape 1 - Activation - Fournisseur de données et Acheteur de données

La première étape du processus nécessite l’intervention du service de conseil en Adobe ou du service à la clientèle. Le fournisseur de données et l’acheteur de données doivent contacter le service de conseil en Adobe ou le service à la clientèle pour demander l’activation.

### Étape 2 - Fournisseur de données - Créer une source de données

Dans votre compte d’Audience Manager, créez une source de données de cookie avec :

* **Audience Manager** ID en tant que clé entrante ;
* L&#39;option **Partager activé** a été cochée.

![](assets/create-datasource.png)

Une fois que vous avez cliqué sur **Enregistrer**, un nouveau sous-dossier est automatiquement créé dans **Enregistrement des caractéristiques > Données tierces**.

![](assets/folder-structure.png)

### Étape 3 - Fournisseur de données - Identifier les caractéristiques du partage

Au cours de cette étape, vous identifiez les caractéristiques que vous souhaitez partager avec votre partenaire. Vous pouvez soit créer de nouvelles caractéristiques, soit modifier des caractéristiques existantes. Dans tous les cas, vous avez besoin des caractéristiques suivantes :

* À associer à la source de données que vous avez créée dans le cadre de l’étape 2.
* À stocker dans le sous-dossier que vous venez de créer, sous Données tierces.

En savoir plus sur [la création de caractéristiques](/help/using/features/traits/create-onboarded-rule-based-traits.md) et [la modification de caractéristiques](/help/using/features/traits/manage-trait-rules.md#edit-trait).

### Étape 4 - Fournisseur de données - Créer un flux de données

Ensuite, créez un flux de données pour partager vos caractéristiques avec l’acheteur de données. Voir [Création d’un flux de données public ou privé](/help/using/features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md) pour savoir comment créer un flux de données.

>[!IMPORTANT]
>
>Dans Paramètres, sélectionnez l’option Privé. Si vous définissez ce champ sur Public, tout client d’Audience Marketplace peut s’abonner à votre flux.

![](assets/create-data-feed.png)

### Étape 5 - Acheteur de données - Demande d&#39;accès

Accédez à **Audience Marketplace > Marketplace**. Recherchez le flux de données créé par le fournisseur de données à l’étape précédente. Cliquez sur **Request Access**. Le contact désigné du fournisseur de données recevra désormais une notification par courrier électronique. Voir aussi [S’abonner à un flux de données privé](/help/using/features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed).

### Étape 6 - Fournisseur de données - Octroi d&#39;un accès

Accédez à **Audience Marketplace > Mes données partagées** et recherchez le flux que vous avez créé à l’étape 4. Cliquez sur la nouvelle demande d’accès et sur **Autoriser l’accès** pour approuver la demande. Voir aussi [Réviser, approuver ou rejeter les requêtes de flux privés](/help/using/features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#manage-private-requests).

### Étape 7 - Acheteur de données - Activer l&#39;Abonnement

Une fois que le fournisseur de données a accordé l’accès au flux de données, vous pouvez voir le flux dans votre compte dans **Audience Marketplace > Marketplace**. Passez en revue les détails, activez le bouton Abonnement, puis cliquez sur **Révision et abonnement**. Voir [Enregistrement pour les flux de données abonnés](/help/using/features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#find-subscribed-data-fee) pour plus d’informations sur l’emplacement des caractéristiques tierces.

Notez que ces caractéristiques ne peuvent être modifiées que dans le compte du fournisseur de données.




