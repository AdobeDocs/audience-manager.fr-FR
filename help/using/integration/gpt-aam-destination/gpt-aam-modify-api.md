---
description: Ajoutez une instruction if pour rechercher les cookies d’Audience Manager avant d’appeler la méthode .setTargeting de balise Google Publisher.
seo-description: Ajoutez une instruction if pour rechercher les cookies d’Audience Manager avant d’appeler la méthode .setTargeting de balise Google Publisher.
seo-title: Modification de l’appel de l’API setTargeting GPT
solution: Audience Manager
title: Modification de l’appel de l’API setTargeting GPT
uuid: 0cd38f30-5d29-4511-a779-d32587f1dafb
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Modification de l’appel `setTargeting` API GPT {#modify-the-gpt-settargeting-api-call}

Ajoutez une instruction if pour rechercher les cookies Audience Manager avant d’appeler la [!DNL Google Publisher Tag] méthode `.setTargeting` .

## Rechercher les cookies Audience Manager avec un `IF` relevé

La `.setTargeting` méthode récupère les données du cookie de destination Audience Manager et du cookie ID utilisateur unique ( `aam_uuid`). Cependant, si `.setTargeting` est appelé avant [!UICONTROL DIL] d’écrire ces cookies ou si les cookies sont vides, des erreurs peuvent s’afficher au chargement de la page. Pour éviter cela, placez la `.setTargeting` méthode dans une `if` instruction qui vérifie ces cookies. S’ils ne sont pas définis, cette instruction empêche `.setTargeting` d’appeler la `AamGpt` fonction.

### `IF` Exemple de code de relevé

Dans cet exemple, le nom du cookie de destination Audience Manager est `Sample`. Vous définissez ce nom lorsque vous créez le cookie de destination dans l’interface utilisateur d’Audience Manager. [!UICONTROL DIL] définit le `aam_uuid` cookie et le nom ne peut pas être modifié.

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
>Selon la méthode d’intégration [!DNL DFP], vous n’avez besoin que de quelques lignes dans l’exemple de code ci-dessus :
>
>* Intégration côté client : utilisez uniquement les lignes 1 à 3.
>* Intégration côté serveur : aucune ligne n' est nécessaire.
>* Incorporer les fichiers [!DNL DFP] journaux pour la création de rapports dans [!DNL Audience Manager]: utilisez uniquement les lignes 4 à 6. Ce code insère la valeur du `aam_uuid` cookie dans les journaux afin qu’ils puissent être assimilés pour la création de rapports.


### `AamGpt` Fonctions et types de données

Définit les variables clés utilisées dans l’ `if` instruction.

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
   <td colname="col3"> <p>Renvoie la clé dans la paire de segments clé-valeur. Si, par exemple, votre paire clé-valeur se composait de <code> color=blue </code>, cela renvoie <code> color </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getValues </code> </p> </td> 
   <td colname="col2"> <p>Tableau de chaînes </p> </td> 
   <td colname="col3"> <p>Renvoie des valeurs dans un tableau, par exemple <code> ["value1","value2"] </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getCookie </code> </p> </td> 
   <td colname="col2"> <p>Int </p> </td> 
   <td colname="col3"> <p>Renvoie l’ID utilisateur d’Audience Manager, par exemple <code> 12345 </code>. </p> </td> 
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [Création d’une destination GPT](../../integration/gpt-aam-destination/gpt-aam-create-destination.md)
>* [Code Audience Manager pour les balises Google Publisher](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

