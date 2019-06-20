---
description: Envoyez ou mettez à jour les fichiers de métadonnées en les envoyant vers un répertoire Amazon S 3 spécial pour votre compte Audience Manager. Pour plus d'informations sur les chemins de distribution/répertoire, les temps de traitement des fichiers et les mises à jour, reportez-vous à cette section.
seo-description: Envoyez ou mettez à jour les fichiers de métadonnées en les envoyant vers un répertoire Amazon S 3 spécial pour votre compte Audience Manager. Pour plus d'informations sur les chemins de distribution/répertoire, les temps de traitement des fichiers et les mises à jour, reportez-vous à cette section.
seo-title: Méthodes de livraison des fichiers de métadonnées
solution: Audience Manager
title: Méthodes de livraison des fichiers de métadonnées
uuid: 5199 ee 9 b -920 d -423 d -8070-05 a 017 prêt 562
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Delivery Methods for Metadata Files{#delivery-methods-for-metadata-files}

Envoyez ou mettez à jour les fichiers de métadonnées en les envoyant vers un répertoire Amazon S 3 spécial pour votre compte Audience Manager. Pour plus d&#39;informations sur les chemins de distribution/répertoire, les temps de traitement des fichiers et les mises à jour, reportez-vous à cette section.

## Delivery Path Syntax and Examples {#syntax}

Les données sont stockées dans un namespace de noms distinct pour chaque client dans un annuaire Amazon S 3. Le chemin d&#39;accès au fichier suit la syntaxe illustrée ci-dessous. Note, *italics* indicates a variable placeholder. Brackets `[ ]` indicate optional parameters. Les autres éléments sont des constantes et ne changent pas.

**Syntaxe :**
<pre><code>…/log_ ingestion/pid =<i>AAM ID</i>/dpid = <i>d_ src</i>/[meta | status]/ <i></i>yyyymmjj <i>ID</i>_ parent <i>ID</i></code></pre>

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
   <td colname="col2"> <p>Cette paire clé-valeur contient l'identifiant de source de données transmis lors d'un appel d'événement. L'ID de source de données est la valeur qui lie tout le contenu de votre fichier aux données réelles auxquelles il appartient. </p> <p>Supposons, par exemple, que vous ayez un élément créatif avec l'ID 123 et le nom « Advertiser Creative A. » comme un appel d'événement ne transmet que l'identifiant que vous devez inclure « Advertiser Creative A » dans le fichier de métadonnées. La campagne et le créatif appartiennent à une source de données. L'ID de source de données est ce qui lie ces éléments et nous permet d'associer précisément le contenu du fichier à un ID envoyé lors d'un appel d'événement. See <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md#how-ids-shape-file-names"> How Event Call IDs Determine File Names, Contents, and Delivery Paths</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <ul id="ul_8AFA4E7FCE984789AF05EA31718F39CD"> 
     <li id="li_A493880F6ECB467DBB590226CC7A5847"> <code> méta</code> </li> 
     <li id="li_2D6DAC956D084A1DB43C9C5B2C821F87"> <code> status</code> </li> 
    </ul> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_5907ADF5B20C4FEC94EF5A09BE02F2CD"> 
      <li id="li_AE70B44FEDCF4A05ADAFF4E49296F67D"> <code> meta</code> est un répertoire de téléchargement/stockage de fichier. </li> 
      <li id="li_2ADEA90E01364E888CAAAB8A65A6383F"> <code> status</code> est un chemin vers un répertoire qui contient des informations de succès ou d'échec sur vos fichiers traités. After your file is processed, you'll see a <code> .info</code> file with <code> yyyymmdd</code> timestamp title. Les fichiers de statut contiennent des données dans un objet JSON. See <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-update-status.md"> Status Updates for Metadata Files</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>aaaammjj</i>_<i>parent ID</i>_<i>child</i></code> </p> </td> 
   <td colname="col2"> <p>Il s'agit du fichier - name. See <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md"> Naming Conventions for Metadata Files</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Exemple de transfert et de chemin d&#39;accès**

To upload a metadata file or to [check its status](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-update-status.md), the file paths will look similar to these:

* Upload path: `/log_ingestion/pid=1234/dpid=567/meta/20150827_1_2`
* Processing status path: `/log_ingestion/pid=1234/dpid=567/status/20150827.info`.

## File Processing Times and Updates {#processing-times}

Les fichiers de métadonnées sont traités quatre fois par jour, à intervalles réguliers.

Pour mettre à jour vos enregistrements de métadonnées, il vous suffit d&#39;envoyer un fichier contenant de nouvelles informations. Vous n&#39;avez pas besoin d&#39;envoyer toutes les mises à jour à chaque fois.
