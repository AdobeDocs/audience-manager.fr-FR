---
description: Ici à l'Audience Manager, nous sommes des ingénieurs, des développeurs, et des ninjas de code comme vous. Et, comme vous, nous voulons travailler avec une documentation API fiable et précise. Par conséquent, nous réécrivons le contenu de notre API dans Swagger et nous le déplaçons vers un nouvel emplacement. Ces modifications sont conçues pour vous aider à améliorer votre expérience avec le code de l’API d’Audience Manager.
seo-description: Ici à l'Audience Manager, nous sommes des ingénieurs, des développeurs, et des ninjas de code comme vous. Et, comme vous, nous voulons travailler avec une documentation API fiable et précise. Par conséquent, nous réécrivons le contenu de notre API dans Swagger et nous le déplaçons vers un nouvel emplacement. Ces modifications sont conçues pour vous aider à améliorer votre expérience avec le code de l’API d’Audience Manager.
seo-title: Migration du code de l’API Audience Manager
solution: Audience Manager
title: Migration du code de l’API Audience Manager
uuid: 93cc28c4-4b91-4c79-93d5-ece9bb4cc9d5
feature: API
exl-id: 081be8a7-5029-45b1-8fb1-0531d5090fe0
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 6%

---

# Migration du code de l’API Audience Manager {#audience-manager-api-code-migration}

Ici à l&#39;Audience Manager, nous sommes des ingénieurs, des développeurs, et des ninjas de code comme vous. Et, comme vous, nous voulons travailler avec une documentation [!DNL API] fiable et précise. Par conséquent, nous réécrivons notre contenu [!DNL API] dans [!DNL Swagger] et nous le déplaçons vers un nouvel emplacement. Ces modifications ont pour but d’améliorer votre expérience avec le code d’Audience Manager [!DNL API].

## Déplacer vers le haut {#code-migration-details}

<!-- api-swagger-migration.xml -->

