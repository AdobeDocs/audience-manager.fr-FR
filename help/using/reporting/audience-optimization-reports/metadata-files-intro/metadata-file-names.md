---
description: Nommez votre fichier de métadonnées d'optimisation d'audience selon ces spécifications.
seo-description: Nommez votre fichier de métadonnées d'optimisation d'audience selon ces spécifications.
seo-title: Conventions d'attribution de noms aux fichiers de métadonnées
solution: Audience Manager
title: Conventions d'attribution de noms aux fichiers de métadonnées
uuid: cab 55 b 2 a -2 e 54-45 f 6-aeea -3735 b 911 f 821
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Naming Conventions for Metadata Files{#naming-conventions-for-metadata-files}

Nommez votre fichier de métadonnées d'optimisation d'audience selon ces spécifications.

## Syntax and ID Categories {#syntax}

La syntaxe suivante définit la structure d'un fichier de métadonnées bien formaté : name. Note, *italics* indicates a variable placeholder. Les autres éléments sont des constantes et ne changent pas.

**Syntaxe :***`yyyymmdd_0_childID`*

>[!NOTE]
>
>*N* 'utilisez pas d'extensions de fichier dans vos fichiers de métadonnées (.txt ou autre).

<!--In the name syntax, you'll notice a parent ID variable. Don't confuse it with the parent ID used in the [metadata file contents](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-contents.md). These 2 variables seem similar, but they represent different things:-->

* The middle component **0** is technically the Parent ID, which is a legacy field. The value should always be set as **0**.
* L'ID enfant peut avoir une valeur comprise entre 1 et 10, selon la dimension. Reportez-vous à l’exemple ci-dessous :

## Child ID dimensions {#child-dimension}

Dans le fichier de métadonnées - nom, l'ID enfant est un identifiant qui classe le type de données dans un fichier et le place dans une hiérarchie. Vous pouvez baliser l'ID enfant dans le fichier - nom avec les identifiants de catégorie suivants :

1. Campagne
1. Création
1. Emplacement
1. Exchange
1. Site
1. Advertiser (if using integration codes in a [data source](../../../features/manage-datasources.md#details))
1. Ordre d'insertion (IO)
1. Vertical (c'est-à-dire une catégorie de secteur industriel ou d'entreprise spécifique telle que « ordinateurs », « automobiles », « espace », etc.)
1. Tactique
1. Unité opérationnelle ou marque

## Exemple {#example}

Pour un fichier de métadonnées Creative, le fichier - nom peut être 20190115_ 0_ 2.

<!--Let's take a look at how you would use these IDs in a metadata file name. As an example, say your data file consists of campaign creatives. In this case, the campaign is a parent object and the creatives are child objects because they belong to, or are contained by, the campaign. As a result, you'd choose the following IDs for the metadata file name:

* Parent ID: `1` 
* Child ID: `2`

Your metadata file name would look like this: `20150827_1_2`

Sometimes, you might have data that does not belong to a parent object. Whenever this is the case, select ID 0 for the parent ID. In this case, your file title would look like this: `20150827_0_2`. -->
