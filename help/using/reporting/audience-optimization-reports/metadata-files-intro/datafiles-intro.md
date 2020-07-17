---
description: Un fichier de données contient des données d’impression, de clic ou de conversion. Lorsque le format est correct, vous pouvez importer ces données dans l’Audience Manager et les utiliser dans les rapports Optimisation des Audiences et dans les fichiers journaux utilisables. Mettez en forme vos fichiers de données selon les spécifications de cette section.
seo-description: Un fichier de données contient des données d’impression, de clic ou de conversion. Lorsque le format est correct, vous pouvez importer ces données dans l’Audience Manager et les utiliser dans les rapports Optimisation des Audiences et dans les fichiers journaux utilisables. Mettez en forme vos fichiers de données selon les spécifications de cette section.
seo-title: Fichiers de données pour les rapports Audience Optimization et fichiers journaux pratiques
solution: Audience Manager
title: Fichiers de données pour les rapports Audience Optimization et fichiers journaux pratiques
uuid: c19eb0c7-47c1-4cdf-8a6c-cd15fe04c379
feature: log files
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '1042'
ht-degree: 5%

---


# Fichiers de données pour les rapports Audience Optimization et fichiers journaux pratiques {#data-files-for-audience-optimization-reports}

Un fichier de données contient des données d’impression, de clic ou de conversion. Une fois formatées correctement, vous pouvez importer ces données dans l&#39;Audience Manager pour les vue dans les rapports [d&#39;optimisation des](../../../reporting/audience-optimization-reports/audience-optimization-reports.md) Audiences et créer des caractéristiques à l&#39;aide des données par le biais de fichiers [journaux](/help/using/integration/media-data-integration/actionable-log-files.md)utilisables. Mettez en forme vos fichiers de données selon ces spécifications dans cette section.

## Présentation {#overview}

Un fichier de données correctement nommé et formaté vous permet d’importer des données d’impression, de clic ou de conversion dans les rapports [Optimisation des](../../../reporting/audience-optimization-reports/audience-optimization-reports.md)Audiences. Cela s’avère utile lorsque vous travaillez avec un partenaire qui n’est pas intégré [!DNL Audience Manager] et que vous souhaitez utiliser les données qu’il contient dans cette suite de rapports. Ce processus nécessite des fichiers distincts pour les données d’impression, de clic et de conversion. Ne mélangez pas ces événements dans un seul fichier.

Un fichier de données doit être accompagné d’un fichier de métadonnées. Le contenu du fichier de métadonnées correspond aux informations relatives au fichier de données et aux étiquettes lisibles dans les menus du rapport. Pour plus d’informations, voir [Aperçu et mappages pour les fichiers](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md)de métadonnées.

## Naming Conventions for Data Files {#naming-conventions}

La syntaxe suivante définit la structure d’un nom de fichier de données bien formé. Remarque : *l’italique* indique un espace réservé de variable qui change en fonction du contenu du fichier.

**Syntaxe :** <pre><i>type d&#39;événement</i>_<i>yyyyymmdd</i></code></pre>

Dans un nom de fichier :

* Le type d&#39;événement indique que le fichier contient des impressions, des clics ou des conversions. Créez un fichier distinct pour chaque type d&#39;événement.
* Un trait de soulignement sépare le type d&#39;événement et l’horodatage de l’année du mois.
* Avant de télécharger, compressez vos fichiers à l’aide de gzip et enregistrez-les avec l’extension de `.gz` fichier.

Pour ces raisons, nommez vos fichiers de données en fonction de leur contenu comme suit :

* Données d’impression : <pre>impressions_<i>yyyymmdd</i>.gz</code></pre>
* Données du clic : <pre>clicks_<i>yyyyymmdd</i>.gz</code></pre>
* Données de conversion : <pre>conversions_<i>yyyymmdd</i>.gz</code></pre>

## Content Format for Data Files {#content-format}

La syntaxe suivante définit la structure de contenu dans un fichier de données bien formé. Remarque : *l’italique* indique un espace réservé de variable et est remplacé par un libellé dans un fichier de données réel.

**Syntaxe :** <pre><i>libellé d’en-tête 1</i> | <i>étiquette d&#39;en-tête 2</i> ... étiquette d&#39; <i>en-tête n</i> | <i>version</i></code></pre>

Dans le contenu du fichier :

* Les libellés d’en-tête doivent s’afficher dans l’ordre indiqué dans le tableau ci-dessous. Les impressions et les clics utilisent les mêmes libellés. Les fichiers de conversion contiennent des en-têtes supplémentaires.
* Si vous n’avez pas de données pour une colonne particulière, renseignez ce champ avec un `-1`.

* Les fichiers *doivent* se terminer par un numéro de version. La version actuelle est 1.1.
* Séparez les en-têtes de fichier et le contenu avec le caractère ASCII 001 non imprimé. Si vous ne pouvez pas utiliser ASCII 001, séparez les en-têtes et les données par un délimiteur de tabulation. Comme il s’agit de caractères non imprimables, l’exemple de syntaxe ci-dessus montre une barre verticale `"|"` à des fins d’affichage uniquement.

**Libellés des champs**

