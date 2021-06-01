---
description: Un fichier de métadonnées associe des identifiants numériques avec des noms que vous pouvez lire et comprendre. Les rapports d’Audience Optimization affichent des noms lisibles dans les menus des différentes options de rapport.
seo-description: Un fichier de métadonnées associe des identifiants numériques avec des noms que vous pouvez lire et comprendre. Les rapports d’Audience Optimization affichent des noms lisibles dans les menus des différentes options de rapport.
seo-title: Présentation et correspondances des fichiers de métadonnées
solution: Audience Manager
title: Présentation et correspondances des fichiers de métadonnées
uuid: 70df7f11-69c5-4873-a69d-8f93f94e9837
feature: Fichiers journaux
exl-id: 8c59ab80-f04a-42df-891e-a187ecd0219f
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '843'
ht-degree: 4%

---

# Présentation et correspondances des fichiers de métadonnées{#overview-and-mappings-for-metadata-files}

Un fichier de métadonnées associe des identifiants numériques avec des noms que vous pouvez lire et comprendre. Les rapports d’Audience Optimization affichent des noms lisibles dans les menus des différentes options de rapport.

## Présentation {#overview}

Une révision des métadonnées et de leur utilisation. Un fichier de métadonnées doit être accompagné d’un fichier de données. Le contenu du fichier de métadonnées correspond aux informations du fichier de données aux libellés associés, lisibles par l’utilisateur, dans les menus du rapport. Pour plus d’informations, voir [Fichiers de données pour les rapports d’Audience Optimization et les fichiers journaux pratiques](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md).

### Les Fichiers De Métadonnées Contiennent Des Données Sur D’Autres Données

Un fichier de métadonnées contient des informations sur d’autres types de données. Pour vous aider à comprendre comment cela fonctionne, examinons comment [!DNL Audience Manager] reçoit des données.

Lors d’un événement d’impression ou de clic, [!DNL Audience Manager] reçoit des données dans une chaîne d’URL appelée *appel d’événement*.

L’appel d’événement classe les informations dans des ensembles de paires clé-valeur définies. Les valeurs d’une paire clé-valeur contiennent des données numériques. Le fichier de métadonnées contient des noms et d’autres informations lisibles correspondant à l’identifiant dans chaque paire clé-valeur.

### Les identifiants de liens de métadonnées vers des noms lisibles

Le fichier de métadonnées est nécessaire pour lier un identifiant numérique à un nom lisible. Par exemple, supposons qu’un appel d’événement contienne un ID créatif dans une paire clé-valeur comme celle-ci : `d_creative:1234`. Sans fichier de métadonnées, ce créatif afficherait 1234 dans un menu d’options.

Cependant, un fichier de métadonnées correctement formaté peut associer ce créatif à un nom réel comme &quot;Créatif publicitaire A&quot;, qui est un nom que vous pouvez lire et reconnaître dans un rapport.

### À quel moment un fichier de métadonnées est-il nécessaire ?

Tout d’abord, un fichier de métadonnées et tous les paramètres répertoriés ci-dessous sont requis dans un appel d’événement lorsque vous souhaitez utiliser les [rapports d’Audience Optimization](../../../reporting/audience-optimization-reports/audience-optimization-reports.md).

Deuxièmement, vous avez besoin d’un fichier de métadonnées si vous envoyez vos propres données à [!DNL Audience Manager] ou si vous souhaitez afficher les données dans les rapports d’autres fournisseurs avec lesquels nous ne sommes pas intégrés. Par exemple, [!DNL Audience Manager] a une intégration avec la balise [Double-cliquez sur Campaign Manager](../../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) (DCM) de Google. En raison de cette relation, [!DNL Audience Manager] peut associer des identifiants aux noms et descriptions utilisés par les options de rapport. Sans intégration, nous pouvons toujours ingérer des données, mais les options de rapport affichent des identifiants numériques au lieu d’un nom descriptif.

![image du menu de métadonnées](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata_menu.png)

## Mappages de fichiers {#file-mappings}

Le tableau suivant répertorie les paires clé-valeur qui contiennent les données utilisées par les rapports [!UICONTROL Audience Optimization]. Si vous devez utiliser un fichier de métadonnées, il contiendra des informations lisibles qui correspondent aux valeurs de ces paires clé-valeur. Les valeurs de ces clés acceptent uniquement les entiers (type de données INT). Remarque : *italics* indique un espace réservé de variable. Les autres éléments sont des constantes ou des clés et ne changent pas.

>[!IMPORTANT]
>
>Si vous utilisez les rapports [!UICONTROL Audience Optimization], *toutes* de ces valeurs sont requises dans l’appel d’événement.

