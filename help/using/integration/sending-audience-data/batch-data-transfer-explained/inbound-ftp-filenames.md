---
description: Décrit les champs obligatoires, la syntaxe, les conventions d’affectation des noms et les tailles de fichiers à respecter lors de l’envoi de données à l’Audience Manager. Définissez les noms et tailles de vos fichiers en fonction de ces spécifications lorsque vous envoyez des données vers un répertoire FTP d’Audience Manager.
seo-description: Décrit les champs obligatoires, la syntaxe, les conventions d’affectation des noms et les tailles de fichiers à respecter lors de l’envoi de données à l’Audience Manager. Définissez les noms et tailles de vos fichiers en fonction de ces spécifications lorsque vous envoyez des données vers un répertoire FTP d’Audience Manager.
seo-title: Exigences en matière de nom et de taille de fichier FTP pour les fichiers de données entrants
solution: Audience Manager
title: Exigences en matière de nom et de taille de fichier FTP pour les fichiers de données entrants
uuid: 49eaafac-5cb0-482f-872a-84c056016bdb
translation-type: tm+mt
source-git-commit: 9a8c0650d3f00a95a8a1f05c248c21b420e727e0
workflow-type: tm+mt
source-wordcount: '896'
ht-degree: 3%

---


# [!DNL FTP] Exigences en matière de nom et de taille de fichier pour les fichiers de données entrants {#ftp-name-and-file-size-requirements-for-inbound-data-files}

Décrit les champs obligatoires, la syntaxe, les conventions d’affectation de nom et les tailles de fichiers que vous devez respecter lors de l’envoi de données à [!DNL Audience Manager]. Définissez les noms et les tailles de vos fichiers en fonction de ces spécifications lorsque vous envoyez des données à un [!DNL FTP] répertoire d’Audiences Manager.

>[!WARNING]
>
>Nous supprimons progressivement la prise en charge des [!DNL FTP] configurations. Bien que l’assimilation de fichiers de données entrants soit toujours prise en charge dans les [!DNL FTP] intégrations existantes, nous vous recommandons vivement [!DNL Amazon S3] d’utiliser les données hors ligne intégrées pour les nouvelles intégrations. Pour plus d’informations, voir Exigences en matière de nom et de taille de fichier [Amazon S3 pour les fichiers](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) de données entrants.

>[!NOTE]
>
>Les styles de texte (`monospaced text`, *italiques*, crochets `[ ]` `( )`, etc.) dans ce document, indiquez les éléments de code et les options. Pour plus d’informations, voir les [conventions de style relatives aux éléments de code et de texte](../../../reference/code-style-elements.md).

## Syntaxe du nom de fichier {#file-name-syntax}

[!DNL FTP] les noms de fichier contiennent les éléments obligatoires et facultatifs suivants :

