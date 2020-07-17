---
description: Le rapport État de l’intégration vérifie les taux de réussite et d’échec du traitement des enregistrements dans vos fichiers de source de données entrants. Ce rapport affiche les données dans un graphique à barres interactif et fournit des mesures de synthèse sous forme de tableau. Il comporte également une option qui échantillonne les fichiers pendant une période fixe et affiche les erreurs les plus courantes pour chaque type d’erreur. Vous pouvez trouver ce rapport dans Analytics > Rapport d’état de l’intégration. Ce rapport est également disponible lorsque vous créez une source de données entrante.
seo-description: Le rapport État de l’intégration vérifie les taux de réussite et d’échec du traitement des enregistrements dans vos fichiers de source de données entrants. Ce rapport affiche les données dans un graphique à barres interactif et fournit des mesures de synthèse sous forme de tableau. Il comporte également une option qui échantillonne les fichiers pendant une période fixe et affiche les erreurs les plus courantes pour chaque type d’erreur. Vous pouvez trouver ce rapport dans Analytics > Rapport d’état de l’intégration. Ce rapport est également disponible lorsque vous créez une source de données entrante.
seo-title: Rapport d’état de l’intégration
solution: Audience Manager
title: Rapport d’état de l’intégration
uuid: 6ca8a90a-436b-4fce-adf1-48f3b96b3ed2
feature: inbound and outbound reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '1498'
ht-degree: 7%

---


# Rapport d’état de l’intégration{#onboarding-status-report-about}

Le rapport État de l’intégration vérifie les taux de réussite et d’échec du traitement des enregistrements dans vos fichiers de source de données entrants. Ce rapport affiche les données dans un graphique à barres interactif et fournit des mesures de synthèse sous forme de tableau. Il comporte également une option qui échantillonne les fichiers pendant une période fixe et affiche les erreurs les plus courantes pour chaque type d’erreur. Vous pouvez trouver ce rapport dans Analytics > Rapport d’état de l’intégration. Ce rapport est également disponible lorsque vous créez une source de données entrante.

