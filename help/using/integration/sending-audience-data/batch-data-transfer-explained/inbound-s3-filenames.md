---
description: Décrit les champs obligatoires, la syntaxe, les conventions de nommage et les tailles de fichier que vous devez suivre lors de l’envoi de données à Audience Manager. Définissez les noms et tailles de vos fichiers en fonction de ces spécifications lorsque vous envoyez des données à un répertoire Audience Manager/Amazon S3.
seo-description: Describes the required fields, syntax, naming conventions and file sizes you need to follow when sending data to Audience Manager. Set the names and sizes of your files according to these specifications when you send data to an Audience Manager / Amazon S3 directory.
seo-title: Amazon S3 Name and File Size Requirements for Inbound Data Files
solution: Audience Manager
title: Exigences relatives au nom et à la taille de fichier Amazon S3 pour les fichiers de données entrants
uuid: 3692a122-6ad5-468c-934e-53067bd8cf71
feature: Inbound Data Transfers
exl-id: 428acdb5-fff0-4b70-b15a-e384aed9cc2d
source-git-commit: a5506a315a98afdf31f8f52fac09b9179f388f30
workflow-type: tm+mt
source-wordcount: '1114'
ht-degree: 2%

---

# Exigences en matière de nom et de taille de fichier [!DNL Amazon S3] pour les fichiers de données entrants {#amazon-s-name-and-file-size-requirements-for-inbound-data-files}

Décrit les champs obligatoires, la syntaxe, les conventions de nommage et les tailles de fichier que vous devez suivre lors de l’envoi de données à [!DNL Audience Manager]. Définissez les noms et tailles de vos fichiers en fonction de ces spécifications lorsque vous envoyez des données à un répertoire [!DNL Audience Manager] / [!DNL Amazon S3].

>[!NOTE]
>
>Les styles de texte (`monospaced text`, *italique*, crochets `[ ]` `( )`, etc.) de ce document indiquent les éléments de code et les options. Pour plus d’informations, voir les [conventions de style relatives aux éléments de code et de texte](../../../reference/code-style-elements.md).

## Syntaxe du nom de fichier {#file-name-syntax}

[!DNL S3] noms de fichier contiennent les éléments obligatoires et facultatifs suivants :

* Préfixe **[!DNL S3]:**   `s3n://AWS_directory/partner_name/date=yyyy-mm-dd/`

