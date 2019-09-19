---
description: Envoyez ou mettez à jour des fichiers de métadonnées en les envoyant vers un répertoire Amazon S3 spécial pour votre compte Audience Manager. Reportez-vous à cette section pour plus d’informations sur les chemins de remise/répertoire, les délais de traitement des fichiers et les mises à jour.
seo-description: Envoyez ou mettez à jour des fichiers de métadonnées en les envoyant vers un répertoire Amazon S3 spécial pour votre compte Audience Manager. Reportez-vous à cette section pour plus d’informations sur les chemins de remise/répertoire, les délais de traitement des fichiers et les mises à jour.
seo-title: Méthodes de remise des fichiers de métadonnées
solution: Audience Manager
title: Méthodes de remise des fichiers de métadonnées
uuid: 5199ee9b-920d-423d-8070-05a017ecd562
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Méthodes de remise des fichiers de métadonnées{#delivery-methods-for-metadata-files}

Envoyez ou mettez à jour des fichiers de métadonnées en les envoyant vers un répertoire Amazon S3 spécial pour votre compte Audience Manager. Reportez-vous à cette section pour plus d’informations sur les chemins de remise/répertoire, les délais de traitement des fichiers et les mises à jour.

## Syntaxe du chemin de remise et exemples {#syntax}

Les données sont stockées dans un espace de noms distinct pour chaque client dans un répertoire Amazon S3. Le chemin d’accès au fichier suit la syntaxe illustrée ci-dessous. Note, *italics* indicates a variable placeholder. Les crochets `[ ]` indiquent des paramètres facultatifs. Les autres éléments sont des constantes et ne changent pas.

**Syntaxe :**
<pre><code>.../log_ingestion/pid=<i>AAM ID</i>/dpid= <i>d_src</i>/[meta|status]/ <i>yyyyyymmdd</i>_ ID <i>parent_ ID enfant</i><i></i></code></pre>

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
   <td colname="col1"> <p> <code> .../log_ingestion/</code> </p> </td> 
   <td colname="col2"> <p>Il s’agit du début du chemin de stockage du répertoire. Vous recevrez le chemin complet lorsque tout sera configuré. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>pid=ID<i>AAM</i></code> </p> </td> 
   <td colname="col2"> <p>Cette paire clé-valeur qui contient votre ID de client <span class="keyword"> Audience Manager</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>dpid=<i>d_src</i></code> </p> </td> 
   <td colname="col2"> <p>Cette paire clé-valeur contient l’ID de source de données transmis lors d’un appel d’événement. L’ID de source de données est la valeur qui lie tout le contenu de votre fichier aux données réelles auxquelles il appartient. </p> <p>Supposons, par exemple, que vous ayez un élément créatif avec l’ID 123 et le nom "Advertiser Creative A". Comme un appel d’événement ne transmet que l’identifiant dont vous avez besoin pour inclure "Advertiser Creative A" dans le fichier de métadonnées. La campagne et l’élément créatif appartiennent à une source de données. L’ID de source de données est ce qui relie ces éléments et nous permet d’associer précisément le contenu du fichier à un ID envoyé lors d’un appel d’événement. Voir <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md#how-ids-shape-file-names"> Comment les ID d’appel d’événement déterminent les noms de fichier, le contenu et les chemins</a>de remise. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <ul id="ul_8AFA4E7FCE984789AF05EA31718F39CD"> 
     <li id="li_A493880F6ECB467DBB590226CC7A5847"> <code> méta</code> </li> 
     <li id="li_2D6DAC956D084A1DB43C9C5B2C821F87"> <code> status</code> </li> 
    </ul> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_5907ADF5B20C4FEC94EF5A09BE02F2CD"> 
      <li id="li_AE70B44FEDCF4A05ADAFF4E49296F67D"> <code> meta</code> est un répertoire de téléchargement/stockage de fichiers. </li> 
      <li id="li_2ADEA90E01364E888CAAAB8A65A6383F"> <code> status</code> est un chemin d’accès à un répertoire contenant des informations de réussite ou d’échec sur vos fichiers traités. Une fois votre fichier traité, vous verrez un fichier .info <code> avec le titre de l’horodatage</code> aaaaaaa <code></code> . Les fichiers d’état contiennent des données dans un objet JSON. Voir Mises à jour <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-update-status.md"> d’état pour les fichiers</a>de métadonnées. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>yyyyymmdd</i>_<i>parent ID</i>_<i>enfant</i></code> </p> </td> 
   <td colname="col2"> <p>Il s’agit du nom de fichier. Voir Conventions <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md"> de dénomination des fichiers</a>de métadonnées. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Exemples de chemins de téléchargement et d’état**

Pour télécharger un fichier de métadonnées ou [vérifier son état](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-update-status.md), les chemins d’accès aux fichiers sont les suivants :

* Chemin de téléchargement : `/log_ingestion/pid=1234/dpid=567/meta/20150827_1_2`
* Chemin d’état de traitement : `/log_ingestion/pid=1234/dpid=567/status/20150827.info`.

## Heures et mises à jour de traitement des fichiers {#processing-times}

Les fichiers de métadonnées sont traités quatre fois par jour, à intervalles réguliers.

Pour mettre à jour vos enregistrements de métadonnées, envoyez simplement un fichier contenant de nouvelles informations. Vous n’avez pas besoin d’envoyer des mises à jour complètes à chaque fois.
