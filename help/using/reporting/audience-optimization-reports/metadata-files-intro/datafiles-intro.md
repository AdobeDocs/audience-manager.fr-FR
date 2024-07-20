---
description: Un fichier de données contient des données d’impression, de clic ou de conversion. Lorsque le format est correct, vous pouvez importer ces données dans Audience Manager et les utiliser dans les rapports d’Audience Optimization et pour les fichiers journaux pratiques. Mettez en forme vos fichiers de données conformément aux spécifications de cette section.
seo-description: A data file contains impression, click, or conversion data. When formatted properly, you can import this data into Audience Manager and use it in the Audience Optimization reports and for Actionable Log Files. Format your data files according to the specifications in this section.
seo-title: Data Files for Audience Optimization Reports and Actionable Log Files
solution: Audience Manager
title: Fichiers de données pour les rapports d’Audience Optimization et les fichiers journaux pratiques
uuid: c19eb0c7-47c1-4cdf-8a6c-cd15fe04c379
feature: Log Files
exl-id: 0da2c1d3-5ff8-40dd-b831-21d8941688ce
source-git-commit: db90a6f1aaf85b10e31e93e316c257b7c3a904aa
workflow-type: tm+mt
source-wordcount: '994'
ht-degree: 1%

---

# Fichiers de données pour les rapports d’Audience Optimization et les fichiers journaux pratiques {#data-files-for-audience-optimization-reports}

Un fichier de données contient des données d’impression, de clic ou de conversion. Lorsque le format est correct, vous pouvez importer ces données dans Audience Manager pour les afficher dans les [rapports d’Audience Optimization](../../../reporting/audience-optimization-reports/audience-optimization-reports.md) et créer des caractéristiques à l’aide des données via les [fichiers journaux pratiques](/help/using/integration/media-data-integration/actionable-log-files.md). Mettez en forme vos fichiers de données conformément à ces spécifications dans cette section.

## Présentation {#overview}

Un fichier de données correctement nommé et formaté vous permet d’importer des données d’impression, de clic ou de conversion dans les [ rapports d’Audience Optimization](../../../reporting/audience-optimization-reports/audience-optimization-reports.md). Cela s’avère utile lorsque vous travaillez avec un partenaire qui n’est pas intégré à [!DNL Audience Manager] et que vous souhaitez utiliser ses données dans cette suite de rapports. Ce processus nécessite des fichiers distincts pour les données d’impression, de clic et de conversion. Ne mélangez pas ces événements dans un seul fichier.

Un fichier de données doit être accompagné d’un fichier de métadonnées. Le contenu du fichier de métadonnées correspond aux informations du fichier de données aux libellés associés, lisibles par l’utilisateur, dans les menus du rapport. Pour plus d’informations, voir [Présentation et mappages des fichiers de métadonnées](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md).

## Conventions de dénomination des fichiers de données {#naming-conventions}

La syntaxe suivante définit la structure d’un nom de fichier de données correctement formé. Remarque : *italics* indique un espace réservé de variable qui change en fonction du contenu du fichier.

