---
description: Affichez la liste de vos sources de données actuellement configurées, ajoutez de nouvelles sources de données et modifiez les sources existantes.
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

# [!UICONTROL Data Sources] Liste et paramètres {#data-sources-list-and-settings}

Affichez une liste de vos [!UICONTROL data sources] actuellement configurés, ajoutez de nouveaux [!UICONTROL data sources] et modifiez les [!UICONTROL data sources] existants.

Vous pouvez également gérer [!UICONTROL data sources] à l’aide des méthodes [!DNL API]. Pour plus d’informations, voir [Méthodes d’API Data Source](../api/rest-api-main/aam-api-data-sources.md).

## [!UICONTROL Data Sources] Mode Liste {#list-view}

Le tableau de bord [!UICONTROL Data Sources] est un espace de travail centralisé pour la gestion des sources de données.

Le tableau de bord [!UICONTROL Data Sources] (**[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**) contient des fonctionnalités et des outils qui vous aident à :

* Affichez tous les [!UICONTROL data sources] existants, y compris la description, l’état de chaque source de données et s’il s’agit de [!UICONTROL Inbound], [!UICONTROL Outbound], des deux ou d’un [!UICONTROL Shared Provider].
* Recherchez [!UICONTROL data sources] par nom.
* Créez, modifiez et supprimez [!UICONTROL data sources].

## [!DNL Data Source] Paramètres et options de menu {#settings-menu-options}

Les paramètres des différentes sections de l&#39;interface de gestion [!UICONTROL Data Source] identifient votre [!DNL data source], déterminent son utilisation ou son partage, et permettent d&#39;activer la création de rapports d&#39;erreur pour le [!UICONTROL Onboarding Status Report].

## [!DNL Data Source] Détails {#details}

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
   <td colname="col1"> <p> <b><span class="uicontrol"> Type d’ID</span></b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_8ADCD4C5CBE543BEAA8FFE0462B74198"> 
      <li id="li_1FC97E2B3E2A4289AFB4A3C2F8E84FEF"> <b><span class="uicontrol"> Cookie</span></b> : identifiant de cookie qui identifie un appareil. Vous pouvez le sélectionner lorsque votre source de données est un navigateur web ou lorsque vous utilisez des données anonymes ou des données qui ne peuvent pas être associées à une seule personne. </li> 
      <li id="li_4B2C9A7F2A5D49448E6D0A2B354D7EE7"> <b><span class="uicontrol"> Device Advertising ID</span></b> : identifiant de l’appareil mobile. Sélectionnez cette option lorsque votre source de données est un appareil mobile ou un appareil compatible Internet. </li> 
      <li id="li_063F1B263B3B4D69B8880F7ACCB82450"> <b><span class="uicontrol"> Cross Device</span></b> : identifiant authentifié fourni par le client. Sélectionnez cette option lorsque vous souhaitez créer : 
       <ul id="ul_D998B4081AD843C2B3B3E642DD011C1F"> 
        <li id="li_C9D2AF70603043D7BE9DF12FD494D7C7">Une source de données multi-appareils et créez une <span class="wintitle"> stratégie de fusion de profils</span>. </li> 
        <li id="li_992BD05E2AFE454CAA4460DDEB2B839B">Une source de données qui utilise les liens fournis par un graphique d’appareil tiers intégré à <span class="keyword"> Audience Manager</span>. </li> 
       </ul> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Définition d’ID</span></b> </p> </td> 
   <td colname="col2"> <p>Les options de <b><span class="uicontrol"> définition d’identifiant </span></b> définissent la relation qu’une source de données entretient avec un identifiant d’utilisateur (UUID) <span class="keyword"> d’Audience Manager </span> et les appareils associés liés par un graphique d’appareil tiers intégré à l’Audience Manager <span class="keyword"> </span>. Les options incluent : </p> <p> 
     <ul id="ul_718ADABF0C0C44E29643C85C69CE294F"> 
      <li id="li_19936095319446698E9A577385CD2A80"> <b><span class="uicontrol"> Personne : </span></b> ID utilisé pour définir une seule personne. Cet identifiant peut être mappé à plusieurs <span class="keyword"> identifiants d'Audience Manager</span>. </li> 
      <li id="li_3D939AFF34654D618A05D2603F34462D"> <b><span class="uicontrol"> Ménage : </span></b> ID utilisé pour définir un groupe de personnes. Cet identifiant peut être mappé à plusieurs identifiants d’Audience Manager. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Data Export Controls] {#export-controls}

[Les contrôles des exportations de données](../features/data-export-controls.md) sont des règles de classification facultatives que vous pouvez appliquer à un [!UICONTROL data source] et à un [!UICONTROL destination]. Elles vous empêchent d’envoyer des données à un [!UICONTROL destination] lorsque cette action enfreint un accord de confidentialité ou d’utilisation des données. Ignorez cette section si vous n’utilisez pas [!UICONTROL Data Export Controls].

>[!IMPORTANT]
>
>Les restrictions d’exportation ne fonctionneront pas, sauf si vous définissez une étiquette d’exportation correspondante sur un [!UICONTROL destination].

Les options incluent :

* **[!UICONTROL No Restriction]**
* **[!UICONTROL Cannot be tied to personally identifiable information]**
* **[!UICONTROL Cannot be used for on-site ad targeting]**
* **[!UICONTROL Cannot be used for off-site ad targeting]**
* **[!UICONTROL Cannot be used for on-site personalization]**

## [!UICONTROL Data Source] Paramètres {#data-source-settings}

[!UICONTROL Data Source Settings] contient les commandes et options répertoriées ci-dessous. Certains de ces paramètres comportent des sous-options et des éléments de menu supplémentaires que vous pouvez sélectionner pour modifier une source de données.

### [!UICONTROL Inbound Data Source] Paramètres

Cochez la case **[!UICONTROL Inbound]** lorsque votre source de données est conçue pour recevoir les données entrantes. La sélection de la case à cocher **[!UICONTROL Inbound]** expose 2 groupes de contrôles supplémentaires décrits ci-dessous.

>[!NOTE]
>
>La case à cocher **[!UICONTROL Inbound]** est uniquement destinée à afficher ou masquer les commandes [!UICONTROL data source] décrites ci-dessous. La désélection de l’option **[!UICONTROL Inbound]** n’a aucune incidence sur l’ingestion des données. Vos données intégrées seront traitées, quelle que soit cette option cochée.

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
   <td colname="col2"> <p>L’option <b><span class="uicontrol"> Inbound</span></b> nécessite un type d’ID. Les options incluent : </p> <p> 
     <ul id="ul_3BC963CE378B4F6CB1861643A4541634"> 
      <li id="li_B86C5E7847424A2B9C094DF02741DDB8"> <b><span class="uicontrol"> ID de client </span></b> : identifie les données entrantes avec un ID de client. </li> 
      <li id="li_AD8E440436314902A794CDB11A3D657F"> <b><span class="uicontrol"> ID d’Audience Manager</span></b> : identifie les données entrantes avec un ID <span class="keyword"> d’Audience Manager</span>. </li> 
      <li id="li_B56608334DDA453B9E4E88E53DAF92FA"> <b><span class="uicontrol"> ID Experience Cloud</span></b> : identifie les données entrantes avec un <span class="keyword"> ID Experience Cloud</span>. Voir <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies et ID Experience Cloud </a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Dépannage du format de fichier </span></b> </p> </td> 
   <td colname="col2"> <p>Sélectionnez <b><span class="uicontrol"> Activer l’échantillonnage des erreurs de fichier </span></b> lorsque vous devez résoudre les problèmes liés au traitement des fichiers entrants. Cette fonctionnalité génère un exemple de rapport d’erreur qui présente le format du fichier et les erreurs de syntaxe. </p> <p>Voir <a href="../reporting/onboarding-status-report.md#onboarding-status-about"> Rapport d’état de l’intégration : À propos de</a> pour plus d’informations sur le reporting des erreurs et l’échantillonnage des erreurs. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Autres paramètres [!UICONTROL Data Source]

<table id="table_82FEFA8DC8294FA18FB4C17F02DF5152"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre </th> 
   <th colname="col2" class="entry"> Sélectionner </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Sortant</span></b> </p> </td> 
   <td colname="col2"> <p>Votre source de données envoie des données vers une destination. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Partage activé</span></b> </p> </td> 
   <td colname="col2"> <p>Votre source de données peut être partagée avec d’autres partenaires. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Utilisation en tant que profil authentifié</span></b> </p> </td> 
   <td colname="col2"> <p>Votre source de données multi-appareils contient un ID authentifié. Un ID authentifié est collecté et synchronisé avec un ID <span class="keyword"> d’Audience Manager</span> lors d’un événement d’authentification (par exemple, un utilisateur se connecte sur site, dans l’application, etc.). L’ID authentifié peut être utilisé pour les données intégrées provenant d’autres sources qui stockent cet ID. Il peut également être utilisé pour lier plusieurs identifiants d’appareil dans <span class="wintitle"> Profile Link</span>. </p> <p>Cette option expose un champ de texte qui permet de renommer la source de données avec un alias. Si vous utilisez un alias, ce nouveau nom remplace le nom de la source de données et apparaît dans les <span class="wintitle"> Options de profil authentifié</span> lorsque vous <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> créez une règle de fusion de profils</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Utilisation comme graphique d’appareil</span></b> </p> </td> 
   <td colname="col2"> <p>Crée une source de données sous forme de graphique d’appareil que vous pouvez fournir à d’autres clients <span class="keyword"> d’Audience Manager</span>. Avant de sélectionner cette option, indiquez à votre consultant <span class="keyword"> Audience Manager</span> avec quels clients cette <span class="wintitle"> Source de données</span> doit être partagée. Votre consultant devra configurer ces entreprises par le biais de nos processus internes. </p> <p>Cette option expose un champ de texte qui permet de renommer la source de données avec un alias. Si vous utilisez un alias, ce nouveau nom remplace le nom de la source de données et apparaît dans les <span class="wintitle"> Options du périphérique</span> lorsque vous <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> créez une règle de fusion de profils</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Partage des identifiants de visiteur ou d’appareil associés avec des clients d’Audience Manager spécifiques</span></b> </p> </td> 
   <td colname="col2"> <p>Votre source de données multi-appareils contient les identifiants d’une représentation graphique des appareils. Un graphique d’appareil est un ensemble d’identifiants qui mappent à un ou plusieurs identifiants <span class="keyword"> d’Audience Manager</span> à une grappe. Ce groupe représente généralement une personne ou un groupe familial plus grand. Disponible uniquement pour les comptes répertoriés comme "Fournisseur de données". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Partager les identifiants de visiteur ou d’appareil associés sur la plateforme d’Audience Manager </span></b> </p> </td> 
   <td colname="col2"> <p>Votre source de données contient des identifiants de visiteur ou d’appareil qui peuvent être partagés entre d’autres solutions <span class="keyword"> Experience Cloud</span>. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Conservation des données pour les ID de client inactifs </span></b> </p> </td> 
   <td colname="col2"> <p>Permet de définir la période de conservation des données pour les ID de client inactifs. Cela détermine la durée pendant laquelle l’Audience Manager conserve les ID de client dans notre base de données après leur dernière consultation sur la plateforme d’Audience Manager.</p> <p>La valeur par défaut est de 24 mois (720 jours). La valeur minimale est de 1 mois et la valeur maximale est de 5 ans. Notez que nous comptabilisons tous les mois comme 30 jours.</p> <p>Audience Manager exécute un processus qui supprime les ID de client inactifs une fois par semaine, conformément à la rétention de données que vous avez définie pour les ID de client inactifs.</p> <p>Audience Manager exécute un processus qui supprime les ID de client inactifs une fois par semaine, conformément à la rétention de données que vous avez définie pour les ID de client inactifs.</p> <p><b>Remarque</b> : Ce contrôle est disponible uniquement pour les sources de données multi-appareils. Voir aussi <a href="../features/profile-merge-rules/merge-rules-start.md#settings"> Création d’une Source de données multi-appareils </a>.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Codes d’intégration de caractéristiques uniques</span></b> </p> </td> 
   <td colname="col2"> <p>Vous souhaitez imposer que deux caractéristiques de la même source de données ne possèdent pas le même code d’intégration. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Codes d’intégration de segment unique</span></b> </p> </td> 
   <td colname="col2"> <p>Vous souhaitez imposer que deux segments provenant de la même source de données ne comportent pas le même code d’intégration. </p> </td> 
  </tr>
 </tbody>
</table>
