---
description: Le rapport Statut d’intégration vérifie les taux de succès et d’échec du traitement des enregistrements dans vos fichiers de source de données entrants. Ce rapport affiche des données dans un graphique à barres interactif et fournit des mesures récapitulatives sous forme tabulaire. Il comprend également une option qui échantillonne les fichiers pour un intervalle de temps fixe et affiche les erreurs les plus courantes pour chaque type d’erreur. Vous trouverez ce rapport dans Analytics > Rapport de statut d’intégration. Ce rapport est également disponible lorsque vous créez une source de données entrante.
seo-description: The Onboarding Status Report checks success and failure rates for processing records in your inbound data source files. This report displays data in an interactive bar chart and provides summary metrics in tabular form. And, it includes an option that samples files for a fixed time interval and displays the most common errors for each error type. You can find this report in Analytics > Onboarding Status Report. This report is also available when you create an inbound data source.
seo-title: Onboarding Status Report
solution: Audience Manager
title: Rapport du statut d’intégration
uuid: 6ca8a90a-436b-4fce-adf1-48f3b96b3ed2
feature: Inbound and Outbound Reports
exl-id: 4517276f-5025-4779-917f-4a0bb22ca56c
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1421'
ht-degree: 0%

---

# Rapport du statut d’intégration{#onboarding-status-report-about}

Le rapport Statut d’intégration vérifie les taux de succès et d’échec du traitement des enregistrements dans vos fichiers de source de données entrants. Ce rapport affiche des données dans un graphique à barres interactif et fournit des mesures récapitulatives sous forme tabulaire. Il comprend également une option qui échantillonne les fichiers pour un intervalle de temps fixe et affiche les erreurs les plus courantes pour chaque type d’erreur. Vous trouverez ce rapport dans Analytics > Rapport de statut d’intégration. Ce rapport est également disponible lorsque vous créez une source de données entrante.