**Syntaxe :** <pre><code><i> {type d’événement</i>_<i>yyymmdd</i></code></pre>

Dans un nom de fichier :

* Le type d’événement indique que le fichier contient des impressions, des clics ou des conversions. Créez un fichier distinct pour chaque type d’événement.
* Un trait de soulignement sépare le type d’événement d’un horodatage d’un mois d’année.
* Avant de charger, compressez vos fichiers à l’aide de gzip et enregistrez-les avec l’extension de fichier `.gz`.

Compte tenu de ces exigences, nommez vos fichiers de données en fonction de leur contenu comme suit :

* Données d’impression : <pre><code>impressions_<i>yyymmdd</i>.gz</code></pre>
* Données du clic : <pre><code>clicks_<i>yyymmdd</i>.gz</code></pre>
* Données de conversion : <pre><code>conversions_<i>yyymmdd</i>.gz</code></pre>

## Format de contenu des fichiers de données {#content-format}

La syntaxe suivante définit la structure de contenu dans un fichier de données correctement formé. Remarque : *italics* indique un espace réservé de variable et est remplacé par un libellé dans un fichier de données réel.

**Syntaxe :** <pre><code><i>libellé d’en-tête 1</i> | <i>libellé d’en-tête 2</i> ... <i>libellé d’en-tête n</i> | <i>version</i></code></pre>

Dans le contenu du fichier :

* Les libellés d’en-tête doivent s’afficher dans l’ordre indiqué dans le tableau ci-dessous. Les impressions et les clics utilisent les mêmes libellés. Les fichiers de conversion contiennent des en-têtes supplémentaires.
* Si vous ne disposez pas de données pour une colonne particulière, renseignez ce champ avec un `-1`.

* Les fichiers *must* se terminent par un numéro de version. La version actuelle est 1.1.
* Séparez les en-têtes de fichier et le contenu par le caractère non imprimable ASCII 001 . Si vous ne pouvez pas utiliser ASCII 001, séparez les en-têtes et les données par un délimiteur de tabulation. Comme il s’agit de caractères non imprimables, l’exemple de syntaxe ci-dessus montre une barre verticale `"|"` à des fins d’affichage uniquement.

**Étiquettes de champ**

Le tableau ci-dessous répertorie et décrit les en-têtes de colonne de votre fichier de données. Les en-têtes sont sensibles à la casse et doivent apparaître dans l’ordre du tableau. Tous les types de données sont des entiers (INT), sauf indication contraire.

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
   <td colname="col2"> <p>Date et heure UTC de l’événement d’impression, de clic ou de conversion. Utilisez le format <code> yyyy-MM-dd HH:mm:ss</code> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>User-ID </p> </td> 
   <td colname="col2"> <p>Votre identifiant pour un visiteur du site, également appelé l’ <span class="term"> identifiant utilisateur unique du fournisseur de données </span> ou DPUUID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Advertiser-ID </p> </td> 
   <td colname="col2"> <p>Identifiant de source de données ou code d’intégration de votre annonceur. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>BU-ID </p> </td> 
   <td colname="col2"> <p>Identifiant de l’unité opérationnelle. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Campaign-ID </p> </td> 
   <td colname="col2"> <p>ID de campagne. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Creative ID </p> </td> 
   <td colname="col2"> <p>ID de création. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID du site </p> </td> 
   <td colname="col2"> <p>Identifiant du site. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Placement-ID </p> </td> 
   <td colname="col2"> <p> Identifiant d’emplacement numérique du serveur de publicités. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Insertion-Order-ID </p> </td> 
   <td colname="col2"> <p>Identifiant de commande d’insertion. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID tactique </p> </td> 
   <td colname="col2"> <p>ID tactique. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Identifiant vertical </p> </td> 
   <td colname="col2"> <p>Identifiant pour un secteur industriel vertical ou une catégorie. </p> </td> 
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
   <td colname="col2"> <p>URL de la landing page de conversion. Type de données : chaîne. </p> <p> <i>Pour les fichiers de données de conversion uniquement.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Event-Type </p> </td> 
   <td colname="col2"> <p>Type de conversion. Indique si une conversion correspond ou non. Les options incluent : </p> 
    <ul id="ul_DA8230D167F241F2B53F29367874D4B1"> 
     <li id="li_2BC2EBCAE12541029A5F62AC0785E7FE"> <code> 0</code> : Impression </li> 
     <li id="li_2A4B1354891144D587624228D8FB5E77"> <code> 1</code> : cliquez sur </li> 
     <li id="li_44E61419DB56471EB2091072595D3E5C"> <code> -1</code> : Non attribué ou inconnu </li> 
    </ul> <p> <i>Pour les fichiers de données de conversion uniquement.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Version </p> </td> 
   <td colname="col2"> <p>Numéro de version requis qui apparaît à la fin de chaque ligne dans un fichier de données d’impression, de clic ou de conversion. La version actuelle est 1.1. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Méthodes de distribution des fichiers de données {#delivery-methods}

Chargez vos fichiers de données d’impression, de clic ou de conversion dans un répertoire Amazon S3 pour votre compte [!DNL Audience Manager]. Reportez-vous à cette section pour plus d’informations sur les chemins de diffusion/répertoire, les temps de traitement des fichiers et les mises à jour.

>[!IMPORTANT]
>
> Contactez votre conseiller en Audience Manager ou l’assistance clientèle pour commencer à configurer un répertoire [!DNL Amazon S3] pour vos fichiers de données.

**Syntaxe du chemin de diffusion et exemples**

Les données sont stockées dans un espace de noms distinct pour chaque client dans un répertoire [!DNL Amazon S3]. Le chemin d’accès au fichier suit la syntaxe illustrée ci-dessous. Remarque : *italics* indique un espace réservé de variable. Les autres éléments sont des constantes ou des clés et ne changent pas.

**Syntaxe :** <pre><code>.../log_ingestion/pid= <i>AAM ID</i>/dpid= <i>d_src</i>/logs/ <i>type de fichier</i>_<i>yyymmdd</i></code></pre>

Le tableau suivant définit chacun de ces éléments dans un chemin de diffusion de fichier.

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
   <td colname="col1"> <p> <code>pid=<i>AAM ID</i></code> </p> </td> 
   <td colname="col2"> <p>Cette paire clé-valeur contient votre ID de client <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>dpid=<i>d_src</i></code> </p> </td> 
   <td colname="col2"> <p>Cette paire clé-valeur contient l’identifiant de source de données transmis lors d’un appel d’événement. Il identifie l’agence d’où proviennent les données et les associe à un fichier de métadonnées pris en charge. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> logs</code> </p> </td> 
   <td colname="col2"> <p> Répertoire de niveau supérieur pour les fichiers de données. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>file type</i>_<i>yyyymmdd</i></code> </p> </td> 
   <td colname="col2"> <p>Un nom de type de fichier qui indique le type de données qu’il contient et un horodatage de diffusion. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Exemple de chemin de téléchargement et nom de fichier**

Lorsque vous chargez un fichier, le chemin d’accès se présente comme suit :

`.../log_ingestion/pid=1234/dpid=567/logs/impressions_20150902`

**Temps et mises à jour de traitement de fichier**

Les fichiers de données sont traités quatre fois par jour, à intervalles réguliers.

Pour mettre à jour vos données, envoyez un fichier contenant toutes les impressions, clics ou conversions pour un jour spécifique. Dans ce cas, un jour correspond à la période de 24 heures allant d’une minuit à l’autre. Il est recommandé d’utiliser l’heure UTC pour définir l’intervalle de jours.

## Étapes suivantes {#next-steps}

Examinez les exigences en matière de dénomination et de création de fichiers de métadonnées. Pour commencer, reportez-vous à la section [Présentation et mappages des fichiers de métadonnées](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md).
