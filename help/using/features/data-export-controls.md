---
description: Les contrôles d’exportation de données vous empêchent d’envoyer des données aux destinations lorsque cette action enfreint la confidentialité des données ou les accords d’utilisation des données.
seo-description: Data Export Controls prevent you from sending data to destinations when this action violates data privacy or data use agreements.
seo-title: Data Export Controls
solution: Audience Manager
title: Contrôles des exportations de données
uuid: de7f3608-c0cb-4049-973a-8be54525c600
feature: Data Export Controls
exl-id: 4369c210-bcf1-48cc-a9bb-0d122f6c03d4
source-git-commit: fc26861e4a53abc57f8814abf823a51894fb6147
workflow-type: tm+mt
source-wordcount: '876'
ht-degree: 1%

---

# Contrôles des exportations de données {#data-export-controls}

[!UICONTROL Data Export Controls] vous empêchent d’envoyer des données aux destinations lorsque cette action enfreint la confidentialité des données ou les accords d’utilisation des données.

## Présentation {#overview}

[!UICONTROL Data Export Controls] vous permettent de classer [sources de données](../features/datasources-list-and-settings.md#data-sources-list-and-settings) et [destinations](../features/destinations/destinations.md). Les classifications que vous appliquez déterminent quand les données peuvent ou ne peuvent pas être exportées vers une destination. Cette fonctionnalité comprend les éléments suivants :

* **[!UICONTROL Data Export Controls]** : vous pouvez définir des contrôles d’exportation de données sur des *sources de données*. Lorsqu’elles sont définies sur une source de données, ces commandes limitent la manière dont cette source de données et ses caractéristiques peuvent être utilisées.
* **[!UICONTROL Data Export Labels]** : vous pouvez définir des libellés d’exportation de données sur *destinations*. Lorsqu’ils sont définis sur une destination, ces libellés identifient la manière dont la destination utilise les données. Consultez [Ajouter des libellés d’exportation de données à une destination](/help/using/features/destinations/add-data-export-labels.md) pour savoir comment ajouter des libellés d’exportation à une destination.

En fonction des classifications appliquées à une source de données et à une destination, les contrôles d’exportation vous empêchent de :

* Ajouter une caractéristique à un segment lorsque la caractéristique appartient à une source de données qui possède un contrôle d’exportation de données incompatible avec un libellé d’exportation de données sur une ou plusieurs des destinations auxquelles le segment est mappé.
Supposons, par exemple, qu’un segment soit mappé à une destination avec le libellé d’exportation **[!DNL This destination may enable a combination with personally identifiable information (PII)]**. Les contrôles d’exportation vous empêchent d’ajouter une caractéristique à ce segment si la source de données à laquelle la caractéristique appartient dispose d’un contrôle d’exportation des données qui indique **[!DNL Cannot be tied to personally identifiable information (PII)]**.
* Envoi de données vers une destination qui possède un libellé d’exportation de données bloqué par un contrôle d’exportation de données sur l’un des éléments suivants :
   * la source de données d’une caractéristique incluse ;
   * La source de données d’une caractéristique utilisée dans un segment inclus ;
   * La règle de fusion de profil utilisée par un segment inclus
   * Toute source de données utilisée par une règle de fusion de profils d’un segment inclus.

Les [!UICONTROL Data Export Controls] sont automatiquement disponibles pour tous les clients Audience Manager. Toutefois, vous avez besoin de droits d&#39;administrateur pour ajouter des contrôles d&#39;exportation à une source de données. L’ajout de libellés d’exportation à une destination nécessite des autorisations d’administrateur *ou* des privilèges suffisants pour créer ou modifier une destination.

## Contrôles et libellés définis {#controls-labels}

[!UICONTROL Data Export Controls] fournir les commandes suivantes pour vous aider à classer les sources de données et les destinations.

Pour bloquer la diffusion des données, vous devez classifier une source de données avec un contrôle d’exportation et ajouter un libellé d’exportation à une destination. Si vous appliquez des contrôles d’exportation à une source de données ou une destination uniquement, cette fonctionnalité ne limite pas la diffusion des données. Lorsqu’elles sont définies à la fois sur la source de données *et* la destination, les contrôles d’exportation limitent les caractéristiques que vous pouvez ajouter à un segment et empêchent l’envoi des membres du segment vers une destination.

En outre, au moins un libellé d’exportation doit correspondre à un contrôle d’exportation avant que les restrictions de diffusion de données ne prennent effet. Supposons, par exemple, que vous ajoutiez le contrôle d’exportation [!UICONTROL PII] à une source de données. Ajoutez ensuite le libellé de ciblage sur site à une destination. Dans ce cas, les contrôles d’exportation ne limiteront pas la diffusion des données, car les paramètres ne correspondent pas. Cependant, si vous ajoutez l’étiquette d’exportation [!UICONTROL PII] à la destination, les contrôles d’exportation bloqueront l’exportation.

>[!IMPORTANT]
>
>Vous ne pouvez pas bloquer l’exportation d’un segment en plaçant un contrôle d’exportation des données sur la source de données du segment. Vous devez définir le contrôle sur l’une des options suivantes :
>
> * les sources de données des caractéristiques utilisées dans le segment ;
> * Règle de fusion de profils utilisée par le segment ;
> * Toute source de données utilisée par la règle de fusion de profils du segment.

<br> 

<table id="table_7D1F0270B5604A82B96A13CC49C937C0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Contrôles d’exportation de données pour une Source de données </th> 
   <th colname="col2" class="entry"> Libellés d’exportation de données pour une destination </th> 
   <th colname="col3" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Aucune restriction</span></b> </td> 
   <td colname="col2"> n/d </td> 
   <td colname="col3"> Par défaut, les restrictions d’exportation ne sont pas définies sur les nouvelles sources de données et destinations. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> ne peut pas être lié à des informations d’identification personnelle</span></b> (PII) </td> 
   <td colname="col2"> <b><span class="uicontrol"> Cette destination peut permettre une combinaison avec des informations d’identification personnelle (PII)</span></b> </td> 
   <td colname="col3">Lorsque cette option est sélectionnée, vous ne pouvez pas : 
    <ul id="ul_0D5A4D0373374217A4BACDFC3BB2F79D"> 
     <li id="li_C32FC26C6E814412A1C73B840E81BB68">Ajoutez des caractéristiques aux segments mappés aux destinations qui utilisent des informations d’identification personnelles. </li> 
     <li id="li_BF4FD10807AF4E109CEA22FBD3F6F9B3">Mappez les segments créés avec une caractéristique de la source de données aux destinations qui utilisent des informations d’identification personnelles. </li> 
    </ul> <p>Cela est souvent requis par les fournisseurs de données tiers et lors de l’utilisation de sources de données contenant des informations de suivi publicitaire/multimédia. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> ne peut pas être utilisé pour le ciblage d’annonces sur site</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> Cette destination peut être utilisée pour le ciblage d’annonces sur site</span></b> </td> 
   <td colname="col3">Lorsque cette option est sélectionnée, vous ne pouvez pas : 
    <ul id="ul_5B17972E7E0C424A833AD540DFF3CBF2"> 
     <li id="li_05810CEAC8CB4616BB2D52DDDADA84A8">Ajoutez des caractéristiques aux segments mappés aux destinations qui personnalisent la diffusion des annonces en fonction de l’historique de navigation web d’un visiteur. </li> 
     <li id="li_B2C3479ECEA74F49B9A2CFDDEE128DF3">Mappez les segments créés avec une caractéristique de la source de données aux destinations qui personnalisent la diffusion des annonces en fonction de l’historique de navigation web d’un visiteur. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> ne peut pas être utilisé pour le ciblage d’annonces hors site</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> Cette destination peut être utilisée pour le ciblage d’annonces hors site</span></b> </td> 
   <td colname="col3">Lorsque cette option est sélectionnée, vous ne pouvez pas : 
    <ul id="ul_B9352FF5282C481BA3A24C581217A156"> 
     <li id="li_0F89583A603D4CD8804724954CFD52C6">Ajoutez des caractéristiques aux segments mappés à des destinations qui reciblent les utilisateurs sur d’autres sites. </li> 
     <li id="li_ABDD8BEDE9AF411695C7BDF9AE522BA7">Mappez les segments créés avec une caractéristique de la source de données aux destinations qui reciblent les utilisateurs sur d’autres sites. </li> 
    </ul> <p>Souvent requis lors de l’utilisation de données provenant de plateformes de médias sociaux. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> ne peut pas être utilisé pour la personnalisation sur site</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> Cette destination peut être utilisée pour la personnalisation de l’annonce publicitaire sur site</span></b> </td> 
   <td colname="col3">Lorsque cette option est sélectionnée, vous ne pouvez pas : 
    <ul id="ul_3360EB209E07402A863F0E7473B99D3F"> 
     <li id="li_88B3842B67E040EB9DC0BBEB8E5EC251">Ajoutez des caractéristiques aux segments mappés aux destinations pour personnaliser le contenu en fonction des intérêts de l’utilisateur ou de l’historique de navigation web. </li> 
     <li id="li_6506254CCE6546039A3D82B60368C8B4">Mappez les segments créés avec une caractéristique de la source de données aux destinations qui personnalisent le contenu en fonction des intérêts de l’utilisateur ou de l’historique de navigation web. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Workflow {#workflow}

Pour commencer, consultez la documentation sur la source de données et la destination . Ces articles fournissent des instructions sur la manière d’ajouter des contrôles d’exportation et des libellés à vos sources de données et destinations.

* [Création d’une source de données](../features/manage-datasources.md#create-data-source)
* [Ajout de libellés d’exportation de données à une destination](../features/destinations/add-data-export-labels.md)