Le tableau ci-dessous liste et décrit les en-têtes de colonne de votre fichier de données. Les en-têtes sont sensibles à la casse et doivent apparaître selon l’ordre indiqué dans le tableau. Tous les types de données sont des entiers (INT), sauf indication contraire.

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
   <td colname="col2"> <p>Date et heure UTC pour le événement d’impression, de clic ou de conversion. Utilisez le <code> yyyy-MM-dd HH:mm:ss</code> format. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>User-ID </p> </td> 
   <td colname="col2"> <p>Votre identifiant pour un visiteur de site, également appelé ID <span class="term"></span> utilisateur unique du fournisseur de données ou DPUUID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Advertiser-ID </p> </td> 
   <td colname="col2"> <p>ID de source de données ou code d’intégration pour votre annonceur. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>BU-ID </p> </td> 
   <td colname="col2"> <p>ID de l'unité opérationnelle. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Campaign-ID </p> </td> 
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
   <td colname="col1"> <p>Emplacement-ID </p> </td> 
   <td colname="col2"> <p> Identifiant de placement numérique du serveur d’annonces. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Insertion-Ordre-ID </p> </td> 
   <td colname="col2"> <p>ID d’ordre d’insertion. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID tactique </p> </td> 
   <td colname="col2"> <p>ID tactique. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID vertical </p> </td> 
   <td colname="col2"> <p>ID d’une catégorie ou d’un secteur industriel vertical. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Quantité </p> </td> 
   <td colname="col2"> <p> Nombre d’éléments vendus dans un événement de conversion. </p> <p> <i>Pour les fichiers de données de conversion uniquement.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Recettes </p> </td> 
   <td colname="col2"> <p>Achat ou autre montant de conversion. Type de données : Flottant. </p> <p> <i>Pour les fichiers de données de conversion uniquement.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Autres données </p> </td> 
   <td colname="col2"> <p>URL du landing page de conversion. Type de données : chaîne. </p> <p> <i>Pour les fichiers de données de conversion uniquement.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Événement-Type </p> </td> 
   <td colname="col2"> <p>Type de conversion. Indique si une conversion correspond ou non. Les options incluent : </p> 
    <ul id="ul_DA8230D167F241F2B53F29367874D4B1"> 
     <li id="li_2BC2EBCAE12541029A5F62AC0785E7FE"> <code> 0</code>: Impression </li> 
     <li id="li_2A4B1354891144D587624228D8FB5E77"> <code> 1</code>: Cliquez sur </li> 
     <li id="li_44E61419DB56471EB2091072595D3E5C"> <code> -1</code>: Non attribué ou inconnu </li> 
    </ul> <p> <i>Pour les fichiers de données de conversion uniquement.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Version </p> </td> 
   <td colname="col2"> <p>Numéro de version requis qui apparaît à la fin de chaque ligne dans un fichier de données d’impression, de clic ou de conversion. La version actuelle est 1.1. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Delivery Methods for Data Files {#delivery-methods}

Téléchargez vos fichiers de données d’impression, de clic ou de conversion vers un répertoire Amazon S3 pour votre [!DNL Audience Manager] compte. Reportez-vous à cette section pour obtenir des informations sur les chemins d’accès aux diffusions/répertoires, les délais de traitement des fichiers et les mises à jour.

>[!IMPORTANT]
>
> Contactez votre conseiller en Audience Manager ou le service d’assistance clientèle pour commencer et configurer un [!DNL Amazon S3] répertoire pour vos fichiers de données.

**Syntaxe du chemin de Diffusion et exemples**

Les données sont stockées dans un espace de nommage distinct pour chaque client dans un [!DNL Amazon S3] annuaire. Le chemin d’accès au fichier suit la syntaxe illustrée ci-dessous. Note, *italics* indicates a variable placeholder. Les autres éléments sont des constantes ou des clés et ne changent pas.

**Syntaxe :** <pre>.../log_assimilation/pid= <i>AAM ID<i>/dpid= <i>d_src</i>/logs/ type <i>de</i>fichier_<i>yyyyymdd</i></code></pre>

Le tableau suivant définit chacun de ces éléments dans un chemin de diffusion de fichiers.

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
   <td colname="col2"> <p>début du chemin d'enregistrement de l'annuaire. Vous recevrez le chemin complet lorsque tout sera configuré. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>pid=<i>AAM ID</i></code> </p> </td> 
   <td colname="col2"> <p>Cette paire clé-valeur contient votre ID de client <span class="keyword"> Audience Manager</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>dpid=<i>d_src</i></code> </p> </td> 
   <td colname="col2"> <p>Cette paire clé-valeur contient l’identifiant de source de données transmis lors d’un appel de événement. Il identifie l'organisme d'où proviennent les données et les lie à un fichier de métadonnées. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> logs</code> </p> </td> 
   <td colname="col2"> <p> Répertoire de niveau supérieur pour les fichiers de données. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>file type</i>_<i>yyyymmdd</i></code> </p> </td> 
   <td colname="col2"> <p>Nom de type de fichier qui indique le type de données qu’il contient et un horodatage de diffusion. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Exemple de chemin de téléchargement et de nom de fichier**

Lorsque vous téléchargez un fichier, le chemin d’accès se présente comme suit :

`.../log_ingestion/pid=1234/dpid=567/logs/impressions_20150902`

**Heures de traitement des fichiers et mises à jour**

Les fichiers de données sont traités quatre fois par jour, à intervalles réguliers.

Pour mettre à jour vos données, envoyez un fichier qui contient toutes les impressions, les clics ou les conversions pour un jour donné. Dans ce cas, un jour correspond à la période de 24 heures allant d’un minuit à l’autre. Il est recommandé d’utiliser l’heure UTC pour définir l’intervalle de jour.

## Étapes suivantes {#next-steps}

Examinez les exigences relatives au nommage et à la création de fichiers de métadonnées. Pour commencer, voir [Aperçu et mappages pour les fichiers](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md)de métadonnées.
