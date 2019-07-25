---
description: Ajoutez une instruction if pour rechercher les cookies Audience Manager avant d'appeler la méthode Google Publisher Tag. settargeting.
seo-description: Ajoutez une instruction if pour rechercher les cookies Audience Manager avant d'appeler la méthode Google Publisher Tag. settargeting.
seo-title: Modification de l'appel de l'API settargeting GPT
solution: Audience Manager
title: Modification de l'appel de l'API settargeting GPT
uuid: 0 cd 38 f 30-5 d 29-4511-a 779-d 32587 f 1 dafb
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Modify the GPT `setTargeting` API Call {#modify-the-gpt-settargeting-api-call}

Add an if statement to check for Audience Manager cookies before calling the [!DNL Google Publisher Tag] `.setTargeting` method.

## Check for Audience Manager Cookies With an `IF` Statement

The `.setTargeting` method gets data from the Audience Manager destination cookie and the unique user ID cookie ( `aam_uuid`). However, if `.setTargeting` gets invoked before [!UICONTROL DIL] writes these cookies, or the cookies are empty, you may see errors when the page loads. To help avoid this, wrap the `.setTargeting` method in an `if` statement that checks for these cookies. If they're not set, this statement prevents `.setTargeting` from calling the `AamGpt` function.

### `IF` Exemple de code de relevé

In this example, the Audience Manager destination cookie name is `Sample`. Vous définissez ce nom lorsque vous créez le cookie de destination dans l'interface utilisateur d'Audience Manager. [!UICONTROL DIL] définit `aam_uuid` le cookie et le nom ne peut pas être modifié.

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
>Depending on how you want to integrate with [!DNL DFP], you only need some of the lines in the code sample above:
>
>* Intégration côté client : utilisez les lignes 1-3 uniquement.
>* Intégration côté serveur : aucune des lignes n'est nécessaire.
>* Ingest [!DNL DFP] log files for reporting in [!DNL Audience Manager]: use lines 4-6 only. This code inserts the value of the `aam_uuid` cookie into the logs so they can be ingested for reporting.


### `AamGpt` Fonctions et types de données

Defines the key variables used in the `if` statement.

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
   <td colname="col1"> <p> <code> Aamgpt. getkey </code> </p> </td> 
   <td colname="col2"> <p>Chaîne </p> </td> 
   <td colname="col3"> <p>Renvoie la clé dans la paire de segments clé-valeur. For example, if your key-value pair consisted of <code> color=blue </code>, this returns <code> color </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Aamgpt. getvalues </code> </p> </td> 
   <td colname="col2"> <p>Tableau de chaînes </p> </td> 
   <td colname="col3"> <p>Returns values in an array, e.g., <code> ["value1","value2"] </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Aamgpt. getcookie </code> </p> </td> 
   <td colname="col2"> <p>Int </p> </td> 
   <td colname="col3"> <p>Returns the Audience Manager user ID, e.g., <code> 12345 </code>. </p> </td> 
  </tr>
 </tbody>
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Création d'une destination GPT](../../integration/gpt-aam-destination/gpt-aam-create-destination.md)
>* [Code Audience Manager pour les balises Google Publisher](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