Le site [Documents de l’API Adobe Audience Manager](https://bank.demdex.com/portal/swagger/index.html) est le nouveau site d’accueil de notre contenu [!DNL API] révisé. Nous allons essayer de réécrire et de déplacer quelques ensembles de méthodes [!DNL API] avec chaque version. Cela signifie que vous devrez archiver le nouvel emplacement et la documentation [API REST](../api/rest-api-main/rest-api-main.md) pour trouver toutes les méthodes disponibles. Finalement, toutes les [!DNL API]s publiques seront sur le site [!DNL Audience Manager] [!DNL API] de la documentation. Le tableau suivant répertorie les [!DNL API]modifiés et migrés.

<!--

<table id="table_CD3C244CB02C48C898745FB982EC828C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> API Type </th> 
   <th colname="col2" class="entry"> API Methods </th> 
  </tr> 
 </thead>
 <tbody>
 <tr> 
   <td colname="col1"> <p> <b>Algorithmic Models</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#/Algorithmic_Models_API" format="https" scope="external"> Algorithmic Models</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Audience Marketplace</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_4CFB3FAAC0B04E5AADD80E7D7FAF2722"> 
      <li id="li_50EE5F6B2278480E9FEA04AD51664F9D"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/?f=Data_Feed_API" format="https" scope="external"> Data Feeds</a> </li> 
      <li id="li_5D372E3819014AB78C12048A9A2DC89F"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Data_Feed_Request_API/" format="https" scope="external"> Data Feed Request</a> </li> 
      <li id="li_0582688D08C346C68B81D86A5C46E053"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/?f=Data_Feed_Finance_API" format="https" scope="external"> Data Feed Finance</a> </li> 
      <li id="li_C1C1CB42D6A74803B4672F6EE2D2D08C"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/?f=Data_Feed_Plans_API" format="https" scope="external"> Data Feed Plans</a> </li> 
      <li id="li_D8F9D791D0824287B9D0B0585E3106AB"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Data_Feed_Subscription_API" format="https" scope="external"> Data Feed Subscriptions</a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Data Source</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Data_Source_API" format="https" scope="external"> Data Sources</a> </p> </td> 
  </tr> 
   <td colname="col1"> <p> <b>Derived Signals</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#/Derived_Signals_API" format="https" scope="external"> Derived Signals</a> </p> </td> 
  </tr>   
  <tr> 
   <td colname="col1"> <p> <b>Folders</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_FD05673B372141F3B0EF2C79A338F744"> 
      <li id="li_5D16FCAF6F0E411694A1CFBE9571BDAC"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Segment_Folder_API" format="https" scope="external"> Segment Folders</a> </li> 
      <li id="li_5DC088C0F8CA4FC193248366C8400030"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Trait_Folder_API" scope="external" format="https"> Trait Folders</a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Reporting</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Reporting_API" format="https" scope="external"> Reporting</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Segments</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_098B0655653D4846B70349A35A055C19"> 
      <li id="li_41A3003BF41147969BC88D4F12A5C1BB"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Segments_API" format="https" scope="external"> Segments</a> </li> 
      <li id="li_22A858D377634D88AE58BE2CE924169C"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Segment_Test_Group_API/" format="https" scope="external"> Segment Test Groups</a> </li> 
      <li id="li_2B505A1B43CF4B29A0336106C321E7FD"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Segment_Test_Group_Draft_API/" format="https" scope="external"> Segment Test Group Draft API</a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Traits</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Traits_API" format="https" scope="external"> Traits</a> </p> </td> 
  </tr>
 </tbody>
</table>

-->


| Type d’API | Méthodes d’API |
---------|----------
| **[!UICONTROL Algorithmic Models**] | [Modèles algorithmiques](https://bank.demdex.com/portal/swagger/index.html#/Algorithmic_Models_API) |
| **[!UICONTROL Audience Marketplace]** | <ul><li>[Flux de données](https://bank.demdex.com/portal/swagger/index.html#/Audience%20Marketplace%20Buyer%20API/get_available_data_feeds_)</li><li>[Requête de flux de données](https://bank.demdex.com/portal/swagger/index.html#/Audience%20Marketplace%20Buyer%20API/post_available_data_feeds__dataSourceId__requests)</li><li>[Finance des flux de données](https://bank.demdex.com/portal/swagger/index.html#/Audience%20Marketplace%20Finance%20API/get_data_feeds_billing_report)</li><li>[Plans de flux de données](https://bank.demdex.com/portal/swagger/index.html#/Audience%20Marketplace%20Seller%20API/get_data_feeds__dataSourceId__plans_)</li><li>[Abonnements aux flux de données](https://bank.demdex.com/portal/swagger/index.html#/Audience%20Marketplace%20Seller%20API/get_data_feeds__dataSourceId__subscriptions)</li></ul> |
| **[!UICONTROL Data Sources]** | [Sources de données ](https://bank.demdex.com/portal/swagger/index.html#/Data_Source_API) |
| **[!UICONTROL Folders]** | <ul><li>[Dossiers de segment](https://bank.demdex.com/portal/swagger/index.html#/Segment_Folder_API)</li><li>[Dossiers de caractéristiques](https://bank.demdex.com/portal/swagger/index.html#/Trait%20Folder%20API)</li></ul> |
| **[!UICONTROL Reporting]** | [Création de rapports](https://bank.demdex.com/portal/swagger/index.html#/Reporting%20API) |
| **[!UICONTROL Segments]** | <ul><li>[Segments ](https://bank.demdex.com/portal/swagger/index.html#/Segments%20API)</li><li>[Groupes de tests de segments](https://bank.demdex.com/portal/swagger/index.html#/Segment%20Test%20Group%20API)</li><li>[API de brouillon de groupe de test de segment](https://bank.demdex.com/portal/swagger/index.html#/Segment%20Test%20Group%20API/post_segment_test_groups_drafts)</li></ul> |
| **[!UICONTROL Traits]** | [Caractéristiques ](https://bank.demdex.com/portal/swagger/index.html#/Traits%20API) |
