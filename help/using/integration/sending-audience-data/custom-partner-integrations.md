---
description: Cette page répertorie les intégrations personnalisées entre Audience Manager et les partenaires de données.
seo-description: This page lists custom integrations between Audience Manager and data partners.
seo-title: Custom Partner Integrations
solution: Audience Manager
title: Intégrations de partenaires personnalisées
feature: Third-party Integration
exl-id: 54af75a4-c05b-42fb-851c-5e242378d9f1
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 15%

---

# Intégrations de partenaires personnalisées {#custom-partner-integrations}

Cette page répertorie les intégrations personnalisées entre Audience Manager et les partenaires de données.

## Oracle Data Cloud {#oracle-data-cloud}

### Description

Audience Manager récupère les données de cookies et d’ID mobile à partir d’Oracle Data Cloud pour Audience Marketplace via des fichiers de données entrants. Les spécifications d’intégration personnalisée décrites ci-dessous se rapportent uniquement aux fichiers de données entrants qui contiennent des identifiants mobiles (IDFA et Android Device ID).

### Spécificités de l’intégration

Les fichiers de données entrants reçus d’Oracle Data Cloud diffèrent de la syntaxe de nom de fichier entrant standard décrite dans [Exigences de nom et de taille de fichier Amazon S3 pour les fichiers de données entrants](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) et de la syntaxe de contenu de fichier entrant standard décrite dans [Contenu de fichier de données entrants : syntaxe, caractères non valides, variables et exemples](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md).

Les éléments mis en surbrillance ci-dessous sont requis, en plus des champs d’implémentation standard pour les fichiers de données entrants. Pour la description de tous les autres champs standard et éléments de nom de fichier, voir Syntaxe du nom de fichier et Syntaxe du contenu du fichier dans les deux pages liées ci-dessus.

### Dénomination du fichier

Les noms de fichier ODC sont structurés comme suit :

`ftp_dpm_`**`odc`**`_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

L’élément de nom de fichier `odc` identifie le fichier comme étant importé à partir d’Oracle Data Cloud et indique au programme de validation de fichier entrant d’Audience Manager de le traiter en tant que tel.

### Contenu du fichier

Les champs du fichier de données entrant ODC doivent apparaître dans l’ordre indiqué ci-dessous :

`<`**`ID type`**`><TAB><user ID><TAB><trait ID>,<trait ID>,<trait ID>,...`

Le `ID type` peut être :

* IDFA
* Identifiant de l’appareil Android

>[!IMPORTANT]
>
>N’envoyez pas les ID d’appareil IDFA et Android dans le même fichier de données entrantes.

## Exemple de fichier ODC entrant

Téléchargez l’[exemple de fichier](/help/using/integration/assets/ftp_dpm_odc_12345_1556223815.sync). Ce fichier qualifie plusieurs IDFA pour l’ID de caractéristique 38838. Vous pouvez ouvrir ce fichier dans un éditeur de texte ou de code standard.
