---
description: Un fichier de données contient des données d’impression, de clic ou de conversion. Une fois formatées correctement, vous pouvez importer ces données dans Audience Manager et les afficher dans les rapports Optimisation de l’audience. Formatez vos fichiers de données en fonction de ces spécifications dans cette section.
seo-description: Un fichier de données contient des données d’impression, de clic ou de conversion. Une fois formatées correctement, vous pouvez importer ces données dans Audience Manager et les afficher dans les rapports Optimisation de l’audience. Formatez vos fichiers de données en fonction de ces spécifications dans cette section.
seo-title: Fichiers de données pour les rapports Optimisation de l’audience
solution: Audience Manager
title: Fichiers de données pour les rapports Optimisation de l’audience
uuid: c19eb0c7-47c1-4cdf-8a6c-cd15fe04c379
translation-type: tm+mt
source-git-commit: 6e504dabacff9be40633d6c91856b57c6e653f71

---


# Fichiers de données pour les rapports Optimisation de l’audience{#data-files-for-audience-optimization-reports}

Un fichier de données contient des données d’impression, de clic ou de conversion. Une fois formatées correctement, vous pouvez importer ces données dans Audience Manager et les afficher dans les rapports Optimisation de l’audience. Formatez vos fichiers de données en fonction de ces spécifications dans cette section.

## Aperçu {#overview}

Un fichier de données correctement nommé et formaté vous permet d’importer des données d’impression, de clic ou de conversion dans les rapports [Optimisation de l’](../../../reporting/audience-optimization-reports/audience-optimization-reports.md)audience. Cela s’avère utile lorsque vous travaillez avec un partenaire qui n’est pas intégré [!DNL Audience Manager] et que vous souhaitez utiliser les données qu’il contient dans cette suite de rapports. Ce processus nécessite des fichiers distincts pour les données d’impression, de clic et de conversion. Ne mélangez pas ces événements dans un seul fichier.

Un fichier de données doit être accompagné d’un fichier de métadonnées. Le contenu du fichier de métadonnées correspond aux informations du fichier de données et aux libellés connexes, lisibles par des personnes, des menus de rapport. Pour plus d’informations, voir [Aperçu et mappages pour les fichiers](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md)de métadonnées.

## Conventions de dénomination des fichiers de données {#naming-conventions}

La syntaxe suivante définit la structure d’un nom de fichier de données bien formé. Remarque : *l’italique* indique un espace réservé de variable qui change en fonction du contenu du fichier.

**Syntaxe :** <pre><code><i>type</i>d’événement_<i>yyyymmdd</i></code></pre>

Dans un nom de fichier :

* Le type d’événement indique que le fichier contient des impressions, des clics ou des conversions. Créez un fichier distinct pour chaque type d’événement.
* Un trait de soulignement sépare le type d’événement d’un horodatage annuel.
* Avant de télécharger, compressez vos fichiers à l’aide de gzip et enregistrez-les avec l’extension de `.gz` fichier.

Compte tenu de ces exigences, nommez vos fichiers de données en fonction de leur contenu comme suit :

* Données d’impression : <pre><code>impressions_<i>yyyyymmd<i>.gz</code></pre>
* Données de clic : <pre><code>clicks_<i>yyyyyymmd</i>.gz</code></pre>
* Données de conversion : <pre><code>conversions_<i>yyyyymmd</i>.gz</code></pre>

## Format de contenu pour les fichiers de données {#content-format}

La syntaxe suivante définit la structure du contenu dans un fichier de données bien formé. Remarque : *l’italique* indique un espace réservé de variable et est remplacé par un libellé dans un fichier de données réel.

**Syntaxe :** <pre><code><i>libellé d’en-tête 1</i> | <i>étiquette d'en-tête 2</i> ... Libellé d’ <i>en-tête n</i> | <i>version</i></code></pre>

Dans le contenu du fichier :

* Les libellés d’en-tête doivent apparaître dans l’ordre indiqué dans le tableau ci-dessous. Les impressions et les clics utilisent les mêmes libellés. Les fichiers de conversion contiennent des en-têtes supplémentaires.
* Si vous n’avez pas de données pour une colonne particulière, renseignez ce champ avec une `-1`.

