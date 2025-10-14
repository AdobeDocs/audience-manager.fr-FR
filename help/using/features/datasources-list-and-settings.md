---
description: Affichez une liste de vos sources de données actuellement configurées, ajoutez de nouvelles sources de données et modifiez les sources existantes.
seo-description: View a list of your currently configured data sources, add new data sources, and edit existing sources.
seo-title: Data Sources List and Settings
solution: Audience Manager
title: Liste et paramètres des sources de données
uuid: 280a6acd-fef0-4737-a96d-9e22fbc8bfaf
feature: Data Sources
exl-id: c561d51e-e1dc-413e-bf24-13f04f10abe6
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '1070'
ht-degree: 0%

---

# Liste [!UICONTROL Data Sources] paramètres {#data-sources-list-and-settings}

Affichez une liste de vos [!UICONTROL data sources] actuellement configurés, ajoutez de nouveaux [!UICONTROL data sources] et modifiez les [!UICONTROL data sources] existants.

Vous pouvez également gérer les [!UICONTROL data sources] à l’aide de méthodes [!DNL API]. Pour plus d’informations, voir [&#x200B; Méthodes de l’API Data Source &#x200B;](../api/rest-api-main/aam-api-data-sources.md).

## Vue Liste [!UICONTROL Data Sources] {#list-view}

Le tableau de bord [!UICONTROL Data Sources] est un espace de travail centralisé pour la gestion des sources de données.

Le tableau de bord [!UICONTROL Data Sources] (**[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**) contient des fonctionnalités et des outils qui vous aident à :

* Affichez toutes vos [!UICONTROL data sources] existantes, y compris la description et le statut de chaque source de données, et indiquez s’il s’agit d’une [!UICONTROL Inbound], d’une [!UICONTROL Outbound], des deux ou d’une [!UICONTROL Shared Provider].
* Recherchez [!UICONTROL data sources] par nom.
* Créer, modifier et supprimer des [!UICONTROL data sources].

## Paramètres [!DNL Data Source] options de menu {#settings-menu-options}

Les paramètres des différentes sections de l’interface de gestion des [!UICONTROL Data Source] identifient vos [!DNL data source], déterminent la manière dont elles sont utilisées ou partagées, et vous permettent d’activer le rapport d’erreur pour le [!UICONTROL Onboarding Status Report].

## Détails de la [!DNL Data Source] {#details}

Outre les champs de texte, la section [!UICONTROL Data Source Details] contient les commandes et options répertoriées ci-dessous.

<table id="table_BF73919473D74444B38939A36C2F7CDA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre </th> 
   <th colname="col2" class="entry"> Options de menu </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Type d’ID de <b><span class="uicontrol"></span></b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_8ADCD4C5CBE543BEAA8FFE0462B74198"> 
      <li id="li_1FC97E2B3E2A4289AFB4A3C2F8E84FEF"> Cookie <b><span class="uicontrol"> : ID </span></b> cookie qui identifie un appareil. Sélectionnez cette option lorsque la source de données est un navigateur web ou lorsque vous utilisez des données anonymes ou des données qui ne peuvent pas être associées à une seule personne. </li> 
      <li id="li_4B2C9A7F2A5D49448E6D0A2B354D7EE7"> Identifiant Advertising de l’appareil <b><span class="uicontrol"></span></b> : identifiant de l’appareil mobile. Sélectionnez cette option lorsque la source de données est un appareil mobile ou un appareil compatible avec Internet. </li> 
      <li id="li_063F1B263B3B4D69B8880F7ACCB82450"> <b><span class="uicontrol"> sur l’ensemble des appareils </span></b> : identifiant authentifié fourni par le client. Sélectionnez cette option lorsque vous souhaitez créer : 
       <ul id="ul_D998B4081AD843C2B3B3E642DD011C1F"> 
        <li id="li_C9D2AF70603043D7BE9DF12FD494D7C7">Une source de données sur plusieurs appareils et créez une règle de fusion de profil <span class="wintitle"></span>. </li> 
        <li id="li_992BD05E2AFE454CAA4460DDEB2B839B">Source de données qui utilise des liens fournis par un graphique d’appareil tiers intégré à <span class="keyword"> Audience Manager</span>. </li> 
       </ul> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Définition de l’ID de <b><span class="uicontrol"></span></b> </p> </td> 
   <td colname="col2"> <p>Les options Définition de l’ID de <b><span class="uicontrol"></span></b> définissent la relation d’une source de données avec un ID utilisateur (UUID) Audience Manager<span class="keyword"> </span> et les appareils associés liés par un graphique d’appareil tiers intégré à <span class="keyword"> Audience Manager</span>. Les options incluent : </p> <p> 
     <ul id="ul_718ADABF0C0C44E29643C85C69CE294F"> 
      <li id="li_19936095319446698E9A577385CD2A80"> <b><span class="uicontrol"> une personne :</span></b> ID utilisé pour définir une seule personne. Cet identifiant peut être mappé à plusieurs identifiants <span class="keyword"> Audience Manager</span>. </li> 
      <li id="li_3D939AFF34654D618A05D2603F34462D"> Ménage <b><span class="uicontrol"> : </span></b> identifiant utilisé pour définir un groupe de personnes. Cet identifiant peut être mappé à plusieurs identifiants Audience Manager. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Data Export Controls] {#export-controls}

Les [&#x200B; Contrôles d’exportation de données &#x200B;](../features/data-export-controls.md) sont des règles de classification facultatives que vous pouvez appliquer à un [!UICONTROL data source] et à un [!UICONTROL destination]. Elles vous empêchent d’envoyer des données à un [!UICONTROL destination] lorsque cette action enfreint un accord d’utilisation ou de confidentialité des données. Ignorez cette section si vous n’utilisez pas [!UICONTROL Data Export Controls].

>[!IMPORTANT]
>
>Les restrictions d’exportation ne fonctionnent pas, sauf si vous définissez un libellé d’exportation correspondant sur un [!UICONTROL destination].

Les options incluent :

* **[!UICONTROL No Restriction]**
* **[!UICONTROL Cannot be tied to personally identifiable information]**
* **[!UICONTROL Cannot be used for on-site ad targeting]**
* **[!UICONTROL Cannot be used for off-site ad targeting]**
* **[!UICONTROL Cannot be used for on-site personalization]**

## [!UICONTROL Data Source] Settings {#data-source-settings}

Le [!UICONTROL Data Source Settings] contient les commandes et options répertoriées ci-dessous. Certains de ces paramètres comportent des sous-options et des éléments de menu supplémentaires que vous pouvez sélectionner pour modifier une source de données.

### [!UICONTROL Inbound Data Source] Settings

Cochez la case **[!UICONTROL Inbound]** lorsque la source de données est conçue pour recevoir des données entrantes. Si vous cochez la case **[!UICONTROL Inbound]**, deux groupes de contrôles supplémentaires sont présentés ci-dessous.

>[!NOTE]
>
>La case à cocher **[!UICONTROL Inbound]** est uniquement destinée à afficher ou masquer les commandes [!UICONTROL data source] décrites ci-dessous. La désactivation de l’option **[!UICONTROL Inbound]** n’affecte en rien l’ingestion des données. Vos données intégrées seront traitées quelle que soit l’option cochée.

<table id="table_B2825B7BE0DB4665B47C589A3787CD93"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre </th> 
   <th colname="col2" class="entry"> Options de menu </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Type d’ID de <b><span class="uicontrol"></span></b> </p> </td> 
   <td colname="col2"> <p>L'option <b><span class="uicontrol"> Inbound</span></b> nécessite un type d'identifiant. Les options incluent : </p> <p> 
     <ul id="ul_3BC963CE378B4F6CB1861643A4541634"> 
      <li id="li_B86C5E7847424A2B9C094DF02741DDB8"> <b><span class="uicontrol"> ID client </span></b> : identifie les données entrantes avec un ID client. </li> 
      <li id="li_AD8E440436314902A794CDB11A3D657F"> <b><span class="uicontrol"> Audience Manager ID</span></b> : identifie les données entrantes avec un Audience Manager<span class="keyword"> ID </span>. </li> 
      <li id="li_B56608334DDA453B9E4E88E53DAF92FA"> <b><span class="uicontrol"> Experience Cloud ID</span></b> : identifie les données entrantes avec un Experience Cloud<span class="keyword"> ID </span>. Voir Cookies <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html?lang=fr" format="https" scope="external"> et Experience Cloud ID</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Dépannage du format de fichier <b><span class="uicontrol"></span></b> </p> </td> 
   <td colname="col2"> <p>Sélectionnez <b><span class="uicontrol"> Activer l’échantillonnage des erreurs de fichier</span></b> lorsque vous devez résoudre les problèmes liés au traitement des fichiers entrants. Cette fonctionnalité génère un exemple de rapport d’erreurs qui indique les erreurs de format de fichier et de syntaxe. </p> <p>Consultez <a href="../reporting/onboarding-status-report.md#onboarding-status-about"> rapport de statut d’intégration : À propos </a> pour plus d’informations sur les rapports d’erreurs et l’échantillonnage d’erreurs. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Autres paramètres de [!UICONTROL Data Source]

<table id="table_82FEFA8DC8294FA18FB4C17F02DF5152"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre </th> 
   <th colname="col2" class="entry"> Sélectionner le moment </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Sortant</span></b> </p> </td> 
   <td colname="col2"> <p>Votre source de données envoie des données vers une destination. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Partage de <b><span class="uicontrol"> activé</span></b> </p> </td> 
   <td colname="col2"> <p>Votre source de données peut être partagée avec d’autres partenaires. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> utiliser comme profil authentifié</span></b> </p> </td> 
   <td colname="col2"> <p>La source de données entre appareils contient un identifiant authentifié. Un identifiant authentifié est collecté et synchronisé avec un identifiant Audience Manager<span class="keyword"> </span> lors d’un événement d’authentification (par exemple, un utilisateur se connecte sur site, in-app, etc.). L’identifiant authentifié peut être utilisé pour intégrer des données provenant d’autres sources qui stockent cet identifiant. Il peut également être utilisé pour lier plusieurs identifiants d’appareil dans <span class="wintitle"> lien de profil</span>. </p> <p>Cette option expose un champ de texte qui permet de renommer la source de données avec un alias. Si vous utilisez un alias, ce nouveau nom remplace le nom de la source de données et apparaît dans les <span class="wintitle"> Options de profil authentifié</span> lorsque vous <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> créer une règle de fusion de profils</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Utiliser comme graphique d’appareil</span></b> </p> </td> 
   <td colname="col2"> <p>Crée une source de données sous forme de graphique d’appareil que vous pouvez fournir à d’autres clients <span class="keyword"> Audience Manager</span>. Avant de sélectionner cette option, indiquez à votre consultant <span class="keyword"> Audience Manager</span> avec quels clients ce <span class="wintitle"> Data Source</span> doit être partagé. Votre consultant devra approvisionner ces entreprises par le biais de nos processus internes. </p> <p>Cette option expose un champ de texte qui permet de renommer la source de données avec un alias. Si vous utilisez un alias, ce nouveau nom remplace le nom de la source de données et apparaît dans les Options de l’appareil <span class="wintitle"></span> lorsque vous <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> créer une règle de fusion de profils</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Partager les identifiants de visiteur ou d’appareil associés avec des clients Audience Manager spécifiques</span></b> </p> </td> 
   <td colname="col2"> <p>La source de données entre appareils contient des identifiants provenant d’un graphique d’appareil. Un graphique d’appareil est un ensemble d’identifiants qui correspondent à un ou plusieurs identifiants Audience Manager<span class="keyword"> </span> à un cluster. Ce groupe représente généralement une personne ou un groupe familial plus important. Disponible uniquement pour les comptes répertoriés comme « Fournisseur de données ». </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Partager les ID de visiteur ou d’appareil associés sur la plateforme Audience Manager</span></b> </p> </td> 
   <td colname="col2"> <p>Votre source de données contient des identifiants visiteur ou appareil qui peuvent être partagés avec d’autres solutions <span class="keyword"> Experience Cloud</span>. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> Conservation <b><span class="uicontrol"> données pour les ID de client inactifs</span></b> </p> </td> 
   <td colname="col2"> <p>Permet de définir la période de conservation des données pour les ID de client inactifs. Cela détermine la durée pendant laquelle Audience Manager conserve les ID de client dans notre base de données après leur dernière consultation sur la plateforme Audience Manager.</p> <p>La valeur par défaut est de 24 mois (720 jours). La valeur minimale que vous pouvez définir est de 1 mois et la valeur maximale est de 5 ans. Notez que tous les mois comptent comme 30 jours.</p> <p>Audience Manager exécute un processus qui supprime les ID de client inactifs une fois par semaine, conformément à la conservation des données que vous avez définie pour les ID de client inactifs.</p> <p>Audience Manager exécute un processus qui supprime les ID de client inactifs une fois par semaine, conformément à la conservation des données que vous avez définie pour les ID de client inactifs.</p> <p><b>Remarque</b> : ce contrôle est disponible uniquement pour les sources de données inter-appareils. Voir aussi Création d’<a href="../features/profile-merge-rules/merge-rules-start.md#settings"> Source de données sur l’ensemble des appareils </a>.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> des codes d’intégration de caractéristiques uniques</span></b> </p> </td> 
   <td colname="col2"> <p>Vous souhaitez que les deux caractéristiques provenant de la même source de données n’aient pas le même code d’intégration. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Codes D’Intégration De Segments Uniques</span></b> </p> </td> 
   <td colname="col2"> <p>Vous souhaitez appliquer le fait que deux segments provenant de la même source de données n’ont pas le même code d’intégration. </p> </td> 
  </tr>
 </tbody>
</table>
