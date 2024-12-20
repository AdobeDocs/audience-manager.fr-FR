---
description: Libellés d’en-tête de colonne définis.
seo-description: Column header labels defined.
seo-title: Bulk Management Tools Glossary
solution: Audience Manager
title: Glossaire des outils de gestion en bloc
uuid: 4658a6bc-9515-4d31-9715-0084760b0cea
feature: BAAAM
exl-id: 036d16c7-1546-4539-a318-455b98e10026
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 0%

---

# Glossaire des outils de gestion en bloc{#bulk-management-tools-glossary}

Libellés d’en-tête de colonne définis.

>[!IMPORTANT]
>
>Les outils de gestion en bloc ne sont pas une offre d’Adobe officiellement prise en charge. Le dépannage et l’assistance par l’intermédiaire de l’assistance clientèle seront gérés au cas par cas.

<!-- 

<p>r_bulk_glossary.xml </p>

 -->

>[!NOTE]
>
>[Les autorisations de groupe RBAC ](../../features/administration/administration-overview.md) attribuées dans l’interface utilisateur de [!DNL Audience Manager] sont honorées dans le [!UICONTROL Bulk Management Tools].

<table id="table_2C2BC2FB3EFC443C9A5AE18EFC6FABFD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> En-tête de colonne </th> 
   <th colname="col2" class="entry"> Définition </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> dataSourceId</span> </p> </td> 
   <td colname="col2"> <p>L’identifiant d’une source de données <a href="../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> </a> que vous souhaitez renvoyer ou attribuer en bloc. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> DEDSignalId</span> </p> </td> 
   <td colname="col2"> <p>Un identifiant <a href="../../features/derived-signals.md"> signal dérivé </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> description</span> </p> </td> 
   <td colname="col2"> <p>Description brève et instructive que vous pouvez donner à un objet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> destinationId</span> </p> </td> 
   <td colname="col2"> <p>L’identifiant de la destination <a href="../../features/destinations/destinations.md"></a> que vous souhaitez mapper ou supprimer. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> destinationMappingId</span> </p> </td> 
   <td colname="col2"> <p>Identifiant spécial attribué à un segment lorsqu’il est mappé à une destination. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> folderId</span> </p> </td> 
   <td colname="col2"> <p>L’identifiant de votre segment ou dossier de caractéristiques. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> name</span> </p> </td> 
   <td colname="col2"> <p>Nom de l’objet avec lequel vous travaillez. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> parentFolderId</span> </p> </td> 
   <td colname="col2"> <p>L’identifiant d’un segment ou d’un dossier de caractéristiques contenant d’autres dossiers. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> sid</span> </p> </td> 
   <td colname="col2"> <p>Identifiant du segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> sourceKey</span> </p> </td> 
   <td colname="col2"> <p>Les signaux sont des bits de données transmis à l’Audience Manager <span class="keyword"></span> en fonction de l’activité de l’utilisateur. Elles sont transmises en tant que <a href="../../reference/key-value-pairs-explained.md"> paires clé-valeur</a>. La clé source est une constante qui ne change pas. Cela permet de classer la valeur source qui peut changer. Voir <a href="../../features/derived-signals.md"> signaux dérivés</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> sourceValue</span> </p> </td> 
   <td colname="col2"> <p>La valeur source est une variable transmise dans le cadre d’une <a href="../../reference/key-value-pairs-explained.md"> paire clé-valeur</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> startDate</span> </p> </td> 
   <td colname="col2"> <p>Indique quand un segment peut commencer à être envoyé à une destination. Utilise le format <i>aaaa-mm-jj</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> targetKey</span> </p> </td> 
   <td colname="col2">Clé utilisée dans le signal dérivé. Voir <a href="../../features/derived-signals.md"> signaux dérivés</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> targetValue</span> </p> </td> 
   <td colname="col2"> <p>Valeur transmise avec une clé de signal dérivée. Voir <a href="../../features/derived-signals.md"> signaux dérivés</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> traitAlias</span> </p> </td> 
   <td colname="col2"> <p>Identifiant transmis à une destination autre que basée sur les cookies. Pour une destination basée sur des cookies, il s’agit de la clé d’une <a href="../../reference/key-value-pairs-explained.md"> paire clé-valeur</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> traitRule/segmentRule</span> </p> </td> 
   <td colname="col2"> <p>La caractéristique ou la règle de segment réelle utilisée pour collecter des données. Une requête en bloc renvoie les règles créées dans <span class="keyword"> Audience Manager</span> avec le <a href="../../features/traits/about-trait-builder.md"> créateur de règles de caractéristiques</a> ou le <a href="../../features/segments/segment-builder.md"> créateur de règles de segment</a>. Vous pouvez également utiliser ces outils pour créer des règles et les appliquer en bloc lorsque vous mettez à jour un segment ou une caractéristique. </p> <p>Voir aussi <a href="../../reference/bulk-management-tools/bulk-rules.md"> Création ou mise à jour de règles de caractéristiques et de segments</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> traitType</span> </p> </td> 
   <td colname="col2"> <p>Chaîne qui identifie le type de caractéristique. Les options incluent : </p> 
    <ul id="ul_AB5B4F87B14241DCBBE44B0B7BD4EF72"> 
     <li id="li_21F9412CDDC64FAA888C6542E284C436"> <code> RULE_BASED_TRAIT</code> </li> 
     <li id="li_5A5EA9A1EC5C45C991875EBBE7979A5A"> <code> ON_BOARDED_TRAIT </code> </li> 
     <li id="li_F38B58ADE3324E97A71E3F94F11945BE"> <code> SEGMENT</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> url</span> </p> </td> 
   <td colname="col2"> <p>Pixel déclenché par le DIL lorsqu’un utilisateur est admissible pour un segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> valueAlias</span> </p> </td> 
   <td colname="col2"> <p>La clé d’une <a href="../../reference/key-value-pairs-explained.md"> paire clé-valeur </a> transmise à une destination de cookie. </p> </td> 
  </tr> 
 </tbody> 
</table>
