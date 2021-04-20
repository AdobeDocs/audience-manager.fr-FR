---
description: Ajoutez une instruction if pour rechercher les cookies d’Audience Manager avant d’appeler la méthode Google Publisher Tag .setTargeting.
seo-description: Ajoutez une instruction if pour rechercher les cookies d’Audience Manager avant d’appeler la méthode Google Publisher Tag .setTargeting.
seo-title: Modification de l’appel API GPT setTargeting
solution: Audience Manager
title: Modification de l’appel API GPT setTargeting
uuid: 0cd38f30-5d29-4511-a779-d32587f1dafb
feature: Third-party Integration
exl-id: cc34b7e8-7bbd-463f-9378-9d3a40c49594
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 9%

---

# Modifier l&#39;appel d&#39;API GPT `setTargeting` {#modify-the-gpt-settargeting-api-call}

Ajoutez une instruction if pour rechercher les cookies d&#39;Audience Manager avant d&#39;appeler la méthode [!DNL Google Publisher Tag] `.setTargeting`.

## Recherchez les cookies d’Audience Manager avec une instruction `IF`.

La méthode `.setTargeting` récupère les données du cookie de destination de l&#39;Audience Manager et du cookie d&#39;ID utilisateur unique ( `aam_uuid`). Cependant, si `.setTargeting` est appelé avant que [!UICONTROL DIL] écrive ces cookies, ou si les cookies sont vides, des erreurs peuvent se produire au chargement de la page. Pour éviter cela, placez la méthode `.setTargeting` dans une instruction `if` qui recherche ces cookies. Si elles ne sont pas définies, cette instruction empêche `.setTargeting` d&#39;appeler la fonction `AamGpt`.

### `IF` Exemple de code de relevé

Dans cet exemple, le nom du cookie de destination de l’Audience Manager est `Sample`. Vous définissez ce nom lorsque vous créez le cookie de destination dans l’interface utilisateur de l’Audience Manager. [!UICONTROL DIL] définit le  `aam_uuid` cookie et le nom ne peut pas être modifié.

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
>Selon la méthode d’intégration avec [!DNL Google Ad Manager], vous n’avez besoin que de certaines lignes dans l’exemple de code ci-dessus :
>
>* Intégration côté client : utilisez uniquement les lignes 1 à 3.
>* Intégration côté serveur : aucune ligne n&#39;est nécessaire.
>* Envoi de [!DNL Google Ad Manager] fichiers journaux pour le rapports dans [!DNL Audience Manager] : n&#39;utilisez que les lignes 4 à 6. Ce code insère la valeur du cookie `aam_uuid` dans les journaux afin qu’ils puissent être ingérés pour le rapports.


### `AamGpt` Fonctions et types de données

Définit les variables clés utilisées dans l&#39;instruction `if`.

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
   <td colname="col3"> <p>Renvoie la clé de la paire de segments clé-valeur. Par exemple, si votre paire clé-valeur est composée de <code> color=blue </code>, elle renvoie <code> color </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getValues </code> </p> </td> 
   <td colname="col2"> <p>Tableau de chaînes </p> </td> 
   <td colname="col3"> <p>Renvoie des valeurs dans un tableau, par exemple <code> ["value1","value2"] </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getCookie </code> </p> </td> 
   <td colname="col2"> <p>Int </p> </td> 
   <td colname="col3"> <p>Renvoie l’ID utilisateur de l’Audience Manager, par exemple <code> 12345 </code>. </p> </td> 
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [Création d’une destination GPT](../../integration/gpt-aam-destination/gpt-aam-create-destination.md)
>* [Code Audience Manager pour les Google Publisher Tags](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

