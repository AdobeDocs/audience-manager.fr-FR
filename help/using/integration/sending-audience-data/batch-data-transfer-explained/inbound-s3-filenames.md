---
description: Décrit les champs obligatoires, la syntaxe, les conventions d'affectation de nom et les tailles de fichier à suivre lors de l'envoi de données à Audience Manager. Définissez les noms et tailles de vos fichiers conformément à ces spécifications lorsque vous envoyez des données à un répertoire Audience Manager/Amazon S 3.
seo-description: Décrit les champs obligatoires, la syntaxe, les conventions d'affectation de nom et les tailles de fichier à suivre lors de l'envoi de données à Audience Manager. Définissez les noms et tailles de vos fichiers conformément à ces spécifications lorsque vous envoyez des données à un répertoire Audience Manager/Amazon S 3.
seo-title: Exigences en matière de taille et de fichier Amazon S 3 pour les fichiers de données entrants
solution: Audience Manager
title: Exigences en matière de taille et de fichier Amazon S 3 pour les fichiers de données entrants
uuid: 3692 a 122-6 ad 5-468 c -934 e -53067 bd 8 cf 71
translation-type: tm+mt
source-git-commit: ec2d05290874a95e9cc9b8318fcc5e1e1986f5b9

---


# Amazon S3 Name and File Size Requirements for Inbound Data Files{#amazon-s-name-and-file-size-requirements-for-inbound-data-files}

Décrit les champs obligatoires, la syntaxe, les conventions d&#39;affectation de nom et les tailles de fichier à suivre lors de l&#39;envoi de données à Audience Manager. Set the names and sizes of your files according to these specifications when you send data to an Audience Manager / [!DNL Amazon S3] directory.

>[!NOTE]
>
>Les styles de texte (`monospaced text`, *italiques*, crochets `[ ]` `( )`, etc.) dans ce document indique les éléments et options du code. Pour plus d’informations, voir les [conventions de style relatives aux éléments de code et de texte](../../../reference/code-style-elements.md).

## File Name Syntax {#file-name-syntax}

[!DNL S3] Les noms de fichier contiennent les éléments obligatoires et facultatifs suivants :

* **[!DNL S3]préfixe :**`s3n://AWS_directory/partner_name/date=yyyy-mm-dd/`

