---
description: Ajoutez une instruction if pour rechercher les cookies d’Audience Manager avant d’appeler la méthode Google Publisher Tag .setTargeting .
seo-description: Add an if statement to check for Audience Manager cookies before calling the Google Publisher Tag .setTargeting method.
seo-title: Modify the GPT setTargeting API Call
solution: Audience Manager
title: Modification de l’appel de l’API GPT setTargeting
uuid: 0cd38f30-5d29-4511-a779-d32587f1dafb
feature: Third-party Integration
exl-id: cc34b7e8-7bbd-463f-9378-9d3a40c49594
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 5%

---

# Modification de l’appel API GPT `setTargeting` {#modify-the-gpt-settargeting-api-call}

Ajoutez une instruction if pour rechercher les cookies d’Audience Manager avant d’appeler la méthode [!DNL Google Publisher Tag] `.setTargeting`.

## Recherchez les cookies d’Audience Manager avec une instruction `IF`.

La méthode `.setTargeting` récupère les données du cookie de destination de l’Audience Manager et du cookie d’identifiant utilisateur unique ( `aam_uuid`). Cependant, si `.setTargeting` est appelé avant que [!UICONTROL DIL] n’écrive ces cookies ou si les cookies sont vides, des erreurs peuvent s’afficher lors du chargement de la page. Pour éviter cela, enveloppez la méthode `.setTargeting` dans une instruction `if` qui recherche ces cookies. Si elles ne sont pas définies, cette instruction empêche `.setTargeting` d’appeler la fonction `AamGpt`.

### `IF` Exemple de code d’instruction

Dans cet exemple, le nom du cookie de destination de l’Audience Manager est `Sample`. Vous définissez ce nom lorsque vous créez le cookie de destination dans l’interface utilisateur de l’Audience Manager. [!UICONTROL DIL] définit le cookie `aam_uuid` et le nom ne peut pas être modifié.

```js
if(typeof AamGpt.getCookie("Sample") != "undefined"){ 
  googletag.pubads().setTargeting(AamGpt.getKey("Sample"),AamGpt.getValues("Sample")); 
}; 
if(typeof AamGpt.getCookie("aam_uuid") != "undefined" ){ 
   googletag.pubads().setTargeting("aamId", AamGpt.getCookie("aam_uuid")); 
};
```

>[!IMPORTANT]
>
>Selon la manière dont vous souhaitez intégrer [!DNL Google Ad Manager], vous n’avez besoin que de certaines lignes dans l’exemple de code ci-dessus :
>
>* Intégration côté client : utilisez uniquement les lignes 1 à 3.
>* Intégration côté serveur : aucune ligne n’est nécessaire.
>* Ingérez [!DNL Google Ad Manager] fichiers journaux pour la création de rapports dans [!DNL Audience Manager] : utilisez uniquement les lignes 4 à 6. Ce code insère la valeur du cookie `aam_uuid` dans les journaux afin qu’ils puissent être ingérés pour la création de rapports.

### `AamGpt` Fonctions et types de données

Définit les variables clés utilisées dans l’instruction `if`.

<table id="table_881391C9BDDF4FACAFC37A47B14B31A1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fonction </th> 
   <th colname="col2" class="entry"> Type </th> 
   <th colname="col3" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getKey </code> </p> </td> 
   <td colname="col2"> <p>Chaîne </p> </td> 
   <td colname="col3"> <p>Renvoie la clé dans la paire de segments clé-valeur. Par exemple, si votre paire clé-valeur est composée de <code> color=blue </code>, la valeur renvoyée est <code> color </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getValues </code> </p> </td> 
   <td colname="col2"> <p>Tableau de chaînes </p> </td> 
   <td colname="col3"> <p>Renvoie les valeurs d’un tableau, par exemple <code> ["value1","value2"] </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getCookie </code> </p> </td> 
   <td colname="col2"> <p>Int </p> </td> 
   <td colname="col3"> <p>Renvoie l’identifiant utilisateur de l’Audience Manager, par exemple <code> 12345 </code>. </p> </td> 
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [Création d’une destination GPT](../../integration/gpt-aam-destination/gpt-aam-create-destination.md)
>* [Code Audience Manager pour les Google Publisher Tags](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)
