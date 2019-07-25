---
description: Mettez en forme le contenu du fichier de métadonnées d'optimisation d'audience conformément à ces spécifications.
seo-description: Mettez en forme le contenu du fichier de métadonnées d'optimisation d'audience conformément à ces spécifications.
seo-title: Format de contenu des fichiers de métadonnées
solution: Audience Manager
title: Format de contenu des fichiers de métadonnées
uuid: 9 ba 44738-3 e 17-40 c 7-9 e 8 c -5 abd 8361 e 16 d
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Content Format for Metadata Files{#content-format-for-metadata-files}

Mettez en forme le contenu du fichier de métadonnées d'optimisation d'audience conformément à ces spécifications.

## du lien personnalisé{#syntax}

La syntaxe suivante définit la structure des contenus bien formés dans un fichier de métadonnées. Note, *italics* indicates a variable placeholder.

**Syntaxe :***ID de contenu* | *name* | *-1*

<!--In the contents syntax, you'll notice a parent ID variable. Don't confuse it with the parent ID used in the [metadata file name](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md). These 2 variables seem similar, but they represent different things. In the file name, the parent ID corresponds to a category like "campaign" (ID 1), "placement" (ID 3), or "tactic" (ID 9), etc. In the file body:-->

The third column **-1** is technically the Parent ID, which is a legacy field. The value should always be set as **-1**.

>[!NOTE]
>
>Notez qu'un fichier de métadonnées par dimension est nécessaire. De ce fait, plusieurs fichiers de métadonnées sont attendus dans le compartiment. The dimensions are listed in the article [Naming Conventions for Metadata File](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md#child-dimension).

**Entrées de fichier distinctes avec ^ a (contrôle-A ou ASCII 001)**

Use `^a` (control-A or ASCII 001) to separate content in your metadata files. Comme il s'agit de caractères non imprimables, l'exemple de syntaxe ci-dessus montre une barre verticale « |à des fins d'affichage uniquement.

If needed, you may download the example file - [20181105_0_1](assets/20181105_0_1.zip). Décompressez-la et modifiez-la dans votre éditeur de choix et ajustez-la en fonction du contenu réel des métadonnées, car elle contient déjà le délimiteur requis.

>[!IMPORTANT]
>
>N'ajoutez pas de rangées d'en-tête aux fichiers de métadonnées.

## Exemples {#examples}

Examinons la structure du contenu dans un fichier de métadonnées. Une partie de cette structure dépend de la dimension. The dimensions are listed in the article [Naming Conventions for Metadata File](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md#child-dimension).

**Campaign**

Dans cet exemple, le titre du fichier est 20180921_ 0_ 1 et les trois colonnes du fichier : ID de campagne, nom et ID parent.

<!--Let's say you want to populate the creative drop down menu with creative names from a particular campaign. In this case, your metadata file name would include ID 1 (campaign) and ID 2 (creative). Following the content syntax, your metadata file would contain the creative ID, creative name, and actual campaign ID.-->

```
//File Title
20180921_0_1

111 Campaign A -1
222 Campaign B -1
333 Campaign C -1
```

**Création**

Dans cet exemple, le titre du fichier est 20180827_ 0_ 2 et les trois colonnes du fichier : ID de création, nom et ID parent.

```
//File Title
20180921_0_2

111 Creative A -1
222 Creative B -1
333 Creative C -1
```

**Site**

Dans cet exemple, le titre du fichier est 20180921_ 0_ 5 et les trois colonnes du fichier : ID du site, nom et ID parent.

```
//File Title
20180921_0_5

111 Site A -1
222 Site B -1
333 Site C -1
```
