---
description: Décrit les champs obligatoires, la syntaxe, les conventions d’affectation de nom et les tailles de fichiers à respecter lors de l’envoi de données à l’Audience Manager. Définissez les noms et tailles de vos fichiers selon ces spécifications lorsque vous envoyez des données à un répertoire Audience Manager / Amazon S3.
seo-description: Décrit les champs obligatoires, la syntaxe, les conventions d’affectation de nom et les tailles de fichiers à respecter lors de l’envoi de données à l’Audience Manager. Définissez les noms et tailles de vos fichiers selon ces spécifications lorsque vous envoyez des données à un répertoire Audience Manager / Amazon S3.
seo-title: Exigences en matière de nom et de taille de fichier Amazon S3 pour les fichiers de données entrants
solution: Audience Manager
title: Exigences en matière de nom et de taille de fichier Amazon S3 pour les fichiers de données entrants
uuid: 3692a122-6ad5-468c-934e-53067bd8cf71
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: d6856a54c649d701c3163c1408f84aea256ebdc1
workflow-type: tm+mt
source-wordcount: '1051'
ht-degree: 5%

---


# [!DNL Amazon S3] Exigences en matière de nom et de taille de fichier pour les fichiers de données entrants  {#amazon-s-name-and-file-size-requirements-for-inbound-data-files}

Décrit les champs obligatoires, la syntaxe, les conventions d’affectation de nom et les tailles de fichiers à respecter lors de l’envoi de données à [!DNL Audience Manager]. Définissez les noms et les tailles de vos fichiers en fonction de ces spécifications lorsque vous envoyez des données dans un répertoire [!DNL Audience Manager] / [!DNL Amazon S3].

>[!NOTE]
>
>Les styles de texte (`monospaced text`, *italiques*, crochets `[ ]` `( )`, etc.) dans ce document, indiquez les éléments de code et les options. Pour plus d’informations, voir les [conventions de style relatives aux éléments de code et de texte](../../../reference/code-style-elements.md).

## Syntaxe du nom de fichier {#file-name-syntax}

[!DNL S3] les noms de fichier contiennent les éléments obligatoires et facultatifs suivants :

* **[!DNL S3]préfixe :**   `s3n://AWS_directory/partner_name/date=yyyy-mm-dd/`

