---
description: Libellés des en-têtes de colonne définis.
seo-description: Libellés des en-têtes de colonne définis.
seo-title: Outils de gestion en masse Glossaire
solution: Audience Manager
title: Outils de gestion en masse Glossaire
uuid: 4658 a 6 bc -9515-4 d 31-9715-0084760 b 0 cea
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Bulk Management Tools Glossary{#bulk-management-tools-glossary}

Libellés des en-têtes de colonne définis.

<!-- 

<p>r_bulk_glossary.xml </p>

 -->

>[!NOTE]
>
>The [!UICONTROL Bulk Management Tools] *are not* supported by [!DNL Audience Manager]. Cet outil est fourni à titre de commodité uniquement. For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [Les permissions de groupe RBAC](../../features/administration/administration-overview.md) attribuées dans [!DNL Audience Manager] l&#39;interface utilisateur sont respectées dans l&#39; [!UICONTROL Bulk Management Tools]interface.

<table id="table_2C2BC2FB3EFC443C9A5AE18EFC6FABFD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> En-tête de colonne </th> 
   <th colname="col2" class="entry"> Définition </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Datasourceid</span> </p> </td> 
   <td colname="col2"> <p>The ID of a <a href="../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> data source</a> you want to return or assign in bulk. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Derivedsignalid</span> </p> </td> 
   <td colname="col2"> <p>A <a href="../../features/derived-signals.md"> derived signal</a> ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> description</span> </p> </td> 
   <td colname="col2"> <p>Brève description informative que vous pouvez donner à un objet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Destinationid</span> </p> </td> 
   <td colname="col2"> <p>The ID of the <a href="../../features/destinations/destinations.md"> destination</a> you want to map or delete. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Destinationmappingid</span> </p> </td> 
   <td colname="col2"> <p>Identifiant spécial affecté à un segment lorsqu'il est associé à une destination. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Folderid</span> </p> </td> 
   <td colname="col2"> <p>ID de votre dossier de segment ou de caractéristiques. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> name</span> </p> </td> 
   <td colname="col2"> <p>Nom de l'objet avec lequel vous travaillez. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Parentfolderid</span> </p> </td> 
   <td colname="col2"> <p>ID d'un dossier de segment ou de caractéristiques contenant d'autres dossiers. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> sid</span> </p> </td> 
   <td colname="col2"> <p>Identifiant du segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Sourcekey</span> </p> </td> 
   <td colname="col2"> <p>Signals are bits of data passed in to <span class="keyword"> Audience Manager</span> based on user activity. These are transmitted as <a href="../../reference/key-value-pairs-explained.md"> key-value pairs</a>. La clé source est une constante qui ne change pas. Cela permet de classer la valeur source qui peut changer. See <a href="../../features/derived-signals.md"> Derived Signals</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Sourcevalue</span> </p> </td> 
   <td colname="col2"> <p>The source value is a variable passed in as part a <a href="../../reference/key-value-pairs-explained.md"> key-value pair</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> startDate</span> </p> </td> 
   <td colname="col2"> <p>Indique quand un segment peut commencer à être envoyé vers une destination. Uses <tt>yyyy-mm-dd</tt> format. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Targetkey</span> </p> </td> 
   <td colname="col2">Clé utilisée dans le signal dérivé. See <a href="../../features/derived-signals.md"> Derived Signals</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Targetvalue</span> </p> </td> 
   <td colname="col2"> <p>Valeur transmise avec une clé de signal dérivée. See <a href="../../features/derived-signals.md"> Derived Signals</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Traitalias</span> </p> </td> 
   <td colname="col2"> <p>ID transmis à une destination basée sur un cookie. For a cookie-based destination, this is the key in a <a href="../../reference/key-value-pairs-explained.md"> key-value pair</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Traitrule/segmentrule</span> </p> </td> 
   <td colname="col2"> <p>Règle de caractéristique ou de segment réelle utilisée pour collecter des données. A bulk request returns the rules created in <span class="keyword"> Audience Manager</span> with the <a href="../../features/traits/about-trait-builder.md"> trait rule builder</a> or the <a href="../../features/segments/segment-builder.md"> segment rule builder</a>. Vous pouvez également utiliser ces outils pour créer des règles et les appliquer en bloc lorsque vous mettez à jour un segment ou une caractéristique. </p> <p>See also, <a href="../../reference/bulk-management-tools/bulk-rules.md"> Create or Update Trait Rules and Segment Rules</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Traittype</span> </p> </td> 
   <td colname="col2"> <p>Chaîne qui identifie le type de caractéristique. Les options incluent : </p> 
    <ul id="ul_AB5B4F87B14241DCBBE44B0B7BD4EF72"> 
     <li id="li_21F9412CDDC64FAA888C6542E284C436"> <code> RULE_ BASED_ TRAIT</code> </li> 
     <li id="li_5A5EA9A1EC5C45C991875EBBE7979A5A"> <code> ON_ BOARDED_ TRAIT </code> </li> 
     <li id="li_F38B58ADE3324E97A71E3F94F11945BE"> <code> SEGMENT</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> url</span> </p> </td> 
   <td colname="col2"> <p>Pixel déclenché par DIL lorsqu'un utilisateur est admissible pour un segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Valuealias</span> </p> </td> 
   <td colname="col2"> <p>The key in a <a href="../../reference/key-value-pairs-explained.md"> key-value pair</a> passed to a cookie destination. </p> </td> 
  </tr> 
 </tbody> 
</table>

