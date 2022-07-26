---
description: Les contrôles des exportations de données vous empêchent d’envoyer des données vers des destinations lorsque cette action enfreint les accords sur la confidentialité des données ou l’utilisation des données.
seo-description: Data Export Controls prevent you from sending data to destinations when this action violates data privacy or data use agreements.
seo-title: Data Export Controls
solution: Audience Manager
title: Contrôles des exportations de données
uuid: de7f3608-c0cb-4049-973a-8be54525c600
feature: Data Export Controls
exl-id: 4369c210-bcf1-48cc-a9bb-0d122f6c03d4
source-git-commit: c7a6de018a0ddd782eecec0844c4f5c824431119
workflow-type: tm+mt
source-wordcount: '882'
ht-degree: 1%

---

# Contrôles des exportations de données {#data-export-controls}

[!UICONTROL Data Export Controls] vous empêche d’envoyer des données vers des destinations lorsque cette action enfreint les accords sur la confidentialité des données ou l’utilisation des données.

## Présentation {#overview}

[!UICONTROL Data Export Controls] vous permettre de classer [sources de données](../features/datasources-list-and-settings.md#data-sources-list-and-settings) et [destinations](../features/destinations/destinations.md). Les classifications que vous appliquez déterminent à quel moment les données peuvent ou non être exportées vers une destination. Cette fonctionnalité comprend :

* **[!UICONTROL Data Export Controls]**: Vous pouvez définir les contrôles des exportations de données sur *sources de données*. Lorsqu’ils sont définis sur une source de données, ces contrôles limitent la manière dont cette source de données et ses caractéristiques peuvent être utilisées.
* **[!UICONTROL Data Export Labels]**: Vous pouvez définir des étiquettes d’exportation de données sur *destinations*. Lorsqu’elles sont définies sur une destination, ces étiquettes identifient la manière dont la destination utilise les données. Voir [Ajout de libellés d’exportation de données à une destination](/help/using/features/destinations/add-data-export-labels.md) pour savoir comment ajouter des libellés d’exportation à une destination.

En fonction des classifications appliquées à une source de données et à une destination, les contrôles d’exportation vous empêchent de :

* Ajout d’une caractéristique à un segment lorsque la caractéristique appartient à une source de données disposant d’un contrôle d’exportation de données incompatible avec un libellé d’exportation de données sur une ou plusieurs des destinations auxquelles le segment est mappé.
Par exemple, supposons qu’un segment soit mappé à une destination avec le libellé d’exportation **[!DNL This destination may enable a combination with personally identifiable information (PII)]**. Les contrôles d’exportation vous empêchent d’ajouter une caractéristique à ce segment si la source de données à laquelle appartient la caractéristique possède un contrôle d’exportation de données qui indique : **[!DNL Cannot be tied to personally identifiable information (PII)]**.
* Envoi de données à une destination dont le libellé d’exportation des données est bloqué par un contrôle d’exportation de données sur l’un des éléments suivants :
   * la source de données d’une caractéristique incluse ;
   * La source de données d’une caractéristique utilisée dans un segment inclus ;
   * la règle de fusion de profils utilisée par un segment inclus ;
   * Toutes les sources de données utilisées par la règle de fusion de profils d’un segment inclus.

[!UICONTROL Data Export Controls] sont disponibles automatiquement pour tous les clients d’Audience Manager. Toutefois, vous avez besoin d’autorisations d’administrateur pour ajouter des contrôles d’exportation à une source de données. L’ajout de libellés d’exportation à une destination nécessite des autorisations d’administrateur. *ou* des privilèges suffisants pour créer ou modifier une destination.

## Contrôles et libellés définis {#controls-labels}

[!UICONTROL Data Export Controls] fournissent les contrôles suivants pour vous aider à classer les sources de données et les destinations.

Pour bloquer la diffusion des données, vous devez classer une source de données avec un contrôle d’exportation et ajouter un libellé d’exportation à une destination. Si vous appliquez des contrôles d’exportation à une source ou à une destination de données uniquement, cette fonctionnalité ne limite pas la diffusion des données. Lorsqu’elle est définie sur la source de données *et* , les contrôles d’exportation limiteront les caractéristiques que vous pouvez ajouter à un segment et empêcheront l’envoi des membres du segment vers une destination.

En outre, au moins un libellé d’exportation doit correspondre à un contrôle d’exportation avant que les restrictions de diffusion des données ne prennent effet. Par exemple, supposons que vous ajoutiez la variable [!UICONTROL PII] exporter le contrôle vers une source de données ; Vous ajoutez ensuite le libellé de ciblage sur site à une destination. Dans ce cas, les contrôles des exportations ne limiteront pas la diffusion des données, car les paramètres ne correspondent pas. Cependant, si vous ajoutez la variable [!UICONTROL PII] libellé d&#39;export vers la destination, les contrôles d&#39;export bloqueront l&#39;export.

>[!IMPORTANT]
>
>Vous ne pouvez pas bloquer l’exportation d’un segment en plaçant un contrôle d’exportation de données sur la source de données du segment. Vous devez définir le contrôle sur l’un des éléments suivants :
> * Les sources de données des caractéristiques utilisées dans le segment ;
> * la règle de fusion de profils utilisée par le segment ;
> * Toutes les sources de données utilisées par la règle de fusion de profils du segment.


<br> 

<table id="table_7D1F0270B5604A82B96A13CC49C937C0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Contrôles des exportations de données pour une source de données </th> 
   <th colname="col2" class="entry"> Étiquettes d’exportation de données pour une destination </th> 
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
   <td colname="col1"> <b><span class="uicontrol"> Ne peut pas être lié à des informations d’identification personnelle</span></b> (PII) </td> 
   <td colname="col2"> <b><span class="uicontrol"> Cette destination peut activer une combinaison avec des informations d’identification personnelle (PII).</span></b> </td> 
   <td colname="col3">Lorsque cette option est sélectionnée, vous ne pouvez pas : 
    <ul id="ul_0D5A4D0373374217A4BACDFC3BB2F79D"> 
     <li id="li_C32FC26C6E814412A1C73B840E81BB68">Ajoutez des caractéristiques aux segments mappés aux destinations qui utilisent des informations d’identification personnelles. </li> 
     <li id="li_BF4FD10807AF4E109CEA22FBD3F6F9B3">Mappez les segments créés avec une caractéristique de la source de données vers les destinations qui utilisent des informations d’identification personnelles. </li> 
    </ul> <p>Cela est souvent requis par les fournisseurs de données tiers et lors de l’utilisation de sources de données contenant des informations de suivi des publicités/médias. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Ne peut pas être utilisé pour le ciblage des publicités sur site</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> Cette destination peut être utilisée pour le ciblage des publicités sur site.</span></b> </td> 
   <td colname="col3">Lorsque cette option est sélectionnée, vous ne pouvez pas : 
    <ul id="ul_5B17972E7E0C424A833AD540DFF3CBF2"> 
     <li id="li_05810CEAC8CB4616BB2D52DDDADA84A8">Ajoutez des caractéristiques aux segments mappés aux destinations qui personnalisent la diffusion des publicités en fonction de l’historique de navigation Web d’un visiteur. </li> 
     <li id="li_B2C3479ECEA74F49B9A2CFDDEE128DF3">Mappez les segments créés avec une caractéristique de la source de données vers les destinations qui personnalisent la diffusion des publicités en fonction de l’historique de navigation Web d’un visiteur. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Ne peut pas être utilisé pour le ciblage des publicités hors site</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> Cette destination peut être utilisée pour le ciblage des publicités hors site.</span></b> </td> 
   <td colname="col3">Ces restrictions sont généralement utilisées avec Lorsque cette option est sélectionnée, vous ne pouvez pas : 
    <ul id="ul_B9352FF5282C481BA3A24C581217A156"> 
     <li id="li_0F89583A603D4CD8804724954CFD52C6">Ajoutez des caractéristiques aux segments mappés aux destinations qui reciblent les utilisateurs sur d’autres sites. </li> 
     <li id="li_ABDD8BEDE9AF411695C7BDF9AE522BA7">Mappez les segments créés avec une caractéristique de la source de données vers les destinations qui reciblent les utilisateurs sur d’autres sites. </li> 
    </ul> <p>Souvent requis lors de l’utilisation de données provenant de plateformes de médias sociaux. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Ne peut pas être utilisé pour la personnalisation sur site</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> Cette destination peut être utilisée pour la personnalisation des publicités sur site.</span></b> </td> 
   <td colname="col3">Lorsque cette option est sélectionnée, vous ne pouvez pas : 
    <ul id="ul_3360EB209E07402A863F0E7473B99D3F"> 
     <li id="li_88B3842B67E040EB9DC0BBEB8E5EC251">Ajoutez des caractéristiques aux segments mappés aux destinations qui personnalisent le contenu en fonction des centres d’intérêt des utilisateurs ou de l’historique de navigation Web. </li> 
     <li id="li_6506254CCE6546039A3D82B60368C8B4">Mappez les segments créés avec une caractéristique de la source de données vers les destinations qui personnalisent le contenu en fonction des intérêts des utilisateurs ou de l’historique de navigation sur le Web. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Workflow {#workflow}

Pour commencer, consultez la documentation sur la source de données et la destination. Ces articles fournissent des instructions sur la manière d’ajouter des contrôles et des étiquettes d’exportation à vos sources de données et destinations.

* [Création d’une source de données](../features/manage-datasources.md#create-data-source)
* [Ajout de libellés d’exportation de données à une destination](../features/destinations/add-data-export-labels.md)
