---
description: Lorsque l’Audience Manager envoie des informations de segment à un partenaire de données, elle les identifie avec des identifiants numériques. En tant que partenaire de données, lorsque vous partagez ces informations avec vos clients (ou travaillez avec eux vous-même), un nom et une description réels offrent une meilleure expérience pour les clients dans les rapports, les tableaux de bord ou d’autres interfaces utilisateur (interface utilisateur). Les partenaires de données peuvent mettre ces noms conviviaux à la disposition de leurs clients avec les méthodes manuelles ou automatisées décrites dans cette section.
seo-description: Lorsque l’Audience Manager envoie des informations de segment à un partenaire de données, elle les identifie avec des identifiants numériques. En tant que partenaire de données, lorsque vous partagez ces informations avec vos clients (ou travaillez avec eux vous-même), un nom et une description réels offrent une meilleure expérience pour les clients dans les rapports, les tableaux de bord ou d’autres interfaces utilisateur (interface utilisateur). Les partenaires de données peuvent mettre ces noms conviviaux à la disposition de leurs clients avec les méthodes manuelles ou automatisées décrites dans cette section.
seo-title: Récupération des métadonnées de segment
solution: Audience Manager
title: Récupération des métadonnées de segment
uuid: 719e2c41-8788-4e8a-967a-e367421f9f84
feature: Segments
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '598'
ht-degree: 1%

---


# Récupération des métadonnées de segment {#retrieving-segment-metadata}

Lorsque l’Audience Manager envoie des informations de segment à un partenaire de données, elle les identifie avec des identifiants numériques. En tant que partenaire de données, lorsque vous partagez ces informations avec vos clients (ou travaillez avec eux vous-même), un nom et une description réels offrent une meilleure expérience pour les clients dans les rapports, les tableaux de bord ou d’autres interfaces utilisateur ([!DNL UI]). Les partenaires de données peuvent mettre ces noms conviviaux à la disposition de leurs clients avec les méthodes manuelles ou automatisées décrites dans cette section.

## Méthode manuelle {#manual-method}

En tant que partenaire de données, vous êtes probablement habitué à obtenir des métadonnées d’audience de vos clients au moyen de processus manuels. Il peut s’agir de fichiers joints à des courriels ou de clients ajoutant ces données par le biais d’un fichier [!DNL UI] que vous avez créé et géré à cette fin. Ces processus fonctionnent, mais ils sont souvent lourds, prennent du temps et peuvent nécessiter une saisie manuelle des données. Ces méthodes sont souvent utilisées pour aider à mettre rapidement en oeuvre une intégration, mais elles ne fournissent pas la meilleure expérience client à long terme. Vous pouvez également utiliser la variable [!DNL Audience Manager] pour [!DNL API] obtenir automatiquement les métadonnées de segment.

## Méthode automatisée {#automated-method}

[!DNL Audience Manager] fournit un ensemble d’API [](../../api/rest-api-main/rest-api-main.md) REST qui vous permettent de récupérer automatiquement les métadonnées de segment. Grâce à [!DNL API]cette fonction, vous pouvez créer des tâches qui récupèrent les métadonnées de segment à intervalles réguliers ou automatiquement, chaque fois que vous traitez [!DNL Audience Manager] des données et recherchez un nouvel identifiant de segment. Pour plus d’informations, voir les étapes ci-dessous.

### Étape 1 : Vérification des API d’Audience Manager

La section [Prise en main des API](../../api/rest-api-main/aam-api-getting-started.md) REST contient des informations sur les exigences générales, l’authentification, les méthodes disponibles, etc. C&#39;est un bon point de départ si vous n&#39;avez pas travaillé avec le [!DNL Audience Manager] passé [!DNL API] .

### Étape 2 : Demande d’informations d’identification d’accès OAuth2

Vous avez besoin d’un ID client et d’un secret pour passer [!DNL API] des appels. Vous pouvez obtenir un ID de client et un secret auprès de votre spécialiste de l’intégration pendant le processus de configuration de l’intégration. Vous pouvez également envoyer une demande par courrier électronique à [!UICONTROL Audience Manager Customer Care] l’adresse [!DNL amsupport@adobe.com].

### Étape 3 : Collecter des informations spécifiques aux clients de chaque client intégré

Demandez à chaque client intégré ce qui suit :

* Nom d&#39;utilisateur : Il s’agit d’un utilisateur restreint disposant d’autorisations en lecture seule pour la destination associée à une intégration spécifique.
* Mot de passe : Mot de passe utilisateur.
* ID de destination : Il s’agit de l’identifiant (entier) associé à la destination créée pour l’intégration serveur à serveur spécifique.

### Étape 4 : Récupération des métadonnées de segment avec un appel d’API

Après avoir exécuté les étapes précédentes, vous pouvez utiliser une `GET` méthode pour récupérer les métadonnées de segment. Pour un exemple de requête et de réponse, voir Correspondances [de destination des](../../api/rest-api-main/aam-api-destinations/aam-api-retrieve-destinations.md#return-dest-mappings)retours. Cet appel renvoie des données de segment formatées en paires clé-valeur dans un [!DNL JSON] objet. Certains des attributs de segment importants renvoyés dans la réponse sont répertoriés dans le tableau suivant.

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
   <td colname="col2"> <p>ID du segment <span class="keyword"> d’Audience Manager</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> elementName</code> </p> </td> 
   <td colname="col2"> <p>Nom du segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> elementDescription</code> </p> </td> 
   <td colname="col2"> <p>Texte décrivant brièvement le segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> elementStatus</code> </p> </td> 
   <td colname="col2"> <p>Statut actuel du mappage de segments. Les options d’état renvoyées sont les suivantes : </p> 
    <ul id="ul_BA3A1F5A773D4ECD9A1A3A1118BDDA8A"> 
     <li id="li_A12B858BD0AD4F35BCD50A4D113D86FF"> <code> active</code> </li> 
     <li id="li_98C04A861C2D4364B5FBD24498E8E9C5"> <code> inactive</code> </li> 
     <li id="li_1913A10948894FF3B507C0A3FE775CC1"> <code> deleted</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>