<table id="table_B2C8C493080E449CA71C4EF07D9476BD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Option de rapport </th> 
   <th colname="col2" class="entry"> Paires clé-valeur des métadonnées </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Annonceur </p> </td> 
   <td colname="col2"> <p> <code>d_adsrc = <i>data source ID or integration code</i></code> </p> <p>Il s’agit de l’identifiant de source de données ou du code d’intégration de l’annonceur fourni lors de la création d’une source de données. Voir <a href="../../../features/manage-datasources.md#create-data-source"> Création d’une source de données</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Unité opérationnelle (BU) </p> </td> 
   <td colname="col2"> <p> <code>d_bu = <i>business unit ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Campagne </p> </td> 
   <td colname="col2"> <p> <code>d_campaign = <i>campaign ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Creative </p> </td> 
   <td colname="col2"> <p> <code>d_creative = <i>creative ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Exchange </p> </td> 
   <td colname="col2"> <p>Accepte 2 paires clé-valeur différentes : </p> 
    <ul id="ul_3B3B751A8A134096B0912E81A0983B9D"> 
     <li id="li_57BAC45A7B274AB695945E174A4D8A35"> <code>d_exchange = <i>ID for the exchange that served the ad</i></code> </li> 
     <li id="li_CCDF00DE59D3451C8EF590DD3E1A806D"> <code>d_site = <i>ID for the site an ad served on</i></code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ordre d’insertion (IO) </p> </td> 
   <td colname="col2"> <p> <code>d_io = <i>insertion order ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Plate-forme </p> </td> 
   <td colname="col2"> <p> <code>d_src = <i>data source ID</i></code> </p> <p>Il s’agit de l’ID de la source de données <a href="../../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> de la plateforme fournissant des informations de métadonnées (par exemple, DFA, Atlas, GBM, MediaMath, etc.).</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tactique </p> </td> 
   <td colname="col2"> <p> <code>d_tactic = <i>tactic ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Vertical </p> </td> 
   <td colname="col2"> <p> <code>d_vert = <i>vertical ID</i></code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Comment les identifiants d’appel d’événement façonnent les noms de fichier, le contenu et les chemins de diffusion {#how-ids-shape-file-names}

Les identifiants transmis par ces paires clé-valeur permettent de créer le nom du fichier de métadonnées et son contenu. Les sections et illustrations suivantes illustrent ce fonctionnement. Ces exemples génèrent un fichier qui contient le nom d’un élément créatif dans une campagne, mais d’autres combinaisons sont possibles.

### Appel d’événement

Dans cet exemple, nous allons créer un fichier de métadonnées qui contient des noms créatifs dans un rapport [!UICONTROL Audience Optimization]. Pour ce faire, nous devons extraire les identifiants de source de données, de campagne et de création d’un appel d’événement.

![image d’appel d’événement](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata_file_event.png)

### Nom de fichier

Le nom de fichier est basé sur les ID de création, de campagne et de source de données. Dans ce cas, comparez ici les différences entre les données clé-valeur dans un appel d’événement et la manière dont elles sont utilisées dans un nom de fichier.

Dans un nom de fichier :

* La clé de source de données passe à `dpid` à partir de `d_src`.

* Les identifiants de création et de campagne représentent une catégorie plutôt qu’un identifiant réel.

![comment est créé un nom de fichier](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata_file_name.png)

Voir [Conventions de dénomination des fichiers de métadonnées](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md).

### Contenu du fichier

Dans cet exemple, le contenu du fichier reflète les identifiants de création et de campagne transmis dans l’appel d’événement. Le nouvel élément ici est un nom lisible. Une fois le traitement effectué, le nom de ce fichier s’affiche comme option dans le menu Créatif d’un rapport [!UICONTROL Audience Optimization].

![contenu d’un fichier de métadonnées](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata_file_contents.png)

Voir [Format de contenu pour les fichiers de métadonnées](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-contents.md).

### Diffusion de fichiers

Après avoir nommé et ajouté des données à un fichier, vous l’envoyez dans un répertoire de stockage Amazon S3 fourni par [!DNL Audience Manager]. Voir [Méthodes de diffusion pour les fichiers de métadonnées](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-delivery-methods.md).

>[!MORELIKETHIS]
>
>* [Fichiers de données pour les rapports d’Audience Optimization](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md)
* [Capture des données de clics de campagne via des appels de pixel](../../../integration/media-data-integration/click-data-pixels.md)
* [Capture des données d’impression de campagne via des appels de pixel](../../../integration/media-data-integration/impression-data-pixels.md)

