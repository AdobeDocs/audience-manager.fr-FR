---
description: Envoyez ou mettez à jour des fichiers de métadonnées en les envoyant dans un répertoire Amazon S3 spécial pour votre compte d’Audience Manager. Reportez-vous à cette section pour obtenir des informations sur les chemins d’accès aux diffusions/répertoires, les délais de traitement des fichiers et les mises à jour.
seo-description: Envoyez ou mettez à jour des fichiers de métadonnées en les envoyant dans un répertoire Amazon S3 spécial pour votre compte d’Audience Manager. Reportez-vous à cette section pour obtenir des informations sur les chemins d’accès aux diffusions/répertoires, les délais de traitement des fichiers et les mises à jour.
seo-title: Méthodes de distribution des fichiers de métadonnées
solution: Audience Manager
title: Méthodes de distribution des fichiers de métadonnées
uuid: 5199ee9b-920d-423d-8070-05a017ecd562
feature: log files
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 4%

---


# Méthodes de distribution des fichiers de métadonnées{#delivery-methods-for-metadata-files}

Envoyez ou mettez à jour des fichiers de métadonnées en les envoyant dans un [!DNL Amazon S3] répertoire spécial pour votre compte d’Audience Manager. Reportez-vous à cette section pour obtenir des informations sur les chemins d’accès aux diffusions/répertoires, les délais de traitement des fichiers et les mises à jour.

>[!IMPORTANT]
>
> Contactez votre conseiller en Audience Manager ou le service d’assistance clientèle pour commencer et configurer un [!DNL Amazon S3] répertoire pour vos fichiers de métadonnées.

## Syntaxe du chemin de Diffusion et exemple {#syntax}

Les données sont stockées dans un espace de nommage distinct pour chaque client dans un [!DNL Amazon S3] annuaire. Le chemin d’accès au fichier suit la syntaxe illustrée ci-dessous. Remarque : les crochets `<>` indiquent une balise d’emplacement de variable. Les autres éléments sont des constantes et ne changent pas.

**Syntaxe :**

```
.../log_ingestion/pid=<AAM ID>/dpid=<d_src>/meta/<yyyymmdd_0_child ID>
```

**Exemple:**

```
.../log_ingestion/pid=1121/dpid=3342/meta/20200112_0_4
```

<br> 

Le tableau suivant définit chacun de ces éléments dans un chemin de diffusion de fichiers.


| Paramètre de fichier | Description |
---------|----------|
| `.../log_ingestion/` | début du chemin d&#39;enregistrement de l&#39;annuaire. Vous recevrez le chemin complet lorsque tout sera configuré. |
| `pid=<AAM ID>` | Cette paire clé-valeur contient votre ID de client d’Audience Manager. |
| `dpid=<d_src>` | Cette paire clé-valeur contient l’identifiant de source de données transmis lors d’un appel de événement. L’ID de source de données est la valeur qui lie tout le contenu de votre fichier aux données réelles auxquelles il appartient. </br> Par exemple, supposons que vous disposez d’un élément créatif avec l’ID 123 et le nom &quot;Advertiser Creative A&quot;. Comme un appel de événement ne transmet que l’identifiant dont vous avez besoin pour inclure &quot;Advertiser Creative A&quot; dans le fichier de métadonnées. La campagne et le créatif appartiennent à une source de données. L’ID de source de données est ce qui relie ces éléments et nous permet d’associer précisément le contenu des fichiers à un identifiant envoyé lors d’un appel de événement. Voir [Comment les ID d’appel de Événement déterminent les noms de fichier, le contenu et les chemins](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md#how-ids-shape-file-names)de Diffusion. |
| `<yyyymmdd_0_child ID>` | Il s&#39;agit du nom de fichier. See [Naming Conventions for Metadata Files](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md). |

## Heures de traitement des fichiers et mises à jour {#processing-times}

Les fichiers de métadonnées sont traités quatre fois par jour, à intervalles réguliers.

Pour mettre à jour vos enregistrements de métadonnées, envoyez simplement un fichier contenant de nouvelles informations. Vous n’avez pas besoin d’envoyer des mises à jour complètes à chaque fois.
