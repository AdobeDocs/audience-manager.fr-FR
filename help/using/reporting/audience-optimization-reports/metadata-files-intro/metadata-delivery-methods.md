---
description: Envoyez ou mettez à jour des fichiers de métadonnées en les envoyant vers un répertoire spécifique Amazon S3 pour votre compte d’Audience Manager. Reportez-vous à cette section pour plus d’informations sur les chemins de diffusion/répertoire, les temps de traitement des fichiers et les mises à jour.
seo-description: Envoyez ou mettez à jour des fichiers de métadonnées en les envoyant vers un répertoire spécifique Amazon S3 pour votre compte d’Audience Manager. Reportez-vous à cette section pour plus d’informations sur les chemins de diffusion/répertoire, les temps de traitement des fichiers et les mises à jour.
seo-title: Méthodes de distribution des fichiers de métadonnées
solution: Audience Manager
title: Méthodes de distribution des fichiers de métadonnées
uuid: 5199ee9b-920d-423d-8070-05a017ecd562
feature: Fichiers journaux
exl-id: 6ef2a80c-2574-4446-b755-28027818b5eb
source-git-commit: 1fc17678ba632bfa17f7525c4fc4ff3b534acf94
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 4%

---

# Méthodes de distribution des fichiers de métadonnées{#delivery-methods-for-metadata-files}

Envoyez ou mettez à jour des fichiers de métadonnées en les envoyant dans un répertoire [!DNL Amazon S3] spécial pour votre compte d’Audience Manager. Reportez-vous à cette section pour plus d’informations sur les chemins de diffusion/répertoire, les temps de traitement des fichiers et les mises à jour.

>[!IMPORTANT]
>
> Contactez votre conseiller en Audience Manager ou l’assistance clientèle pour commencer à configurer un répertoire [!DNL Amazon S3] pour vos fichiers de métadonnées.

## Syntaxe du chemin de diffusion et exemple {#syntax}

Les données sont stockées dans un espace de noms distinct pour chaque client dans un répertoire [!DNL Amazon S3]. Le chemin d’accès au fichier suit la syntaxe illustrée ci-dessous. Notez que les crochets `<>` indiquent un espace réservé variable. Les autres éléments sont des constantes et ne changent pas.

**Syntaxe :**

```
.../log_ingestion/pid=<AAM ID>/dpid=<d_src>/meta/<yyyymmdd_0_child ID>
```

**Exemple:**

```
.../log_ingestion/pid=1121/dpid=3342/meta/20200112_0_4
```

<br> 

Le tableau suivant définit chacun de ces éléments dans un chemin de diffusion de fichier.


| Paramètre de fichier | Description |
|---------|----------|
| `.../log_ingestion/` | Il s’agit du début du chemin de stockage du répertoire. Vous recevrez le chemin complet lorsque tout sera configuré. |
| `pid=<AAM ID>` | Cette paire clé-valeur contient votre ID client d’Audience Manager. |
| `dpid=<d_src>` | Cette paire clé-valeur contient l’identifiant de source de données transmis lors d’un appel d’événement. L’identifiant de source de données est la valeur qui lie tout le contenu de votre fichier aux données réelles auxquelles il appartient. </br> Supposons, par exemple, que vous ayez un créatif avec l’ID 123 et le nom &quot;Créatif publicitaire A&quot;. Lorsqu’un appel d’événement transmet uniquement l’identifiant, vous devez inclure &quot;Advertiser Creative A&quot; dans le fichier de métadonnées. La campagne et le contenu créatif appartiennent à une source de données. L’identifiant de source de données est ce qui relie ces données et nous permet d’associer précisément le contenu du fichier à un identifiant envoyé lors d’un appel d’événement. Voir [Comment les ID d’appel d’événement déterminent les noms de fichier, le contenu et les chemins de diffusion](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md#how-ids-shape-file-names). |
| `<yyyymmdd_0_child ID>` | Il s’agit du nom du fichier. Voir [Conventions de dénomination des fichiers de métadonnées](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md). |

## Heures et mises à jour de traitement des fichiers {#processing-times}

Les fichiers de métadonnées sont traités quatre fois par jour, à intervalles réguliers.

Pour mettre à jour vos enregistrements de métadonnées, envoyez simplement un fichier contenant de nouvelles informations. Vous n’avez pas besoin d’envoyer des mises à jour complètes à chaque fois.
