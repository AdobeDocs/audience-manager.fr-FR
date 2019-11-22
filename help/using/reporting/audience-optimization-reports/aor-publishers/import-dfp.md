---
description: Avant qu’Audience Manager puisse activer Audience Optimization pour les éditeurs, vous devez vous assurer que toutes les conditions préalables décrites dans cet article sont remplies. Contactez l’assistance clientèle après avoir vérifié toutes les conditions préalables.
seo-description: Avant qu’Audience Manager puisse activer Audience Optimization pour les éditeurs, vous devez vous assurer que toutes les conditions préalables décrites dans cet article sont remplies. Contactez l’assistance clientèle après avoir vérifié toutes les conditions préalables.
seo-title: Importation de fichiers de données DPF dans Audience Manager
solution: Audience Manager
title: Importation de fichiers de données DPF dans Audience Manager
uuid: c685f34f-3e50-4c4b-99fa-d8bbafe0b268
translation-type: tm+mt
source-git-commit: 9f091fa765e937fb47b3328d8f5f2dab24a85040

---


# Importation de fichiers de données DPF dans Audience Manager{#import-dfp-data-files-into-audience-manager}

Avant qu’Audience Manager puisse activer Audience Optimization pour les éditeurs, vous devez vous assurer que toutes les conditions préalables décrites dans cet article sont remplies. Contactez l’assistance clientèle après avoir vérifié toutes les conditions préalables.

## Conditions préalables pour l’importation du journal DFP {#prereqs-dfp-ingestion}

Notez que le processus décrit dans cette section doit être terminé *avant* de passer aux conditions préalables requises pour l'assimilation des journaux.

Pour utiliser les fichiers journaux DFP ( [!DNL DoubleClick For Publishers]) dans [!DNL Audience Manager], vous devez d’abord définir l’ID utilisateur unique (UUID) [d’](../../../reference/ids-in-aam.md) Audience Manager dans l’appel de balise publicitaire. Ce faisant, notre ID est inclus dans les journaux DFP et nous pouvons faire correspondre les ID entre DFP et [!DNL Audience Manager]. Utilisez [!DNL Audience Manager] le code ou [!UICONTROL DIL] le pour définir l’ [!UICONTROL Audience Management Module] [!DNL Audience Manager] UUID dans un cookie propriétaire.

Voici comment définir l’ [!DNL Audience Manager] ID dans l’appel de balise publicitaire, comme expliqué dans notre documentation :

* [Via Google Publisher Tag (GPT)](../../../integration/gpt-aam-destination/gpt-aam-modify-api.md)
* [Via une destination de cookie](../../../integration/gpt-aam-destination/gpt-aam-create-destination.md)

Vous devez définir vous-même la [!DNL Audience Manager] carte d'identité et vous pouvez travailler avec [!DNL Audience Manager] un consultant pour vérifier si tout fonctionne. Vous avez correctement défini l’ [!DNL Audience Manager] ID si :

* `'aamid'` est la clé utilisée comme identifiant.
* La valeur ID utilisateur est correctement formatée en tant qu’ [!DNL Audience Manager] UUID, comme décrit dans notre [index d’ID dans Audience Manager](../../../reference/ids-in-aam.md).
* Vous avez inclus l’ [!DNL Audience Manager] UUID dans un champ défini dans vos journaux DFP (ex. : ciblage personnalisé).

## Conditions préalables pour l'activation de la gestion des journaux {#prereqs-ingestion-enablement}

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
   <td colname="col2"> <p>Vérifiez que les étapes requises pour définir l’UUID d’Audience Manager <span class="keyword"></span> (décrites ci-dessus) ont été effectuées avant de passer à l’étape 2. </p> </td> 
   <td colname="col3"> <p><span class="keyword"> Assistance clientèle ou conseil d’Audience Manager</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Étape 2 </p> </td> 
   <td colname="col2"> <p>Votre administrateur DFP crée : </p> <p> 
     <ol id="ol_FCFA9B11CFF948A488DF9CB298FC04C4"> 
      <li id="li_BC946EDCC3324578AEB64EDDA55B5ACA">Un compte de service pour l’assimilation de DFP se connecte à <span class="keyword"> Audience Manager</span>. </li> 
      <li id="li_6B2FC7D73A3246419E55C004E17ACA25">Nouvelles informations d’identification. <p>Remarque :  Cela peut nécessiter une adresse de courriel unique spécifique à ce projet et sera utilisé lors de la configuration de l'accès au compartiment de stockage Google. </p> </li> 
      <li id="li_95444B9FD1B34659A9634814B262A681">Clé privée (informations d’identification JSON) </li> 
     </ol> </p> </td> 
   <td colname="col3"> <p>Votre administrateur DFP </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Étape 3 </p> </td> 
   <td colname="col2"> <p>Votre administrateur DFP accorde à l’API l’accès au compte de service. Cette étape permet d’accéder aux métadonnées pour délimiter les dimensions (éléments de ligne, commandes, éléments créatifs). <p>Remarque :  Utilisez l’accès par courrier électronique au compte de service que vous avez configuré à l’étape 2 pour autoriser l’accès à l’API. </p> </p> </td> 
   <td colname="col3"> <p>Votre administrateur DFP </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Étape 4 </p> </td> 
   <td colname="col2"> <p>Votre administrateur DFP établit l’accès au compartiment de stockage Google. N'oubliez pas : </p> <p> 
     <ul id="ul_3E8DCC73454243D998BD9024D0966A4E"> 
      <li id="li_3691DBD28006412288458175F75873C6">Cela peut être fait via un groupe Google. </li> 
      <li id="li_4774806B263245CEAAAB89BD2AA7F23F">Associez l’adresse électronique unique attribuée au compte de service au compartiment de stockage. </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p>Votre administrateur DFP </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Etape 5 </p> </td> 
   <td colname="col2"> <p>Votre administrateur DFP fournit l’ID réseau DFP. Cela nous permet de transmettre l’ID réseau lors d’appels à l’API. </p> </td> 
   <td colname="col3"> <p>Votre administrateur DFP </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Etape 6 </p> </td> 
   <td colname="col2"> <p>Compilez les conditions préalables requises dans un courrier électronique adressé au service à la clientèle AAM (aamsupport@adobe.com) pour lancer le processus d’assimilation des journaux. Ebauche du courrier électronique à l’aide du modèle dans la section suivante. </p> </td> 
   <td colname="col3"> <p>Vous ou <span class="keyword"> Audience Manager</span> Consulting en votre nom </p> </td> 
  </tr> 
 </tbody> 
</table>

## Modèle de courrier électronique {#email-template}

Pour finaliser l'activation de l'assimilation des journaux, envoyez-nous un e-mail à aamsupport@adobe.com. Veuillez utiliser le modèle [de courrier électronique](assets/enable_dfp_ingestion.txt)ci-joint.