`ftp_dpm_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

Pour connaître les autres formats de nom de fichier acceptés, voir Intégrations [de partenaire](/help/using/integration/sending-audience-data/custom-partner-integrations.md)personnalisé.

>[!NOTE] {importance=&quot;high&quot;}
>
>[!DNL Audience Manager] uniquement les processus [!DNL ASCII] et les fichiers [!DNL UTF-8] codés.

### Nommer les éléments

Le tableau définit les éléments d’un nom de [!DNL FTP] fichier.

<table id="table_1EA97D75004148CE85F702427DB7E97A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elément Nom de fichier </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> ftp_dpm_</code> </p> </td> 
   <td colname="col2"> <p>Chemin d’accès et nom du répertoire FTP de votre <span class="keyword"> Audience Manager</span> . Contactez votre gestionnaire de compte pour connaître le répertoire FTP et les informations d’identification. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>DPID</i> </code> </p> </td> 
   <td colname="col2"> <p>Un identifiant qui indique à <span class="keyword"> l’Audience Manager</span> si un fichier de données contient vos propres ID d’utilisateur, Android ou iOS. Accepte les options suivantes : </p> 
    <ul id="ul_818EB3EB2E5543F0B048BCEBB6699562"> 
     <li id="li_ED6B13CB49794F6BA3DB6D807F788BAF"> <b>ID de partenaire de données :</b> Il s’agit d’une Audience Manager d’ID unique attribuée à votre société ou organisation. Utilisez cet ID affecté dans un nom de fichier lors de l’envoi de données contenant vos propres ID utilisateur. Par exemple, <code>...ftp_dpm_21_123456789.sync</code> indique à <span class="keyword"> l’Audience Manager</span> qu’un partenaire doté de l’ID 21 a envoyé le fichier et qu’il contient les ID utilisateur attribués par ce partenaire. </li> 
     <li id="li_1955911BA11F4F458227B77F383F25A3"> <b>Identifiants Android (GAID) :</b> Utilisez l’ID 20914 dans un nom de fichier de données s’il contient un ID Android. Par exemple, <code>...ftp_dpm_20914_123456789.sync</code> indique à <span class="keyword"> l’Audience Manager</span> que le fichier de données contient uniquement des ID Android. </li> 
     <li id="li_54E7734C121646AF82095806DD1AED61"> <b>ID iOS (IDFA) :</b> Utilisez l’ID 20915 dans un nom de fichier de données s’il contient des ID iOS. Par exemple, <code>...ftp_dpm_20915_123456789.sync</code> indique à <span class="keyword"> l’Audience Manager</span> que le fichier de données contient uniquement des ID iOS. </li> 
    </ul> <p> <p>Remarque :  Ne mélangez pas les types d’ID dans vos fichiers de données. Par exemple, si votre nom de fichier contient l’identifiant Android, n’insérez pas d’ID iOS ou vos propres ID dans le fichier de données. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>_DPID_TARGET_DATA_OWNER</i> </code> </p> </td> 
   <td colname="col2"> <p>Espace réservé pour un identifiant. Par exemple, vous pouvez définir l’ID d’ <span class="keyword"> Audience Manager</span> si vous définissez le DPID sur un ID de source de données ou un ID Android ou iOS. Cela permet à <span class="keyword"> l’Audience Manager</span> de lier les données de fichier à votre entreprise. </p> <p>Par exemple : </p> 
    <ul id="ul_55EBBCB11F2B4A858AEFBFA1CD99E286"> 
     <li id="li_3404428F4E3D49A5AB6EDF56310D923F"> <code>...ftp_dpm_33_21_1234567890.sync</code> La montre un partenaire avec l'ID 21 a envoyé des données d'une source de données qui utilise l'ID 33. </li> 
     <li id="li_CF8D5AF678764E9984A088FD5D7BBFB6"> <code>...ftp_dpm_20914_21_1234567890.sync</code> La montre un partenaire avec l'ID 21 a envoyé des données qui contiennent des ID Android. </li> 
     <li id="li_3D73168391D7443BADDF27153090274D"> <code>...ftp_dpm_20915_21_1234567890.sync</code> La montre un partenaire doté de l'ID 21 a envoyé des données contenant des ID iOS. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> (.sync |.overwrite)</code> </p> </td> 
   <td colname="col2"> <p>Options de synchronisation comprenant : </p> <p> 
     <ul id="ul_DAAF61EC636C4456BECDDC34C3F86E83"> 
      <li id="li_6EC6DE442B4546AA9F4F800D65C8A4EC"> <code> sync</code>: Scénario normal lorsque des fournisseurs de données tiers envoient des caractéristiques par utilisateur pour être ajoutées ou supprimées dans le système d’Audience Manager. </li> 
      <li id="li_8FE8430C2C004F87835D55231A0D99C9"> <code> overwrite</code>: Permet aux clients et aux fournisseurs de données d’envoyer une liste de caractéristiques par utilisateur qui doit remplacer toutes les caractéristiques existantes de cet utilisateur pour une source de données donnée en Audience Manager. Vous n’avez pas besoin d’inclure tous vos utilisateurs dans un fichier de remplacement. Incluez uniquement les utilisateurs que vous souhaitez modifier. Les caractéristiques qui ne sont pas attribuées à la source de données de cible ne seront pas effacées. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>SPLIT_NUMBER</i></code>] </p> </td> 
   <td colname="col2"> <p>Entier. Utilisé lorsque vous divisez des fichiers volumineux en plusieurs parties afin d’améliorer les temps de traitement. Le numéro indique la partie du fichier d'origine que vous envoyez. </p> <p>Pour un traitement efficace des fichiers, fractionnez vos fichiers de données comme indiqué : </p> 
    <ul id="ul_E9446C5CA42649658093904D49D4369C"> 
     <li id="li_B275708DFE3F49E29EFAE6B838429E39">Non compressé : 1 Go </li> 
     <li id="li_A9638EB46ED14E0680B6575D5457E32F">Comprimé : 200 à 300 Mo </li> 
    </ul> <p>Consultez les 2 premiers exemples <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md#file-name-examples"> de noms de</a> fichier ci-dessous. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>TIMESTAMP</i> </code> </p> </td> 
   <td colname="col2"> <p>Horodatage UTC UNIX à 10 chiffres en secondes. L’horodatage permet de rendre chaque nom de fichier unique. </p> 
    <draft-comment> 
     <p> <p>Remarque :  L’Audience Manager n’utilise pas l’horodatage lors du traitement des fichiers entrants. L’horodatage du nom de fichier a été abandonné en Audience Manager mais est toujours requis pour la compatibilité ascendante. </p> </p> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>Gzip est le format de compression autorisé pour un nom de fichier FTP. Si vous utilisez la compression de fichier, assurez-vous que le nom de fichier possède l’extension appropriée. </p> <p>Les fichiers compressés doivent être de 3 Go ou moins. Si vos fichiers sont plus volumineux, contactez le service d’assistance clientèle. Bien que l'Audience Manager puisse gérer des fichiers volumineux, nous pouvons vous aider à réduire la taille de vos fichiers et à rendre les transferts de données plus efficaces. Voir <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md"> Compression de fichiers pour les fichiers</a> de transfert de données entrants. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Exemples de noms de fichier {#file-name-examples}

Les exemples suivants montrent des noms de fichier correctement formatés. Vos noms de fichier peuvent ressembler.

<ul class="simplelist"> 
 <li> <code> ftp_dpm_478_1366545717.sync.1.gz</code> </li> 
 <li> <code> ftp_dpm_478_1366545717.sync.2.gz</code> </li> 
 <li> <code> ftp_dpm_478_1366545717.overwrite</code> </li> 
</ul>

[Téléchargez](assets/ftp_dpm_1234_1445374061.overwrite) le fichier d’exemple si vous avez besoin d’exemples supplémentaires. Ce fichier est enregistré avec l&#39;extension de `.overwrite` fichier. Ouvrez-le dans un éditeur de texte simple.

## Taille de fichier acceptée {#accepted-file-sizes}

Tenez compte des chiffres ci-dessous pour le traitement le plus rapide/le plus précoce de vos fichiers ainsi que pour les limitations de taille de fichier lorsque vous envoyez des données à un [!DNL Audience Manager] / [!DNL FTP] répertoire.

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

>[!MORELIKETHIS]
>
>* [Exigences en matière de nom Amazon S3 pour les fichiers de données entrants](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

