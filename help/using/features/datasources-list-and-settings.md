---
description: Affichez la liste des sources de données actuellement configurées, ajoutez de nouvelles sources de données et modifiez les sources existantes.
seo-description: Affichez la liste des sources de données actuellement configurées, ajoutez de nouvelles sources de données et modifiez les sources existantes.
seo-title: Liste et paramètres des sources de données
solution: Audience Manager
title: Liste et paramètres des sources de données
uuid: 280 a 6 acd-fef 0-4737-a 96 d -9 e 22 fbc 8 bfaf
translation-type: tm+mt
source-git-commit: c785c07a1572e9968e62a1bc753d24780eda64c5

---


# Data Sources List and Settings {#data-sources-list-and-settings}

Affichez la liste des sources de données actuellement configurées, ajoutez de nouvelles sources de données et modifiez les sources existantes.

<!-- c_datasources.xml -->

You can also manage data sources using [!DNL API] methods. For more information, see [Data Source API Methods](../api/rest-api-main/aam-api-data-sources.md).

## Data Sources List View {#list-view}

[!UICONTROL Data Sources] Le tableau de bord est un espace de travail centralisé pour la gestion des sources de données.

<!-- c_datasources_list.xml -->

[!UICONTROL Data Sources] Le tableau de bord (**[!UICONTROL Audience Data]** &gt; **[!UICONTROL Data Sources]**) contient des fonctionnalités et des outils qui vous aident à :

* See all your existing data sources, including each data source's description, status, and whether it is [!UICONTROL Inbound], [!UICONTROL Outbound], both, or a [!UICONTROL Shared Provider].
* Recherchez les sources de données par nom.
* Créez, modifiez et supprimez des sources de données.

## Data Source Settings and Menu Options {#settings-menu-options}

The settings in the different sections of the [!UICONTROL Data Source] management interface identify your data source, determine how it is used or shared, and let you enable error reporting for the [!UICONTROL Onboarding Status Report].

## Data Source Details {#details}

<!-- datasource-settings-definitions.xml -->

In addition to text fields, the [!UICONTROL Data Source Details] section contains the controls and options listed below.

