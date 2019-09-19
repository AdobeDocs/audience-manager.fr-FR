---
description: Affichez la liste de vos sources de données actuellement configurées, ajoutez de nouvelles sources de données et modifiez les sources existantes.
seo-description: Affichez la liste de vos sources de données actuellement configurées, ajoutez de nouvelles sources de données et modifiez les sources existantes.
seo-title: Liste et paramètres des sources de données
solution: Audience Manager
title: Liste et paramètres des sources de données
uuid: 280a6acd-fef0-4737-a96d-9e22fbc8bfaf
translation-type: tm+mt
source-git-commit: c785c07a1572e9968e62a1bc753d24780eda64c5

---


# Liste et paramètres des sources de données {#data-sources-list-and-settings}

Affichez la liste de vos sources de données actuellement configurées, ajoutez de nouvelles sources de données et modifiez les sources existantes.

<!-- c_datasources.xml -->

Vous pouvez également gérer les sources de données à l’aide de [!DNL API] méthodes. Pour plus d’informations, voir Méthodes [d’API de source de](../api/rest-api-main/aam-api-data-sources.md)données.

## Vue Liste des sources de données {#list-view}

Le [!UICONTROL Data Sources] tableau de bord est un espace de travail centralisé pour la gestion des sources de données.

<!-- c_datasources_list.xml -->

Le [!UICONTROL Data Sources] tableau de bord (**[!UICONTROL Audience Data]** &gt; **[!UICONTROL Data Sources]**) contient des fonctionnalités et des outils qui vous aident à :

* Affichez toutes vos sources de données existantes, y compris la description, l’état de chaque source de données et si c’est [!UICONTROL Inbound], [!UICONTROL Outbound]les deux ou un [!UICONTROL Shared Provider].
* Recherchez les sources de données par nom.
* Créez, modifiez et supprimez des sources de données.

## Paramètres de source de données et options de menu {#settings-menu-options}

Les paramètres des différentes sections de l’interface de [!UICONTROL Data Source] gestion identifient votre source de données, déterminent son utilisation ou son partage et vous permettent d’activer la création de rapports d’erreur pour la [!UICONTROL Onboarding Status Report].

## Détails de la source de données {#details}

<!-- datasource-settings-definitions.xml -->

