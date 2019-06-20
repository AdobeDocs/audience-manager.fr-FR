---
description: Avant qu’Audience Manager puisse activer Audience Optimization pour les éditeurs, vous devez vous assurer que toutes les conditions préalables décrites dans cet article sont remplies. Contactez l’assistance clientèle après avoir vérifié toutes les conditions préalables.
seo-description: Avant qu’Audience Manager puisse activer Audience Optimization pour les éditeurs, vous devez vous assurer que toutes les conditions préalables décrites dans cet article sont remplies. Contactez l’assistance clientèle après avoir vérifié toutes les conditions préalables.
seo-title: Importation de fichiers de données DPF dans Audience Manager
solution: Audience Manager
title: Importation de fichiers de données DPF dans Audience Manager
uuid: c 685 f 34 f -3 e 50-4 c 4 b -99 fa-d 8 bbafe 0 b 268
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Importation de fichiers de données DPF dans Audience Manager{#import-dfp-data-files-into-audience-manager}

Avant qu’Audience Manager puisse activer Audience Optimization pour les éditeurs, vous devez vous assurer que toutes les conditions préalables décrites dans cet article sont remplies. Contactez l’assistance clientèle après avoir vérifié toutes les conditions préalables.

## Prerequisites for DFP Log Ingestion {#prereqs-dfp-ingestion}

Note that the process described in this section must be completed *before* you move on to the prerequisites for log ingestion enablement.

In order to use DFP ( [!DNL DoubleClick For Publishers]) log files in [!DNL Audience Manager], you must first set our [Audience Manager Unique User ID (UUID)](../../../reference/ids-in-aam.md) in the ad tag call. By doing this, our ID is included in the DFP logs and we can match IDs between DFP and [!DNL Audience Manager]. Use [!DNL Audience Manager] [!UICONTROL DIL] code or the [!UICONTROL Audience Management Module] to set the [!DNL Audience Manager] UUID in a first party cookie.

Here is how to set the [!DNL Audience Manager] ID in the ad tag call, as explained in our documentation:

* [Via la balise Google Publisher (GPT)](../../../integration/gpt-aam-destination/gpt-aam-create-destination.md)
* [Via une destination de cookie](../../../integration/gpt-aam-destination/gpt-aam-modify-api.md)

You need to set the [!DNL Audience Manager] ID yourself, and can work with [!DNL Audience Manager] consulting to check if everything works. You have set the [!DNL Audience Manager] ID correctly if:

* `'aamid'` est la clé utilisée comme identifiant.
* The User ID value is correctly formatted as the [!DNL Audience Manager] UUID, as described in our [Index of IDs in Audience Manager](../../../reference/ids-in-aam.md).
* You have included the [!DNL Audience Manager] UUID in a defined field in your DFP logs (e.g. CustomTargeting).

## Prerequisites for Log Ingestion Enablement {#prereqs-ingestion-enablement}

<table id="table_C980A9F9B0FB4157B4908A64768B1571"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Étape </th> 
   <th colname="col2" class="entry"> Détails </th> 
   <th colname="col3" class="entry"> Propriétaire </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Étape 1 </p> </td> 
   <td colname="col2"> <p>Confirm that the required steps to set the <span class="keyword"> Audience Manager</span> UUID (outlined above) have been completed prior to moving to Step 2 </p> </td> 
   <td colname="col3"> <p><span class="keyword"> Assistance</span> clientèle d'Audience Manager ou conseil </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Étape 2 </p> </td> 
   <td colname="col2"> <p>Votre administrateur DFP crée les éléments suivants : </p> <p> 
     <ol id="ol_FCFA9B11CFF948A488DF9CB298FC04C4"> 
      <li id="li_BC946EDCC3324578AEB64EDDA55B5ACA">A service account for ingesting DFP logs into <span class="keyword"> Audience Manager</span>. </li> 
      <li id="li_6B2FC7D73A3246419E55C004E17ACA25">Nouvelles informations d'identification. <p>Remarque : Cette opération peut nécessiter une adresse électronique unique spécifique à ce projet et être utilisée lors de l'attribution d'un accès au compartiment de stockage Google. </p> </li> 
      <li id="li_95444B9FD1B34659A9634814B262A681">Clé privée (informations d'identification basées sur JSON) </li> 
     </ol> </p> </td> 
   <td colname="col3"> <p>Votre administrateur DFP </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Étape 3 </p> </td> 
   <td colname="col2"> <p>Votre administrateur DFP octroie l'accès aux API au compte de service. Cette étape permet d'accéder aux métadonnées pour délimiter les dimensions (éléments de ligne, commandes, créations). <p>Remarque : Utilisez l'accès par courrier électronique de compte de service que vous configurez à l'étape 2 pour autoriser l'accès à l'API. </p> </p> </td> 
   <td colname="col3"> <p>Votre administrateur DFP </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Étape 4 </p> </td> 
   <td colname="col2"> <p>Votre administrateur DFP établit l'accès au compartiment de stockage Google. Mémoriser : </p> <p> 
     <ul id="ul_3E8DCC73454243D998BD9024D0966A4E"> 
      <li id="li_3691DBD28006412288458175F75873C6">Cela peut être fait via un groupe Google. </li> 
      <li id="li_4774806B263245CEAAAB89BD2AA7F23F">Associez l'adresse électronique unique affectée au compte de service au compartiment de stockage. </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p>Votre administrateur DFP </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Etape 5 </p> </td> 
   <td colname="col2"> <p>Votre administrateur DFP fournit l'identifiant réseau DFP. Cela permet de transmettre l'ID réseau lors de la réalisation d'appels à l'API. </p> </td> 
   <td colname="col3"> <p>Votre administrateur DFP </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Etape 6 </p> </td> 
   <td colname="col2"> <p>Compilez les conditions préalables dans un e-mail à l'assistance clientèle AAM (aamsupport@adobe.com) pour déclencher le processus d'ingestion du journal. Brouillon du courrier électronique à l'aide du modèle dans la section suivante. </p> </td> 
   <td colname="col3"> <p>You, or <span class="keyword"> Audience Manager</span> Consulting on your behalf </p> </td> 
  </tr> 
 </tbody> 
</table>

## E-Mail Template {#email-template}

Pour finaliser l&#39;activation de l&#39;ingestion du journal, envoyez-nous un e-mail à aamsupport@adobe.com. Please use the [attached e-mail template](assets/enable_dfp_ingestion.txt).
