---
description: Cette page répertorie les intégrations personnalisées entre Audience Manager et les partenaires de données.
seo-description: Cette page répertorie les intégrations personnalisées entre Audience Manager et les partenaires de données.
seo-title: Intégrations personnalisées des partenaires
solution: Audience Manager
title: Intégrations personnalisées des partenaires
feature: Third-party Integration
exl-id: 54af75a4-c05b-42fb-851c-5e242378d9f1
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 22%

---

# Intégrations personnalisées des partenaires {#custom-partner-integrations}

Cette page répertorie les intégrations personnalisées entre Audience Manager et les partenaires de données.

## Cloud de données d’Oracle {#oracle-data-cloud}

### Description

Audience Manager récupère les données de cookies et d’ID mobile à partir d’Oracle Data Cloud pour Audience Marketplace via des fichiers de données entrants. Les spécifications d’intégration personnalisées décrites ci-dessous se rapportent uniquement aux fichiers de données entrants qui contiennent des ID de dispositifs portables (IDFA et Android Device ID).

### Caractéristiques de l’intégration

Les fichiers de données entrantes reçus de l&#39;Oracle Data Cloud diffèrent de la syntaxe de nom de fichier entrant standard décrite dans [Amazon S3 Name and File Size Requirements for Inbound Data Files](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) et de la syntaxe de contenu de fichier entrant standard décrite dans [Contenu du fichier de données entrantes : Syntaxe, Caractères non valides, Variables et Exemples](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md).

Les éléments mis en évidence ci-dessous sont requis, en plus des champs de mise en oeuvre standard pour les fichiers de données entrants. Pour obtenir la description de tous les autres champs standard et éléments de nom de fichier, voir Syntaxe du nom de fichier et Syntaxe du contenu du fichier dans les deux pages liées ci-dessus.

### Nommage de fichier

Les noms de fichiers ODC sont structurés comme suit :

`ftp_dpm_`**`odc`**`_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

L’élément de nom de fichier `odc` identifie le fichier comme étant importé à partir de l’Oracle Data Cloud et demande au programme de validation des fichiers entrants d’Audience Manager de le traiter comme tel.

### Contenu du fichier

Les champs du fichier de données entrantes ODC doivent apparaître dans l’ordre indiqué ci-dessous :

`<`**`ID type`**`><TAB><user ID><TAB><trait ID>,<trait ID>,<trait ID>,...`

`ID type` peut être :

* IDFA
* ID de périphérique Android

>[!IMPORTANT]
>
>N’envoyez pas d’ID d’appareil IDFA et Android dans le même fichier de données entrant.

## Exemple de fichier d&#39;entrée ODC

Téléchargez l&#39;[exemple de fichier](/help/using/integration/assets/ftp_dpm_odc_12345_1556223815.sync). Ce fichier qualifie plusieurs IDFA pour l’ID de caractéristique 38838. Vous pouvez ouvrir ce fichier dans un éditeur de texte ou un éditeur de code standard.
