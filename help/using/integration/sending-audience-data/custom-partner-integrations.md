---
description: Cette page répertorie les intégrations personnalisées entre Audience Manager et les partenaires de données.
seo-description: Cette page répertorie les intégrations personnalisées entre Audience Manager et les partenaires de données.
seo-title: Intégrations de partenaires personnalisés
solution: Audience Manager
title: Intégrations de partenaires personnalisés
translation-type: tm+mt
source-git-commit: 3e7c993b1ddd2829e382de56ea246a667ff3ce0c

---


# Custom Partner Integrations {#custom-partner-integrations}

Cette page répertorie les intégrations personnalisées entre Audience Manager et les partenaires de données.

## Oracle Data Cloud {#oracle-data-cloud}

**Description**

Audience Manager récupère les données de cookies et d’ID mobile à partir d’Oracle Data Cloud pour Audience Marketplace via des fichiers de données entrants. Les spécifications d&#39;intégration personnalisées décrites ci-dessous font référence uniquement aux fichiers de données entrants qui contiennent des ID mobiles (ID IDFA et Android Device ID).

<br> 

**Particularités d&#39;intégration**

Inbound Data Files received from the Oracle Data Cloud differ from the standard inbound file name syntax described in [Amazon S3 Name and File Size Requirements for Inbound Data Files](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) and from the standard inbound file content syntax described in [Inbound Data File Contents: Syntax, Invalid Characters, Variables, and Examples](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md).

Les éléments présentés ci-dessous sont obligatoires, en plus des champs d&#39;implémentation standard des fichiers de données entrantes. Pour obtenir la description de tous les autres champs et fichiers standard - nom du nom, voir Fichier - Nom syntaxe et syntaxe du contenu du fichier dans les deux pages liées ci-dessus.

<br> 

**Nommage de fichier**

Les noms de fichiers ODC sont structurés comme suit :

<pre>ftp_dpm_<b>odc</b>_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]</pre>

The `odc` file name element identifies the file as being imported from the Oracle Data Cloud and instructs the Audience Manager inbound file validator to process it as such.

<br> 

**Contenu du fichier**

Les champs du fichier de données d&#39;entrée ODC doivent figurer dans l&#39;ordre indiqué ci-dessous :

<pre>&lt;<b>ID type</b>&gt;&lt;TAB&gt;&lt;user ID&gt;&lt;TAB&gt;&lt;trait ID&gt;,&lt;trait ID&gt;,&lt;trait ID&gt;,...</pre>

The `ID type` can be:

* IDFA
* ID de périphérique Android

>[!IMPORTANT]
>
>N&#39;envoyez pas d&#39;ID de périphérique IDFA et Android dans le même fichier de données entrantes.

<br> 

**Exemple de fichier inbound ODC**

Download the [sample file](/help/using/integration/assets/ftp_dpm_odc_12345_1556223815.sync). Ce fichier qualifie plusieurs IDFA pour l&#39;ID de caractéristique 38838. Vous pouvez ouvrir ce fichier dans un éditeur de texte ou un éditeur de code standard.