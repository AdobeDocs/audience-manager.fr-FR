---
description: Ici, chez Audience Manager, nous sommes des ingénieurs, des développeurs, et des ninjas de code comme vous. Et, comme vous, nous voulons travailler avec une documentation API fiable et précise. Par conséquent, nous réécrivons le contenu de notre API dans Swagger et le déplaçons vers un nouvel emplacement. Ces modifications sont conçues pour vous aider à améliorer votre expérience avec le code API d’Audience Manager.
seo-description: Ici, chez Audience Manager, nous sommes des ingénieurs, des développeurs, et des ninjas de code comme vous. Et, comme vous, nous voulons travailler avec une documentation API fiable et précise. Par conséquent, nous réécrivons le contenu de notre API dans Swagger et le déplaçons vers un nouvel emplacement. Ces modifications sont conçues pour vous aider à améliorer votre expérience avec le code API d’Audience Manager.
seo-title: Migration du code API d’Audience Manager
solution: Audience Manager
title: Migration du code API d’Audience Manager
uuid: 93cc28c4-4b91-4c79-93d5-ece9bb4cc9d5
translation-type: tm+mt
source-git-commit: d368699d0de9a43cb7cf2c1af64da941a811db71

---


# Audience Manager API Code Migration {#audience-manager-api-code-migration}

Ici, chez Audience Manager, nous sommes des ingénieurs, des développeurs, et des ninjas de code comme vous. Et, comme vous, nous voulons travailler avec une [!DNL API] documentation fiable et précise. Par conséquent, nous réécrivons notre [!DNL API] contenu [!DNL Swagger] et le déplaçons vers un nouvel emplacement. Ces modifications sont conçues pour vous aider à améliorer votre expérience avec le code Audience Manager [!DNL API] .

## Monter {#code-migration-details}

<!-- api-swagger-migration.xml -->

Le site Docs [de l’API](https://bank.demdex.com/portal/swagger/index.html) Adobe Audience Manager constitue le nouvel accueil pour notre [!DNL API] contenu révisé. Nous essayerons de réécrire et de déplacer quelques ensembles de [!DNL API] méthodes avec chaque version. Cela signifie que vous devrez vérifier le nouvel emplacement et la documentation de l’API [](../api/rest-api-main/rest-api-main.md) REST pour trouver toutes les méthodes disponibles. A terme, tous les publics [!DNL API]seront sur le site des [!DNL Audience Manager] [!DNL API] documents. Le tableau suivant répertorie les [!DNL API]versions révisées et migrées.

<table id="table_CD3C244CB02C48C898745FB982EC828C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type d’API </th> 
   <th colname="col2" class="entry"> Méthodes API </th> 
  </tr> 
 </thead>
 <tbody>
 <tr> 
   <td colname="col1"> <p> <b>Modèles algorithmiques</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#/Algorithmic_Models_API" format="https" scope="external"> Modèles algorithmiques</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Audience Marketplace</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_4CFB3FAAC0B04E5AADD80E7D7FAF2722"> 
      <li id="li_50EE5F6B2278480E9FEA04AD51664F9D"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/?f=Data_Feed_API" format="https" scope="external"> Flux de données</a> </li> 
      <li id="li_5D372E3819014AB78C12048A9A2DC89F"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Data_Feed_Request_API/" format="https" scope="external"> Demande de flux de données</a> </li> 
      <li id="li_0582688D08C346C68B81D86A5C46E053"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/?f=Data_Feed_Finance_API" format="https" scope="external"> Data Feed Finance</a> </li> 
      <li id="li_C1C1CB42D6A74803B4672F6EE2D2D08C"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/?f=Data_Feed_Plans_API" format="https" scope="external"> Formules de flux de données</a> </li> 
      <li id="li_D8F9D791D0824287B9D0B0585E3106AB"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Data_Feed_Subscription_API" format="https" scope="external"> Abonnements aux flux de données</a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Source de données</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Data_Source_API" format="https" scope="external"> Sources de données</a> </p> </td> 
  </tr> 
   <td colname="col1"> <p> <b>Signaux dérivés</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#/Derived_Signals_API" format="https" scope="external"> Signaux dérivés</a> </p> </td> 
  </tr>   
  <tr> 
   <td colname="col1"> <p> <b>Dossiers</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_FD05673B372141F3B0EF2C79A338F744"> 
      <li id="li_5D16FCAF6F0E411694A1CFBE9571BDAC"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Segment_Folder_API" format="https" scope="external"> Dossiers de segment</a> </li> 
      <li id="li_5DC088C0F8CA4FC193248366C8400030"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Trait_Folder_API" scope="external" format="https"> Dossiers de caractéristiques</a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Création de rapports</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Reporting_API" format="https" scope="external"> Création de rapports</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Segments</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_098B0655653D4846B70349A35A055C19"> 
      <li id="li_41A3003BF41147969BC88D4F12A5C1BB"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Segments_API" format="https" scope="external"> Segments</a> </li> 
      <li id="li_22A858D377634D88AE58BE2CE924169C"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Segment_Test_Group_API/" format="https" scope="external"> Groupes de tests de segments</a> </li> 
      <li id="li_2B505A1B43CF4B29A0336106C321E7FD"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Segment_Test_Group_Draft_API/" format="https" scope="external"> API de brouillon de groupe de tests de segments</a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Caractéristiques</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Traits_API" format="https" scope="external"> Caractéristiques</a> </p> </td> 
  </tr>
 </tbody>
</table>