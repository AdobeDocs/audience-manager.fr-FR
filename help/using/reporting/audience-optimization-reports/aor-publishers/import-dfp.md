---
description: Avant qu’Audience Manager puisse activer Audience Optimization pour les éditeurs, vous devez vous assurer que toutes les conditions préalables décrites dans cet article sont remplies. Contactez l’assistance clientèle après avoir vérifié toutes les conditions préalables.
seo-description: Avant qu’Audience Manager puisse activer Audience Optimization pour les éditeurs, vous devez vous assurer que toutes les conditions préalables décrites dans cet article sont remplies. Contactez l’assistance clientèle après avoir vérifié toutes les conditions préalables.
seo-title: Importation des fichiers de données Google Ad Manager dans l’Audience Manager
solution: Audience Manager
title: Importation des fichiers de données Google Ad Manager dans l’Audience Manager
uuid: c685f34f-3e50-4c4b-99fa-d8bbafe0b268
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: e007279d81998031d2d61d0e68fe911813cadf8e
workflow-type: tm+mt
source-wordcount: '567'
ht-degree: 16%

---


# Importer des fichiers de données Google Ad Manager (anciennement DFP) dans l’Audience Manager{#import-dfp-data-files-into-audience-manager}

Avant qu’Audience Manager puisse activer Audience Optimization pour les éditeurs, vous devez vous assurer que toutes les conditions préalables décrites dans cet article sont remplies. Contactez l’assistance clientèle après avoir vérifié toutes les conditions préalables.

## Conditions préalables pour l&#39;importation du journal Google Ad Manager {#prereqs-dfp-ingestion}

Notez que le processus décrit dans cette section doit être terminé *avant* de passer aux conditions préalables à l&#39;importation des journaux.

Pour utiliser les fichiers journaux [!DNL Google Ad Manager] (anciennement Google DFP) dans [!DNL Audience Manager], vous devez d’abord définir notre identifiant d’utilisateur unique [Audience Manager (UUID)](../../../reference/ids-in-aam.md) dans l’appel de balise publicitaire. Ce faisant, notre ID est inclus dans les [!DNL Google Ad Manager] journaux et nous pouvons faire correspondre les ID entre [!DNL Google Ad Manager] et [!DNL Audience Manager]. Utilisez [!DNL Audience Manager] le [!UICONTROL DIL] code ou [!UICONTROL Audience Management Module] le pour définir l’ [!DNL Audience Manager] UUID dans un cookie propriétaire.

Voici comment définir l’ [!DNL Audience Manager] identifiant dans l’appel de balise d’annonce, comme expliqué dans notre documentation :

* [Via la balise Google Publisher (GPT)](../../../integration/gpt-aam-destination/gpt-aam-modify-api.md)
* [Via une destination de cookie](../../../integration/gpt-aam-destination/gpt-aam-create-destination.md)

Vous devez définir vous-même l&#39; [!DNL Audience Manager] ID et vous pouvez travailler avec [!DNL Audience Manager] un consultant pour vérifier si tout fonctionne. Vous avez correctement défini l’ [!DNL Audience Manager] identifiant si :

* `'aamid'` est la clé utilisée comme identifiant.
* La valeur ID utilisateur est correctement formatée en tant qu’ [!DNL Audience Manager] UUID, comme décrit dans notre [Index d’ID en Audience Manager](../../../reference/ids-in-aam.md).
* Vous avez inclus l’ [!DNL Audience Manager] UUID dans un champ défini de vos [!DNL Google Ad Manager] journaux (par exemple, Ciblage personnalisé).

## Conditions préalables pour l&#39;activation de la journalisation des embouteillages {#prereqs-ingestion-enablement}

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
   <td colname="col2"> <p>Confirmer que les étapes requises pour définir l'UUID <span class="keyword"> Audience Manager</span> (décrite ci-dessus) ont été effectuées avant de passer à l'étape 2 </p> </td> 
   <td colname="col3"> <p><span class="keyword"> Audience Manager</span> du service à la clientèle ou du conseil </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Étape 2 </p> </td> 
   <td colname="col2"> <p>Votre administrateur Google Ad Manager crée : </p> <p> 
     <ol id="ol_FCFA9B11CFF948A488DF9CB298FC04C4"> 
      <li id="li_BC946EDCC3324578AEB64EDDA55B5ACA">Un compte de service pour l’importation de Google Ad Manager se connecte à <span class="keyword"> l’Audience Manager</span>. </li> 
      <li id="li_6B2FC7D73A3246419E55C004E17ACA25">Nouvelles informations d’identification. <p>Remarque :  Cela peut nécessiter une adresse de messagerie unique spécifique à ce projet et sera utilisé lors de l'attribution de l'accès au compartiment d'Enregistrements Google. </p> </li> 
      <li id="li_95444B9FD1B34659A9634814B262A681">Clé privée (informations d’identification JSON) </li> 
     </ol> </p> </td> 
   <td colname="col3"> <p>Votre administrateur Google Ad Manager </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Étape 3 </p> </td> 
   <td colname="col2"> <p>Votre administrateur Google Ad Manager accorde l’accès à l’API au compte de service. Cette étape permet d’accéder aux métadonnées pour délimiter les dimensions (éléments de ligne, commandes, éléments créatifs). <p>Remarque :  Utilisez l’accès par courrier électronique au compte de service que vous avez configuré à l’étape 2 pour accorder l’autorisation d’accéder à l’API. </p> </p> </td> 
   <td colname="col3"> <p>Votre administrateur Google Ad Manager </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Étape 4 </p> </td> 
   <td colname="col2"> <p>Votre administrateur Google Ad Manager établit l’accès au compartiment d’Enregistrements Google. Rappelez-vous : </p> <p> 
     <ul id="ul_3E8DCC73454243D998BD9024D0966A4E"> 
      <li id="li_3691DBD28006412288458175F75873C6">Cela peut être fait via un groupe Google. </li> 
      <li id="li_4774806B263245CEAAAB89BD2AA7F23F">Associez l’adresse électronique unique attribuée au compte de service au compartiment d’enregistrements. </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p>Votre administrateur Google Ad Manager </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Etape 5 </p> </td> 
   <td colname="col2"> <p>Votre administrateur Google Ad Manager fournit l’identifiant réseau Google Ad Manager. Cela nous permet de transmettre l'ID réseau lors d'appels à l'API. </p> </td> 
   <td colname="col3"> <p>Votre administrateur Google Ad Manager </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Etape 6 </p> </td> 
   <td colname="col2"> <p>Compilez les conditions préalables dans un e-mail adressé au service à la clientèle AAM (aamsupport@adobe.com) pour lancer le processus d’assimilation des journaux. Ebauche du courrier électronique à l’aide du modèle dans la section suivante. </p> </td> 
   <td colname="col3"> <p>Vous, ou <span class="keyword"> Audience Manager</span> Consulting en votre nom </p> </td> 
  </tr> 
 </tbody> 
</table>

## Modèle de courrier électronique {#email-template}

Pour finaliser l&#39;activation de l&#39;assimilation des journaux, envoyez-nous un courriel à aamsupport@adobe.com. Veuillez utiliser le modèle [de courrier électronique](assets/enable_dfp_ingestion.txt)ci-joint.
