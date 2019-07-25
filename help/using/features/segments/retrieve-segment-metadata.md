---
description: Lorsque Audience Manager envoie des informations de segment à un partenaire de données, il identifie ces objets avec des identifiants numériques. En tant que partenaire de données, lorsque vous partagez ces informations avec vos clients (ou travaillez avec vous-même), un nom et une description réels offrent une meilleure expérience aux clients dans les rapports, les tableaux de bord ou d'autres interfaces utilisateur (UI). Les partenaires de données peuvent mettre ces noms conviviaux à la disposition de leurs clients avec les méthodes manuelles ou automatisées décrites dans cette section.
seo-description: Lorsque Audience Manager envoie des informations de segment à un partenaire de données, il identifie ces objets avec des identifiants numériques. En tant que partenaire de données, lorsque vous partagez ces informations avec vos clients (ou travaillez avec vous-même), un nom et une description réels offrent une meilleure expérience aux clients dans les rapports, les tableaux de bord ou d'autres interfaces utilisateur (UI). Les partenaires de données peuvent mettre ces noms conviviaux à la disposition de leurs clients avec les méthodes manuelles ou automatisées décrites dans cette section.
seo-title: Récupération des métadonnées de segment
solution: Audience Manager
title: Récupération des métadonnées de segment
uuid: 719 e 2 c 41-8788-4 e 8 a -967 a-e 367421 f 9 f 84
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Retrieving Segment Metadata {#retrieving-segment-metadata}

Lorsque Audience Manager envoie des informations de segment à un partenaire de données, il identifie ces objets avec des identifiants numériques. As a data partner, when you share this information with your customers (or work with it yourself), an actual name and description provide a better experience for customers in reports, dashboards, or other user interfaces ([!DNL UI]). Les partenaires de données peuvent mettre ces noms conviviaux à la disposition de leurs clients avec les méthodes manuelles ou automatisées décrites dans cette section.

## Manual method {#manual-method}

En tant que partenaire de données, vous avez probablement la possibilité d'obtenir des métadonnées d'audience auprès de vos clients par le biais de processus manuels. This could include files attached to emails or from customers adding that data through a [!DNL UI] you've built and maintained for this purpose. Ces processus fonctionnent, mais ils sont souvent fastidieux, temps - consommer et peuvent exiger un travail manuel de saisie de données. Ces méthodes sont souvent utilisées pour aider à obtenir une intégration rapidement et rapidement, mais elles ne fournissent pas la meilleure expérience client à long terme. As an alternative, you can use the [!DNL Audience Manager] [!DNL API] to get segment metadata automatically.

## Automated method {#automated-method}

[!DNL Audience Manager] fournit un ensemble d'API [REST](../../api/rest-api-main/rest-api-main.md) qui vous permettent de récupérer automatiquement les métadonnées de segment. With the [!DNL API], you can create jobs that retrieve segment metadata at scheduled intervals or automatically, whenever you process [!DNL Audience Manager] data and find a new segment ID. Pour plus d'informations, voir les étapes ci-dessous.

### Étape 1 : Vérification des API Audience Manager

The [Getting Started with REST APIs](../../api/rest-api-main/aam-api-getting-started.md) section contains information about general requirements, authentication, available methods, etc. This is a good place to begin if you haven't worked with the [!DNL Audience Manager] [!DNL API] before.

### Étape 2 : Demande d'accès oauth 2

You need a client ID and secret to make [!DNL API] calls. Vous pouvez obtenir un ID client et un secret de votre spécialiste d'intégration lors du processus de configuration de l'intégration. You can also send an email request to [!UICONTROL Audience Manager Customer Care] at [!DNL amsupport@adobe.com].

### Étape 3 : Recueillir des informations spécifiques aux clients de chaque client intégré

Demandez ce qui suit à chaque client intégré :

* Nom d'utilisateur : Ceci s'applique à un utilisateur restreint disposant d'autorisations en lecture seule pour la destination associée à une intégration spécifique.
* Mot de passe : Mot de passe de l'utilisateur.
* ID de destination : Il s'agit de l'identifiant (entier) associé à la destination créée pour l'intégration de serveur à serveur spécifique.

### Étape 4 : Récupération des métadonnées de segment avec un appel d'API

After completing the previous steps, you can use a `GET` method to retrieve segment metadata. For a sample request and response, see [Return Destination Mappings](../../api/rest-api-main/aam-api-destinations/aam-api-retrieve-destinations.md#return-dest-mappings). This call returns segment data formatted as key-value pairs in a [!DNL JSON] object. Certains des attributs importants de segment renvoyés dans la réponse sont répertoriés dans le tableau suivant.

<table id="table_446384AE9A36408A9C570CB7DB72C3D6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Destinationmappingid</code> </p> </td> 
   <td colname="col2"> <p>The <span class="keyword"> Audience Manager</span> segment ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Elementname</code> </p> </td> 
   <td colname="col2"> <p>Nom du segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Elementdescription</code> </p> </td> 
   <td colname="col2"> <p>Un texte décrivant brièvement le segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Elementstatus</code> </p> </td> 
   <td colname="col2"> <p>Etat actuel du mappage de segments. Les options d'état renvoyées sont les suivantes : </p> 
    <ul id="ul_BA3A1F5A773D4ECD9A1A3A1118BDDA8A"> 
     <li id="li_A12B858BD0AD4F35BCD50A4D113D86FF"> <code> actif</code> </li> 
     <li id="li_98C04A861C2D4364B5FBD24498E8E9C5"> <code> inactif</code> </li> 
     <li id="li_1913A10948894FF3B507C0A3FE775CC1"> <code> supprimé</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>