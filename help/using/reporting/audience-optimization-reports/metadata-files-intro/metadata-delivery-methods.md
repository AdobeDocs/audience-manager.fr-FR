---
description: Envoyez ou mettez à jour des fichiers de métadonnées en les envoyant vers un répertoire Amazon S3 spécial pour votre compte Audience Manager. Reportez-vous à cette section pour plus d’informations sur les chemins de remise/répertoire, les délais de traitement des fichiers et les mises à jour.
seo-description: Envoyez ou mettez à jour des fichiers de métadonnées en les envoyant vers un répertoire Amazon S3 spécial pour votre compte Audience Manager. Reportez-vous à cette section pour plus d’informations sur les chemins de remise/répertoire, les délais de traitement des fichiers et les mises à jour.
seo-title: Méthodes de remise des fichiers de métadonnées
solution: Audience Manager
title: Méthodes de remise des fichiers de métadonnées
uuid: 5199ee9b-920d-423d-8070-05a017ecd562
translation-type: tm+mt
source-git-commit: de51f27cac0d165d043e90db978a6949d6a43761

---


# Méthodes de remise des fichiers de métadonnées{#delivery-methods-for-metadata-files}

Envoyez ou mettez à jour des fichiers de métadonnées en les envoyant dans un [!DNL Amazon S3] répertoire spécial pour votre compte Audience Manager. Reportez-vous à cette section pour plus d’informations sur les chemins de remise/répertoire, les délais de traitement des fichiers et les mises à jour.

## Syntaxe du chemin de livraison et exemple {#syntax}

Les données sont stockées dans un espace de noms distinct pour chaque client dans un [!DNL Amazon S3] répertoire. Le chemin d’accès au fichier suit la syntaxe illustrée ci-dessous. Notez que les crochets `<>` indiquent un espace réservé de variable. Les autres éléments sont des constantes et ne changent pas.

**Syntaxe :**

```
.../log_ingestion/pid=<AAM ID>/dpid=<d_src>/meta/<yyyymmdd_0_child ID>
```

**Exemple :**

```
.../log_ingestion/pid=1121/dpid=3342/meta/20200112_0_4
```

<br> 

Le tableau suivant définit chacun de ces éléments dans un chemin de remise de fichier.


| Paramètre de fichier | Description |
---------|----------|
| `.../log_ingestion/` | Il s’agit du début du chemin de stockage du répertoire. Vous recevrez le chemin complet lorsque tout sera configuré. |
| `pid=<AAM ID>` | Cette paire clé-valeur contient votre ID de client Audience Manager. |
| `dpid=<d_src>` | Cette paire clé-valeur contient l’ID de source de données transmis lors d’un appel d’événement. L’ID de source de données est la valeur qui lie tout le contenu de votre fichier aux données réelles auxquelles il appartient. </br> Supposons, par exemple, que vous ayez un élément créatif avec l’ID 123 et le nom &quot;Advertiser Creative A&quot;. Comme un appel d’événement ne transmet que l’identifiant dont vous avez besoin pour inclure &quot;Advertiser Creative A&quot; dans le fichier de métadonnées. La campagne et l’élément créatif appartiennent à une source de données. L’ID de source de données est ce qui relie ces éléments et nous permet d’associer précisément le contenu du fichier à un ID envoyé lors d’un appel d’événement. Voir [Comment les ID d’appel d’événement déterminent les noms de fichier, le contenu et les chemins](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md#how-ids-shape-filenames)de remise. |
| `<yyyymmdd_0_child ID>` | Il s’agit du nom de fichier. Voir Conventions [de dénomination des fichiers](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md)de métadonnées. |

## Heures et mises à jour de traitement des fichiers {#processing-times}

Les fichiers de métadonnées sont traités quatre fois par jour, à intervalles réguliers.

Pour mettre à jour vos enregistrements de métadonnées, envoyez simplement un fichier contenant de nouvelles informations. Vous n’avez pas besoin d’envoyer des mises à jour complètes à chaque fois.
