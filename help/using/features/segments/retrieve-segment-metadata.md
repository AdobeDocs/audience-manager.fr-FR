---
description: Lorsqu’Audience Manager envoie des informations sur les segments à un partenaire de données, il identifie ces objets par des identifiants numériques. En tant que partenaire de données, lorsque vous partagez ces informations avec vos clients (ou que vous les utilisez vous-même), un nom et une description réels offrent une meilleure expérience aux clients dans les rapports, les tableaux de bord ou d’autres interfaces utilisateur. Les partenaires de données peuvent mettre ces noms conviviaux à la disposition de leurs clients à l’aide des méthodes manuelles ou automatisées décrites dans cette section.
seo-description: When Audience Manager sends segment information to a data partner, it identifies these objects with numeric IDs. As a data partner, when you share this information with your customers (or work with it yourself), an actual name and description provide a better experience for customers in reports, dashboards, or other user interfaces (UI). Data partners can make these friendly names available to their customers with either the manual or automated methods described in this section.
seo-title: Retrieving Segment Metadata
solution: Audience Manager
title: Récupération des métadonnées de segment
uuid: 719e2c41-8788-4e8a-967a-e367421f9f84
feature: Segments
exl-id: 64922cf8-f7bf-4e33-871f-d33626b06360
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 0%

---

# Récupération des métadonnées de segment {#retrieving-segment-metadata}

Lorsqu’Audience Manager envoie des informations sur les segments à un partenaire de données, il identifie ces objets par des identifiants numériques. En tant que partenaire de données, lorsque vous partagez ces informations avec vos clients (ou que vous les utilisez vous-même), un nom et une description réels offrent une meilleure expérience aux clients dans les rapports, les tableaux de bord ou d’autres interfaces utilisateur ([!DNL UI]). Les partenaires de données peuvent mettre ces noms conviviaux à la disposition de leurs clients à l’aide des méthodes manuelles ou automatisées décrites dans cette section.

## Méthode manuelle {#manual-method}

En tant que partenaire de données, vous êtes probablement habitué à obtenir des métadonnées d’audience de vos clients par le biais de processus manuels. Il peut s’agir de fichiers joints à des e-mails ou provenant de clients qui ajoutent ces données par le biais d’un [!DNL UI] que vous avez créé et géré à cet effet. Ces processus fonctionnent, mais ils sont souvent lourds, longs et peuvent nécessiter un travail de saisie manuelle des données. Ces méthodes sont souvent utilisées pour aider à mettre rapidement en route une intégration, mais elles ne fournissent pas la meilleure expérience client à long terme. Vous pouvez également utiliser l’[!DNL Audience Manager] [!DNL API] pour obtenir automatiquement des métadonnées de segment.

## Méthode automatisée {#automated-method}

[!DNL Audience Manager] fournit un ensemble d’API [REST](../../api/rest-api-main/rest-api-main.md) qui vous permettent de récupérer automatiquement les métadonnées des segments. Avec le [!DNL API], vous pouvez créer des tâches qui récupèrent des métadonnées de segment à intervalles planifiés ou automatiquement, chaque fois que vous traitez des données de [!DNL Audience Manager] et recherchez un nouvel identifiant de segment. Pour plus d’informations, reportez-vous aux étapes ci-dessous.

### Étape 1 : vérifier les API Audience Manager

La section [Prise en main des API REST](../../api/rest-api-main/aam-api-getting-started.md) contient des informations sur les exigences générales, l’authentification, les méthodes disponibles, etc. C’est un bon point de départ si vous n’avez pas déjà travaillé avec le [!DNL Audience Manager] [!DNL API].

### Étape 2 : demander des informations d’identification d’accès OAuth2

Vous avez besoin d’un identifiant client et d’un secret pour effectuer des appels [!DNL API]. Vous pouvez obtenir un identifiant client et un secret auprès de votre spécialiste de l’intégration pendant le processus de configuration de l’intégration. Vous pouvez également envoyer une demande par e-mail à [!UICONTROL Audience Manager Customer Care] sur [!DNL amsupport@adobe.com].

### Étape 3 : collecter des informations spécifiques au client auprès de chaque client intégré

Demandez les éléments suivants à chaque client intégré :

* Nom d’utilisateur : il s’adresse à un utilisateur restreint disposant d’autorisations en lecture seule pour la destination associée à une intégration spécifique.
* Mot de passe : mot de passe de l’utilisateur.
* Identifiant de destination : il s’agit de l’identifiant (un entier) associé à la destination créée pour l’intégration serveur à serveur spécifique.

### Étape 4 : récupérer les métadonnées de segment avec un appel API

Après avoir suivi les étapes précédentes, vous pouvez utiliser une méthode `GET` pour récupérer les métadonnées du segment. Pour obtenir un exemple de requête et de réponse, voir [Renvoi des mappages de destination](../../api/rest-api-main/aam-api-destinations/aam-api-retrieve-destinations.md#return-dest-mappings). Cet appel renvoie des données de segment formatées en tant que paires clé-valeur dans un objet [!DNL JSON]. Certains des attributs de segment importants renvoyés dans la réponse sont répertoriés dans le tableau suivant.

<table id="table_446384AE9A36408A9C570CB7DB72C3D6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> destinationMappingId</code> </p> </td> 
   <td colname="col2"> <p>Identifiant de segment <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> elementName</code> </p> </td> 
   <td colname="col2"> <p>Nom du segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> elementDescription</code> </p> </td> 
   <td colname="col2"> <p>du texte qui décrit brièvement le segment ; </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> elementStatus</code> </p> </td> 
   <td colname="col2"> <p>Statut actuel du mappage de segments. Les options de statut renvoyées sont les suivantes : </p> 
    <ul id="ul_BA3A1F5A773D4ECD9A1A3A1118BDDA8A"> 
     <li id="li_A12B858BD0AD4F35BCD50A4D113D86FF"> <code> active</code> </li> 
     <li id="li_98C04A861C2D4364B5FBD24498E8E9C5"> <code> inactive</code> </li> 
     <li id="li_1913A10948894FF3B507C0A3FE775CC1"> <code> deleted</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>
