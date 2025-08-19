---
description: Mettez en forme le contenu de votre fichier de métadonnées Audience Optimization en fonction de ces spécifications.
seo-description: Format the contents of your Audience Optimization metadata file according to these specifications.
seo-title: Content Format for Metadata Files
solution: Audience Manager
title: Format de contenu des fichiers de métadonnées
uuid: 9ba44738-3e17-40c7-9e8c-5abd8361e16d
feature: Log Files
exl-id: 1aed39f4-f893-4f25-b041-e198895e338a
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '299'
ht-degree: 1%

---

# Format de contenu des fichiers de métadonnées{#content-format-for-metadata-files}

Mettez en forme le contenu de votre fichier de métadonnées Audience Optimization en fonction de ces spécifications.

## Syntaxe {#syntax}

La syntaxe suivante définit la structure d’un contenu correctement formé dans un fichier de métadonnées. Notez que *l’italique* indique un espace réservé de variable.

**Syntaxe :** *Identifiant du contenu* | *name* | *-1*

<!--In the contents syntax, you'll notice a parent ID variable. Don't confuse it with the parent ID used in the [metadata file name](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md). These 2 variables seem similar, but they represent different things. In the file name, the parent ID corresponds to a category like "campaign" (ID 1), "placement" (ID 3), or "tactic" (ID 9), etc. In the file body:-->

La troisième colonne **-1** est techniquement l’identifiant parent, qui est un champ hérité. La valeur doit toujours être définie sur **-1**.

>[!NOTE]
>
>Notez qu’un fichier de métadonnées par dimension est nécessaire, de sorte que plusieurs fichiers de métadonnées sont attendus dans le compartiment. Les dimensions sont répertoriées dans l’article [Conventions de dénomination pour le fichier de métadonnées](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md#child-dimension).

**Entrées de fichier séparées par ^a (control-A ou ASCII 001)**

Utilisez `^a` (control-A ou ASCII 001) pour séparer le contenu de vos fichiers de métadonnées. Comme il s’agit de caractères non imprimables, l’exemple de syntaxe ci-dessus affiche une barre verticale « | » à des fins d’affichage uniquement.

Si nécessaire, vous pouvez télécharger le fichier d’exemple - [20181105_0_1](assets/20181105_0_1.zip). Décompressez-le, modifiez-le dans l’éditeur de votre choix et ajustez-le en fonction du contenu réel des métadonnées, car il contient déjà le délimiteur requis.

>[!IMPORTANT]
>
>N’ajoutez pas de lignes d’en-tête aux fichiers de métadonnées.

## Exemples {#examples}

Examinons comment structurer le contenu d’un fichier de métadonnées. Une partie de cette structure dépend de la dimension. Les dimensions sont répertoriées dans l’article [Conventions de dénomination pour le fichier de métadonnées](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md#child-dimension).

**Campaign**

Dans cet exemple, le titre du fichier est 20180921_0_1 et les trois colonnes du fichier sont les suivantes : Identifiant de la campagne, Nom et Identifiant parent.

<!--Let's say you want to populate the creative drop down menu with creative names from a particular campaign. In this case, your metadata file name would include ID 1 (campaign) and ID 2 (creative). Following the content syntax, your metadata file would contain the creative ID, creative name, and actual campaign ID.-->

```
//File Title
20180921_0_1

111 Campaign A -1
222 Campaign B -1
333 Campaign C -1
```

**Creative**

Dans cet exemple, le titre du fichier est 20180827_0_2 et les trois colonnes du fichier sont les suivantes : Creative ID, Name et Parent ID.

```
//File Title
20180921_0_2

111 Creative A -1
222 Creative B -1
333 Creative C -1
```

**Site**

Dans cet exemple, le titre du fichier est 20180921_0_5 et les trois colonnes du fichier sont : Identifiant du site, Nom et Identifiant parent.

```
//File Title
20180921_0_5

111 Site A -1
222 Site B -1
333 Site C -1
```
