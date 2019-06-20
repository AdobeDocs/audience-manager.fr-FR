---
description: Un fichier de métadonnées associe des ID numériques aux noms que vous pouvez lire et comprendre. Les rapports Optimisation d'audience affichent des noms lisibles dans les menus des options de rapport.
seo-description: Un fichier de métadonnées associe des ID numériques aux noms que vous pouvez lire et comprendre. Les rapports Optimisation d'audience affichent des noms lisibles dans les menus des options de rapport.
seo-title: Présentation et mappages des fichiers de métadonnées
solution: Audience Manager
title: Présentation et mappages des fichiers de métadonnées
uuid: 70 df 7 f 11-69 c 5-4873-a 69 d -8 f 93 f 94 e 9837
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Overview and Mappings for Metadata Files{#overview-and-mappings-for-metadata-files}

Un fichier de métadonnées associe des ID numériques aux noms que vous pouvez lire et comprendre. Les rapports Optimisation d&#39;audience affichent des noms lisibles dans les menus des options de rapport.

## Aperçu {#overview}

Une analyse des métadonnées et de leur utilisation. Un fichier de métadonnées doit être accompagné d&#39;un fichier de données. Le contenu du fichier de métadonnées correspond aux informations sur le fichier de données aux libellés humainement lisibles dans les menus des rapports. For more information, see [Data Files for Audience Optimization Reports](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md).

### Les fichiers de métadonnées contiennent des données sur d&#39;autres données

Un fichier de métadonnées contient des informations sur d&#39;autres types de données. To help you understand how this works, let’s review how [!DNL Audience Manager] receives data.

During an impression or click event, [!DNL Audience Manager] receives data in an URL string known as an *event call*.

L&#39;appel d&#39;événement organise les informations dans des ensembles de paires clé-valeur définies. Les valeurs d&#39;une paire clé-valeur contiennent des données numériques. Le fichier de métadonnées contient des noms et d&#39;autres informations lisibles correspondant à l&#39;ID dans chaque paire clé-valeur.

### ID de lien de métadonnées en noms lisibles

Le fichier de métadonnées doit lier un ID numérique à un nom lisible. As an example, say an event call contains a creative ID in a key-value pair like this: `d_creative:1234`. Sans fichier de métadonnées, ce créatif s&#39;affichera sous la forme 1234 dans un menu d&#39;options.

Cependant, un fichier de métadonnées correctement formaté peut lier ce créatif à un nom réel, tel que « Advertiser Creative A », qui est un nom que vous pouvez lire et reconnaître dans un rapport.

### Quand avez-vous besoin d&#39;un fichier de métadonnées ?

First, a metadata file, and all of the parameters listed below, are required in an event call when you want to use the [Audience Optimization Reports](../../../reporting/audience-optimization-reports/audience-optimization-reports.md).

Second, you need a metadata file if you’re sending your own data to [!DNL Audience Manager] or if you want to see data in the reports from other providers we’re not integrated with. For example, [!DNL Audience Manager] has an integration with Google’s [Double-click Campaign Manager](../../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) (DCM). Because of this relationship, [!DNL Audience Manager] can associate IDs with names and descriptions used by the report options. Sans intégration, nous pouvons toujours assimiler des données, mais les options du rapport afficheront des identifiants numériques plutôt que des noms descriptifs.

![](assets/metadata_menu.png)

## File Mappings {#file-mappings}

The following table lists the key-value pairs that hold data used by the [!UICONTROL Audience Optimization] reports. Si vous devez utiliser un fichier de métadonnées, il contiendra des informations intelligibles qui correspondent aux valeurs de ces paires clé-valeur. Les valeurs de ces clés acceptent uniquement des entiers (type de données INT). Note, *italics* indicates a variable placeholder. Les autres éléments sont des constantes ou des clés et ne changent pas.

>[!IMPORTANT]
>
>If you&#39;re using the [!UICONTROL Audience Optimization] reports, *all* of these values are required in the event call.

<table id="table_B2C8C493080E449CA71C4EF07D9476BD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Option de rapport </th> 
   <th colname="col2" class="entry"> Paires clé-valeur de métadonnées </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Annonceur </p> </td> 
   <td colname="col2"> <p> <code>d_ adsrc = <i>ID de source de données ou code d'intégration</i></code> </p> <p>Il s'agit du code d'intégration ou de source de données de l'annonceur fourni lors de la création d'une source de données. See <a href="../../../features/manage-datasources.md#create-data-source"> Create a Data Source</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Unité opérationnelle (BU) </p> </td> 
   <td colname="col2"> <p> <code>d_ bu = <i>ID d'unité opérationnelle</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Campagne </p> </td> 
   <td colname="col2"> <p> <code>d_ campaign = <i>ID de campagne</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Création </p> </td> 
   <td colname="col2"> <p> <code>d_ creative = <i>ID créatif</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Exchange </p> </td> 
   <td colname="col2"> <p>Accepte 2 paires clé-valeur différentes : </p> 
    <ul id="ul_3B3B751A8A134096B0912E81A0983B9D"> 
     <li id="li_57BAC45A7B274AB695945E174A4D8A35"> <code>d_ exchange = <i>ID pour l'échange qui a servi la publicité</i></code> </li> 
     <li id="li_CCDF00DE59D3451C8EF590DD3E1A806D"> <code>d_ site = <i>ID du site une publicité diffusée sur</i></code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ordre d'insertion (IO) </p> </td> 
   <td colname="col2"> <p> <code>d_ io = <i>ID de l'ordre d'insertion</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Plate-forme </p> </td> 
   <td colname="col2"> <p> <code>d_ src = <i>ID de source de données</i></code> </p> <p>This is the <a href="../../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> data source</a> ID for the platform providing metadata information (e.g., DFA, Atlas, GBM, MediaMath, etc.). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tactique </p> </td> 
   <td colname="col2"> <p> <code>d_ tactique = <i>ID tactique</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Vertical </p> </td> 
   <td colname="col2"> <p> <code>d_ vert = <i>ID vertical</i></code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## How Event Call IDs Shape File Names, Contents, and Delivery Paths {#how-ids-shape-file-names}

Les ID transmis par ces paires clé-valeur permettent de créer le fichier de métadonnées - nom et contenu. Les sections et illustrations suivantes montrent comment cela fonctionne. Ces exemples créent un fichier qui contient le nom d&#39;un élément créatif dans une campagne, mais d&#39;autres combinaisons sont possibles.

### Appel d&#39;événement

In this example we&#39;ll create a metadata file that brings creative names in to an [!UICONTROL Audience Optimization] report. Pour ce faire, nous devons extraire les ID d&#39;élément créatif, de campagne et de source de données d&#39;un appel d&#39;événement.

![](assets/metadata_file_event.png)

### Nom de fichier

Le fichier - nom est basé sur les identifiants d&#39;élément créatif, de campagne et de source de données. Dans ce cas, comparez les différences ici entre les données clé-valeur d&#39;un appel d&#39;événement et comment elles sont utilisées dans un fichier - name.

Dans un fichier - name :

* The data source key changes to `dpid` from `d_src`.

* Les ID d&#39;élément créatif et de campagne représentent une catégorie plutôt qu&#39;un identifiant réel.

![](assets/metadata_file_name.png)

See [Naming Conventions for Metadata Files](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md).

### Contenu du fichier

Dans cet exemple, le contenu du fichier reflète les ID de créatif et de campagne transmis lors de l&#39;appel d&#39;événement. Le nouvel élément ici est un nom lisible. Once processed, the name in this file will appear as an option in the Creative menu of an [!UICONTROL Audience Optimization] report.

![](assets/metadata_file_contents.png)

See [Content Format for Metadata Files](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-contents.md).

### Remise de fichiers

After you name and add data to a file, you send it to an Amazon S3 storage directory provided by [!DNL Audience Manager]. See [Delivery Methods for Metadata Files](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-delivery-methods.md) and [Status Updates for Metadata Files](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-update-status.md).

>[!MORE_ LIKE_ THIS]
>
>* [Fichiers de données pour les rapports Optimisation d&#39;audience](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md)
>* [Capture des données de clic de campagne par appels de pixels](../../../integration/media-data-integration/click-data-pixels.md)
>* [Capture des données d’impression de campagne via des appels de pixel](../../../integration/media-data-integration/impression-data-pixels.md)

