---
description: Avant qu’Audience Manager puisse activer Audience Optimization pour les éditeurs, vous devez vous assurer que toutes les conditions préalables décrites dans cet article sont remplies. Contactez l’assistance clientèle après avoir vérifié toutes les conditions préalables.
seo-description: Before Audience Manager can enable Audience Optimization for Publishers, you must ensure that all prerequisites outlined in this article are met. Contact Customer Care after checking off all prerequisites.
seo-title: Import Google Ad Manager Data Files Into Audience Manager
solution: Audience Manager
title: Importation de fichiers de données Google Ad Manager dans Audience Manager
uuid: c685f34f-3e50-4c4b-99fa-d8bbafe0b268
feature: Audience Optimization Reports
exl-id: 62b72dd1-e664-4c6a-8c0a-f7a662d62a47
source-git-commit: 7147091e6c253e8124f5f21a2251c1a76ac9d808
workflow-type: tm+mt
source-wordcount: '511'
ht-degree: 14%

---

# Importation de fichiers de données Google Ad Manager (anciennement DFP) dans Audience Manager{#import-dfp-data-files-into-audience-manager}

Avant qu’Audience Manager puisse activer Audience Optimization pour les éditeurs, vous devez vous assurer que toutes les conditions préalables décrites dans cet article sont remplies. Contactez l’assistance clientèle après avoir vérifié toutes les conditions préalables.

## Conditions préalables à l’ingestion du journal de Google Ad Manager {#prereqs-dfp-ingestion}

Notez que le processus décrit dans cette section doit être terminé *avant* que vous passiez aux conditions préalables à l’activation de l’ingestion des journaux.

Pour utiliser les fichiers journaux [!DNL Google Ad Manager] (anciennement Google DFP) dans [!DNL Audience Manager], vous devez d’abord définir notre [identifiant utilisateur unique de l’Audience Manager (UUID)](../../../reference/ids-in-aam.md) dans l’appel de balise publicitaire. Ce faisant, notre ID est inclus dans les journaux [!DNL Google Ad Manager] et nous pouvons établir une correspondance avec les identifiants entre [!DNL Google Ad Manager] et [!DNL Audience Manager]. Utilisez le code [!DNL Audience Manager] [!UICONTROL DIL] ou [!UICONTROL Audience Management Module] pour définir l’UUID [!DNL Audience Manager] dans un cookie propriétaire.

Voici comment définir l’ID [!DNL Audience Manager] dans l’appel de balise publicitaire, comme expliqué dans notre documentation :

* [Via Google Publisher Tag (GPT)](../../../integration/gpt-aam-destination/gpt-aam-modify-api.md)
* [Via une destination de cookie](../../../integration/gpt-aam-destination/gpt-aam-create-destination.md)

Vous devez définir vous-même l’ID [!DNL Audience Manager] et pouvez travailler avec le service de conseil [!DNL Audience Manager] pour vérifier si tout fonctionne. Vous avez correctement défini l&#39;ID [!DNL Audience Manager] si :

* `'aamid'` est la clé utilisée comme identifiant.
* La valeur de l’ID utilisateur est correctement formatée en tant qu’UUID [!DNL Audience Manager], comme décrit dans notre [Index des ID en Audience Manager](../../../reference/ids-in-aam.md).
* Vous avez inclus l’UUID [!DNL Audience Manager] dans un champ défini dans vos journaux [!DNL Google Ad Manager] (par exemple, le ciblage personnalisé).

## Conditions préalables pour l’activation de l’ingestion par journal {#prereqs-ingestion-enablement}

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
   <td colname="col2"> <p>Vérifiez que les étapes requises pour définir l’UUID <span class="keyword"> Audience Manager</span> (décrites ci-dessus) ont été effectuées avant de passer à l’étape 2. </p> </td> 
   <td colname="col3"> <p><span class="keyword"> Audience Manager</span> Assistance clientèle ou conseil </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Étape 2 </p> </td> 
   <td colname="col2"> <p>Votre administrateur Google Ad Manager crée : </p> <p> 
     <ol id="ol_FCFA9B11CFF948A488DF9CB298FC04C4"> 
      <li id="li_BC946EDCC3324578AEB64EDDA55B5ACA">Un compte de service pour l’ingestion de Google Ad Manager se connecte à l’ <span class="keyword"> Audience Manager</span>. </li> 
      <li id="li_6B2FC7D73A3246419E55C004E17ACA25">Nouvelles informations d’identification <p>Remarque : une adresse électronique unique spécifique à ce projet peut être requise. Elle sera utilisée lors de la configuration de l’accès au compartiment de stockage Google. </p> </li> 
      <li id="li_95444B9FD1B34659A9634814B262A681">Clé privée (informations d’identification basées sur JSON) </li> 
     </ol> </p> </td> 
   <td colname="col3"> <p>Votre administrateur Google Ad Manager </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Étape 3 </p> </td> 
   <td colname="col2"> <p>Votre administrateur Google Ad Manager accorde l’accès à l’API au compte de service. Cette étape permet d’accéder aux métadonnées pour délimiter les dimensions (éléments de ligne, commandes, éléments créatifs). <p>Remarque : utilisez l’accès par e-mail au compte de service que vous avez configuré à l’étape 2 pour accorder l’autorisation d’accès à l’API. </p> </p> </td> 
   <td colname="col3"> <p>Votre administrateur Google Ad Manager </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Étape 4 </p> </td> 
   <td colname="col2"> <p>Votre administrateur Google Ad Manager établit l’accès au compartiment de stockage de Google. Souvenez-vous : </p> <p> 
     <ul id="ul_3E8DCC73454243D998BD9024D0966A4E"> 
      <li id="li_3691DBD28006412288458175F75873C6">Vous pouvez le faire via un groupe Google. </li> 
      <li id="li_4774806B263245CEAAAB89BD2AA7F23F">Associez l’adresse électronique unique affectée au compte de service au compartiment de stockage. </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p>Votre administrateur Google Ad Manager </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Etape 5 </p> </td> 
   <td colname="col2"> <p>Votre administrateur Google Ad Manager fournit l’identifiant réseau Google Ad Manager. Cela nous permet de transmettre l’identifiant réseau lors d’appels à l’API. </p> </td> 
   <td colname="col3"> <p>Votre administrateur Google Ad Manager </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Etape 6 </p> </td> 
   <td colname="col2"> <p>Compilez les conditions préalables et ouvrez un ticket d’assistance en suivant les instructions détaillées <a href="https://experienceleague.adobe.com/docs/customer-one/using/home.html?lang=fr">ici</a> pour lancer le processus d’ingestion des journaux. </p> </td> 
   <td colname="col3"> <p>Vous, ou <span class="keyword"> Audience Manager </span> Consulting en votre nom </p> </td> 
  </tr> 
 </tbody> 
</table>
