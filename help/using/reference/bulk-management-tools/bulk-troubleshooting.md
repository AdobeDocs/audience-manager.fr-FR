---
description: Que faire lorsque les feuilles de calcul renvoient une erreur ou que votre requête en bloc échoue.
seo-description: Que faire lorsque les feuilles de calcul renvoient une erreur ou que votre requête en bloc échoue.
seo-title: Conseils de dépannage pour les outils de gestion en bloc
solution: Audience Manager
title: Conseils de dépannage pour les outils de gestion en bloc
uuid: 550908a1-e24e-4f31-954b-7132c0c8dc3e
feature: BAAAM
exl-id: 4f1c501c-2e28-4ce5-829f-4d81d10cdccd
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 5%

---

# Conseils de dépannage pour les outils de gestion en bloc{#troubleshooting-tips-for-bulk-management-tools}

Que faire lorsque les feuilles de calcul renvoient une erreur ou que votre requête en bloc échoue.



<!-- 

<p>r_bulk_troubleshoot.xml </p>

 -->

>[!NOTE]
>
>[Les ](../../features/administration/administration-overview.md) autorisations de groupe RBAC attribuées dans l’ [!DNL Audience Manager] interface utilisateur sont honorées dans le  [!UICONTROL Bulk Management Tools].

Des facteurs tels qu’un trafic réseau important, l’utilisation du serveur et des jeux de données volumineux peuvent entraîner l’échec ou l’expiration d’une demande en bloc. En cas de problème, la feuille de calcul cesse d’écrire des données et affiche un message d’erreur. Lorsque cela se produit, vous devez :

* Lisez le message d’erreur.
* Réparez le problème.
* Supprimez toutes les lignes qui ont déjà été mises à jour.
* Essayez à nouveau la requête en bloc.

## Erreurs d’authentification, longs délais ou comportement inréactif {#delays-behavior}

Le tableau suivant répertorie certains problèmes courants que vous pouvez rencontrer lors de requêtes en masse avec les feuilles de calcul. Essayez de résoudre ces problèmes avec les solutions recommandées. Si les solutions recommandées ne résolvent pas le problème, enregistrez votre travail, redémarrez votre ordinateur, puis réessayez la demande sans lancer ou utiliser d’autres applications.

<table id="table_AC6FB99402214A4EAC6E709465BB67AF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Problème </th> 
   <th colname="col2" class="entry"> Solution </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Erreur d’authentification</b> </td> 
   <td colname="col2"> 
    <b>Mise à jour vers la dernière version de Microsoft Excel</b> : Lorsqu’une nouvelle version de Microsoft Excel est publiée et que vous utilisez une ancienne version, il se peut que vous rencontriez une erreur d’authentification dans la feuille de calcul de gestion en bloc. Mettez à jour vers la dernière version de Microsoft Excel pour résoudre l’erreur d’authentification.
</td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Longs délais</b> </td> 
   <td colname="col2"> 
    <ul id="ul_AA6F414024B2475AB1C0B46DC3FF0B36"> 
     <li id="li_ECC83AC39D7142519AA9A223DB8FCF23"> <b>Désactivez le mode</b> de compatibilité : Vérifiez si d’autres feuilles de calcul sont ouvertes en mode de compatibilité de Microsoft Excel. Le mode de compatibilité peut augmenter les exécutions. Fermez toutes les feuilles de calcul que vous avez ouvertes dans ce mode et réessayez votre demande en bloc. </li> 
     <li id="li_234BFCF563234DE198884F33AB75280D"> <b>Ressources</b> système : Des ressources système limitées entraînent de longs délais. Essayez de fermer tous les autres programmes avant d’effectuer une requête en bloc. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Aucune réponse</b> </td> 
   <td colname="col2">Si vous cliquez sur un bouton d’action, rien ne se passe : 
    <ul id="ul_142E63CDD556414AB639E51734FEDBCF"> 
     <li id="li_DBB6C819603D46B5AECC9C854FDAFDF1">Assurez-vous que vous disposez du bon ensemble d’en-têtes pour l’action de sélection. </li> 
     <li id="li_391C9031907A4085BDAD42054960045C">Assurez-vous d’utiliser la feuille de calcul appropriée pour les en-têtes copiés. </li> 
     <li id="li_76A7241989204933858621FAAB5C3408">Vérifiez la position des données que vous souhaitez utiliser dans une opération en bloc. Tous les en-têtes commencent dans la colonne A, ligne 1. Toutes les données sont placées dans les en-têtes correspondants commençant dans la colonne A, la ligne 2 (immédiatement sous les en-têtes). </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Messages d’erreur

Parfois, vous pouvez recevoir des messages d’erreur lorsque vous effectuez des modifications en bloc. Pour interpréter le message d’erreur, voir [Codes de réponse définis](/help/using/api/rest-api-main/aam-api-getting-started.md) dans la documentation de l’API.
