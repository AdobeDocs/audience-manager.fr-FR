---
description: Ajoutez une instruction if pour vérifier les cookies Audience Manager avant d’appeler la méthode Google Publisher Tag .setTargeting.
seo-description: Add an if statement to check for Audience Manager cookies before calling the Google Publisher Tag .setTargeting method.
seo-title: Modify the GPT setTargeting API Call
solution: Audience Manager
title: Modifier l’appel API setTargeting GPT
uuid: 0cd38f30-5d29-4511-a779-d32587f1dafb
feature: Third-party Integration
exl-id: cc34b7e8-7bbd-463f-9378-9d3a40c49594
TQID: https://experienceleague.adobe.com/2K-1BhtAdC60YW3nxvT7cVgQVSsY3gaWy7NbG-FcDqM
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: a8b0238e-1d43-4679-a3b4-5ba1bad83baaid: a99472c1-6aae-4c7a-8aa0-f60636369620
subfeature_v2: id: a49258d4-867f-4130-b875-d72c001bdf6c
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 278
ht-degree: 5%

---

# Modifier l’appel API GPT `setTargeting` {#modify-the-gpt-settargeting-api-call}

Ajoutez une instruction if pour vérifier les cookies Audience Manager avant d’appeler la méthode [!DNL Google Publisher Tag] `.setTargeting`.

## Rechercher des cookies Audience Manager avec une instruction `IF`

La méthode `.setTargeting` récupère les données du cookie de destination Audience Manager et du cookie d’ID utilisateur unique (`aam_uuid`). Cependant, si `.setTargeting` est appelé avant [!UICONTROL DIL]’écriture de ces cookies, ou si les cookies sont vides, des erreurs peuvent s’afficher au chargement de la page. Pour éviter cela, encapsulez la méthode `.setTargeting` dans une instruction `if` qui vérifie ces cookies. Si elles ne sont pas définies, cette instruction empêche `.setTargeting` d&#39;appeler la fonction `AamGpt`.

### Exemple de code de relevé `IF`

Dans cet exemple, le nom du cookie de destination Audience Manager est `Sample`. Ce nom est défini lors de la création du cookie de destination dans l’interface utilisateur d’Audience Manager. [!UICONTROL DIL] définit le cookie `aam_uuid` et le nom ne peut pas être modifié.

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
>Selon la manière dont vous souhaitez intégrer à [!DNL Google Ad Manager], il vous suffit de quelques-unes des lignes de l’exemple de code ci-dessus :
>
>* Intégration côté client : utilisez uniquement les lignes 1 à 3.
>* Intégration côté serveur : aucune des lignes n’est nécessaire.
>* Ingérez [!DNL Google Ad Manager] fichiers journaux pour le compte rendu des performances dans [!DNL Audience Manager] : utilisez uniquement les lignes 4 à 6. Ce code insère la valeur du cookie `aam_uuid` dans les journaux afin qu’ils puissent être ingérés pour la création de rapports.

### Fonctions `AamGpt` et types de données

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
   <td colname="col3"> <p>Renvoie la clé de la paire de segments clé-valeur. Par exemple, si votre paire clé-valeur se composait de <code> color=blue </code>, cette fonction renvoie <code> color </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getValues </code> </p> </td> 
   <td colname="col2"> <p>Tableau de chaînes </p> </td> 
   <td colname="col3"> <p>Renvoie des valeurs dans un tableau, par exemple <code> ["value1","value2"] </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getCookie </code> </p> </td> 
   <td colname="col2"> <p>Int </p> </td> 
   <td colname="col3"> <p>Renvoie l’identifiant utilisateur Audience Manager, par exemple <code> 12345 </code>. </p> </td> 
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [Création d’une destination GPT](../../integration/gpt-aam-destination/gpt-aam-create-destination.md)
>* [Code Audience Manager pour les Google Publisher Tags](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)
