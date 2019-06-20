---
description: Que faire lorsque les feuilles de calcul renvoient une erreur ou que votre requête en masse échoue.
seo-description: Que faire lorsque les feuilles de calcul renvoient une erreur ou que votre requête en masse échoue.
seo-title: Conseils de dépannage des outils de gestion en masse
solution: Audience Manager
title: Conseils de dépannage des outils de gestion en masse
uuid: 550908 a 1-e 24 e -4 f 31-954 b -7132 c 0 c 8 dc 3 e
translation-type: tm+mt
source-git-commit: cb3819192c523f9c20e9a15ca5d43ef36c49e900

---


# Troubleshooting Tips for Bulk Management Tools{#troubleshooting-tips-for-bulk-management-tools}

Que faire lorsque les feuilles de calcul renvoient une erreur ou que votre requête en masse échoue.



<!-- 

<p>r_bulk_troubleshoot.xml </p>

 -->

>[!NOTE]
>
>The [!UICONTROL Bulk Management Tools] *are not* supported by [!DNL Audience Manager]. Cet outil est fourni à titre de commodité uniquement. For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [Les permissions de groupe RBAC](../../features/administration/administration-overview.md) attribuées dans [!DNL Audience Manager] l&#39;interface utilisateur sont respectées dans l&#39; [!UICONTROL Bulk Management Tools]interface.

Des facteurs tels que le trafic réseau important, l&#39;utilisation du serveur et les jeux de données volumineux peuvent entraîner l&#39;échec ou l&#39;expiration d&#39;une demande en masse. S&#39;il y a un problème, la feuille de calcul arrête d&#39;écrire les données et affiche un message d&#39;erreur. Lorsque cela se produit, vous devez :

* Lisez le message d&#39;erreur.
* Corrigez le problème.
* Supprimez toutes les lignes qui ont déjà été mises à jour.
* Essayez de nouveau la demande en bloc.

## Long delays or unresponsive behavior {#delays-behavior}

Le tableau suivant répertorie certains problèmes courants que vous pouvez rencontrer lors de la réalisation de requêtes en bloc avec les feuilles de calcul. Tentez de résoudre ces problèmes avec les solutions recommandées. Si les solutions recommandées ne résolvent pas le problème, enregistrez votre travail, redémarrez votre ordinateur, puis relancez la requête sans lancer ni utiliser d&#39;autres applications.

<table id="table_AC6FB99402214A4EAC6E709465BB67AF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Problème </th> 
   <th colname="col2" class="entry"> Solution </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Longs délais</b> </td> 
   <td colname="col2"> 
    <ul id="ul_AA6F414024B2475AB1C0B46DC3FF0B36"> 
     <li id="li_ECC83AC39D7142519AA9A223DB8FCF23"> <b>Désactivation du mode de compatibilité</b>: Vérifiez si d'autres feuilles de calcul s'ouvrent en mode de compatibilité Microsoft Excel. Le mode Compatibilité peut accroître les moteurs d'exécution. Fermez les feuilles de calcul que vous avez ouvertes dans ce mode et essayez de nouveau votre demande en bloc. </li> 
     <li id="li_234BFCF563234DE198884F33AB75280D"> <b>Ressources système</b>: Les ressources système limitées contribuent aux longs délais. Fermez tous les autres programmes avant de lancer une demande en bloc. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Aucune réponse</b> </td> 
   <td colname="col2">Si vous cliquez sur un bouton d'action et rien ne se passe : 
    <ul id="ul_142E63CDD556414AB639E51734FEDBCF"> 
     <li id="li_DBB6C819603D46B5AECC9C854FDAFDF1">Assurez-vous d'avoir le jeu d'en-têtes approprié pour l'action de sélection. </li> 
     <li id="li_391C9031907A4085BDAD42054960045C">Assurez-vous d'utiliser la feuille de calcul appropriée pour les en-têtes copiés. </li> 
     <li id="li_76A7241989204933858621FAAB5C3408">Vérifiez la position des données à utiliser dans une opération en bloc. Tous les en-têtes commencent dans la colonne A, ligne 1. Toutes les données sont placées dans les en-têtes correspondants à partir de la colonne A, ligne 2 (juste sous les en-têtes). </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