* **Eléments de nom de fichier :**   `ftp_dpm_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

Pour connaître les autres formats de nom de fichier acceptés, voir [Intégrations de partenaire personnalisées](/help/using/integration/sending-audience-data/custom-partner-integrations.md).

<!--
Removed  {importance="high"} for ExL
-->

>[!NOTE]
>
>[!DNL Audience Manager] traite uniquement  [!DNL ASCII] et  [!DNL UTF-8] les fichiers codés.

### Eléments de nom

Le tableau définit les éléments dans un nom de fichier [!DNL S3].

<table id="table_455D174BAB9B494D973DA1023F22B962"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elément Nom </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> <i>AWS_directory</i> </code> </p> </td> 
   <td colname="col2"> <p>Chemin d’accès et nom du compartiment Amazon S3. Contactez votre gestionnaire de compte pour connaître le nom, le chemin et les informations d’identification de votre répertoire S3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>date=<i>yyyy-mm-dd</i></code> </p> </td> 
   <td colname="col2"> <p>Horodatage (basé sur l’heure UTC) du moment où vous envoyez les fichiers à votre compartiment S3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>DPID</i> </code> </p> </td> 
   <td colname="col2"> <p>Un identifiant qui indique à <span class="keyword"> Audience Manager</span> si un fichier de données contient vos propres ID utilisateur, ID Android, ID iOS ou autres ID appartenant à <a href="/help/using/features/global-data-sources.md"> les sources de données globales </a>. Accepte les options suivantes :</p> 
    <ul id="ul_818EB3EB2E5543F0B048BCEBB6699562"> 
     <li id="li_ED6B13CB49794F6BA3DB6D807F788BAF"> <b>ID de source de données (également appelé ID du fournisseur de données) : </b> Il s’agit d’un identifiant unique attribué par l’Audience Manager à une source de données (reportez-vous à l’ <a href="/help/using/reference/ids-in-aam.md"> index d’Audience Manager des ID  </a>). Utilisez cet ID affecté dans un nom de fichier lors de l’envoi de données contenant vos propres ID utilisateur. Par exemple, <code>...ftp_dpm_21_123456789.sync</code> indique à <span class="keyword"> Audience Manager</span> des données embarquées à des ID appartenant à la source de données 21. </li> 
     <li id="li_1955911BA11F4F458227B77F383F25A3"> <b>Identifiants Android (GAID) : </b> utilisez ID 20914 dans un nom de fichier de données s’il contient des identifiants Android. Vous devez utiliser le champ <code><i>_DPID_TARGET_DATA_OWNER</i></code> lorsque vous utilisez des ID Android. Par exemple, <code>...ftp_dpm_20914_DPID_TARGET_DATA_OWNER_123456789.sync</code> indique à <span class="keyword"> Audience Manager</span> que le fichier de données contient uniquement des identifiants Android et que ces identifiants doivent correspondre aux caractéristiques appartenant à la source de données <code><i>_DPID_TARGET_DATA_OWNER</i></code>.</li> 
     <li id="li_54E7734C121646AF82095806DD1AED61"> <b>ID iOS (IDFA) : </b> utilisez ID 20915 dans un nom de fichier de données s’il contient des ID iOS. Vous devez utiliser le champ <code><i>_DPID_TARGET_DATA_OWNER</i></code> lorsque vous utilisez des ID iOS. Par exemple, <code>...ftp_dpm_20915_DPID_TARGET_DATA_OWNER_123456789.sync</code> indique à <span class="keyword"> Audience Manager</span> que le fichier de données contient uniquement des ID iOS et que ces identifiants doivent correspondre aux caractéristiques de la source de données <code><i>_DPID_TARGET_DATA_OWNER</i></code>.</li>
     <li> <b>ID appartenant à d’autres sources</b> de données globales : Vous pouvez embarquer des identifiants Roku pour la publicité (RIDA), des identifiants Microsoft Advertising (MAID) et d’autres identifiants. Utilisez l’identifiant correspondant à chaque source de données, comme décrit dans l’article <a href="/help/using/features/global-data-sources.md"> sources de données globales </a>.</li> 
    </ul> <p> <p>Remarque :  Ne mélangez pas les types d’ID dans vos fichiers de données. Par exemple, si votre nom de fichier contient l’identifiant Android, n’insérez pas d’ID iOS ou vos propres ID dans le fichier de données. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>_DPID_TARGET_DATA_OWNER</i> </code> </p> </td> 
   <td colname="col2"> <p>Ce champ indique à l’Audience Manager à quelle source de données intégrer les données. Ce champ est obligatoire si vous définissez le DPID sur un ID Android, un ID iOS ou un autre ID appartenant à des sources de données globales. Cela permet à <span class="keyword"> Audience Manager</span> de lier les données de fichier à votre organisation. </p> <p>Par exemple : </p> 
    <ul> 
     <li> <code>...ftp_dpm_33_21_1234567890.sync</code> indique à l’Audience Manager que vous définissez des ID de client appartenant à la source de données 33 pour les caractéristiques ou les signaux appartenant à la source de données 21. </li> 
     <li> <b>Identifiants Android (GAID) : </b> <code>...ftp_dpm_20914_21_1234567890.sync</code> indique à  <span class="keyword"> Audience </span> Manager que le fichier de données contient uniquement des identifiants Android et que ces identifiants doivent correspondre aux caractéristiques de la source de données 21.</li> 
     <li> <b>Identifiants iOS (IDFA) : </b> <code>...ftp_dpm_20915_21_1234567890.sync</code> indique à  <span class="keyword"> Audience </span> Manager que le fichier de données contient uniquement des identifiants iOS et que ces identifiants doivent correspondre aux caractéristiques de la source de données 21.</li>
     <li> <b>ID appartenant à d’autres sources</b> de données globales :  <code>...ftp_dpm_121963_21_1234567890.sync</code> indique à  <span class="keyword"> Audience </span> Manager que le fichier de données contient uniquement des identifiants Roku et que ces identifiants doivent être inclus dans les caractéristiques appartenant à la source de données 21. Utilisez l’identifiant correspondant à chaque source de données, comme décrit dans l’article <a href="/help/using/features/global-data-sources.md"> sources de données globales </a>.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>partner_name</i> </code> </p> </td> 
   <td colname="col2"> <p>Nom de la société ou de l'organisation que vous utilisez dans <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>TIMESTAMP</i> </code> </p> </td> 
   <td colname="col2"> <p>Horodatage UTC UNIX à 10 chiffres en secondes. L’horodatage permet de rendre chaque nom de fichier unique. </p> 
    <!-- 
     <p> <p>Note:  Audience Manager does not use the timestamp during processing of inbound files. The timestamp in the filename has been deprecated in Audience Manager but is still required for backwards compatibility. </p> </p> 
    --> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> (.sync|.overwrite)</code> </p> </td> 
   <td colname="col2"> <p>Options de synchronisation comprenant : </p> <p> 
     <ul id="ul_DAAF61EC636C4456BECDDC34C3F86E83"> 
      <li id="li_6EC6DE442B4546AA9F4F800D65C8A4EC"> <code> sync</code>: Scénario normal lorsque des fournisseurs de données tiers envoient des caractéristiques par utilisateur pour être ajoutées ou supprimées dans le système d’Audience Manager. </li> 
      <li id="li_8FE8430C2C004F87835D55231A0D99C9"> <code> overwrite</code>: Permet aux fournisseurs de données d’envoyer une liste de caractéristiques par utilisateur qui doit remplacer toutes les caractéristiques tierces existantes de cet utilisateur pour ce fournisseur de données dans l’Audience Manager. Vous n’avez pas besoin d’inclure tous vos utilisateurs dans un fichier de remplacement. Incluez uniquement les utilisateurs que vous souhaitez modifier. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>SPLIT_NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>Entier. Utilisé lorsque vous divisez des fichiers volumineux en plusieurs parties afin d’améliorer les temps de traitement. Le numéro indique la partie du fichier d'origine que vous envoyez. </p> <p>Pour un traitement efficace des fichiers, fractionnez vos fichiers de données comme indiqué : </p> 
    <ul id="ul_E9446C5CA42649658093904D49D4369C"> 
     <li id="li_B275708DFE3F49E29EFAE6B838429E39">Non compressé : 1 Go </li> 
     <li id="li_A9638EB46ED14E0680B6575D5457E32F">Comprimé : 200 à 300 Mo </li> 
    </ul> <p>Voir les 2 premiers exemples de noms de fichier <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md#file-name-examples"></a> ci-dessous. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>Lors de l’envoi de fichiers vers Amazon S3, utilisez la compression gzip uniquement. Une fois compressés, ces fichiers obtiennent l'extension <code> .gz</code>. N’utilisez pas la compression .zip. </p> <p>Les fichiers compressés doivent être de 3 Go ou moins. Si vos fichiers sont plus volumineux, contactez le service à la clientèle. Bien que l'Audience Manager puisse gérer des fichiers volumineux, nous pouvons vous aider à réduire la taille de vos fichiers et à rendre les transferts de données plus efficaces. Voir <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md">Compression de fichiers pour les fichiers de transfert de données entrants</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Exemples de noms de fichier {#file-name-examples}

Les exemples suivants montrent des noms de fichier correctement formatés. Vos noms de fichier peuvent ressembler.

<ul class="simplelist"> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.sync.1.gz</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.sync.2.gz</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.sync</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_567_1366545717.sync.gz</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.overwrite</code> </li> 
</ul>

Vous pouvez [télécharger](assets/ftp_dpm_1234_1445374061.overwrite) le fichier exemple si vous souhaitez d’autres exemples. Ce fichier a été enregistré avec l&#39;extension de fichier `.overwrite`. Ouvrez-le dans un éditeur de texte simple.

## Taille de fichier acceptée {#accepted-file-sizes}

Tenez compte des chiffres ci-dessous pour le traitement le plus rapide/le plus précoce de vos fichiers ainsi que pour les limites de taille de fichier lorsque vous envoyez des données dans un répertoire [!DNL Audience Manager] / [!DNL Amazon S3].

<table id="table_59FCC63806684DF8BE54A1EAF224A234"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type de fichier </th> 
   <th colname="col2" class="entry"> Taille optimale </th> 
   <th colname="col3" class="entry"> Taille maximale </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>Compressé</b> </td> 
   <td colname="col2"> <p>200 à 300 Mo </p> </td> 
   <td colname="col3"> <p>3 Go </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Non compressé</b> </td> 
   <td colname="col2"> <p>1 Go </p> </td> 
   <td colname="col3"> <p>5 Go </p> </td> 
  </tr> 
 </tbody> 
</table>


>[!NOTE]
>
>Le processus de validation des données entrantes marquera les fichiers vides comme non valides et ne les traitera pas.

## Limites de longueur de ligne {#line-limits}

Les fichiers de données entrants ont une longueur de ligne limitée à 10 2400 octets. Les lignes dépassant cette limite sont exclues du transfert.

>[!MORELIKETHIS]
>
>* [Exigences en matière de nom FTP pour les fichiers de données entrants](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md)

