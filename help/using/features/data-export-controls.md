---
description: Les contrôles d'exportation de données vous empêchent d'envoyer des données aux destinations lorsque cette action enfreint les accords de confidentialité ou d'utilisation des données.
seo-description: Les contrôles d'exportation de données vous empêchent d'envoyer des données aux destinations lorsque cette action enfreint les accords de confidentialité ou d'utilisation des données.
seo-title: Contrôles des exportations de données
solution: Audience Manager
title: Contrôles des exportations de données
uuid: de 7 f 3608-c 0 cb -4049-973 a -8 be 54525 c 600
translation-type: tm+mt
source-git-commit: f67ab906bfbd9900941649c4d9045ea94f1e7f4c

---


# Contrôles des exportations de données {#data-export-controls}

[!UICONTROL Data Export Controls] vous éviter d'envoyer des données aux destinations lorsque cette action enfreint les accords de confidentialité ou d'utilisation des données.

## Aperçu {#overview}

[!UICONTROL Data Export Controls] vous permet de classer [les sources de données](../features/datasources-list-and-settings.md#data-sources-list-and-settings) et [les destinations](../features/destinations/destinations.md). Les classifications que vous appliquez déterminent si les données peuvent ou ne peuvent pas être exportées vers une destination. Cette fonctionnalité se compose des éléments suivants :

* **[!UICONTROL Data Export Controls]**: Vous pouvez définir les contrôles d'exportation de données sur *les sources de données*. Lorsqu'elles sont définies sur une source de données, ces commandes limitent la manière dont cette source de données et ses caractéristiques peuvent être utilisées.
* **[!UICONTROL Data Export Labels]**: Vous pouvez définir les étiquettes d'exportation des données sur *les destinations*. Lorsqu'elles sont définies sur une destination, ces étiquettes identifient la manière dont la destination utilise les données. Voir [Ajout de libellés d'exportation de données à une destination](/help/using/features/destinations/add-data-export-labels.md) pour savoir comment ajouter des étiquettes d'exportation à une destination.

Selon les classifications appliquées à une source de données et à une destination, les commandes d'exportation vous arrêtent de :

* Ajout d'une caractéristique à un segment lorsque la caractéristique appartient à une source de données dont le contrôle d'exportation de données est incompatible avec une étiquette d'exportation de données sur une ou plusieurs destinations auxquelles le segment est associé.
Par exemple, supposons qu'un segment soit mappé à une destination avec le libellé d'exportation **[UICONTROL ! Cette destination peut permettre une combinaison avec des informations d'identification personnelle]**. Les contrôles d'exportation vous empêchent d'ajouter une caractéristique à ce segment si la source de données à laquelle la caractéristique appartient possède un contrôle d'exportation de données qui indique **[UICONTROL ! Ne peut pas être lié à des informations d'identification personnelle]**.
* L'envoi d'une donnée à une destination de destination dispose d'un libellé d'exportation de données bloqué par un contrôle d'exportation de données sur les éléments suivants :
   * Source de données d'une caractéristique incluse ;
   * Source de données d'une caractéristique utilisée dans un segment inclus ;
   * Règle de fusion de profil utilisée par un segment inclus ;
   * Toute source de données utilisée par la règle de fusion de profil d'un segment inclus.

[!UICONTROL Data Export Controls] sont automatiquement disponibles pour tous les clients Audience Manager. Cependant, vous avez besoin des autorisations d'administrateur pour ajouter des contrôles d'exportation à une source de données. L'ajout de libellés d'exportation à une destination requiert des autorisations d'administrateur *ou* des privilèges suffisants pour créer ou modifier une destination.

## Contrôles et étiquettes définis {#controls-labels}

[!UICONTROL Data Export Controls] fournissez les commandes suivantes pour vous aider à classifier les sources de données et les destinations.

Pour bloquer la diffusion des données, vous devez classer une source de données avec un contrôle d'exportation et ajouter une étiquette d'exportation à une destination. Si vous appliquez des contrôles d'exportation à une source de données ou à une destination uniquement, cette fonction ne limite pas la remise des données. Lorsqu'elles sont définies sur la source *de données et* la destination, les commandes d'exportation limitent les caractéristiques que vous pouvez ajouter à un segment et empêchent l'envoi des membres du segment à une destination.

De plus, au moins une étiquette d'exportation doit correspondre à un contrôle d'exportation avant que les restrictions de remise de données ne soient prises en compte. Par exemple, imaginons que vous ajoutiez le contrôle [!UICONTROL PII] d'exportation à une source de données. Ensuite, vous ajoutez le libellé de ciblage sur site à une destination. Dans ce cas, les commandes d'exportation ne limitent pas la remise des données car les paramètres ne correspondent pas. Toutefois, si vous ajoutez le libellé [!UICONTROL PII] d'exportation à la destination, les commandes d'exportation bloquent l'exportation.

>[!IMPORTANT]
>
>[Vous ne pouvez pas bloquer l'exportation d'un segment en plaçant un contrôle d'exportation de données sur la source de données du segment, vous devez définir le contrôle sur l'un des éléments suivants :
> * Sources de données des caractéristiques utilisées dans le segment ;
> * Règle de fusion de profil utilisée par le segment ;
> * Toute source de données utilisée par la règle de fusion du profil.


<br> 

<table id="table_7D1F0270B5604A82B96A13CC49C937C0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Contrôles d'exportation des données pour une source de données </th> 
   <th colname="col2" class="entry"> Étiquettes d'exportation des données pour une destination </th> 
   <th colname="col3" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Aucune restriction</span></b> </td> 
   <td colname="col2"> n/d </td> 
   <td colname="col3"> Par défaut, les restrictions d'exportation ne sont pas définies sur les nouvelles sources de données et les destinations. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Ne peut pas être lié à des informations</span></b> d'identification personnelle </td> 
   <td colname="col2"> <b><span class="uicontrol"> Cette destination peut permettre une combinaison avec des informations d'identification personnelle</span></b> </td> 
   <td colname="col3">Lorsque cette option est sélectionnée, vous ne pouvez pas : 
    <ul id="ul_0D5A4D0373374217A4BACDFC3BB2F79D"> 
     <li id="li_C32FC26C6E814412A1C73B840E81BB68">Ajoutez des caractéristiques aux segments mappés aux destinations qui utilisent des informations d'identification personnelle. </li> 
     <li id="li_BF4FD10807AF4E109CEA22FBD3F6F9B3">Faites correspondre les segments créés avec une caractéristique de la source de données aux destinations qui utilisent des informations d'identification personnelle. </li> 
    </ul> <p>Cela est souvent requis par les fournisseurs de données tiers et lors de l'utilisation de sources de données contenant des informations de suivi publicitaire/média. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Ne peut pas être utilisé pour le ciblage publicitaire sur site</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> Cette destination peut être utilisée pour le ciblage publicitaire sur site</span></b> </td> 
   <td colname="col3">Lorsque cette option est sélectionnée, vous ne pouvez pas : 
    <ul id="ul_5B17972E7E0C424A833AD540DFF3CBF2"> 
     <li id="li_05810CEAC8CB4616BB2D52DDDADA84A8">Ajoutez des caractéristiques aux segments associés aux destinations qui personnalisent la diffusion de publicité en fonction de l'historique de navigation d'un visiteur. </li> 
     <li id="li_B2C3479ECEA74F49B9A2CFDDEE128DF3">Faites correspondre les segments créés avec une caractéristique de la source de données aux destinations qui personnalisent la diffusion de publicité en fonction de l'historique de navigation d'un visiteur. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Ne peut pas être utilisé pour le ciblage publicitaire hors site</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> Cette destination peut être utilisée pour le ciblage publicitaire hors site</span></b> </td> 
   <td colname="col3">Ces restrictions sont généralement utilisées avec le paramètre Lorsque sélectionné, vous ne pouvez pas : 
    <ul id="ul_B9352FF5282C481BA3A24C581217A156"> 
     <li id="li_0F89583A603D4CD8804724954CFD52C6">Ajoutez des caractéristiques aux segments associés aux destinations qui ciblent à nouveau les utilisateurs d'autres sites. </li> 
     <li id="li_ABDD8BEDE9AF411695C7BDF9AE522BA7">Mappez les segments créés avec une caractéristique de la source de données vers les destinations qui reciblent les utilisateurs d'autres sites. </li> 
    </ul> <p>Souvent requis lorsque vous travaillez avec des données provenant de plateformes de médias sociaux. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Ne peut pas être utilisé pour la personnalisation sur site</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> Cette destination peut être utilisée pour la personnalisation publicitaire sur site.</span></b> </td> 
   <td colname="col3">Lorsque cette option est sélectionnée, vous ne pouvez pas : 
    <ul id="ul_3360EB209E07402A863F0E7473B99D3F"> 
     <li id="li_88B3842B67E040EB9DC0BBEB8E5EC251">Ajoutez des caractéristiques aux segments associés aux destinations qui personnalisent le contenu en fonction des intérêts de l'utilisateur ou de l'historique de navigation Web. </li> 
     <li id="li_6506254CCE6546039A3D82B60368C8B4">Faites correspondre les segments créés avec une caractéristique de la source de données aux destinations qui personnalisent le contenu en fonction des intérêts de l'utilisateur ou de l'historique de navigation Web. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Processus{#workflow}

Pour commencer, examinez la source de données et la documentation de destination. Ces articles contiennent des instructions sur l'ajout de commandes et de libellés d'exportation à vos sources de données et à vos destinations.

* [Création d'une source de données](../features/manage-datasources.md#create-data-source)
* [Ajout d'étiquettes d'exportation de données à une destination](../features/destinations/add-data-export-labels.md)