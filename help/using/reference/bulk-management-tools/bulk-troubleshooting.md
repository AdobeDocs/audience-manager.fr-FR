---
description: Que faire lorsque les feuilles de calcul renvoient une erreur ou que votre requête en masse échoue.
seo-description: Que faire lorsque les feuilles de calcul renvoient une erreur ou que votre requête en masse échoue.
seo-title: Conseils de dépannage pour les outils de gestion en bloc
solution: Audience Manager
title: Conseils de dépannage pour les outils de gestion en bloc
uuid: 550908a1-e24e-4f31-954b-7132c0c8dc3e
feature: baaam
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '402'
ht-degree: 0%

---


# Conseils de dépannage pour les outils de gestion en bloc{#troubleshooting-tips-for-bulk-management-tools}

Que faire lorsque les feuilles de calcul renvoient une erreur ou que votre requête en masse échoue.



<!-- 

<p>r_bulk_troubleshoot.xml </p>

 -->

>[!NOTE]
>
>[Les autorisations](../../features/administration/administration-overview.md) de groupe RBAC attribuées dans l’ [!DNL Audience Manager] interface utilisateur sont respectées dans le [!UICONTROL Bulk Management Tools].

Des facteurs tels que le trafic réseau important, l’utilisation du serveur et les jeux de données volumineux peuvent entraîner l’échec ou l’expiration d’une demande en bloc. En cas de problème, la feuille de calcul arrête l’écriture des données et affiche un message d’erreur. Dans ce cas, vous devez :

* Lisez le message d’erreur.
* Résolvez le problème.
* Supprimez toutes les lignes déjà mises à jour.
* Réessayez la demande en bloc.

## Erreurs d’authentification, retards importants ou comportement inactif {#delays-behavior}

Le tableau suivant liste certains problèmes courants que vous pouvez rencontrer lors de demandes en masse avec les feuilles de calcul. Essayez de résoudre ces problèmes avec les solutions recommandées. Si les solutions recommandées ne résolvent pas le problème, enregistrez votre travail, redémarrez votre ordinateur, puis réessayez la demande sans lancer ou utiliser d’autres applications.

<table id="table_AC6FB99402214A4EAC6E709465BB67AF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Problème </th> 
   <th colname="col2" class="entry"> Solution </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Erreur d'authentification</b> </td> 
   <td colname="col2"> 
    <b>Mise à jour vers la dernière version de Microsoft Excel</b>: Lorsqu'une nouvelle version de Microsoft Excel est publiée et que vous utilisez une ancienne version, une erreur d'authentification peut se produire dans la feuille de calcul Gestion en bloc. Mettez à jour vers la dernière version de Microsoft Excel pour résoudre l'erreur d'authentification.
</td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Retards longs</b> </td> 
   <td colname="col2"> 
    <ul id="ul_AA6F414024B2475AB1C0B46DC3FF0B36"> 
     <li id="li_ECC83AC39D7142519AA9A223DB8FCF23"> <b>Désactiver le mode</b>de compatibilité : Vérifiez si d'autres feuilles de calcul sont ouvertes en mode de compatibilité Microsoft Excel. Le mode de compatibilité peut augmenter les délais d’exécution. Fermez toutes les feuilles de calcul que vous avez peut-être ouvertes dans ce mode et réessayez votre demande en masse. </li> 
     <li id="li_234BFCF563234DE198884F33AB75280D"> <b>Ressources</b>système : Les ressources limitées du système contribuent à de longs retards. Essayez de fermer tous les autres programmes avant d'effectuer une demande en bloc. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Aucune réponse</b> </td> 
   <td colname="col2">Si vous cliquez sur un bouton d'action et que rien ne se passe : 
    <ul id="ul_142E63CDD556414AB639E51734FEDBCF"> 
     <li id="li_DBB6C819603D46B5AECC9C854FDAFDF1">Assurez-vous que vous disposez du bon jeu d’en-têtes pour l’action de sélection. </li> 
     <li id="li_391C9031907A4085BDAD42054960045C">Veillez à utiliser la feuille de calcul appropriée pour les en-têtes copiés. </li> 
     <li id="li_76A7241989204933858621FAAB5C3408">Vérifiez la position des données que vous souhaitez utiliser dans une opération en bloc. Tous les en-têtes sont débuts dans la colonne A, ligne 1. Toutes les données sont placées dans des en-têtes correspondants commençant à la colonne A, ligne 2 (juste en dessous des en-têtes). </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Messages d’erreur

Parfois, vous pouvez recevoir des messages d’erreur lorsque vous effectuez des modifications en masse. Pour interpréter le message d’erreur, reportez-vous à la section Codes de [réponse définis](/help/using/api/rest-api-main/aam-api-getting-started.md) dans notre documentation API.

