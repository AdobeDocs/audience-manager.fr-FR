---
description: Le rapport État d'intégration vérifie les taux de réussite et d'échec du traitement des enregistrements dans vos fichiers de source de données entrants. Ce rapport affiche les données dans un graphique à barres interactif et fournit des mesures récapitulatives sous forme de tableau. Il comporte également une option qui échantillonne les fichiers pendant une période fixe et affiche les erreurs les plus courantes pour chaque type d’erreur. Vous pouvez trouver ce rapport dans Analytics > Rapport d'état. Ce rapport est également disponible lorsque vous créez une source de données entrantes.
seo-description: Le rapport État d'intégration vérifie les taux de réussite et d'échec du traitement des enregistrements dans vos fichiers de source de données entrants. Ce rapport affiche les données dans un graphique à barres interactif et fournit des mesures récapitulatives sous forme de tableau. Il comporte également une option qui échantillonne les fichiers pendant une période fixe et affiche les erreurs les plus courantes pour chaque type d’erreur. Vous pouvez trouver ce rapport dans Analytics > Rapport d'état. Ce rapport est également disponible lorsque vous créez une source de données entrantes.
seo-title: Rapport sur l'état à propos de
solution: Audience Manager
title: Rapport sur l'état à propos de
uuid: 6 ca 8 a 90 a -436 b -4 fce-adf 1-48 f 3 b 96 b 3 ed 2
translation-type: tm+mt
source-git-commit: b213a1ecde4c85dc66dada24dec602ed1d9b0332

---


# Onboarding Status Report{#onboarding-status-report-about}

Le rapport État d&#39;intégration vérifie les taux de réussite et d&#39;échec du traitement des enregistrements dans vos fichiers de source de données entrants. Ce rapport affiche les données dans un graphique à barres interactif et fournit des mesures récapitulatives sous forme de tableau. Il comporte également une option qui échantillonne les fichiers pendant une période fixe et affiche les erreurs les plus courantes pour chaque type d’erreur. Vous pouvez trouver ce rapport dans Analytics &gt; Rapport d&#39;état. Ce rapport est également disponible lorsque vous créez une source de données entrantes.

>[!NOTE]
>
>Seuls les utilisateurs disposant des privilèges d&#39;administrateur peuvent afficher ce rapport dans l&#39;interface utilisateur d&#39;Audience Manager. Pour que les utilisateurs non administrateurs soient avertis de l&#39;état des fichiers entrants transférés, ajoutez leurs e-mails au rapport. See [Receive E-mail Notifications](/help/using/reporting/onboarding-status-report.md#receive-email-notifications).

## Onboarding Status Report: About {#onboarding-status-about}

[!UICONTROL Onboarding Status Report] Le contrôle vérifie les taux de réussite et d&#39;échec pour le traitement des enregistrements dans vos fichiers de source de données entrants. Ce rapport affiche les données dans un graphique à barres interactif et fournit des mesures récapitulatives sous forme de tableau. Il comporte également une option qui échantillonne les fichiers pendant une période fixe et affiche les erreurs les plus courantes pour chaque type d’erreur. You can find this report in **[!UICONTROL Analytics > Onboarding Status Report]**. Ce rapport est également disponible lorsque vous créez une source de données entrantes.

## Error Reporting and Error Sampling {#error-reporting-sampling}

Error reporting and error sampling are 2 separate features of the [!UICONTROL Onboarding Status] report.

<table id="table_4706D891D4C545E8BF9D8A0CC052CC48"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fonctionnalité </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Rapports d'erreurs</b> </p> </td>
   <td colname="col2"> <p>Les rapports d'erreur indiquent les taux de réussite et d'échec du nombre d'enregistrements traités dans une source de données entrantes. Elle renvoie les données dans un graphique à barres empilées, empilées et en tant que mesures récapitulatives dans les tableaux sous le graphique. </p> <p>La création de rapports d'erreur est automatique. Il s'exécute en continu pour toutes les sources de données entrantes. Elle renvoie les données selon la plage des intervalles de temps prédéfinis ou un intervalle personnalisé défini avec un widget de calendrier. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Echantillonnage d'erreur</b> </p> </td>
   <td colname="col2"> <p>L'échantillonnage d'erreurs analyse le contenu de vos fichiers de données et renvoie les 10 erreurs les plus courantes pour chaque type d'erreur. Les erreurs dans vos fichiers de données entrants empêchent le traitement des enregistrements individuels. Utilisez ce rapport comme outil de dépannage pour réduire le nombre d'erreurs de fichier et améliorer les taux de traitement. </p> <p>Vous devez activer manuellement l'échantillonnage d'erreur. Il s'exécute pendant 14 jours à compter du jour d'activation, puis se désactive. Vous pouvez réactiver l'échantillonnage d'erreur après l'expiration de l'intervalle de 14 jours. You activate error sampling when you <a href="../features/manage-datasources.md#create-data-source"> create an inbound data source</a> or by checking the <b><span class="uicontrol"> Error Sampling</span></b> check box from the <span class="wintitle"> Data Source Settings</span> section of an existing inbound data source. </p> <p>L'échantillonnage d'erreurs est un processus exigeant un calcul. Par conséquent, il renvoie uniquement les 10 premières erreurs pour chaque catégorie d'erreur. Elle n'est pas conçue pour renvoyer toutes les erreurs contenues dans une source de données entrantes. Ces erreurs constituent un échantillon représentatif d'un groupe potentiellement plus important d'erreurs similaires. Examinez la totalité de votre fichier pour les types d'erreur signalés par ce rapport, reformatez le fichier et envoyez-le à nouveau. </p> <p>See <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> Inbound Data File Contents: Syntax, Variables, and Examples</a> for more information about how to properly format an data file for an inbound data source. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Error Report Bar Chart {#error-report-bar-chart}

