---
description: Envoyez ou mettez à jour des fichiers de métadonnées en les envoyant à un répertoire Amazon S3 spécial pour votre compte Audience Manager. Reportez-vous à cette section pour plus d’informations sur les chemins de diffusion/répertoire, les temps de traitement des fichiers et les mises à jour.
seo-description: Send or update metadata files by sending them to a special Amazon S3 directory for your Audience Manager account. Refer to this section for information about delivery/directory paths, file processing times, and updates.
seo-title: Delivery Methods for Metadata Files
solution: Audience Manager
title: Méthodes de diffusion des fichiers de métadonnées
uuid: 5199ee9b-920d-423d-8070-05a017ecd562
feature: Log Files
exl-id: 6ef2a80c-2574-4446-b755-28027818b5eb
source-git-commit: 1fc17678ba632bfa17f7525c4fc4ff3b534acf94
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 0%

---

# Méthodes de diffusion des fichiers de métadonnées{#delivery-methods-for-metadata-files}

Envoyez ou mettez à jour des fichiers de métadonnées en les envoyant à un répertoire [!DNL Amazon S3] spécial pour votre compte Audience Manager. Reportez-vous à cette section pour plus d’informations sur les chemins de diffusion/répertoire, les temps de traitement des fichiers et les mises à jour.

>[!IMPORTANT]
>
> Contactez votre consultant Audience Manager ou l’assistance clientèle pour commencer à configurer un répertoire [!DNL Amazon S3] pour vos fichiers de métadonnées.

## Syntaxe et exemple du chemin de diffusion {#syntax}

Les données sont stockées dans un espace de noms distinct pour chaque client dans un répertoire [!DNL Amazon S3]. Le chemin d’accès au fichier suit la syntaxe affichée ci-dessous. Notez que les crochets inclinés `<>` indiquer un espace réservé variable. Les autres éléments sont des constantes et ne changent pas.

**Syntaxe :**

```
.../log_ingestion/pid=<AAM ID>/dpid=<d_src>/meta/<yyyymmdd_0_child ID>
```

**Exemple :**

```
.../log_ingestion/pid=1121/dpid=3342/meta/20200112_0_4
```

<br> 

Le tableau suivant définit chacun de ces éléments dans un chemin de diffusion de fichier.


| Paramètre de fichier | Description |
|---------|----------|
| `.../log_ingestion/` | Il s’agit du début du chemin de stockage du répertoire. Vous recevrez le chemin d’accès complet une fois que tout sera configuré. |
| `pid=<AAM ID>` | Cette paire clé-valeur contient votre ID client Audience Manager. |
| `dpid=<d_src>` | Cette paire clé-valeur contient l’identifiant de source de données transmis lors d’un appel d’événement. L’identifiant de la source de données est la valeur qui lie tout le contenu de votre fichier aux données réelles auxquelles il appartient. </br> Supposons, par exemple, que vous ayez un contenu publicitaire avec l’ID 123 et le nom « Advertiser Creative A ». Lorsqu’un appel d’événement transmet uniquement l’ID, vous devez inclure « Advertiser Creative A » dans le fichier de métadonnées. La campagne et le contenu créatif appartiennent à une source de données. L’identifiant de source de données est ce qui les relie et nous permet d’associer précisément le contenu du fichier à un identifiant envoyé lors d’un appel d’événement. Consultez la section [&#x200B; Comment les identifiants d’appel d’événement déterminent les noms de fichiers, le contenu et les chemins de diffusion](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md#how-ids-shape-file-names). |
| `<yyyymmdd_0_child ID>` | Il s’agit du nom du fichier. Voir [&#x200B; Conventions de dénomination pour les fichiers de métadonnées](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md). |

## Temps de traitement des fichiers et mises à jour {#processing-times}

Les fichiers de métadonnées sont traités quatre fois par jour, à intervalles réguliers.

Pour mettre à jour vos enregistrements de métadonnées, envoyez simplement un fichier contenant de nouvelles informations. Vous n’avez pas besoin d’envoyer de mises à jour complètes à chaque fois.