* Les fichiers *doivent* se terminer par un numéro de version. La version actuelle est 1.1.
* Séparez les en-têtes de fichier et le contenu avec le caractère ASCII 001 non imprimable. Si vous ne pouvez pas utiliser ASCII 001, séparez les en-têtes et les données par un délimiteur de tabulation. Comme il s’agit de caractères non imprimables, l’exemple de syntaxe ci-dessus montre une barre verticale `"|"` à des fins d’affichage uniquement.

**Libellés de champ**

Le tableau ci-dessous répertorie et décrit les en-têtes de colonne de votre fichier de données. Les en-têtes sont sensibles à la casse et doivent s’afficher comme indiqué dans le tableau. Tous les types de données sont des entiers (INT), sauf indication contraire.

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
   <td colname="col2"> <p>Date et heure UTC pour l’événement d’impression, de clic ou de conversion. Utilisez le format <code> aaaa-jj-mm hh:mm:ss</code> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>User-ID </p> </td> 
   <td colname="col2"> <p>Votre identifiant pour un visiteur du site, également appelé ID <span class="term"> utilisateur unique du fournisseur de</span> données ou DPUUID. </p> </td> 
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
   <td colname="col1"> <p>Site-ID </p> </td> 
   <td colname="col2"> <p>ID du site. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Placement-ID </p> </td> 
   <td colname="col2"> <p> Identifiant de placement numérique du serveur d’annonces. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Insertion-Ordre-ID </p> </td> 
   <td colname="col2"> <p>ID de l’ordre d’insertion. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tactique-ID </p> </td> 
   <td colname="col2"> <p>ID tactique. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Vertical-ID </p> </td> 
   <td colname="col2"> <p>ID d’un secteur industriel vertical ou d’une catégorie. </p> </td> 
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
   <td colname="col2"> <p>URL de la page d’entrée de conversion. Type de données : chaîne. </p> <p> <i>Pour les fichiers de données de conversion uniquement.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Event-Type </p> </td> 
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

## Méthodes de remise des fichiers de données {#delivery-methods}

Téléchargez vos fichiers de données d’impression, de clic ou de conversion vers un répertoire Amazon S3 pour votre [!DNL Audience Manager] compte. Reportez-vous à cette section pour plus d’informations sur les chemins de remise/répertoire, les délais de traitement des fichiers et les mises à jour.

**Syntaxe du chemin de remise et exemples**

Les données sont stockées dans un espace de noms distinct pour chaque client dans un répertoire Amazon S3. Le chemin d’accès au fichier suit la syntaxe illustrée ci-dessous. Note, *italics* indicates a variable placeholder. Les autres éléments sont des constantes ou des clés et ne changent pas.

**Syntaxe :** <pre><code>.../log_ingestion/pid= ID <i><i>AAM/dpid= <i>d_src</i>/logs/ type <i>de</i>fichier_<i>yyyymmdd</i></code></pre>

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
   <td colname="col2"> <p>Cette paire clé-valeur contient l’ID de source de données transmis lors d’un appel d’événement. Il identifie l’agence dont proviennent les données et les associe à un fichier de métadonnées. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> journaux</code> </p> </td> 
   <td colname="col2"> <p> Répertoire de niveau supérieur pour les fichiers de données. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> type <i>de</i>fichier<i>_yyyymmdd</i></code> </p> </td> 
   <td colname="col2"> <p>Nom de type de fichier qui indique le type de données qu’il contient et un horodatage de remise. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Exemple de chemin de téléchargement et nom de fichier**

Lorsque vous téléchargez un fichier, le chemin d’accès se présente comme suit :

`.../log_ingestion/pid=1234/dpid=567/logs/impressions_20150902`

**Heures et mises à jour de traitement des fichiers**

Les fichiers de données sont traités quatre fois par jour, à intervalles réguliers.

Pour mettre à jour vos données, envoyez un fichier contenant toutes les impressions, les clics ou les conversions pour un jour donné. Dans ce cas, un jour correspond à la période de 24 heures qui s’étend d’un minuit à l’autre. En règle générale, vous pouvez utiliser l’heure UTC pour définir l’intervalle de jour.

## Étapes suivantes {#next-steps}

Vérifiez les conditions requises pour nommer et créer des fichiers de métadonnées. Pour commencer, voir [Aperçu et mappages pour les fichiers](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md)de métadonnées.