* **Éléments de nom de fichier :**   `ftp_dpm_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

Pour les autres formats de nom de fichier acceptés, voir [Intégrations de partenaires personnalisées](/help/using/integration/sending-audience-data/custom-partner-integrations.md).

<!--
Removed  {importance="high"} for ExL
-->

>[!NOTE]
>
>[!DNL Audience Manager] traite uniquement les fichiers codés [!DNL ASCII] et [!DNL UTF-8].

### Nommer les éléments

Le tableau définit les éléments dans un nom de fichier [!DNL S3].

<table id="table_455D174BAB9B494D973DA1023F22B962"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Élément de nom </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> <i>AWS_directory</i> </code> </p> </td> 
   <td colname="col2"> <p>Chemin et nom de votre compartiment Amazon S3. Contactez votre gestionnaire de compte pour obtenir le nom, le chemin et les informations d’identification de votre répertoire S3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>date=<i>yyyy-mm-dd</i></code> </p> </td> 
   <td colname="col2"> <p>Horodatage (basé sur l’heure UTC) du moment où vous envoyez les fichiers à votre compartiment S3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>DPID</i> </code> </p> </td> 
   <td colname="col2"> <p>Un identifiant qui indique <span class="keyword"> Audience Manager</span> si un fichier de données contient vos propres identifiants d’utilisateur, Android ID, iOS ID ou d’autres identifiants appartenant à <a href="/help/using/features/global-data-sources.md"> sources de données globales</a>. Accepte les options suivantes :</p> 
    <ul id="ul_818EB3EB2E5543F0B048BCEBB6699562"> 
     <li id="li_ED6B13CB49794F6BA3DB6D807F788BAF"> <b>Identifiant du Source de données (également appelé identifiant du fournisseur de données) : </b> il s’agit d’un identifiant unique qu’Audience Manager attribue à une source de données (consultez la <a href="/help/using/reference/ids-in-aam.md"> Index des identifiants Audience Manager </a> ). Utilisez cet ID affecté dans un nom de fichier lors de l’envoi de données contenant vos propres ID utilisateur. Par exemple, <code>...ftp_dpm_21_123456789.sync</code> indique <span class="keyword"> Audience Manager</span> d’intégrer des données aux identifiants appartenant à la source de données 21. </li> 
     <li id="li_1955911BA11F4F458227B77F383F25A3"> <b>Android IDs (GAID) :</b> utilisez l’ID 20914 dans un nom de fichier de données s’il contient des Android ID. Vous devez utiliser le <code><i>_DPID_TARGET_DATA_OWNER</i></code> de champs lorsque vous utilisez les Android ID. Par exemple, <code>...ftp_dpm_20914_DPID_TARGET_DATA_OWNER_123456789.sync</code> indique <span class="keyword"> Audience Manager</span> que le fichier de données contient uniquement les Android ID et que les ID doivent être qualifiés pour les caractéristiques appartenant à la source de données <code><i>_DPID_TARGET_DATA_OWNER</i></code>.</li> 
     <li id="li_54E7734C121646AF82095806DD1AED61"> <b>iOS IDs (IDFA) :</b> utilisez ID 20915 dans un nom de fichier de données s’il contient des iOS IDs. Vous devez utiliser le <code><i>_DPID_TARGET_DATA_OWNER</i></code> de champs lorsque vous utilisez les iOS ID. Par exemple, <code>...ftp_dpm_20915_DPID_TARGET_DATA_OWNER_123456789.sync</code> indique <span class="keyword"> Audience Manager</span> que le fichier de données contient uniquement les iOS ID et que les ID doivent être qualifiés pour les caractéristiques appartenant à la source de données <code><i>_DPID_TARGET_DATA_OWNER</i></code>.</li>
     <li> <b>ID appartenant à d’autres sources de données globales</b> : vous pouvez intégrer des ID Roku pour Advertising (RIDA), des ID Microsoft Advertising (MAID) et d’autres ID. Utilisez l’identifiant correspondant à chaque source de données, comme décrit dans l’article <a href="/help/using/features/global-data-sources.md"> les sources de données globales </a>.</li> 
    </ul> <p> <p>Remarque : ne mélangez pas les types d’ID dans vos fichiers de données. Par exemple, si votre nom de fichier comprend l’identifiant Android, ne placez pas d’iOS ID ou vos propres ID dans le fichier de données. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>_DPID_TARGET_DATA_OWNER</i> </code> </p> </td> 
   <td colname="col2"> <p>Ce champ indique à Audience Manager la source de données à laquelle intégrer des données. Ce champ est obligatoire si vous définissez le DPID sur un Android ID ou un iOS ID ou un autre ID appartenant aux sources de données globales. Cela permet à Audience Manager de lier les données du fichier à votre organisation. <br> Cette source de données cible doit appartenir à votre société. À des fins de partage de données tierces, pour ingérer des données dans une source de données cible appartenant à une autre société, vous devez disposer d’un mappage d’accès entre votre société et la source de données cible. Contactez votre consultant Adobe ou le service clientèle afin de configurer le mappage.</p> <p><b>Remarque importante :</b> vous <i>pas</i> devez demander un mappage pour les relations de partage de données existantes (pour les sources de données cibles appartenant à d’autres sociétés auxquelles vous avez intégré des données avant le 14 mars 2022). Le mappage n’est pas non plus requis lors de l’intégration de données dans des sources de données cibles qui appartiennent à votre PID. </p> <p>Par exemple : </p> 
    <ul> 
     <li> <code>...ftp_dpm_33_21_1234567890.sync</code> indique à Audience Manager que vous qualifiez des ID de client appartenant à la source de données 33 pour des caractéristiques ou des signaux appartenant à la source de données 21. </li> 
     <li> <b>Android IDs (GAID) :</b> <code>...ftp_dpm_20914_21_1234567890.sync</code> indique à <span class="keyword"> Audience Manager</span> que le fichier de données contient uniquement des Android ID et que les ID doivent être qualifiés pour les caractéristiques appartenant à la source de données 21.</li> 
     <li> <b>iOS IDs (IDFA) : </b> <code>...ftp_dpm_20915_21_1234567890.sync</code> indique à <span class="keyword"> Audience Manager</span> que le fichier de données contient uniquement des iOS ID et que les ID doivent être qualifiés pour les caractéristiques appartenant à la source de données 21.</li>
     <li> <b>ID appartenant à d’autres sources de données globales</b> : <code>...ftp_dpm_121963_21_1234567890.sync</code> indique à <span class="keyword"> Audience Manager</span> que le fichier de données contient uniquement des ID Roku et que les ID doivent être qualifiés pour les caractéristiques appartenant à la source de données 21. Utilisez l’identifiant correspondant à chaque source de données, comme décrit dans l’article <a href="/help/using/features/global-data-sources.md"> les sources de données globales </a>.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>partner_name</i> </code> </p> </td> 
   <td colname="col2"> <p>Nom de société ou d’organisation que vous utilisez dans <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>TIMESTAMP</i> </code> </p> </td> 
   <td colname="col2"> <p>Date et heure UNIX UTC à 10 chiffres, en secondes. L’horodatage permet de rendre chaque nom de fichier unique. </p> 
    <!-- 
     <p> <p>Note:  Audience Manager does not use the timestamp during processing of inbound files. The timestamp in the filename has been deprecated in Audience Manager but is still required for backwards compatibility. </p> </p> 
    --> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> (.sync|.overwrite)</code> </p> </td> 
   <td colname="col2"> <p>Options de synchronisation qui incluent : </p> <p> 
     <ul id="ul_DAAF61EC636C4456BECDDC34C3F86E83"> 
      <li id="li_6EC6DE442B4546AA9F4F800D65C8A4EC"> <code> sync</code> : scénario normal lorsque des fournisseurs de données tiers envoient des caractéristiques, par utilisateur, pour être ajoutées ou supprimées dans le système Audience Manager. </li> 
      <li id="li_8FE8430C2C004F87835D55231A0D99C9"> <code> overwrite</code> : permet aux fournisseurs de données d’envoyer une liste de caractéristiques par utilisateur, qui doit remplacer toutes les caractéristiques tierces existantes de cet utilisateur pour ce fournisseur de données dans Audience Manager. Il n’est pas nécessaire d’inclure tous les utilisateurs dans un fichier de remplacement. Incluez uniquement les utilisateurs que vous souhaitez modifier. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>SPLIT_NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>Nombre entier. Utilisé lorsque vous divisez des fichiers volumineux en plusieurs parties afin d’améliorer les temps de traitement. Le nombre indique la partie du fichier original que vous envoyez. </p> <p>Pour un traitement efficace des fichiers, fractionnez vos fichiers de données comme indiqué : </p> 
    <ul id="ul_E9446C5CA42649658093904D49D4369C"> 
     <li id="li_B275708DFE3F49E29EFAE6B838429E39">Non compressé : 1 Go </li> 
     <li id="li_A9638EB46ED14E0680B6575D5457E32F">Comprimé : 200 à 300 Mo </li> 
    </ul> <p>Consultez les 2 premiers exemples de noms de fichier <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md#file-name-examples"></a> ci-dessous. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>Lors de l’envoi de fichiers à Amazon S3, utilisez uniquement la compression gzip. Une fois compressés, ces fichiers obtiennent l’extension <code> .gz</code>. N’utilisez pas la compression .zip. </p> <p>Les fichiers compressés doivent faire 3 Go ou moins. Si vos fichiers sont plus volumineux, contactez l’assistance clientèle. Bien qu’Audience Manager puisse gérer des fichiers volumineux, nous pouvons vous aider à réduire la taille de vos fichiers et à rendre les transferts de données plus efficaces. Voir Compression de fichiers <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md"> pour les fichiers de transfert de données entrants</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Exemples de noms de fichier {#file-name-examples}

Les exemples suivants affichent les noms de fichiers correctement formatés. Vos noms de fichier peuvent ressembler.

<ul class="simplelist"> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.sync.1.gz</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.sync.2.gz</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.sync</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_567_1366545717.sync.gz</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.overwrite</code> </li> 
</ul>

Vous pouvez [télécharger](assets/ftp_dpm_1234_1445374061.overwrite) l’exemple de fichier si vous souhaitez des exemples supplémentaires. Ce fichier a été enregistré avec l’extension de fichier `.overwrite`. Ouvrez-le à l’aide d’un simple éditeur de texte.

## Tailles de fichier acceptées {#accepted-file-sizes}

Tenez compte des chiffres ci-dessous pour le traitement le plus rapide/le plus précoce de vos fichiers, ainsi que pour les limitations de taille de fichier lorsque vous envoyez des données à un répertoire [!DNL Audience Manager]/[!DNL Amazon S3].

<table id="table_59FCC63806684DF8BE54A1EAF224A234"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type de fichier </th> 
   <th colname="col2" class="entry"> Taille Optimale </th> 
   <th colname="col3" class="entry"> Taille maximale </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>Compressé</b> </td> 
   <td colname="col2"> <p>200 à 300 Mo </p> </td> 
   <td colname="col3"> <p>3 GO </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Non compressé</b> </td> 
   <td colname="col2"> <p>1 GO </p> </td> 
   <td colname="col3"> <p>5 GO </p> </td> 
  </tr> 
 </tbody> 
</table>


>[!NOTE]
>
>Le processus de validation des données entrantes marque les fichiers vides comme non valides et ne les traite pas.

## Limites de longueur des lignes {#line-limits}

Les fichiers de données entrants sont limités à 102400 octets. Les lignes dépassant cette limite sont exclues du transfert.

>[!MORELIKETHIS]
>
>* [Exigences en matière de nom FTP pour les fichiers de données entrants](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md)
