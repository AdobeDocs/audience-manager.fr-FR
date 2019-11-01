---
description: Informations de base sur les fichiers de flux de données client (CDF) et instructions de démarrage. Commencez ici si vous souhaitez recevoir des fichiers CDF ou simplement plus d'informations.
keywords: données propriétaires;2e partie;données propriétaires;2e partie;données propriétaires;deuxième partie
seo-description: Informations de base sur les fichiers de flux de données client (CDF) et instructions de démarrage. Commencez ici si vous souhaitez recevoir des fichiers CDF ou simplement plus d'informations.
seo-title: Flux de données client
solution: Audience Manager
title: Flux de données client
uuid: a5de1630-2c7a-4862-9ba0-f8343cdd2782
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Flux de données client {#customer-data-feeds}

Informations de base sur [!UICONTROL Customer Data Feed] ([!UICONTROL CDF]) fichiers et instructions sur la façon de commencer. Commencez ici si vous souhaitez recevoir [!UICONTROL CDF] des fichiers ou simplement obtenir plus d'informations.

## Contenu et objet du fichier {#file-contents-purpose}

<!-- cdf-intro.xml -->

Un [!UICONTROL CDF] fichier contient les mêmes données qu’un appel [!DNL Audience Manager] d’événement ( `/event`) envoie à nos serveurs. Cela inclut des données telles que les ID utilisateur, les ID de caractéristiques, les ID de segment et tous les autres paramètres capturés par un appel d’événement. Les [!DNL Audience Manager] systèmes internes traitent les données d’événement dans un [!UICONTROL CDF] fichier dont le contenu est organisé en champs qui apparaissent dans un ordre défini. [!DNL Audience Manager] essaie de générer [!UICONTROL CDF] des fichiers toutes les heures et de les stocker dans un compartiment sécurisé spécifique au client sur un [!DNL Amazon S3] serveur. Nous fournissons ces fichiers afin que vous puissiez travailler avec [!DNL Audience Manager] des données en dehors des limites imposées par notre interface utilisateur.

>[!NOTE]
>
>Vous ne devez pas utiliser [!UICONTROL CDF] les fichiers comme proxy pour surveiller le trafic des pages, rapprocher les écarts de rapport ou pour la facturation, etc.

## Prise en main {#getting-started}

Il n’existe aucun processus en libre-service pour démarrer la remise des [!UICONTROL CDF] fichiers. Contact your [!DNL Audience Manager] consultant or Customer Care to get started. Lors de l’implémentation, votre [!DNL Audience Manager] représentant :

* Configurez votre [!DNL Amazon S3] compartiment de stockage.
* Fournissez des informations d’identification d’authentification en lecture seule [!DNL S3] à votre compartiment de stockage de fichiers. Vous ne pourrez ni afficher ni accéder aux répertoires et aux fichiers appartenant à d’autres clients.

Les notifications et [!UICONTROL CDF] les fichiers s’affichent dans votre [!DNL S3] compartiment lorsqu’ils sont prêts pour le téléchargement. Vous êtes responsable de la surveillance et du téléchargement des fichiers à partir du [!DNL S3] répertoire qui vous est affecté. Voir Notifications [de traitement des fichiers de flux de données](#cdf-file-processing-notifications)client.

## Étapes suivantes {#next-steps}

Les sections ci-dessous et la FAQ [sur le flux de données](../faq/faq-cdf.md) client peuvent vous aider à mieux vous familiariser avec ce service.

## Contenu du flux de données client défini {#cdf-defined}

Répertorie et définit les éléments de données et les tableaux dans un [!UICONTROL CDF] fichier, par ordre d’apparition. Les définitions comprennent les types de données, mais ces informations ne font pas partie d’un [!UICONTROL CDF] fichier.

## Définitions {#definitions}

<!-- cdf-contents-defined.xml -->

Un [!UICONTROL CDF] fichier comprend certains ou tous les champs définis ci-dessous. Pour plus d’informations sur l’organisation interne des fichiers, voir Structure [des fichiers de flux de données](#cdf-file-structure)client.

<table id="table_46BC897A30C2469AB5911F5B85A3FAA7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Champ </th> 
   <th colname="col2" class="entry"> Type de données </th> 
   <th colname="col3" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code> Event Time</code> </p> </td> 
   <td colname="col2"> <p>Horodatage </p> </td> 
   <td colname="col3"> <p>Heure à laquelle un fichier CDF a été traité par les serveurs <span class="wintitle"></span> de collecte de données (DCS). L’horodatage utilise le format hh:mm:ss <i></i> aaaa-mm-jj et est défini dans le fuseau horaire UTC. </p> <p> <p>Remarque : L’heure de l’événement <i>n’est pas</i>: <p> 
       <ul id="ul_41ABC813FAAC4659AC8DA13F4A6DD7EB"> 
        <li id="li_0192D253EA4C49C4BF2E8BA62CEE028E">Heure de l’événement de page ou de l’appel d’événement lui-même, bien qu’elle puisse être proche de cette heure. </li> 
        <li id="li_271DF14395BC495FBF17186588A554A8">Lié à l’heure DCS dans le nom de fichier. <a href="#different-processing-times">Voir aussi </a> Heures du nom de fichier du flux de données client et Heures du contenu du fichier... . </li> 
       </ul> </p> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Device</code> </p> </td> 
   <td colname="col2"> <p>Chaîne </p> </td> 
   <td colname="col3"> <p>Il s’agit de l’ID <span class="wintitle"> utilisateur</span> unique (UUID), qui est un ID de périphérique à 38 chiffres pour le visiteur de votre site. Voir également <a href="../reference/ids-in-aam.md">Index des ID dans Audience Manager</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Container ID</code> </p> </td> 
   <td colname="col2"> <p>Numérique </p> </td> 
   <td colname="col3"> <p>L’ID du conteneur qui déclenche l’ID est synchronisé. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Realized Traits</code> </p> </td> 
   <td colname="col2"> <p>Tableau numérique </p> </td> 
   <td colname="col3"> <p>Tableau d’identifiants de caractéristiques qui contient toutes les caractéristiques pour lesquelles un visiteur s’est rendu compte (qualifié) dans l’appel d’événement. </p> <p>Notez que le tableau peut contenir des caractéristiques pour lesquelles le visiteur s’était qualifié avant et pour lesquelles il se réqualifie via cet appel d’événement. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Realized Segments</code> </p> </td> 
   <td colname="col2"> <p>Tableau numérique </p> </td> 
   <td colname="col3"> <p>Tableau d’ID de segment qui contient tous les segments pour lesquels un visiteur a réalisé (qualifié) l’appel d’événement. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Request Parameters</code> </p> </td> 
   <td colname="col2"> <p>Chaîne </p> </td> 
   <td colname="col3"> <p>Chaîne qui capture tous les paramètres (variables, identifiants, paires clé-valeur, identifiants publicitaires de périphériques, etc.) transmis lors de l’appel d’événement. </p> <p>Exemple raccourci : </p> <p> <code> d_rtbd:json,c_contextData.a.CarrierName:mobile,c_contextData.a.adid:92D56353-49C5-431E-B474-FC528D585810,c_contextData.a,RunMode:Application,c_contextData.a.DaysSinceLastUpgrade:61,d_cid_ic:xid%01EACB6E40-AC65-4012-9FE9-ABD59965E9C4%011,c_contextData.a.PrevSessionLength:583</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Referer Data Type</code> </p> </td> 
   <td colname="col2"> <p>Chaîne </p> </td> 
   <td colname="col3"> <p>URL non codée de la page de référence (le cas échéant). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> IP Data Type</code> </p> </td> 
   <td colname="col2"> <p>Chaîne </p> </td> 
   <td colname="col3"> <p>Adresse IP du visiteur capturé dans l’appel d’événement. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> MCDevice </code> </p> </td> 
   <td colname="col2"> <p>Chaîne </p> </td> 
   <td colname="col3"> <p>Identifiant <span class="keyword"> Experience Cloud</span> (MID) affecté au visiteur du site. See also, <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies and theExperience Cloud ID service</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> All Segments</code> </p> </td> 
   <td colname="col2"> <p>Tableau numérique </p> </td> 
   <td colname="col3"> <p>Tableau d’ID de segment contenant les segments précédemment réalisés et les nouveaux segments pour lesquels le visiteur est qualifié. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> All Traits</code> </p> </td> 
   <td colname="col2"> <p>Tableau numérique </p> </td> 
   <td colname="col3"> <p>Tableau d’identifiants de caractéristiques propriétaires et tiers contenant les caractéristiques précédemment réalisées et les nouvelles caractéristiques pour lesquelles le visiteur s’est qualifié depuis le dernier flux de données généré. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Structure du fichier du flux de données client {#cdf-file-structure}

Répertorie et définit la structure de données d’un [!UICONTROL CDF] fichier. Cela inclut la séquence de données, les délimiteurs de champ et les séparateurs, un mappage de fichier de données et un exemple de fichier.

## Identifiants de champ de données et séquence {#identifiers-and-sequence}

<!-- cdf-file-structure.xml -->

[!UICONTROL CDF] ne contiennent pas de colonnes ou d’en-têtes de champ marqués. A la place, un [!UICONTROL CDF] fichier définit des champs et des tableaux avec des [!DNL ASCII] caractères non imprimables. En outre, le [!UICONTROL CDF] fichier répertorie chaque champ et tableau dans un ordre spécifique. La compréhension des identificateurs de champ et de l’ordre vous aidera à analyser correctement le fichier.

<table id="table_D2C8786DF7CE47E5ADB8930EC825F8F6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elément Fichier CDF </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Séparateurs de champs et délimiteurs </p> </td> 
   <td colname="col2"> <p>Ces caractères non imprimables définissent les éléments et la structure du fichier CDF : </p> <p> 
     <ul id="ul_056A9B90AC88405CBB5F81A56CD6E4C9"> 
      <li id="li_B9DA15DCB6A445D781B8753C1C4262B0">Ctrl + a (ASCII <code> 001</code> ou <code> ^A</code>) sépare les données de champs individuels par un indicateur d’espace non imprimable. </li> 
      <li id="li_E68D0CC065B34AC9AF91F166CAA2A67C">Ctrl + b (ASCII <code> 002</code> ou <code> ^B</code>) sépare les données d’un tableau et les paramètres de requête. </li> 
      <li id="li_6C32D927FEF04CDE9887374E8C2688E7">Ctrl + c (ASCII <code> 003</code> ou <code> ^C</code>) définit des paires clé-valeur. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Séquence de champ </p> </td> 
   <td colname="col2"> <p> <p>Important : <span class="keyword"> Audience Manager</span> se réserve le droit d’ajouter de nouveaux champs à la fin du fichier CDF dans les prochaines versions. Cela signifie que la conception technique de votre système d’analyse de fichiers ne doit pas supposer un nombre fixe de colonnes (bien qu’elle puisse supposer un ordre fixe pour les colonnes existantes). </p> </p> <p>Les données contenues dans votre fichier CDF s’affichent dans l’ordre indiqué ci-dessous. </p> <p> 
     <ol id="ol_1FDF4A7F089448ED8A724378C23009C8"> 
      <li id="li_CB97D90B54EB4F95861583D4A5F660C7"> Heure de l’événement </li> 
      <li id="li_C44E8CCB1A964B7A941FD772FB8A7608">Device  </li> 
      <li id="li_F8AE0D4CA19D411686A240FE06F56147">ID de conteneur </li> 
      <li id="li_660D17989BE54610A01229C47894E8A9"> Caractéristiques réalisées </li> 
      <li id="li_1591180564374204852785C6FFCA4F74"> Segments réalisés </li> 
      <li id="li_FE38DA4969EE4E19B39124E77E2EA5F9">Paramètres de requête </li> 
      <li id="li_9AC25DA883214FBC902D7CE9DACFAE28">Referer </li> 
      <li id="li_BA05F1C33B5B4625B450425FF1911B30">Adresse IP </li> 
      <li id="li_08E632FB135F42B5830D5CBFE6EE6BE8">ID de périphérique Experience Cloud (ou MID). See also, <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID Service</a> </li> 
      <li id="li_7A05AF4790A1425A90D019681DF4A595"> Tous les segments </li> 
      <li id="li_1B5A6F076A354BA0A931CB260E6D2675">Toutes les caractéristiques </li> 
     </ol> </p> <p>Pour consulter la description des champs, voir Définition <a href="#cdf-defined"></a>du contenu du flux de données client. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Carte de fichiers CDF {#cdf-file-map}

[!UICONTROL CDF] les données du fichier s’affichent dans l’ordre indiqué ci-dessous.

![](assets/sequence-map.png)

## Identification des tableaux

Les tableaux d’un [!UICONTROL CDF] fichier commencent et se terminent par le séparateur de `Ctrl + a` champs. Le premier élément d’un tableau s’affiche ainsi comme un champ de données autonome. Par exemple, le tableau des caractéristiques réalisées commence par `^A1234`. Le délimiteur et l’ID de tableau `^B5678` suivent cette entrée. Par conséquent, vous pouvez être tenté de penser que le premier élément du tableau des caractéristiques réalisées est ID 5678 (car il commence par `^B`). Ce n’est pas le cas, c’est pourquoi vous devez connaître la séquence et la structure d’un fichier de données. Même si le premier élément du tableau de caractéristiques réalisé (ou l’un des autres tableaux d’un [!UICONTROL CDF] fichier) commence par `^A`, l’ordre d’apparition ou de position du fichier définit le début d’un tableau. Et le premier élément d’un tableau est toujours séparé de l’entrée précédente par `^A`.

## Exemple de fichier CDF {#sample-file}

Un exemple de [!UICONTROL CDF] fichier peut ressembler à ce qui suit. Nous avons inséré des sauts de ligne dans cet exemple pour l'aider à s'adapter à la page.

![](assets/CDF-sample.png)

## Conventions d’attribution de noms aux fichiers de flux de données client {#cdf-naming-conventions}

Les sections ci-dessous répertorient et définissent les éléments de votre nom de [!UICONTROL CDF] fichier.

## Nom de fichier CDF : Syntaxe et exemple {#cdf-file-name}

<!-- cdf-file-name.xml -->

Un nom de [!UICONTROL CDF] fichier type contient les éléments répertoriés ci-dessous. Note, *italics* indicates a variable placeholder:

### Syntaxe

```
s3://aam-cdf/YOUR-S3-BUCKET-NAME/day=yyyy-mm-dd/hour=hh/AAM-CDF-PARTNER-ID-AAM PROCESS-ID_0.gz
```

### Exemple

```
s3://aam-cdf/dataCompany/day=2017-09-14/hour=17/AAM_CDF_1234_000058_0.gz
```

Dans votre [!DNL S3] compartiment de stockage, les fichiers sont triés par ordre croissant selon l'ID de partenaire ([!UICONTROL PID]), le jour et l'heure.

## Définition des éléments de nom de fichier CDF {#cdf-file-name-elements}

Le tableau suivant répertorie et définit les éléments d’un nom de [!UICONTROL CDF] fichier.

<table id="table_4AC4F90C1C7D43E2A93CB3B6908D7E94"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elément Nom de fichier </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> s3://aam-cdf/</code> </p> </td> 
   <td colname="col2"> <p>Il s’agit du compartiment de stockage racine par défaut de votre fichier CDF sur un serveur Amazon S3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>your S3 bucket name</i> </code> </p> </td> 
   <td colname="col2"> <p>Nom du compartiment S3 en lecture seule qui contient vos fichiers CDF. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>day=<i>yyyy-mm-dd</i></code> </p> </td> 
   <td colname="col2"> <p>date de traitement de votre fichier. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>hour=<i>hh</i></code> </p> </td> 
   <td colname="col2"> <p>Valeur d’heure exprimée en notation de 24 heures et définie dans le fuseau horaire UTC. <a href="#different-processing-times">Voir aussi </a> Heures du nom de fichier du flux de données client et Heures du contenu du fichier... . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>partner ID</i> </code> </p> </td> 
   <td colname="col2"> <p>Votre identifiant de partenaire. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>AAM process ID</i>_0</code> </p> </td> 
   <td colname="col2"> <p>ID de processus interne d’Audience Manager <span class="keyword"></span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> .gz</code> </p> </td> 
   <td colname="col2"> <p>Une extension de fichier gzip. Les fichiers CDF sont compressés par gzip. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Notifications de traitement des fichiers de flux de données client {#cdf-file-processing-notifications}

[!DNL Audience Manager] écrit un `.info` fichier dans votre [!DNL S3] répertoire pour vous informer lorsque votre [!UICONTROL Customer Data File] ([!UICONTROL CDF]) est prêt pour le téléchargement. Le `.info` fichier comprend également des métadonnées [!DNL JSON] formatées sur le contenu de vos [!UICONTROL CDF] fichiers. Consultez cette section pour en savoir plus sur la syntaxe et les champs utilisés par ce fichier de notification.

## Exemple de fichier d’informations {#sample-info-file}

<!-- cdf-notifications.xml -->

Chaque `.info` fichier contient une `Files` `Totals` section et une section. La `Files` section contient un tableau contenant des mesures spécifiques pour chaque fichier horaire. La `Totals` section contient des mesures regroupées dans tous vos [!UICONTROL CDF] fichiers pour un jour donné. Le contenu de votre `.info` fichier peut ressembler à l’exemple suivant.

```js
{
    "Files": [
        {
            "FileByteSize": 2709730,
            "FileChecksumMD5": "a9ea418e79511642cff11c2a898037dc-1",
            "FileName": "AAM_CDF_1109_000000_0.gz",
            "FileSequenceNumber": 1
        },
        {
            "FileByteSize": 2783351,
            "FileChecksumMD5": "7b469485d60274b6991acd0817855840-3",
            "FileName": "AAM_CDF_1109_000001_0.gz",
            "FileSequenceNumber": 2
        }
    ],
    "Totals": {
        "Day": "2017-09-26",
        "Hour": "18",
        "TotalByteSize": 150092997,
        "TotalNumberFiles": 2
    }
}
```

## Définition des champs du fichier d’informations {#info-file-fields-defined}

Les tableaux suivants répertorient et définissent les éléments d’un [!UICONTROL CDF] fichier `.info` .

### Objet Fichiers

<table id="table_582101B414864DA991CE813A7937ECC6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Champ </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Files</code> </p> </td> 
   <td colname="col2"> <p>Démarre le tableau contenant des métadonnées sur vos fichiers CDF. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileByteSize</code> </p> </td> 
   <td colname="col2"> <p>Taille du fichier en octets. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileChecksumMD5</code> </p> </td> 
   <td colname="col2"> <p>Amazon S3 ETag. Le nombre suivant le trait d’union indique le nombre de parties utilisées pour créer le fichier pendant le téléchargement en plusieurs parties. La valeur <code> ETag</code> n’est pas identique à la somme de contrôle MD5 du fichier. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileName</code> </p> </td> 
   <td colname="col2"> <p>Nom de fichier. Voir Conventions <a href="#cdf-naming-conventions"> de dénomination des fichiers de flux de données</a>du client. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileSequenceNumber</code> </p> </td> 
   <td colname="col2"> <p>Numéro d’index pour chaque fichier. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Totaux, objet

<table id="table_44F0B2D229E84A5DB3041760B1A50858"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Champ </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Totals</code> </p> </td> 
   <td colname="col2"> <p>Démarre l’objet qui contient des données agrégées sur tous vos fichiers CDF. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Day</code> </p> </td> 
   <td colname="col2"> <p>Jour de disponibilité des données. Utilise le format <i>aaaa-mm-jj</i> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Hour</code> </p> </td> 
   <td colname="col2"> <p>Heure pour laquelle les données sont disponibles. Utilise le format 24 heures défini dans le fuseau horaire UTC. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalByteSize</code> </p> </td> 
   <td colname="col2"> <p>Taille totale de tous vos fichiers CDF pour cette date, en octets. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalNumberFiles</code> </p> </td> 
   <td colname="col2"> <p>Nombre total de fichiers téléchargés dans votre répertoire S3. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Fil de données client Nom de fichier Heures et Contenu du fichier Heures différentes {#different-processing-times}

Votre [!UICONTROL CDF] fichier contient des horodatages dans le nom de fichier et le contenu du fichier. Ces horodatages enregistrent différents processus d’événement pour le même [!UICONTROL CDF] fichier. Il n’est pas rare de voir des horodatages différents dans le nom et le contenu du même fichier. La compréhension de chaque horodatage permet d’éviter les erreurs courantes lors de l’utilisation de ces données ou lors d’une tentative de tri temporel.

## Localisation des horodatages des fichiers CDF {#locating-timestamps}

<!-- cdf-time-differences.xml -->

[!UICONTROL CDF] les fichiers enregistrent le temps différemment en 2 emplacements distincts.

![](assets/cdf-timestamp.png)

## Comprendre la différence entre les horodatages {#understanding-timestamps}

Le tableau suivant fournit des détails supplémentaires sur les horodatages de vos [!UICONTROL CDF] fichiers, ainsi que des informations sur la manière de les utiliser correctement.

| Emplacement de l’horodatage | Description |
|--- |--- |
| Nom de fichier | L’horodatage du nom de fichier CDF marque l’heure à laquelle [!DNL Audience Manager] vous avez commencé à préparer votre fichier pour la remise. Cet horodatage est défini dans le fuseau horaire UTC. Il utilise le `hour=` paramètre, avec le temps formaté comme une heure de 2 chiffres en notation de 24 heures. Cette heure peut être différente de l’heure de l’événement enregistrée dans le contenu du fichier. VENTILATION Lorsque vous travaillez avec des fichiers CDF, vous constaterez parfois que votre compartiment S3 est vide pendant une heure donnée. Un compartiment vide peut signifier l’une des significations suivantes :<ul><li>Il n'y a pas de données pour cette heure particulière. </li><li> Nos serveurs sont lourdement chargés et ne peuvent pas traiter les fichiers pendant une heure particulière. Lorsque le serveur récupère, il place les fichiers qui auraient dû être transférés dans un intervalle de temps antérieur dans un intervalle de temps avec une valeur d'heure ultérieure. Par exemple, vous verrez ceci lorsqu’un fichier qui aurait dû figurer dans le compartiment 17 de l’heure apparaît dans le compartiment 18 de l’heure (avec `hour=18` le nom du fichier). Dans ce cas, le serveur a probablement commencé à traiter votre fichier à l’heure 17, mais n’a pas pu le terminer dans cet intervalle. Au lieu de cela, le fichier est déplacé vers l’intervalle horaire suivant.</li></ul><br>**Important**: N’utilisez pas l’horodatage du nom de fichier pour regrouper les événements par heure. Si vous devez grouper par heure, utilisez l’ `EventTime` horodatage dans le contenu du fichier. |
| Contenu du fichier | L’horodatage du contenu du fichier CDF marque l’heure à laquelle les serveurs de collecte de données ont commencé à traiter le fichier. Cet horodatage est défini dans le fuseau horaire UTC. Il utilise le `EventTime` champ, avec le temps au format *`yyyy-mm-dd hh:mm:ss`*. Cette heure est proche de l’heure réelle de l’événement sur la page, mais elle peut être différente de l’indicateur d’heure dans le nom de fichier. <br> **Conseil**: Contrairement à l’ `hour=` horodatage du nom de fichier, vous pouvez utiliser `EventTime` pour regrouper les données par heure. |

>[!MORELIKETHIS]
>
>* [FAQ sur le flux de données client](../faq/faq-cdf.md)

