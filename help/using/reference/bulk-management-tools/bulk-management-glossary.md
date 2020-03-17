---
description: Libellés d’en-tête de colonne définis.
seo-description: Libellés d’en-tête de colonne définis.
seo-title: Glossaire des outils de gestion en bloc
solution: Audience Manager
title: Glossaire des outils de gestion en bloc
uuid: 4658a6bc-9515-4d31-9715-0084760b0cea
translation-type: tm+mt
source-git-commit: 8cc3d9d629536c48b7013ffede16c0b112704c89

---


# Glossaire des outils de gestion en bloc{#bulk-management-tools-glossary}

Libellés d’en-tête de colonne définis.

<!-- 

<p>r_bulk_glossary.xml </p>

 -->

>[!NOTE]
>
>[Les autorisations](../../features/administration/administration-overview.md) de groupe RBAC attribuées dans l’ [!DNL Audience Manager] interface utilisateur sont respectées dans le [!UICONTROL Bulk Management Tools].

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
   <td colname="col2"> <p>ID d’une source <a href="../../features/datasources-list-and-settings.md#data-sources-list-and-settings"></a> de données que vous souhaitez renvoyer ou affecter en bloc. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> secondarySignalId</span> </p> </td> 
   <td colname="col2"> <p>ID de signal <a href="../../features/derived-signals.md"></a> dérivé. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> description</span> </p> </td> 
   <td colname="col2"> <p>Description brève et instructive que vous pouvez donner à un objet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> destinationId</span> </p> </td> 
   <td colname="col2"> <p>ID de la destination <a href="../../features/destinations/destinations.md"></a> à mapper ou à supprimer. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> destinationMappingId</span> </p> </td> 
   <td colname="col2"> <p>ID spécial affecté à un segment lorsqu’il est mappé à une destination. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> folderId</span> </p> </td> 
   <td colname="col2"> <p>ID de votre segment ou dossier de caractéristiques. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> name</span> </p> </td> 
   <td colname="col2"> <p>Nom de l’objet avec lequel vous travaillez. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> parentFolderId</span> </p> </td> 
   <td colname="col2"> <p>ID d’un segment ou d’un dossier de caractéristiques contenant d’autres dossiers. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> sid</span> </p> </td> 
   <td colname="col2"> <p>ID de segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> sourceKey</span> </p> </td> 
   <td colname="col2"> <p>Les signaux sont des bits de données transmis à <span class="keyword"> Gestionnaire de</span> en fonction des de l’utilisateur. Elles sont transmises sous forme de paires <a href="../../reference/key-value-pairs-explained.md"> clé-valeur</a>. La clé source est une constante qui ne change pas. Cela permet de classer la valeur source qui peut changer. Voir Signaux <a href="../../features/derived-signals.md"></a>dérivés. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> sourceValue</span> </p> </td> 
   <td colname="col2"> <p>La valeur source est une variable transmise dans le cadre d’une paire <a href="../../reference/key-value-pairs-explained.md"></a>clé-valeur. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> startDate</span> </p> </td> 
   <td colname="col2"> <p>Indique à quel moment un segment peut  être envoyé vers une destination. Utilise le format <tt>aaaa-mm-jj</tt> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> targetKey</span> </p> </td> 
   <td colname="col2">Clé utilisée dans le signal dérivé. Voir Signaux <a href="../../features/derived-signals.md"></a>dérivés. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> targetValue</span> </p> </td> 
   <td colname="col2"> <p>Valeur transmise avec une clé de signal dérivée. Voir Signaux <a href="../../features/derived-signals.md"></a>dérivés. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> traitAlias</span> </p> </td> 
   <td colname="col2"> <p>ID transmis à une destination sans cookie. Pour une destination basée sur un cookie, il s’agit de la clé d’une paire <a href="../../reference/key-value-pairs-explained.md"></a>clé-valeur. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> traitRule/segmentRule</span> </p> </td> 
   <td colname="col2"> <p>Caractéristique ou règle de segment réelle utilisée pour collecter des données. Une requête en bloc renvoie les règles créées dans  Gestionnaire <span class="keyword"> de</span> de <a href="../../features/traits/about-trait-builder.md"> avec le créateur</a> de règles de <a href="../../features/segments/segment-builder.md"> caractéristiques ou le créateur</a>de règles de segments. Vous pouvez également utiliser ces outils pour créer des règles et les appliquer en bloc lorsque vous mettez à jour un segment ou une caractéristique. </p> <p>Voir aussi <a href="../../reference/bulk-management-tools/bulk-rules.md"> Créer ou mettre à jour des règles de caractéristiques et des règles</a>de segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> traitType</span> </p> </td> 
   <td colname="col2"> <p>Chaîne identifiant le type de caractéristique. Les options incluent : </p> 
    <ul id="ul_AB5B4F87B14241DCBBE44B0B7BD4EF72"> 
     <li id="li_21F9412CDDC64FAA888C6542E284C436"> <code> RULE_BASED_TRAIT</code> </li> 
     <li id="li_5A5EA9A1EC5C45C991875EBBE7979A5A"> <code> ON_BOARDED_TRAIT </code> </li> 
     <li id="li_F38B58ADE3324E97A71E3F94F11945BE"> <code> SEGMENT</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> url</span> </p> </td> 
   <td colname="col2"> <p>Pixel déclenché par DIL lorsqu’un utilisateur est admissible pour un segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> valueAlias</span> </p> </td> 
   <td colname="col2"> <p>Clé d’une paire <a href="../../reference/key-value-pairs-explained.md"></a> clé-valeur transmise à une destination de cookie. </p> </td> 
  </tr> 
 </tbody> 
</table>