Le rapport d&#39;erreur graphique les taux de réussite et d&#39;échec du traitement d&#39;enregistrement dans un graphique à barres empilées, comme illustré dans l&#39;exemple suivant. Le graphique est interactif. Un clic sur une barre affiche des mesures récapitulatives pour cette journée dans un tableau sous le graphique.

![](assets/stacked-graph.png)

## Error Report Tables {#error-report-tables}

Le rapport d&#39;erreur affiche les données tabulaires sous le graphique à barres. Le tableau présente les taux de réussite et d&#39;échec ainsi que les totaux et les pourcentages.

**Enregistrements réussis et échecs**

Cette vue par défaut indique le nombre de fréquences du total des enregistrements dans votre rapport et inclut une ventilation des erreurs par type d&#39;erreur.

![](assets/success-failure.png)

**Totaux et pourcentages**

Click **[!UICONTROL Totals & Percentages]** to see what % of your files were processed successfully.

![](assets/totals-percentages.png)

## Error Sampling Report for 14 Days {#error-reporting-14-days}

Avec l&#39;échantillonnage d&#39;erreur actif, le rapport présente les 10 erreurs principales pour chaque type d&#39;erreur. Cliquez sur un bouton d&#39;erreur en haut du rapport pour afficher chaque jeu de données échantillonnées.

>[!NOTE]
>
>Le rapport ne met pas en évidence les erreurs d&#39;enregistrement avec cette version actuelle. To find and fix file errors, you should review the results and compare those to the specifications in the [Inbound Data File Contents](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) documentation.

![](assets/error-samples.png)

## Receive E-mail Notifications {#receive-email-notifications}

Vous pouvez ajouter les adresses électroniques des destinataires qui doivent être avertis de l&#39;état des fichiers entrants transférés. Notez que vous pouvez sélectionner différents destinataires pour différentes sources de données.

![](assets/mail-notifications.png)

## Create an Onboarding Status Report {#create-onboard-status-report}

A [!UICONTROL Sample Error Report] returns the number records in a data source were processed successfully and how many failed. Follow these steps to generate a [!UICONTROL Sample Error Report].

<!-- 

create-onboarding-status-report.xml

 -->


1. Go to **[!UICONTROL Analytics > Onboarding Status Report]**. Recherchez une source de données ou choisissez-en une dans la liste.

2. Sélectionnez une plage de dates. Les options incluent :

   * Ensemble d&#39;intervalles de rapport fixes.
   * Widgets Calendrier vous permettant de créer une plage de dates personnalisée.

3. Cliquez sur **[!UICONTROL OK]**.

## Onboarding Status Report Terms and Definitions {#report-terms-conditions}

Guide de référence pour les étiquettes et les termes utilisés dans ce rapport.

<table id="table_1D44A2E6B4C847848B818190DD336841"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Terme </th> 
   <th colname="col2" class="entry"> Définition </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Fichier de synchronisation des données - nom</b> </p> </td> 
   <td colname="col2"> <p>Lists files that <span class="keyword"> Audience Manager</span> received and processed from you selected inbound data source. </p> <p>Le traitement du fichier échoue si le fichier - nom est mal formaté. File name requirements vary depending on how you send this data to <span class="keyword"> Audience Manager</span>. Delivery methods include <span class="keyword"> Amazon S3</span> and FTP. Pour obtenir des instructions sur la manière de nommer vos fichiers, voir : </p> <p> 
     <ul id="ul_9A32906A14CA41C5AED0E13930DB31BA"> 
      <li id="li_A5A0E6ED711D4002B52092619F87C7D6"> <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md"> Exigences en matière de nom Amazon S3 pour les fichiers de données entrants </a> </li> 
      <li id="li_9590241AEC0C482D91C64DB760B32B0D"> <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md"> Exigences en matière de nom FTP pour les fichiers de données entrants </a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Erreurs de format</b> </p> </td> 
   <td colname="col2"> <p>Indique le nombre d'enregistrements ayant échoué au traitement, car ils ne correspondaient pas à la syntaxe ou aux exigences de formatage. See <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> Inbound Data File Contents: Syntax, Variables, and Examples</a> for information on how to format your data. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>ID AAM non valide</b> </p> </td> 
   <td colname="col2"> <p>Lists the number of improperly formatted <span class="keyword"> Audience Manager</span> user IDs (UUID). En règle générale, cela indique les ID : </p> 
    <ul id="ul_8304250E8F0F44918A50CF9D8D8D1F83"> 
     <li id="li_B100B4C2623B4E099E022869A4978357">Ne correspondait pas au format attendu à 38 chiffres. </li> 
     <li id="li_44E8A9AD13174A20A5742E56ED786634">Contient des caractères alphabétiques. Les ID ne doivent être que des nombres. </li> 
    </ul> </td> 
  </tr>

