---
description: Que faire lorsque les feuilles de calcul renvoient une erreur ou que votre requête en bloc échoue.
seo-description: What to do when the worksheets return an error or your bulk request fails.
seo-title: Troubleshooting Tips for Bulk Management Tools
solution: Audience Manager
title: Conseils de dépannage pour les outils de gestion en bloc
uuid: 550908a1-e24e-4f31-954b-7132c0c8dc3e
feature: BAAAM
exl-id: 4f1c501c-2e28-4ce5-829f-4d81d10cdccd
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '410'
ht-degree: 0%

---

# Conseils de dépannage pour les outils de gestion en bloc{#troubleshooting-tips-for-bulk-management-tools}

Que faire lorsque les feuilles de calcul renvoient une erreur ou que votre requête en bloc échoue.

>[!IMPORTANT]
>
>Les outils de gestion en bloc ne sont pas une offre Adobe officiellement prise en charge. Le dépannage et l’assistance par l’intermédiaire de l’assistance clientèle seront gérés au cas par cas.

<!-- 

<p>r_bulk_troubleshoot.xml </p>

 -->

>[!NOTE]
>
>Les [autorisations de groupe RBAC](../../features/administration/administration-overview.md) attribuées dans l’interface utilisateur de [!DNL Audience Manager] sont respectées dans la [!UICONTROL Bulk Management Tools].

Des facteurs tels qu’un trafic réseau important, l’utilisation d’un serveur et des jeux de données volumineux peuvent entraîner l’échec ou l’expiration d’une requête en bloc. En cas de problème, la feuille de calcul cesse d’écrire des données et affiche un message d’erreur. Dans ce cas, vous devez :

* Lisez le message d’erreur.
* Résolvez le problème.
* Supprimez toutes les lignes déjà mises à jour.
* Effectuez à nouveau la requête en bloc.

## Erreurs d’authentification, retards importants ou comportement non réactif {#delays-behavior}

Le tableau suivant répertorie certains problèmes courants que vous pouvez rencontrer lors de l’exécution de requêtes en bloc avec les feuilles de calcul . Essayez de résoudre ces problèmes à l’aide des solutions recommandées. Si les solutions recommandées ne résolvent pas le problème, vous devez enregistrer votre travail, redémarrer votre ordinateur et réitérer la demande sans lancer ou travailler avec d’autres applications.

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
    <b>Mise à jour vers la dernière version de Microsoft Excel</b> : lorsqu’une nouvelle version de Microsoft Excel est publiée et que vous utilisez une version plus ancienne, vous pouvez rencontrer une erreur d’authentification dans la feuille de calcul de gestion en bloc. Mettez à jour vers la dernière version de Microsoft Excel pour résoudre l’erreur d’authentification.
</td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Délais importants</b> </td> 
   <td colname="col2"> 
    <ul id="ul_AA6F414024B2475AB1C0B46DC3FF0B36"> 
     <li id="li_ECC83AC39D7142519AA9A223DB8FCF23"> <b>Désactiver le mode de compatibilité</b> : vérifiez si d’autres feuilles de calcul sont ouvertes en mode de compatibilité Microsoft Excel. Le mode de compatibilité peut augmenter les durées d’exécution. Fermez toutes les feuilles de calcul ouvertes dans ce mode et effectuez à nouveau votre demande en bloc. </li> 
     <li id="li_234BFCF563234DE198884F33AB75280D"> <b>Ressources système</b> : des ressources système limitées entraînent de longs retards. Essayez de fermer tous les autres programmes avant d’effectuer une requête en bloc. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Pas de réponse</b> </td> 
   <td colname="col2">Si vous cliquez sur un bouton d’action et que rien ne se passe : 
    <ul id="ul_142E63CDD556414AB639E51734FEDBCF"> 
     <li id="li_DBB6C819603D46B5AECC9C854FDAFDF1">Assurez-vous que vous disposez du jeu d’en-têtes approprié pour l’action de sélection. </li> 
     <li id="li_391C9031907A4085BDAD42054960045C">Vérifiez que vous utilisez la feuille de calcul appropriée pour les en-têtes copiés. </li> 
     <li id="li_76A7241989204933858621FAAB5C3408">Vérifiez la position des données que vous souhaitez utiliser dans une opération en bloc. Tous les en-têtes commencent dans la colonne A, ligne 1. Toutes les données sont transmises dans les en-têtes correspondants à partir de la colonne A, ligne 2 (immédiatement sous les en-têtes). </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Messages d’erreur

Parfois, vous pouvez recevoir des messages d’erreur lors de modifications en bloc. Pour interpréter le message d’erreur, consultez [Codes de réponse définis](/help/using/api/rest-api-main/aam-api-getting-started.md) dans la documentation de l’API .