>[!NOTE]
>
>Seuls les utilisateurs disposant de droits d’administrateur peuvent afficher ce rapport dans l’interface utilisateur de l’Audience Manager. Vous pouvez demander à des utilisateurs non administrateurs d’être informés de l’état des fichiers entrants téléchargés en ajoutant leurs courriels au rapport. Voir [Recevoir des notifications](/help/using/reporting/onboarding-status-report.md#receive-email-notifications)par courrier électronique.

## Rapport d&#39;état de l&#39;intégration : A propos {#onboarding-status-about}

The [!UICONTROL Onboarding Status Report] checks success and failure rates for processing records in your inbound data source files. Ce rapport affiche les données dans un graphique à barres interactif et fournit des mesures de synthèse sous forme de tableau. Il comporte également une option qui échantillonne les fichiers pendant une période fixe et affiche les erreurs les plus courantes pour chaque type d’erreur. Vous pouvez trouver ce rapport dans **[!UICONTROL Analytics > Onboarding Status Report]**. Ce rapport est également disponible lorsque vous créez une source de données entrante.

## Rapports d’erreur et échantillonnage d’erreurs {#error-reporting-sampling}

Le rapports d&#39;erreur et l&#39;échantillonnage d&#39;erreurs sont deux fonctions distinctes du [!UICONTROL Onboarding Status] rapport.

<table id="table_4706D891D4C545E8BF9D8A0CC052CC48"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fonctionnalité </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Rapports d’erreur</b> </p> </td>
   <td colname="col2"> <p>Le rapports d’erreurs vous montre les taux de réussite et d’échec du nombre d’enregistrements traités dans une source de données entrante. Il renvoie des données sous la forme d’un graphique à barres empilées interactif et sous forme de mesures récapitulatives dans des tableaux situés sous le graphique. </p> <p>Le rapports d’erreur est automatique. Il s’exécute en continu pour toutes vos sources de données entrantes. Elle renvoie des données basées sur la plage d’intervalles de temps prédéfinis ou sur un intervalle de temps personnalisé que vous avez défini avec un widget de calendrier. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Echantillonnage d’erreur</b> </p> </td>
   <td colname="col2"> <p>L’échantillonnage d’erreurs analyse le contenu de vos fichiers de données et renvoie les 10 erreurs les plus courantes pour chaque type d’erreur. Les erreurs de vos fichiers de données entrants empêchent le traitement d’enregistrements individuels. Utilisez ce rapport comme outil de dépannage pour réduire le nombre d'erreurs de fichier et améliorer les taux de traitement. </p> <p>Vous devez activer manuellement l’échantillonnage des erreurs. Il court pendant 14 jours à partir du jour de l'activation et s'éteint ensuite. Vous pouvez réactiver l’échantillonnage d’erreurs après l’expiration de l’intervalle de 14 jours. Vous activez l’échantillonnage d’erreurs lorsque vous <a href="../features/manage-datasources.md#create-data-source"> créez une source</a> de données entrantes ou en cochant la case <b><span class="uicontrol"> Echantillonnage</span></b> d’erreurs dans la section Paramètres <span class="wintitle"></span> de la source de données d’une source de données entrante existante. </p> <p>L’échantillonnage d’erreurs est un processus exigeant sur le plan informatique. Par conséquent, elle ne renvoie que les 10 premières erreurs pour chaque catégorie d’erreur. Il n’est pas conçu pour renvoyer toutes les erreurs contenues dans une source de données entrante. Ces erreurs constituent un échantillon représentatif d’un groupe potentiellement plus important d’erreurs similaires. Examinez l'intégralité du fichier pour identifier les types d'erreurs signalés par ce rapport, reformétez le fichier et renvoyez-le. </p> <p>Voir <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> Contenu du fichier de données entrantes : Syntaxe, variables et exemples</a> pour plus d’informations sur la manière de formater correctement un fichier de données pour une source de données entrante. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Graphique à barres de rapports d’erreurs {#error-report-bar-chart}

Le rapport d’erreurs présente sous forme de graphique à barres empilées les taux de réussite et d’échec du traitement des enregistrements, comme indiqué dans l’exemple suivant. Le graphique est interactif. Cliquez sur une barre pour afficher des mesures récapitulatives pour cette journée dans un tableau sous le graphique.

![](assets/stacked-graph.png)

## Tableaux des rapports d’erreurs {#error-report-tables}

Le rapport d’erreur affiche des données tabulaires sous le graphique à barres. Le tableau présente les taux de réussite et d’échec ainsi que les totaux et les pourcentages.

**Enregistrements réussis et échecs**

Cette vue par défaut vous montre le nombre de fréquences des enregistrements totaux dans votre rapport et inclut une ventilation des erreurs par type d&#39;erreur.

![](assets/success-failure.png)

**Totaux et pourcentages**

Cliquez sur **[!UICONTROL Totals & Percentages]** pour afficher le pourcentage de vos fichiers traités avec succès.

![](assets/totals-percentages.png)

## Rapport d’échantillonnage d’erreurs pendant 14 jours {#error-reporting-14-days}

L&#39;échantillonnage des erreurs étant actif, le rapport vous montre les 10 erreurs principales pour chaque type d&#39;erreur. Cliquez sur un bouton de type d’erreur en haut du rapport pour afficher chaque ensemble de données échantillonnées.

>[!NOTE]
>
>Le rapport ne met pas en évidence les erreurs d’enregistrement de cette version actuelle. Pour rechercher et corriger des erreurs de fichier, vous devez examiner les résultats et les comparer aux spécifications de la documentation Contenu [du fichier de données](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) entrant.

![](assets/error-samples.png)

## Recevoir des notifications par courrier électronique {#receive-email-notifications}

Vous pouvez ajouter les adresses de messagerie des destinataires que vous souhaitez être averti de l’état des fichiers entrants téléchargés. Notez que vous pouvez sélectionner différents destinataires pour différentes sources de données.

![](assets/mail-notifications.png)

## Création d’un rapport d’état d’intégration {#create-onboard-status-report}

Un [!UICONTROL Sample Error Report] renvoie le nombre d&#39;enregistrements d&#39;une source de données traités avec succès et le nombre d&#39;échecs. Pour générer un [!UICONTROL Sample Error Report]fichier, procédez comme suit.

<!-- 

create-onboarding-status-report.xml

 -->


1. Allez à **[!UICONTROL Analytics > Onboarding Status Report]**. Recherchez une source de données ou choisissez-en une dans la liste.

2. Sélectionnez une plage de dates. Les options incluent :

   * Ensemble d’intervalles de rapport fixes.
   * Widgets de calendrier qui vous permettent de créer une plage de dates personnalisée.

3. Cliquez sur **[!UICONTROL OK]**.

## Termes et définitions du rapport d’état d’intégration {#report-terms-conditions}

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
   <td colname="col1"> <p> <b>Nom du fichier de synchronisation des données</b> </p> </td> 
   <td colname="col2"> <p>Liste les fichiers <span class="keyword"> d’Audience Manager</span> reçus et traités à partir de la source de données entrantes sélectionnée. </p> <p>Le traitement des fichiers échoue si le nom de fichier n'est pas correctement formaté. Les exigences en matière de nom de fichier varient selon la manière dont vous envoyez ces données à <span class="keyword"> l’Audience Manager</span>. Les méthodes de Diffusion incluent <span class="keyword"> Amazon S3</span> et FTP. Pour obtenir des instructions sur la manière de nommer vos fichiers, voir : </p> <p> 
     <ul id="ul_9A32906A14CA41C5AED0E13930DB31BA"> 
      <li id="li_A5A0E6ED711D4002B52092619F87C7D6"> <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md"> Exigences en matière de nom Amazon S3 pour les fichiers de données entrants </a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Erreurs de format</b> </p> </td> 
   <td colname="col2"> <p>Liste le nombre d'enregistrements dont le traitement a échoué car ils ne correspondaient pas à la syntaxe ou au formatage requis. Voir <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> Contenu du fichier de données entrantes : Syntaxe, Variables et Exemples</a> pour plus d’informations sur la manière de formater vos données. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>ID AAM non valide</b> </p> </td> 
   <td colname="col2"> <p>Liste le nombre d’ID d’utilisateur d’ <span class="keyword"> Audience Manager</span> mal formatés (UUID). En règle générale, cela indique les identifiants : </p> 
    <ul id="ul_8304250E8F0F44918A50CF9D8D8D1F83"> 
     <li id="li_B100B4C2623B4E099E022869A4978357">Ne correspondait pas au format de 38 chiffres attendu. </li> 
     <li id="li_44E8A9AD13174A20A5742E56ED786634">Contient des caractères alphabétiques. Les identifiants doivent être des nombres uniquement. </li> 
    </ul> </td> 
  </tr>

<tr> 
   <td colname="col1"> <p> <b>ID de périphérique non valide</b> </p> </td> 
   <td colname="col2"> <p>Liste le nombre d’ID de périphérique global mal formatés. Voir <a href="../reference/ids-in-aam.md">Index des identifiants dans les sources</a> de données <a href="../features/global-data-sources.md">globales et d’Audience Manager</a> pour en savoir plus sur la manière dont les identifiants de périphérique doivent être formatés et sur les sources de données globales à utiliser, en fonction du type de périphérique.</p>
  <p>La section d'échantillonnage des erreurs du rapport contient des informations détaillées sur les ID de périphérique non valides, telles que :</p>
   <ul>
    <li>ID de source de données correspondant à l'ID de périphérique non valide ;</li>
    <li>ID de périphérique non valide ;</li>
    <li>Type d’ID de périphérique attendu, en fonction de la source de données.</li>
   </ul>
  </tr>



<tr> 
   <td colname="col1"> <p> <b>Aucun ID AAM correspondant</b> </p> </td> 
   <td colname="col2"> <p>Il s’agit d’identifiants embarqués <span class="keyword"> dont</span> l’Audience Managerne peut pas correspondre à un identifiant existant. Les identifiants intégrés peuvent avoir ce statut lorsque <span class="keyword"> l’Audience Manager</span> n’a pas encore effectué de synchronisation des identifiants ou qu’elle ne peut toujours pas correspondre à l’identifiant, même après une synchronisation. </p> <p>Dans le cas d’identifiants de téléphonie mobile inégalés, <span class="keyword"> l’Audience Manager</span> : </p> 
    <ul id="ul_B0D6AF9EB27D4017B35E36824B403879"> 
     <li id="li_D141000A50D3463182CBA4571DCC5373">Continuez à stocker cet identifiant et essayez de le synchroniser. </li> 
     <li id="li_2EFCEE716F254ABCBC5FBF749B7564E6">Enregistrez-le comme enregistrement <span class="wintitle"></span> stocké dans le rapport si l'ID ne peut pas être synchronisé. </li> 
    </ul> <p>Si votre fichier intégré contient des identifiants mobiles, vous pouvez traiter ces chiffres un peu plus légèrement que les autres mesures. Elles n’affectent pas les taux de réussite et de correspondance des fichiers suivants. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Aucun trait n'a été trouvé</b> </p> </td> 
   <td colname="col2"> <p>Caractéristiques de Liste que <span class="keyword"> l’Audience Manager</span> ne peut pas correspondre à une caractéristique intégrée. Cela pourrait être le résultat de : </p> 
    <ul id="ul_43619035AB6641B6949302FB50BDB5B1"> 
     <li id="li_D4C6306BF2B143198108702B309CE8CF">Caractéristiques mal formatées dans votre fichier de données entrant. Pour savoir comment formater votre fichier de données, voir Contenu du fichier de données <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> entrantes : Syntaxe, variables et exemples</a>. </li> 
     <li id="li_A1C708A007D24EE09B7C629AFC6E43C3">Caractéristiques qui n’ont pas encore été définies en <span class="keyword"> Audience Manager</span>. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Pourcentage de réussite</b> </p> </td> 
   <td colname="col2"> <p>Pourcentage d’enregistrements de votre fichier qui ont été stockés avec succès. Pourcentage de succès = enregistrements traités / nombre d'enregistrements dans un fichier. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Enregistrements reçus</b> </p> </td> 
   <td colname="col2"> <p>Nombre total d'enregistrements reçus. Dans la plupart des cas, ce nombre doit correspondre au nombre total d’enregistrements (lignes) dans votre fichier de données entrant. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Enregistrements stockés</b> </p> </td> 
   <td colname="col2"> <p>Nombre d'enregistrements enregistrés avec succès. En raison d'erreurs de format de fichier, certains enregistrements reçus peuvent ne pas être stockés par <span class="keyword"> Audience Manager</span>. Le nombre d'enregistrements stockés peut être inférieur au nombre d'enregistrements reçus. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Traits totaux réalisés</b> </p> </td> 
   <td colname="col2"> <p>Nombre de caractéristiques pour tous les utilisateurs dans tous les fichiers entrants stockés dans la plate-forme <span class="keyword"> d’Audience Manager</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Total des signaux inutilisés</b> </p> </td> 
   <td colname="col2"> <p>Nombre total de signaux inutilisés reçus dans le rapport. Ce total est basé sur le nombre total d'enregistrements enregistrés avec succès. </p> <p>Voir Rapport <a href="../reporting/dynamic-reports/unused-signals.md"> Signaux</a> inutilisés pour en savoir plus. </p> </td> 
  </tr> 
 </tbody> 
</table>