* **Fichier - nom du nom :**`ftp_dpm_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

For other accepted file name formats, see [Custom Partner Integrations](/help/using/integration/sending-audience-data/custom-partner-integrations.md).

>[!NOTE] {importance = « high »}
>
>[!DNL Audience Manager] uniquement les processus [!DNL ASCII] et [!DNL UTF-8] les fichiers codés.

### Nommer les éléments

The table defines the elements in an [!DNL S3] file name.

<table id="table_455D174BAB9B494D973DA1023F22B962"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elément Nom </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code><i>Répertoire AWS_</i></code> </p> </td> 
   <td colname="col2"> <p>Chemin d'accès et nom de votre corbeille Amazon S 3. Contactez votre gestionnaire de compte pour connaître le nom, le chemin et les informations d'identification du répertoire S 3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>date =<i>aaaa-mm-jj</i></code> </p> </td> 
   <td colname="col2"> <p>Horodatage (selon l'heure UTC) de l'envoi des fichiers vers votre compartiment S 3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>DPID</i></code> </p> </td> 
   <td colname="col2"> <p>The <span class="term"> Data Provider ID</span> (DPID) is an identifier that tells <span class="keyword"> Audience Manager</span> if a data file contains your own user IDs or Android or iOS IDs. Accepte les options suivantes : </p> <p> <b>ID de partenaire de données</b> </p> <p>Il s'agit d'un identifiant unique attribué par Audience Manager à votre société ou organisation. Utilisez l'ID attribué dans un fichier - nom lors de l'envoi de données contenant votre propre utilisateur - id. For example, <code>...ftp_dpm_21_123456789.sync</code> tells <span class="keyword"> Audience Manager</span> that a partner with ID 21 sent the file and it contains user IDs assigned by that partner. </p> <p> <b>Android ID (GAID)</b> </p> <p> Utilisez l'ID 20914 comme DPID dans un fichier de données - nom si le fichier contient des ID Android. When you use ID 20914 as the DPID, you still need to identify your company to <span class="keyword"> Audience Manager</span>. This means the file name must use the <code><i>_DPID_TARGET_DATA_OWNER</i></code> parameter to hold your company ID. Par exemple, supposons que vous transfériez des fichiers avec des ID Android et que votre ID de fournisseur de données soit 21. In this case, the file name would look like <code>...ftp_dpm_20914_21_123456789.sync</code>. This tells <span class="keyword"> Audience Manager</span> the file contains Android IDs and is from a partner identified by ID 21. </p> <p> <b>ID ios (IDFA)</b> </p> <p> Utilisez l'ID 20915 comme DPID dans un fichier de données - nom si le fichier contient des ID ios. When you use ID 20915 as the DPID, you still need to identify your company to <span class="keyword"> Audience Manager</span>. This means the file name must use the <code><i>_DPID_TARGET_DATA_OWNER</i></code> parameter to hold your company ID. Par exemple, supposons que vous transfériez des fichiers avec des ID Android et que votre ID de fournisseur de données soit 21. In this case, the file name would look like <code>...ftp_dpm_20915_21_123456789.sync</code>. This tells <span class="keyword"> Audience Manager</span> the file contains iOS IDs and is from a partner identified by ID 21. </p> 
    <draft-comment> 
     <ul id="ul_818EB3EB2E5543F0B048BCEBB6699562"> 
      <li id="li_ED6B13CB49794F6BA3DB6D807F788BAF"> <b>ID du partenaire de données :</b> Il s'agit d'un identifiant unique attribué par Audience Manager à votre société ou organisation. Utilisez l'ID attribué dans un fichier - nom lors de l'envoi de données contenant votre propre utilisateur - id. For example, <code>...ftp_dpm_21_123456789.sync</code> tells <span class="keyword"> Audience Manager</span> that a partner with ID 21 sent the file and it contains user IDs assigned by that partner. </li> 
      <li id="li_1955911BA11F4F458227B77F383F25A3"> <b>Android ID (GAID) :</b> Utilisez l'ID 20914 dans un fichier de données - nom s'il contient un ID Android. For example, <code>...ftp_dpm_20914_21_123456789.sync</code> tells <span class="keyword"> Audience Manager</span> that the data file contains Android IDs only. Remarque : l'ID 21 </li> 
      <li id="li_54E7734C121646AF82095806DD1AED61"> <b>ID ios (IDFA) :</b> Utilisez l'ID 20915 dans un fichier de données - nom s'il contient des ID ios. For example, <code>...ftp_dpm_20915_123456789.sync</code> tells <span class="keyword"> Audience Manager</span> that the data file contains iOS IDs only. </li> 
     </ul> 
    </draft-comment> <p> <p>Remarque : Ne mélanger pas de types d'ID dans vos fichiers de données. Par exemple, si votre fichier comporte l'identifiant Android, ne placez pas d'ID ios ni vos propres ID dans le fichier de données. </p> </p> <p>See also the <code><i>_DPID_TARGET_DATA_OWNER</i></code> entry below. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>_ DPID_ TARGET_ DATA_ OWNER</i></code> </p> </td> 
   <td colname="col2"> <p>Balise d'emplacement pour un identifiant. For example, you could set it to your <span class="keyword"> Audience Manager</span> ID if you set the DPID to a data source ID or an Android or iOS ID. This lets <span class="keyword"> Audience Manager</span> link the file data back to your organization. </p> <p>Par exemple : </p> 
    <ul id="ul_55EBBCB11F2B4A858AEFBFA1CD99E286"> 
     <li id="li_3404428F4E3D49A5AB6EDF56310D923F"> <code>… ftp_ dpm_ 33_ 21_ 1234567890. sync</code> indique qu'un partenaire avec l'ID 21 a envoyé des données à partir d'une source de données utilisant l'ID 33. </li> 
     <li id="li_CF8D5AF678764E9984A088FD5D7BBFB6"> <code>… ftp_ dpm_ 20914_ 21_ 1234567890. sync</code> indique qu'un partenaire avec l'ID 21 a envoyé des données contenant des ID Android. </li> 
     <li id="li_3D73168391D7443BADDF27153090274D"> <code>… ftp_ dpm_ 20915_ 21_ 1234567890. sync</code> indique qu'un partenaire avec l'ID 21 a envoyé des données qui contiennent des ID ios. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>partner_ name</i></code> </p> </td> 
   <td colname="col2"> <p>The company or organization name you use in <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>TIMESTAMP</i></code> </p> </td> 
   <td colname="col2"> <p>Horodatage UTC UNIX de 10 chiffres, en secondes. L'horodatage permet de rendre chaque fichier unique. </p> 
    <draft-comment> 
     <p> <p>Remarque : Audience Manager n'utilise pas l'horodatage pendant le traitement des fichiers entrants. L'horodatage du nom de fichier est obsolète dans Audience Manager, mais il est toujours requis pour la compatibilité ascendante. </p> </p> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> (. sync |. overwrite)</code> </p> </td> 
   <td colname="col2"> <p>Options de synchronisation qui incluent : </p> <p> 
     <ul id="ul_DAAF61EC636C4456BECDDC34C3F86E83"> 
      <li id="li_6EC6DE442B4546AA9F4F800D65C8A4EC"> <code> synchronisation</code>: Scénario normal lorsque des fournisseurs de données tiers envoient des caractéristiques par utilisateur à ajouter ou à supprimer dans le système Audience Manager. </li> 
      <li id="li_8FE8430C2C004F87835D55231A0D99C9"> <code> overwrite</code>: Permet aux fournisseurs de données d'envoyer une liste de caractéristiques par utilisateur qui doit écraser toutes les caractéristiques tierces existantes de cet utilisateur pour ce fournisseur de données dans Audience Manager. Il n'est pas nécessaire d'inclure tous les utilisateurs dans un fichier de remplacement. Incluez uniquement les utilisateurs que vous souhaitez modifier. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>SPLIT_ NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>Entier. Utilisé lorsque vous fractionnez des fichiers volumineux en plusieurs parties afin d'améliorer les temps de traitement. Le nombre indique la partie du fichier d'origine dans lequel vous envoyez le fichier. </p> <p>Pour un traitement efficace des fichiers, divisez vos fichiers de données comme indiqué ci-dessous : </p> 
    <ul id="ul_E9446C5CA42649658093904D49D4369C"> 
     <li id="li_B275708DFE3F49E29EFAE6B838429E39">Décompressé : 1 Go </li> 
     <li id="li_A9638EB46ED14E0680B6575D5457E32F">Compressé : 200-300 Mo </li> 
    </ul> <p>See the first 2 <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md#file-name-examples"> file name examples</a> below. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>Lorsque vous envoyez des fichiers à Amazon S 3, utilisez uniquement la compression gzip. When compressed, these files get the <code> .gz</code> extension. N'utilisez pas la compression.zip. </p> <p>Les fichiers compressés doivent être de 3 Go ou plus. Si vos fichiers sont plus volumineux, contactez le service à la clientèle. Bien qu'Audience Manager puisse gérer des fichiers volumineux, nous pouvons vous aider à réduire la taille de vos fichiers et à améliorer l'efficacité des transferts de données. See <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md"> File Compression for Inbound Data Transfer Files</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## File Name Examples {#file-name-examples}

Les exemples suivants montrent les noms de fichier correctement formatés. Vos noms de fichier peuvent être similaires.

<ul class="simplelist"> 
 <li> <code> s 3 n:// &lt; AWS_ Bucket &gt;/&lt; nom_ partenaire &gt;/date = 2016-05-09/ftp_dpm_478_1366545717.sync.1.gz</code> </li> 
 <li> <code> s 3 n:// &lt; AWS_ Bucket &gt;/&lt; nom_ partenaire &gt;/date = 2016-05-09/ftp_dpm_478_1366545717.sync.2.gz</code> </li> 
 <li> <code> s 3 n:// &lt; AWS_ Bucket &gt;/&lt; nom_ partenaire &gt;/date = 2016-05-09/ftp_ dpm_ 478_ 1366545717. sync</code> </li> 
 <li> <code> s 3 n:// &lt; AWS_ Bucket &gt;/&lt; nom_ partenaire &gt;/date = 2016-05-09/ftp_dpm_478_567_1366545717.sync.gz</code> </li> 
 <li> <code> s 3 n:// &lt; AWS_ Bucket &gt;/&lt; nom_ partenaire &gt;/date = 2016-05-09/ftp_ dpm_ 478_ 1366545717. overwrite</code> </li> 
</ul>

You can [download](assets/ftp_dpm_1234_1445374061.overwrite) the sample file if you want additional examples. This file has been saved with the `.overwrite` file extension. Ouvrez-le avec un éditeur de texte simple.

## Accepted File Sizes {#accepted-file-sizes}

Consider the figures below for fastest/earliest processing of your files as well as for file size limitations when you send data to an [!DNL Audience Manager] / [!DNL Amazon S3] directory.

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
   <td colname="col2"> <p>200-300 Mo </p> </td> 
   <td colname="col3"> <p>3 Go </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Décompressé</b> </td> 
   <td colname="col2"> <p>1 Go </p> </td> 
   <td colname="col3"> <p>5 Go </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Le processus de validation des données entrantes marquera les fichiers vides comme non valides et ne les traitera pas.

>[!MORE_ LIKE_ THIS]
>
>* [Exigences en matière de nom FTP pour les fichiers de données entrants](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md)