<table id="table_BF73919473D74444B38939A36C2F7CDA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre </th> 
   <th colname="col2" class="entry"> Options de menu </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Type d’ID</span></b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_8ADCD4C5CBE543BEAA8FFE0462B74198"> 
      <li id="li_1FC97E2B3E2A4289AFB4A3C2F8E84FEF"> <b><span class="uicontrol"> Cookie</span></b>: ID de cookie identifiant un périphérique. Vous sélectionnez cela lorsque votre source de données est un navigateur Web ou lorsque vous travaillez avec des données anonymes ou des données qui ne peuvent pas être associées à une seule personne. </li> 
      <li id="li_4B2C9A7F2A5D49448E6D0A2B354D7EE7"> <b><span class="uicontrol"> ID de publication de périphérique</span></b>: Identifiant de périphérique mobile. Sélectionnez cette option lorsque votre source de données est un périphérique mobile ou un périphérique compatible avec Internet. </li> 
      <li id="li_063F1B263B3B4D69B8880F7ACCB82450"> <b><span class="uicontrol"> Cross Device</span></b>: Identifiant authentifié fourni par le client. Sélectionnez cette option lorsque vous souhaitez créer : 
       <ul id="ul_D998B4081AD843C2B3B3E642DD011C1F"> 
        <li id="li_C9D2AF70603043D7BE9DF12FD494D7C7">A cross-device data source and build a <span class="wintitle"> Profile Merge Rule</span>. </li> 
        <li id="li_992BD05E2AFE454CAA4460DDEB2B839B">A data source that uses links provided by the <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/" format="https" scope="external"> Adobe Experience Cloud Device Co-op</a> or another, third-party device graph that is integrated with <span class="keyword"> Audience Manager</span>. </li> 
       </ul> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Définition d'ID</span></b> </p> </td> 
   <td colname="col2"> <p>The <b><span class="uicontrol"> ID Definition</span></b> options define the relationship a data source has to an <span class="keyword"> Audience Manager</span> user ID (UUID) and associated devices linked by the <span class="keyword"> Adobe Experience Cloud Device Co-op</span> or another, third-party device graph that is integrated with <span class="keyword"> Audience Manager</span>. Les options incluent : </p> <p> 
     <ul id="ul_718ADABF0C0C44E29643C85C69CE294F"> 
      <li id="li_19936095319446698E9A577385CD2A80"> <b><span class="uicontrol"> Personne :</span></b> ID utilisé pour définir une seule personne. This ID can be mapped to multiple <span class="keyword"> Audience Manager</span> IDs. </li> 
      <li id="li_3D939AFF34654D618A05D2603F34462D"> <b><span class="uicontrol"> Foyer :</span></b> ID utilisé pour définir un groupe de personnes. Cet ID peut être associé à plusieurs identifiants Audience Manager. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Contrôles des exportations de données {#export-controls}

[Les contrôles d'exportation de données](../features/data-export-controls.md) sont des règles de classification facultatives que vous pouvez appliquer à une source de données et à une destination. Elles vous empêchent d'envoyer des données à une destination lorsque cette action enfreint un accord de confidentialité ou d'utilisation des données. Skip this section if you do not use [!UICONTROL Data Export Controls].

>[!IMPORTANT]
>
>Les restrictions d'exportation ne fonctionnent que si vous définissez un libellé d'exportation correspondant sur une destination.

Les options incluent :

* **[!UICONTROL No Restriction]**
* **[!UICONTROL Cannot be tied to personally identifiable information]**
* **[!UICONTROL Cannot be used for on-site ad targeting]**
* **[!UICONTROL Cannot be used for off-site ad targeting]**
* **[!UICONTROL Cannot be used for on-site personalization]**

## Data Source Settings {#data-source-settings}

The [!UICONTROL Data Source Settings] contains the controls and options listed below. Certains de ces paramètres comportent des sous-options et des éléments de menu supplémentaires que vous pouvez sélectionner pour modifier une source de données.

### Paramètres de source de données entrants

Select the **[!UICONTROL Inbound]** check box when your data source is designed to receive inbound data. Selecting the **[!UICONTROL Inbound]** check box exposes 2 additional groups of controls described below.

<table id="table_B2825B7BE0DB4665B47C589A3787CD93"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre </th> 
   <th colname="col2" class="entry"> Options de menu </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Type d’ID</span></b> </p> </td> 
   <td colname="col2"> <p>The <b><span class="uicontrol"> Inbound</span></b> option requires an ID type. Les options incluent : </p> <p> 
     <ul id="ul_3BC963CE378B4F6CB1861643A4541634"> 
      <li id="li_B86C5E7847424A2B9C094DF02741DDB8"> <b><span class="uicontrol"> ID client</span></b>: Identifie les données entrantes avec un ID de client. </li> 
      <li id="li_AD8E440436314902A794CDB11A3D657F"> <b><span class="uicontrol"> ID Audience Manager</span></b>: Identifie les données entrantes avec un <span class="keyword"> identifiant Audience Manager</span> . </li> 
      <li id="li_B56608334DDA453B9E4E88E53DAF92FA"> <b><span class="uicontrol"> Experience Cloud ID</span></b>: Identifie les données entrantes avec un <span class="keyword"> ID</span> d'expérience. Voir <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external">Cookies et Experience Cloud ID</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Résolution des problèmes de format de fichier</span></b> </p> </td> 
   <td colname="col2"> <p>Select <b><span class="uicontrol"> Enable file error sampling</span></b> when you need to troubleshoot problems with inbound file processing. Cette fonctionnalité génère un exemple d'erreur qui illustre le format de fichier et les erreurs de syntaxe. </p> <p>See <a href="../reporting/onboarding-status-report.md#onboarding-status-about"> Onboarding Status Report: About</a> for information about error reporting and error sampling. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Autres paramètres de source de données

<table id="table_82FEFA8DC8294FA18FB4C17F02DF5152"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre </th> 
   <th colname="col2" class="entry"> Sélectionner lorsque </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Sortant</span></b> </p> </td> 
   <td colname="col2"> <p>Votre source de données envoie des données à une destination. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Partager activé</span></b> </p> </td> 
   <td colname="col2"> <p>Votre source de données peut être partagée avec d'autres partenaires. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Utiliser comme profil authentifié</span></b> </p> </td> 
   <td colname="col2"> <p>La source de données sur plusieurs périphériques contient un ID authentifié. An Authenticated ID is collected and synced to an <span class="keyword"> Audience Manager</span> ID during an authentication event (e.g, a user logs in on-site, in-app, etc.). L'ID authentifié peut être utilisé pour les données sur le site provenant d'autres sources qui stockent cet identifiant. It can also be used to link multiple device IDs in <span class="wintitle"> Profile Link</span>. </p> <p>Cette option expose un champ de texte qui vous permet de renommer la source de données avec un alias. If you use an alias, this new name overrides the data source name and appears in the <span class="wintitle"> Authenticated Profile Options</span> when you <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> create a Profile Merge rule</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Utilisation comme graphique de périphérique</span></b> </p> </td> 
   <td colname="col2"> <p>Creates a data source as a device graph which you can provide to other <span class="keyword"> Audience Manager</span> customers. Before you select this option, tell with your <span class="keyword"> Audience Manager</span> consultant which customers this <span class="wintitle"> Data Source</span> should be shared with. Votre consultant devra fournir ces entreprises au moyen de nos processus internes. </p> <p>Cette option expose un champ de texte qui vous permet de renommer la source de données avec un alias. If you use an alias, this new name overrides the data source name and appears in the <span class="wintitle"> Device Options</span> when you <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> create a Profile Merge rule</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Partage des identifiants de visiteur ou de périphérique associés avec des clients Audience Manager spécifiques</span></b> </p> </td> 
   <td colname="col2"> <p>La source de données sur plusieurs périphériques contient des ID d'un graphique de périphérique. A device graph is a collection of IDs which map to one or more <span class="keyword"> Audience Manager</span> IDs to a cluster. Cette grappe représente généralement une personne ou un groupe plus large. Disponible uniquement pour les comptes répertoriés comme fournisseur de données.  » » </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Partage des ID des visiteurs ou des périphériques associés à l'échelle de la plate-forme Audience Manager</span></b> </p> </td> 
   <td colname="col2"> <p>Your data source contains visitor or device IDs that can be shared across other <span class="keyword"> Experience Cloud</span> solutions. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Rétention des données pour les ID de client inactifs</span></b> </p> </td> 
   <td colname="col2"> <p>Permet de définir la période de rétention des données pour les ID de client inactifs. Ceci détermine la durée pendant laquelle Audience Manager conserve les ID de client dans notre base de données après leur dernière consultation sur la plate-forme Audience Manager.</p> <p>La valeur par défaut est de 24 mois (720 jours). La valeur minimale est de 1 mois et la valeur maximale est de 5 ans. Notez que nous comptons tous les mois sur 30 jours.</p> <p>Audience Manager exécute un processus qui supprime les identifiants client inactifs une fois par semaine, conformément à la rétention des données que vous avez définie pour les ID de client inactifs.</p> <p>Audience Manager exécute un processus qui supprime les identifiants client inactifs une fois par semaine, conformément à la rétention des données que vous avez définie pour les ID de client inactifs.</p> <p><b>Remarque</b>: Cette commande est disponible uniquement pour les sources de données inter-périphériques. See also, <a href="../features/profile-merge-rules/merge-rules-start.md#settings"> Create a Cross-Device Data Source </a>.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Codes d'intégration de caractéristiques uniques</span></b> </p> </td> 
   <td colname="col2"> <p>Vous souhaitez imposer que deux caractéristiques issues de la même source de données ne possèdent pas le même code d'intégration. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Codes d'intégration de segment uniques</span></b> </p> </td> 
   <td colname="col2"> <p>Vous souhaitez imposer que deux segments d'une même source de données ne possèdent pas le même code d'intégration. </p> </td> 
  </tr>
 </tbody>
</table>
