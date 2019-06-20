---
description: Un fichier de données contient des données d'impression, de clic ou de conversion. Lorsque le formatage est correct, vous pouvez importer ces données dans Audience Manager et les afficher dans les rapports Optimisation d'audience. Mettez en forme vos fichiers de données selon ces spécifications dans cette section.
seo-description: Un fichier de données contient des données d'impression, de clic ou de conversion. Lorsque le formatage est correct, vous pouvez importer ces données dans Audience Manager et les afficher dans les rapports Optimisation d'audience. Mettez en forme vos fichiers de données selon ces spécifications dans cette section.
seo-title: Fichiers de données pour les rapports Optimisation d'audience
solution: Audience Manager
title: Fichiers de données pour les rapports Optimisation d'audience
uuid: c 19 eb 0 c 7-47 c 1-4 cdf -8 a 6 c-cd 15 fe 04 c 379
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Data Files for Audience Optimization Reports{#data-files-for-audience-optimization-reports}

Un fichier de données contient des données d&#39;impression, de clic ou de conversion. Lorsque le formatage est correct, vous pouvez importer ces données dans Audience Manager et les afficher dans les rapports Optimisation d&#39;audience. Mettez en forme vos fichiers de données selon ces spécifications dans cette section.

## Aperçu {#overview}

A properly named and formatted data file lets you import impression, click, or conversion data into the [Audience Optimization Reports](../../../reporting/audience-optimization-reports/audience-optimization-reports.md). This is useful when working with a partner who is not integrated with [!DNL Audience Manager] and you want to work with their data in that report suite. Ce processus nécessite des fichiers distincts pour les données d&#39;impression, de clic et de conversion. Ne mixez pas ces événements dans un seul fichier.

Un fichier de données doit être accompagné d&#39;un fichier de métadonnées. Le contenu du fichier de métadonnées correspond aux informations sur le fichier de données aux libellés humainement lisibles dans les menus des rapports. For more information, see [Overview and Mappings for Metadata Files](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md).

## Naming Conventions for Data Files {#naming-conventions}

La syntaxe suivante définit la structure d&#39;un fichier de données bien formaté. Note, *italics* indicates a variable placeholder that changes depending on the file contents.

**Syntaxe :** <pre><code><i>event type</i>_<i>yyyymmjj</i></code></pre>

Dans un fichier - name :

* Le type d&#39;événement indique que le fichier contient des impressions, des clics ou des conversions. Créez un fichier distinct pour chaque type d&#39;événement.
* Un trait de soulignement sépare le type d&#39;événement et un horodatage de date-mois.
* Before uploading, compress your files using gzip and save them with the `.gz` file extension.

Selon ces exigences, nommez vos fichiers de données en fonction de leur contenu :

* Données d&#39;impression : <pre><code>impressions_<i>aaaammjj<i>.gz</code></pre>
* Données de clic : <pre><code>clics_<i>aaaammjj</i>.gz</code></pre>
* Données de conversion : <pre><code>conversions_<i>aaaammjj</i>.gz</code></pre>

## Content Format for Data Files {#content-format}

La syntaxe suivante définit la structure de contenu dans un fichier de données bien structuré. Note, *italics* indicates a variable placeholder and is replaced with an label in an actual data file.

**Syntaxe :** <pre><code><i>libellé d&#39;en-tête 1</i> | <i>libellé d&#39;en-tête 2</i> … <i>libellé d&#39;en-tête n</i> | <i>version</i></code></pre>

Dans le contenu du fichier :

* Les étiquettes d&#39;en-tête doivent apparaître dans l&#39;ordre, comme illustré dans le tableau ci-dessous. Les impressions et les clics utilisent les mêmes étiquettes. Les fichiers de conversion contiennent des en-têtes supplémentaires.
* If you don&#39;t have data for a particular column, populate that field with a `NULL` object or `-1`.

* Files *must* end with a version number. La version actuelle est 1.1.
* Séparez les en-têtes et contenus du fichier par le caractère ASCII 001 non imprimable. Si vous ne pouvez pas utiliser ASCII 001, séparez les en-têtes et les données par un délimiteur de tabulation. As these are non-printing characters, the syntax example above shows a pipe `"|"` for display purposes only.

**Libellés des champs**

Le tableau ci-dessous répertorie et décrit les en-têtes de colonne de votre fichier de données. Les en-têtes sont sensibles à la casse et doivent apparaître comme indiqué dans le tableau. Tous les types de données sont des entiers (INT) sauf indication contraire.

<table id="table_D8C5068741C3460380505F95F3016757"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Étiquette </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Horodatage </p> </td> 
   <td colname="col2"> <p>Date et heure UTC pour l'impression, le clic ou l'événement de conversion. Use the <code> yyyy-dd-mm hh:mm:ss</code> format. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Utilisateur - ID </p> </td> 
   <td colname="col2"> <p>Your ID for a site visitor, also known as the <span class="term"> data provider unique user ID</span> or DPUUID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Advertiser-ID </p> </td> 
   <td colname="col2"> <p>Identifiant de source de données ou code d'intégration de votre annonceur. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>BU-ID </p> </td> 
   <td colname="col2"> <p>ID d'unité opérationnelle. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Campagne-ID </p> </td> 
   <td colname="col2"> <p>ID de campagne. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Creative-ID </p> </td> 
   <td colname="col2"> <p>ID d’élément créatif. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID du site </p> </td> 
   <td colname="col2"> <p>ID du site. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Placement-ID </p> </td> 
   <td colname="col2"> <p> Identifiant de placement numérique à partir du serveur d'annonces. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Insertion-Commande-ID </p> </td> 
   <td colname="col2"> <p>ID de l'ordre d'insertion. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tactique-ID </p> </td> 
   <td colname="col2"> <p>ID tactile. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Vertical-ID </p> </td> 
   <td colname="col2"> <p>Identifiant d'un secteur industriel vertical ou d'une catégorie. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Quantité </p> </td> 
   <td colname="col2"> <p> Nombre d'articles vendus dans un événement de conversion. </p> <p> <i>Pour les fichiers de données de conversion uniquement.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Recettes </p> </td> 
   <td colname="col2"> <p>Achat ou autre montant de conversion. Type de données : Flottant. </p> <p> <i>Pour les fichiers de données de conversion uniquement.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Autres données </p> </td> 
   <td colname="col2"> <p>URL de la page d'entrée de conversion. Type de données : chaîne. </p> <p> <i>Pour les fichiers de données de conversion uniquement.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Event-Type </p> </td> 
   <td colname="col2"> <p>Type de conversion. Indique si une conversion est correspondance ou non. Les options incluent : </p> 
    <ul id="ul_DA8230D167F241F2B53F29367874D4B1"> 
     <li id="li_2BC2EBCAE12541029A5F62AC0785E7FE"> <code> 0</code>: Impression </li> 
     <li id="li_2A4B1354891144D587624228D8FB5E77"> <code> 1</code>: Cliquez sur </li> 
     <li id="li_44E61419DB56471EB2091072595D3E5C"> <code> -1</code>: Non attribué ou inconnu </li> 
    </ul> <p> <i>Pour les fichiers de données de conversion uniquement.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Version </p> </td> 
   <td colname="col2"> <p>Numéro de version requis qui s'affiche à la fin de chaque ligne dans un fichier d'impression, de clic ou de conversion. La version actuelle est 1.1. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Delivery Methods for Data Files {#delivery-methods}

Upload your impression, click, or conversion data files to an Amazon S3 directory for your [!DNL Audience Manager] account. Pour plus d&#39;informations sur les chemins de distribution/répertoire, les temps de traitement des fichiers et les mises à jour, reportez-vous à cette section.

**Syntaxe des chemins de livraison et exemples**

Les données sont stockées dans un namespace de noms distinct pour chaque client dans un annuaire Amazon S 3. Le chemin d&#39;accès au fichier suit la syntaxe illustrée ci-dessous. Note, *italics* indicates a variable placeholder. Les autres éléments sont des constantes ou des clés et ne changent pas.

**Syntaxe :** <pre><code>…/log_ ingestion/pid = <i>AAM ID<i>/dpid = <i>d_ src</i>/logs/ <i>file type</i>_<i>yyyymmjj</i></code></pre>

Le tableau suivant définit chacun de ces éléments dans un chemin de remise de fichier.

<table id="table_E3DB873D4CB3479AA7173838EB9898CE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre de fichier </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> …/log_ ingestion/</code> </p> </td> 
   <td colname="col2"> <p>Il s'agit du début du chemin de stockage des répertoires. Vous recevrez le chemin d'accès complet lorsque tout est configuré. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>pid =<i>ID AAM</i></code> </p> </td> 
   <td colname="col2"> <p>This key-value pair that contains your <span class="keyword"> Audience Manager</span> customer ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>dpid =<i>d_ src</i></code> </p> </td> 
   <td colname="col2"> <p>Cette paire clé-valeur contient l'identifiant de source de données transmis lors d'un appel d'événement. Il identifie l'agence d'où proviennent les données et les relie à un fichier de métadonnées pris en charge. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> journaux</code> </p> </td> 
   <td colname="col2"> <p> Répertoire de niveau supérieur pour les fichiers de données. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>type de fichier</i>_<i>aaaammjj</i></code> </p> </td> 
   <td colname="col2"> <p>Nom de type de fichier qui indique le type de données qu'il contient et un horodatage de diffusion. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Exemple de chemin de téléchargement et fichier - nom**

Lorsque vous téléchargez un fichier, le chemin ressemble à celui-ci :

`.../log_ingestion/pid=1234/dpid=567/logs/impressions_20150902`

**Délais et mises à jour du traitement des fichiers**

Les fichiers de données sont traités quatre fois par jour, à intervalles réguliers.

Pour mettre à jour vos données, envoyez un fichier contenant toutes les impressions, clics ou conversions pour un jour donné. Dans ce cas, un jour est la période de 24 heures d&#39;une minuit à l&#39;autre. Il est recommandé d&#39;utiliser l&#39;heure UTC pour définir l&#39;intervalle de journée.

## Étapes suivantes {#next-steps}

Vérifiez les conditions requises pour nommer et créer des fichiers de métadonnées. To get started, see [Overview and Mappings for Metadata Files](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md).