>[!NOTE]
>
>Seuls les utilisateurs disposant de droits d’administrateur peuvent voir ce rapport dans l’interface utilisateur d’Audience Manager. Les utilisateurs non-administrateurs peuvent être avertis du statut des fichiers entrants chargés en ajoutant leurs e-mails au rapport. Voir [Recevoir des notifications par e-mail](/help/using/reporting/onboarding-status-report.md#receive-email-notifications).

## Rapport de statut d’intégration : À propos {#onboarding-status-about}

Le [!UICONTROL Onboarding Status Report] vérifie les taux de réussite et d’échec du traitement des enregistrements dans vos fichiers de source de données entrants. Ce rapport affiche des données dans un graphique à barres interactif et fournit des mesures récapitulatives sous forme tabulaire. Il comprend également une option qui échantillonne les fichiers pour un intervalle de temps fixe et affiche les erreurs les plus courantes pour chaque type d’erreur. Ce rapport se trouve dans **[!UICONTROL Analytics > Onboarding Status Report]**. Ce rapport est également disponible lorsque vous créez une source de données entrante.

## Rapports d’erreurs et échantillonnage d’erreurs {#error-reporting-sampling}

Le rapport d’erreurs et l’échantillonnage d’erreurs sont deux fonctionnalités distinctes du rapport [!UICONTROL Onboarding Status].

<table id="table_4706D891D4C545E8BF9D8A0CC052CC48"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fonctionnalité </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Rapport d’erreurs</b> </p> </td>
   <td colname="col2"> <p>Le rapport d’erreurs vous indique les taux de succès et d’échec pour le nombre d’enregistrements traités dans une source de données entrante. Il renvoie les données dans un graphique à barres interactif et empilé et sous forme de mesures récapitulatives dans les tableaux situés sous le graphique. </p> <p>Le rapport d’erreur est automatique. Il s’exécute en continu pour toutes vos sources de données entrantes. Elle renvoie des données en fonction d’une plage d’intervalles de temps prédéfinis ou d’un intervalle de temps personnalisé que vous définissez avec un widget Calendrier. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Échantillonnage d’erreur</b> </p> </td>
   <td colname="col2"> <p>L’échantillonnage d’erreur analyse le contenu de vos fichiers de données et renvoie les 10 erreurs les plus courantes pour chaque type d’erreur. Les erreurs dans vos fichiers de données entrants empêchent le traitement des enregistrements individuels. Utilisez ce rapport comme outil de dépannage pour réduire le nombre d’erreurs de fichier et améliorer les taux de traitement. </p> <p>Vous devez activer manuellement l’échantillonnage d’erreur. Il s’exécute pendant 14 jours à compter du jour de l’activation, puis s’éteint spontanément. Vous pouvez réactiver l’échantillonnage d’erreur après l’expiration de l’intervalle de 14 jours. Vous activez l’échantillonnage d’erreur lorsque vous <a href="../features/manage-datasources.md#create-data-source"> créer une source de données entrante</a> ou en cochant la case <b><span class="uicontrol"> l’échantillonnage d’erreur</span></b> dans la section Paramètres de Source de données <span class="wintitle"> </span> d’une source de données entrante existante. </p> <p>L’échantillonnage d’erreurs est un processus exigeant en termes de calcul. Par conséquent, il renvoie uniquement les 10 premières erreurs pour chaque catégorie d’erreur. Il n’est pas conçu pour renvoyer chaque erreur contenue dans une source de données entrante. Ces erreurs sont un échantillon représentatif d’un groupe potentiellement plus grand d’erreurs similaires. Vérifiez l'ensemble du fichier pour connaître les types d'erreurs que ce rapport signale, reformatez le fichier et renvoyez-le. </p> <p>Voir <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> du contenu du fichier de données entrant : syntaxe, variables et exemples</a> pour plus d’informations sur le format correct d’un fichier de données pour une source de données entrante. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Graphique à barres du rapport d’erreurs {#error-report-bar-chart}

Le rapport d’erreurs présente sous forme graphique les taux de succès et d’échec du traitement des enregistrements dans un graphique à barres empilées, comme illustré dans l’exemple suivant. Le graphique est interactif. Cliquez sur une barre pour afficher les mesures récapitulatives de ce jour dans un tableau situé sous le graphique.

![](assets/stacked-graph.png)

## Tableaux de rapports d’erreurs {#error-report-tables}

Le rapport d’erreurs affiche des données tabulaires sous le graphique à barres. Le tableau présente les taux de succès et d’échec, ainsi que les totaux et les pourcentages.

**Enregistrements réussis et en échec**

Cette vue par défaut vous indique le nombre total d’enregistrements de votre rapport par fréquence et inclut une répartition des erreurs par type d’erreur.

![](assets/success-failure.png)

**Totaux et pourcentages**

Cliquez sur **[!UICONTROL Totals & Percentages]** pour voir quel % de vos fichiers a été traité avec succès.

![](assets/totals-percentages.png)

## Rapport d’échantillonnage d’erreurs pendant 14 jours {#error-reporting-14-days}

Lorsque l’échantillonnage d’erreur est actif, le rapport affiche les 10 principales erreurs pour chaque type d’erreur. Cliquez sur un bouton de type d’erreur en haut du rapport pour afficher chaque ensemble de données échantillonnées.

>[!NOTE]
>
>Le rapport ne met pas en évidence les erreurs d’enregistrement dans cette version actuelle. Pour rechercher et corriger les erreurs de fichier, vous devez examiner les résultats et les comparer aux spécifications de la documentation [Contenu du fichier de données entrant](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md).

![](assets/error-samples.png)

## Recevoir des notifications par e-mail {#receive-email-notifications}

Vous pouvez ajouter les adresses e-mail des destinataires à avertir du statut des fichiers entrants chargés. Notez que vous pouvez sélectionner différents destinataires pour différentes sources de données.

![](assets/mail-notifications.png)

## Création d’un rapport de statut d’intégration {#create-onboard-status-report}

Une [!UICONTROL Sample Error Report] renvoie le nombre d’enregistrements traités avec succès dans une source de données et le nombre d’échecs. Pour générer un [!UICONTROL Sample Error Report], procédez comme suit.

<!-- 

create-onboarding-status-report.xml

 -->


1. Accédez à **[!UICONTROL Analytics > Onboarding Status Report]**. Recherchez une source de données ou choisissez-en une dans la liste.

2. Sélectionnez une période. Les options incluent :

   * Ensemble d’intervalles de rapports fixes.
   * Les widgets de calendrier qui vous permettent de créer une période personnalisée.

3. Cliquez sur **[!UICONTROL OK]**.

## Termes et définitions du rapport de statut d’intégration {#report-terms-conditions}

Guide de référence pour les libellés et termes utilisés dans ce rapport.

<table id="table_1D44A2E6B4C847848B818190DD336841"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Terme </th> 
   <th colname="col2" class="entry"> Définition </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Nom du fichier de synchronisation des données</b> </p> </td> 
   <td colname="col2"> <p>Répertorie les fichiers reçus et traités <span class="keyword"> Audience Manager</span> à partir de la source de données entrante sélectionnée. </p> <p>Le traitement du fichier échoue si le nom de fichier est mal formaté. Les exigences en matière de nom de fichier varient selon la manière dont vous envoyez ces données à <span class="keyword"> Audience Manager</span>. Les méthodes de diffusion incluent <span class="keyword"> Amazon S3</span> et FTP. Pour obtenir des instructions sur la manière de nommer vos fichiers, voir : </p> <p> 
     <ul id="ul_9A32906A14CA41C5AED0E13930DB31BA"> 
      <li id="li_A5A0E6ED711D4002B52092619F87C7D6"> <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md"> des exigences de nom Amazon S3 pour les fichiers de données entrants </a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Erreurs de format</b> </p> </td> 
   <td colname="col2"> <p>Répertorie le nombre d'enregistrements dont le traitement a échoué car ils ne correspondaient pas aux exigences de syntaxe ou de mise en forme. Voir <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> Contenu du fichier de données entrant : syntaxe, variables et exemples</a> pour plus d’informations sur le format de vos données. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Identifiant AAM non valide</b> </p> </td> 
   <td colname="col2"> <p>Répertorie le nombre d’ID utilisateur <span class="keyword"> Audience Manager</span> incorrectement formatés (UUID). En règle générale, cela indique les identifiants : </p> 
    <ul id="ul_8304250E8F0F44918A50CF9D8D8D1F83"> 
     <li id="li_B100B4C2623B4E099E022869A4978357">Ne correspond pas au format attendu de 38 chiffres. </li> 
     <li id="li_44E8A9AD13174A20A5742E56ED786634">Contiennent des caractères alphabétiques. Les identifiants ne doivent être que des chiffres. </li> 
    </ul> </td> 
  </tr>

<tr> 
   <td colname="col1"> <p> <b>Identifiant d’appareil non valide</b> </p> </td> 
   <td colname="col2"> <p>Répertorie le nombre d’identifiants globaux d’appareil incorrectement formatés. Voir <a href="../reference/ids-in-aam.md">Index des identifiants dans Audience Manager</a> et <a href="../features/global-data-sources.md">Sources de données globales</a> pour plus d’informations sur le formatage des identifiants d’appareil et sur les sources de données globales à utiliser, en fonction du type d’appareil.</p>
  <p>La section d’échantillonnage d’erreur du rapport comprend des informations détaillées sur les identifiants d’appareil non valides, tels que :</p>
   <ul>
    <li>l’identifiant de source de données correspondant à l’identifiant d’appareil non valide ;</li>
    <li>L’identifiant d’appareil non valide ;</li>
    <li>Type d’identifiant d’appareil attendu, en fonction de la source de données.</li>
   </ul>
  </tr>



<tr> 
   <td colname="col1"> <p> <b>Aucun ID AAM correspondant</b> </p> </td> 
   <td colname="col2"> <p>Il s’agit d’identifiants intégrés <span class="keyword"> Audience Manager</span> qui ne peuvent pas correspondre à un identifiant existant. Les identifiants intégrés peuvent avoir ce statut lorsqu’<span class="keyword"> Audience Manager</span> n’a pas encore effectué de synchronisation des identifiants ou ne peut toujours pas correspondre à l’identifiant, même après une synchronisation. </p> <p>Dans le cas d’identifiants mobiles sans correspondance, <span class="keyword"> Audience Manager </span> : </p> 
    <ul id="ul_B0D6AF9EB27D4017B35E36824B403879"> 
     <li id="li_D141000A50D3463182CBA4571DCC5373">Continuer à stocker et essayer de synchroniser cet identifiant. </li> 
     <li id="li_2EFCEE716F254ABCBC5FBF749B7564E6">Enregistrez-le en tant qu’enregistrement stocké <span class="wintitle"> dans le rapport</span> si l’identifiant ne peut pas être synchronisé. </li> 
    </ul> <p>Si votre fichier intégré contient des identifiants mobiles, vous pouvez traiter ces chiffres un peu plus légèrement que les autres mesures. Elles n’affectent pas les taux de succès et de correspondance pour les fichiers suivants. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Aucune caractéristique réalisée</b> </p> </td> 
   <td colname="col2"> <p>Répertorie les caractéristiques qui <span class="keyword"> Audience Manager</span> mais ne peuvent pas correspondre à une caractéristique intégrée. Cela pourrait être le résultat de : </p> 
    <ul id="ul_43619035AB6641B6949302FB50BDB5B1"> 
     <li id="li_D4C6306BF2B143198108702B309CE8CF">Caractéristiques mal formatées dans votre fichier de données entrant. Pour plus d’informations sur le format de votre fichier de données, voir <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> du contenu du fichier de données entrant : syntaxe, variables et exemples</a>. </li> 
     <li id="li_A1C708A007D24EE09B7C629AFC6E43C3">Caractéristiques qui n’ont pas encore été définies dans <span class="keyword"> Audience Manager</span>. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Pourcentage de succès</b> </p> </td> 
   <td colname="col2"> <p>Pourcentage d’enregistrements stockés avec succès dans votre fichier. Pourcentage de succès = enregistrements traités / nombre d'enregistrements dans un fichier. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Enregistrements reçus</b> </p> </td> 
   <td colname="col2"> <p>Nombre total d’enregistrements reçus. Dans la plupart des cas, ce nombre doit correspondre au nombre total d’enregistrements (lignes) dans votre fichier de données entrant. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b> Enregistrements stockés </b> </p> </td> 
   <td colname="col2"> <p>Nombre d’enregistrements stockés avec succès. En raison d’erreurs de format de fichier, certains enregistrements reçus peuvent ne pas être stockés par <span class="keyword"> Audience Manager</span>. Le nombre d'enregistrements stockés peut être inférieur au nombre d'enregistrements reçus. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Total des caractéristiques réalisées</b> </p> </td> 
   <td colname="col2"> <p>Nombre de caractéristiques pour tous les utilisateurs sur tous les fichiers entrants qui sont stockées sur la plateforme <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Total des signaux inutilisés</b> </p> </td> 
   <td colname="col2"> <p>Nombre total de signaux non utilisés reçus dans le rapport. Ce total est basé sur le nombre total d’enregistrements stockés avec succès. </p> <p>Pour plus d<a href="../reporting/dynamic-reports/unused-signals.md">informations</a> voir Rapport sur les signaux inutilisés . </p> </td> 
  </tr> 
 </tbody> 
</table>
