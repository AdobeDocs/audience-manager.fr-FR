---
description: Cette page répertorie les intégrations personnalisées entre Audience Manager et les partenaires de données.
seo-description: This page lists custom integrations between Audience Manager and data partners.
seo-title: Custom Partner Integrations
solution: Audience Manager
title: Intégrations personnalisées des partenaires
feature: Third-party Integration
exl-id: 54af75a4-c05b-42fb-851c-5e242378d9f1
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 15%

---

# Intégrations personnalisées des partenaires {#custom-partner-integrations}

Cette page répertorie les intégrations personnalisées entre Audience Manager et les partenaires de données.

## Oracle Data Cloud {#oracle-data-cloud}

### Description

Audience Manager récupère les données de cookies et d’ID mobile à partir d’Oracle Data Cloud pour Audience Marketplace via des fichiers de données entrants. Les spécifications d’intégration personnalisées décrites ci-dessous se rapportent uniquement aux fichiers de données entrants qui contiennent des identifiants mobiles (IDFA et Android Device ID).

### Spécificités de l’intégration

Les fichiers de données entrants reçus de l’Oracle Data Cloud diffèrent de la syntaxe standard du nom de fichier entrant décrite dans [Exigences en matière de nom et de taille de fichier Amazon S3 pour les fichiers de données entrants](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) et de la syntaxe standard du contenu du fichier entrant décrite dans [Contenu du fichier de données entrant : syntaxe, caractères non valides, variables et exemples](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md).

Les éléments présentés ci-dessous sont requis, en plus des champs de mise en oeuvre standard pour les fichiers de données entrants. Pour obtenir une description de tous les autres champs standard et éléments de nom de fichier, voir Syntaxe du nom de fichier et Syntaxe du contenu du fichier dans les deux pages liées ci-dessus.

### Dénomination de fichier

Les noms de fichiers ODC sont structurés comme suit :

`ftp_dpm_`**`odc`**`_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

L’élément de nom de fichier `odc` identifie le fichier comme étant importé à partir du cloud de données d’Oracle et indique au programme de validation des fichiers entrants d’Audience Manager de le traiter comme tel.

### Contenu du fichier

Les champs du fichier de données entrant ODC doivent apparaître dans l’ordre indiqué ci-dessous :

`<`**`ID type`**`><TAB><user ID><TAB><trait ID>,<trait ID>,<trait ID>,...`

`ID type` peut être :

* IDFA
* Identifiant de périphérique Android

>[!IMPORTANT]
>
>N’envoyez pas d’identifiants d’appareil IDFA et Android dans le même fichier de données entrant.

## Exemple de fichier entrant ODC

Téléchargez le [fichier d&#39;exemple](/help/using/integration/assets/ftp_dpm_odc_12345_1556223815.sync). Ce fichier qualifie plusieurs IDFA pour le trait ID 38838. Vous pouvez ouvrir ce fichier dans un éditeur de texte ou un éditeur de code standard.