Outre les champs de texte, la [!UICONTROL Data Source Details] section contient les commandes et options répertoriées ci-dessous.

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
      <li id="li_1FC97E2B3E2A4289AFB4A3C2F8E84FEF"> <b><span class="uicontrol"> Cookie</span></b>: ID de cookie qui identifie un périphérique. Sélectionnez cette option lorsque votre source de données est un navigateur Web ou lorsque vous utilisez des données anonymes ou des données qui ne peuvent pas être associées à une seule personne. </li> 
      <li id="li_4B2C9A7F2A5D49448E6D0A2B354D7EE7"> <b><span class="uicontrol"> ID</span></b>de publicité du périphérique : Identifiant du périphérique mobile. Sélectionnez cette option lorsque la source de données est un périphérique mobile ou un périphérique compatible Internet. </li> 
      <li id="li_063F1B263B3B4D69B8880F7ACCB82450"> <b><span class="uicontrol"> Périphérique</span></b>croisé : Identifiant authentifié fourni par le client. Sélectionnez cette option lorsque vous souhaitez créer : 
       <ul id="ul_D998B4081AD843C2B3B3E642DD011C1F"> 
        <li id="li_C9D2AF70603043D7BE9DF12FD494D7C7">Source de données sur plusieurs périphériques et création d’une règle <span class="wintitle"> de fusion de</span>profil. </li> 
        <li id="li_992BD05E2AFE454CAA4460DDEB2B839B">Source de données qui utilise les liens fournis par <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/" format="https" scope="external"> Adobe Experience Cloud Device Co-op</a> ou un autre graphique de périphériques tiers intégré à <span class="keyword"> Audience Manager</span>. </li> 
       </ul> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Définition d’ID</span></b> </p> </td> 
   <td colname="col2"> <p>Les options Définition <b><span class="uicontrol"> de l’</span></b> ID définissent la relation entre une source de données et un ID utilisateur d’Audience Manager <span class="keyword"> (UUID) et les périphériques associés liés par</span> Adobe Experience Cloud Device Co-op <span class="keyword"> ou un autre graphique de périphérique tiers intégré à</span> <span class="keyword"> Audience Manager. </span> Les options incluent : </p> <p> 
     <ul id="ul_718ADABF0C0C44E29643C85C69CE294F"> 
      <li id="li_19936095319446698E9A577385CD2A80"> <b><span class="uicontrol"></span></b> Personne : ID utilisé pour définir une seule personne. Cet identifiant peut être mappé à plusieurs identifiants <span class="keyword"> Audience Manager</span> . </li> 
      <li id="li_3D939AFF34654D618A05D2603F34462D"> <b><span class="uicontrol"></span></b> Ménage : ID utilisé pour définir un groupe de personnes. Cet identifiant peut être mappé à plusieurs identifiants Audience Manager. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Contrôles des exportations de données {#export-controls}

[Les contrôles](../features/data-export-controls.md) d’exportation de données sont des règles de classification facultatives que vous pouvez appliquer à une source de données et à une destination. Elles vous empêchent d’envoyer des données vers une destination lorsque cette action enfreint un accord de confidentialité ou d’utilisation des données. Ignorez cette section si vous n’utilisez pas [!UICONTROL Data Export Controls].

>[!IMPORTANT]
>
>Les restrictions d’exportation ne fonctionneront pas, sauf si vous définissez une étiquette d’exportation correspondante sur une destination.

Les options incluent :

* **[!UICONTROL No Restriction]**
* **[!UICONTROL Cannot be tied to personally identifiable information]**
* **[!UICONTROL Cannot be used for on-site ad targeting]**
* **[!UICONTROL Cannot be used for off-site ad targeting]**
* **[!UICONTROL Cannot be used for on-site personalization]**

## Data Source Settings {#data-source-settings}

Le [!UICONTROL Data Source Settings] contient les commandes et options répertoriées ci-dessous. Certains de ces paramètres comportent des sous-options et des options de menu supplémentaires que vous pouvez sélectionner pour modifier une source de données.

### Paramètres de source de données entrantes

Cochez la **[!UICONTROL Inbound]** case lorsque votre source de données est conçue pour recevoir les données entrantes. La sélection de la **[!UICONTROL Inbound]** case à cocher expose deux groupes de commandes supplémentaires décrits ci-dessous.

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
   <td colname="col2"> <p>L’option <b><span class="uicontrol"> Envoi</span></b> nécessite un type d’ID. Les options incluent : </p> <p> 
     <ul id="ul_3BC963CE378B4F6CB1861643A4541634"> 
      <li id="li_B86C5E7847424A2B9C094DF02741DDB8"> <b><span class="uicontrol"> ID</span></b>client : Identifie les données entrantes avec un ID de client. </li> 
      <li id="li_AD8E440436314902A794CDB11A3D657F"> <b><span class="uicontrol"> ID</span></b>Audience Manager : Identifie les données entrantes avec un <span class="keyword"> identifiant Audience Manager</span> . </li> 
      <li id="li_B56608334DDA453B9E4E88E53DAF92FA"> <b><span class="uicontrol"> Experience Cloud ID</span></b>: Identifie les données entrantes avec un <span class="keyword"> ID Experience Cloud</span> . Voir <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external">Cookies et Experience Cloud ID</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Résolution des problèmes de format de fichier</span></b> </p> </td> 
   <td colname="col2"> <p>Sélectionnez <b><span class="uicontrol"> Activer l’échantillonnage</span></b> des erreurs de fichier lorsque vous devez résoudre les problèmes liés au traitement des fichiers entrants. Cette fonctionnalité génère un exemple de rapport d’erreur qui montre les erreurs de format de fichier et de syntaxe. </p> <p>Voir Rapport <a href="../reporting/onboarding-status-report.md#onboarding-status-about"> d’état d’intégration : À propos</a> des rapports d’erreurs et de l’échantillonnage d’erreurs. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Autres paramètres de source de données

<table id="table_82FEFA8DC8294FA18FB4C17F02DF5152"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre </th> 
   <th colname="col2" class="entry"> Sélectionner quand </th> 
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
   <td colname="col1"> <p> <b><span class="uicontrol"> Utiliser comme profil authentifié</span></b> </p> </td> 
   <td colname="col2"> <p>Votre source de données sur plusieurs périphériques contient un identifiant authentifié. Un ID authentifié est collecté et synchronisé avec un ID <span class="keyword"> Audience Manager</span> lors d’un événement d’authentification (par exemple, un utilisateur se connecte sur site, in-app, etc.). L’identifiant authentifié peut être utilisé pour les données embarquées provenant d’autres sources qui stockent cet identifiant. Il peut également être utilisé pour lier plusieurs ID de périphérique dans <span class="wintitle"> le lien</span>de profil. </p> <p>Cette option expose un champ de texte qui vous permet de renommer la source de données avec un alias. Si vous utilisez un alias, ce nouveau nom remplace le nom de la source de données et s’affiche dans les Options <span class="wintitle"> de profil</span> authentifié lorsque vous <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> créez une règle</a>de fusion de profil. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Utiliser comme graphique de périphérique</span></b> </p> </td> 
   <td colname="col2"> <p>Crée une source de données sous la forme d’un graphique de périphérique que vous pouvez fournir à d’autres clients d’ <span class="keyword"> Audience Manager</span> . Avant de sélectionner cette option, indiquez à votre <span class="keyword"> consultant Audience Manager</span> avec quels clients cette source <span class="wintitle"> de données</span> doit être partagée. Votre consultant devra fournir à ces entreprises les services nécessaires par le biais de nos processus internes. </p> <p>Cette option expose un champ de texte qui vous permet de renommer la source de données avec un alias. Si vous utilisez un alias, ce nouveau nom remplace le nom de la source de données et s’affiche dans les Options <span class="wintitle"> de périphérique lorsque vous</span> créez une règle <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"></a>de fusion de profil. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Partager les identifiants de visiteur ou de périphérique associés avec des clients Audience Manager spécifiques</span></b> </p> </td> 
   <td colname="col2"> <p>La source de données inter-périphériques contient des ID provenant d’un graphique de périphérique. Un graphique de périphérique est un ensemble d’identifiants qui mappent un ou plusieurs identifiants <span class="keyword"> Audience Manager</span> à une grappe. Ce groupe représente généralement une personne ou un groupe familial plus grand. Disponible uniquement pour les comptes répertoriés comme "fournisseur de données". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Partage des identifiants de visiteur ou de périphérique associés sur la plateforme Audience Manager</span></b> </p> </td> 
   <td colname="col2"> <p>Votre source de données contient des identifiants de visiteur ou de périphérique qui peuvent être partagés dans d’autres solutions <span class="keyword"> Experience Cloud</span> . </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Conservation des données pour les ID de client inactifs</span></b> </p> </td> 
   <td colname="col2"> <p>Permet de définir la période de rétention des données pour les ID de client inactifs. Cela détermine la durée pendant laquelle Audience Manager conserve les ID de client dans notre base de données après leur dernière consultation sur la plateforme Audience Manager.</p> <p>La valeur par défaut est de 24 mois (720 jours). La valeur minimale que vous pouvez définir est de 1 mois et la valeur maximale est de 5 ans. Notez que nous comptons tous les mois comme 30 jours.</p> <p>Audience Manager exécute un processus qui supprime les ID de client inactifs une fois par semaine, conformément à la rétention de données que vous avez définie pour les ID de client inactifs.</p> <p>Audience Manager exécute un processus qui supprime les ID de client inactifs une fois par semaine, conformément à la rétention de données que vous avez définie pour les ID de client inactifs.</p> <p><b>Remarque</b>: Ce contrôle est disponible uniquement pour les sources de données inter-périphériques. Voir aussi <a href="../features/profile-merge-rules/merge-rules-start.md#settings"> Création d’une source de données sur plusieurs périphériques </a>.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Codes d'intégration de caractéristiques uniques</span></b> </p> </td> 
   <td colname="col2"> <p>Vous souhaitez faire respecter le fait que deux caractéristiques de la même source de données n’ont pas le même code d’intégration. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Codes d'intégration de segment unique</span></b> </p> </td> 
   <td colname="col2"> <p>Vous souhaitez faire respecter le fait que deux segments provenant de la même source de données n’ont pas le même code d’intégration. </p> </td> 
  </tr>
 </tbody>
</table>
