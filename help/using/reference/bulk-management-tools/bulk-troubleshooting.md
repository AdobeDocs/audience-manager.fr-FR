---
description: Que faire lorsque les feuilles de calcul renvoient une erreur ou que votre requête en masse échoue.
seo-description: Que faire lorsque les feuilles de calcul renvoient une erreur ou que votre requête en masse échoue.
seo-title: Conseils de dépannage pour les outils de gestion en bloc
solution: Audience Manager
title: Conseils de dépannage pour les outils de gestion en bloc
uuid: 550908a1-e24e-4f31-954b-7132c0c8dc3e
translation-type: tm+mt
source-git-commit: 6f13cefb2f56bbc2e0bfff9a6d31925001403c50

---


# Conseils de dépannage pour les outils de gestion en bloc{#troubleshooting-tips-for-bulk-management-tools}

Que faire lorsque les feuilles de calcul renvoient une erreur ou que votre requête en masse échoue.



<!-- 

<p>r_bulk_troubleshoot.xml </p>

 -->

>[!NOTE]
>
>Les variables ne [!UICONTROL Bulk Management Tools] sont pas *prises en charge par* [!DNL Audience Manager]. Cet outil est fourni à titre pratique et à titre de courtoisie seulement. Pour les modifications en masse, nous vous recommandons de travailler avec les API [Audience Manager](../../api/rest-api-main/aam-api-getting-started.md) à la place. [Les autorisations](../../features/administration/administration-overview.md) de groupe RBAC attribuées dans l’ [!DNL Audience Manager] interface utilisateur sont respectées dans [!UICONTROL Bulk Management Tools].

Des facteurs tels que le trafic réseau important, l’utilisation du serveur et les jeux de données volumineux peuvent entraîner l’échec ou l’expiration d’une demande en masse. En cas de problème, la feuille de calcul arrête l’écriture des données et affiche un message d’erreur. Dans ce cas, vous devez :

* Lisez le message d’erreur.
* Résolvez le problème.
* Supprimez toutes les lignes qui ont déjà été mises à jour.
* Réessayez la demande en bloc.

## Retards longs ou comportement inactif {#delays-behavior}

Le tableau suivant répertorie les problèmes courants que vous pouvez rencontrer lors de l’exécution de requêtes en masse avec les feuilles de calcul. Essayez de résoudre ces problèmes avec les solutions recommandées. Si les solutions recommandées ne résolvent pas le problème, enregistrez votre travail, redémarrez votre ordinateur et réessayez la requête sans lancer ou utiliser d’autres applications.

<table id="table_AC6FB99402214A4EAC6E709465BB67AF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Problème </th> 
   <th colname="col2" class="entry"> Solution </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Retards longs</b> </td> 
   <td colname="col2"> 
    <ul id="ul_AA6F414024B2475AB1C0B46DC3FF0B36"> 
     <li id="li_ECC83AC39D7142519AA9A223DB8FCF23"> <b>Désactivation du mode</b>de compatibilité : Vérifiez si d'autres feuilles de calcul sont ouvertes en mode de compatibilité Microsoft Excel. Le mode de compatibilité peut augmenter les runtimes. Fermez toutes les feuilles de calcul que vous avez peut-être ouvertes dans ce mode et réessayez votre demande en masse. </li> 
     <li id="li_234BFCF563234DE198884F33AB75280D"> <b>Ressources</b>système : Des ressources système limitées contribuent à de longs retards. Fermez tous les autres programmes avant de lancer une demande en masse. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Aucune réponse</b> </td> 
   <td colname="col2">Si vous cliquez sur un bouton d'action et que rien ne se passe : 
    <ul id="ul_142E63CDD556414AB639E51734FEDBCF"> 
     <li id="li_DBB6C819603D46B5AECC9C854FDAFDF1">Vérifiez que vous disposez du bon jeu d’en-têtes pour l’action de sélection. </li> 
     <li id="li_391C9031907A4085BDAD42054960045C">Veillez à utiliser la feuille de calcul appropriée pour les en-têtes copiés. </li> 
     <li id="li_76A7241989204933858621FAAB5C3408">Vérifiez la position des données que vous souhaitez utiliser dans une opération en bloc. Tous les en-têtes commencent dans la colonne A, ligne 1. Toutes les données sont placées dans les en-têtes correspondants, en commençant par la colonne A, ligne 2 (immédiatement sous les en-têtes). </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Messages d’erreur

Il arrive que vous receviez des messages d’erreur lorsque vous effectuez des modifications en masse. Pour interpréter le message d’erreur, reportez-vous à la section Codes de [réponse définis](/help/using/api/rest-api-main/aam-api-getting-started.md) dans notre documentation API.