<tr> 
   <td colname="col1"> <p> <b>ID de périphérique non valide</b> </p> </td> 
   <td colname="col2"> <p>Indique le nombre d'ID de périphérique global mal formatés. See <a href="../reference/ids-in-aam.md">Index of IDs in Audience Manager</a> and <a href="../features/global-data-sources.md">Global Data Sources</a>  for details on how device IDs should be formatted and what global data sources you should use, based on the device type.</p>
  <p>La section d'échantillonnage d'erreur du rapport contient des informations détaillées sur les ID de périphérique non valides, tels que :</p>
   <ul>
    <li>L'ID de source de données correspondant à l'ID de périphérique non valide ;</li>
    <li>ID de périphérique non valide ;</li>
    <li>Type d'ID de périphérique attendu, basé sur la source de données.</li>
   </ul>
  </tr>



<tr> 
   <td colname="col1"> <p> <b>Aucun ID AAM correspondant</b> </p> </td> 
   <td colname="col2"> <p>These are onboarded IDs <span class="keyword"> Audience Manager</span> cannot match to an existing ID. Onboarded IDs can have this status when <span class="keyword"> Audience Manager</span> has not yet performed an ID sync or it still can't match the ID even after a synch. </p> <p>In the case of unmatched mobile IDs, <span class="keyword"> Audience Manager</span> will: </p> 
    <ul id="ul_B0D6AF9EB27D4017B35E36824B403879"> 
     <li id="li_D141000A50D3463182CBA4571DCC5373">Continuez à stocker et essayez de synchroniser cet identifiant. </li> 
     <li id="li_2EFCEE716F254ABCBC5FBF749B7564E6">Record it as a <span class="wintitle"> Stored Record</span> in the report if the ID cannot be synched. </li> 
    </ul> <p>Si votre fichier intégré contient des ID mobiles, vous pouvez considérer ces nombres légèrement plus légèrement que les autres mesures. Elles n'affecteront pas les taux de réussite et de correspondance des fichiers suivants. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Aucune caractéristique réalisée</b> </p> </td> 
   <td colname="col2"> <p>Lists traits that <span class="keyword"> Audience Manager</span> cannot match to an onboarded trait. Il peut s'agir du résultat de : </p> 
    <ul id="ul_43619035AB6641B6949302FB50BDB5B1"> 
     <li id="li_D4C6306BF2B143198108702B309CE8CF">Caractéristiques mal formatées dans votre fichier de données entrantes. For on how to format your data file, see <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> Inbound Data File Contents: Syntax, Variables, and Examples</a>. </li> 
     <li id="li_A1C708A007D24EE09B7C629AFC6E43C3">Traits that have not yet been defined in <span class="keyword"> Audience Manager</span>. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Pourcentage réussi</b> </p> </td> 
   <td colname="col2"> <p>pourcentage d'enregistrements stockés dans votre fichier. Pourcentage de réussite = enregistrements traités/nombre d'enregistrements dans un fichier. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Enregistrements reçus</b> </p> </td> 
   <td colname="col2"> <p>Nombre total d'enregistrements reçus. Dans la plupart des cas, ce nombre doit correspondre au nombre total d'enregistrements (lignes) dans le fichier de données entrantes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Enregistrements stockés</b> </p> </td> 
   <td colname="col2"> <p>Nombre d'enregistrements stockés avec succès. Because of file format errors, some of the records received may not be stored by <span class="keyword"> Audience Manager</span>. Le nombre d'enregistrements stockés peut être inférieur au nombre d'enregistrements reçus. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Caractéristiques générées totales</b> </p> </td> 
   <td colname="col2"> <p>The number of traits for all users across all inbound files that get stored in the <span class="keyword"> Audience Manager</span> platform. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Total des signaux inutilisés</b> </p> </td> 
   <td colname="col2"> <p>Nombre total de signaux inutilisés reçus dans le rapport. Ce total est basé sur le nombre total d'enregistrements enregistrés. </p> <p>See <a href="../reporting/dynamic-reports/unused-signals.md"> Unused Signals Report</a> for more information. </p> </td> 
  </tr> 
 </tbody> 
</table>
