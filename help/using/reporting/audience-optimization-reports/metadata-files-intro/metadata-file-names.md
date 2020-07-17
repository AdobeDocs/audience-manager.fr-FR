---
description: Nommez votre fichier de métadonnées Optimisation des Audiences en fonction de ces spécifications.
seo-description: Nommez votre fichier de métadonnées Optimisation des Audiences en fonction de ces spécifications.
seo-title: Conventions de dénomination des fichiers de métadonnées
solution: Audience Manager
title: Conventions de dénomination des fichiers de métadonnées
uuid: cab55b2a-2e54-45f6-aeea-3735b911f821
feature: log files
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 10%

---


# Conventions de dénomination des fichiers de métadonnées{#naming-conventions-for-metadata-files}

Nommez votre fichier de métadonnées Optimisation des Audiences en fonction de ces spécifications.

## Catégories de syntaxe et d’ID {#syntax}

La syntaxe suivante définit la structure d’un nom de fichier de métadonnées bien formé. Note, *italics* indicates a variable placeholder. Les autres éléments sont des constantes et ne changent pas.

**Syntaxe :***`yyyymmdd_0_childID`*

>[!NOTE]
>
>*N’utilisez pas* d’extensions de fichier dans vos fichiers de métadonnées (.txt ou autre).

<!--In the name syntax, you'll notice a parent ID variable. Don't confuse it with the parent ID used in the [metadata file contents](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-contents.md). These 2 variables seem similar, but they represent different things:-->

* Le composant intermédiaire **0** est techniquement l’identifiant parent, qui est un champ hérité. La valeur doit toujours être définie sur **0**.
* L’ID enfant peut avoir une valeur comprise entre 1 et 10, selon la dimension. Reportez-vous à l’exemple ci-dessous :

## Dimensions d’ID enfant {#child-dimension}

Dans le nom du fichier de métadonnées, l’ID enfant est un identifiant qui classe le type de données dans un fichier et le place dans une hiérarchie. Vous pouvez baliser l’ID enfant dans le nom de fichier avec les ID de catégorie suivants :

1. Campagne
1. Créatif
1. Emplacement
1. Exchange
1. Site
1. Advertiser (en cas d’utilisation de codes d’intégration dans une source [de](../../../features/manage-datasources.md#details)données)
1. Ordre d’insertion (E/S)
1. Vertical (c.-à-d. une catégorie industrielle ou commerciale spécifique telle que &quot;ordinateurs&quot;, &quot;automobiles&quot;, &quot;immobilier&quot;, etc.)
1. Tactique
1. Unité commerciale ou marque

## Exemple {#example}

Pour un fichier de métadonnées créatives, le nom de fichier peut être 20190115_0_2.

<!--Let's take a look at how you would use these IDs in a metadata file name. As an example, say your data file consists of campaign creatives. In this case, the campaign is a parent object and the creatives are child objects because they belong to, or are contained by, the campaign. As a result, you'd choose the following IDs for the metadata file name:

* Parent ID: `1` 
* Child ID: `2`

Your metadata file name would look like this: `20150827_1_2`

Sometimes, you might have data that does not belong to a parent object. Whenever this is the case, select ID 0 for the parent ID. In this case, your file title would look like this: `20150827_0_2`. -->
