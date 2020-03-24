---
description: Cette page répertorie les intégrations personnalisées entre Audience Manager et les partenaires de données.
seo-description: Cette page répertorie les intégrations personnalisées entre Audience Manager et les partenaires de données.
seo-title: Intégrations personnalisées de partenaires
solution: Audience Manager
title: Intégrations personnalisées de partenaires
translation-type: tm+mt
source-git-commit: c069c901df6d8737f611d27ce7dffd4072e50adf

---


# Intégrations personnalisées de partenaires {#custom-partner-integrations}

Cette page répertorie les intégrations personnalisées entre Audience Manager et les partenaires de données.

## Oracle Data Cloud {#oracle-data-cloud}

### Description

Audience Manager récupère les données de cookies et d’ID mobile à partir d’Oracle Data Cloud pour Audience Marketplace via des fichiers de données entrants. Les spécifications d’intégration personnalisées décrites ci-dessous se rapportent uniquement aux fichiers de données entrants qui contiennent des ID mobiles (IDFA et Android Device ID).

### Caractéristiques de l’intégration

Les fichiers de données entrants reçus d’Oracle Data Cloud diffèrent de la syntaxe standard du nom de fichier entrant décrite dans [Amazon S3 Name et File Size Requirements for Inbound Data Files](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) et de la syntaxe standard du contenu du fichier entrant décrite dans la section Contenu du fichier de données [entrantes : Syntaxe, Caractères non valides, Variables et Exemples](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md).

Les éléments mis en évidence ci-dessous sont obligatoires, en plus des champs d’implémentation standard pour les fichiers de données entrants. Pour obtenir la description de tous les autres champs standard et éléments de nom de fichier, voir Syntaxe du nom de fichier et Syntaxe du contenu du fichier dans les deux pages liées ci-dessus.

### Nommage de fichier

Les noms de fichiers ODC sont structurés comme suit :

`ftp_dpm_`**`odc`**`_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

L’élément `odc` de nom de fichier identifie le fichier comme étant importé à partir d’Oracle Data Cloud et indique au programme de validation des fichiers entrants de   Manager de le traiter comme tel.

### Contenu du fichier

Les champs du fichier de données entrantes ODC doivent apparaître dans l’ordre indiqué ci-dessous :

`<`**`ID type`**`><TAB><user ID><TAB><trait ID>,<trait ID>,<trait ID>,...`

Vous `ID type` pouvez :

* IDFA
* ID de périphérique Android

>[!IMPORTANT]
>
>N’envoyez pas d’ID de périphérique IDFA et Android dans le même fichier de données entrant.

## Exemple de fichier entrant ODC

Téléchargez l’ [exemple de fichier](/help/using/integration/assets/ftp_dpm_odc_12345_1556223815.sync). Ce fichier qualifie plusieurs fichiers IDFA pour l’ID de caractéristique 38838. Vous pouvez ouvrir ce fichier dans un éditeur de texte ou un éditeur de code standard.