---
description: Vue d’une liste de vos sources de données actuellement configurées, ajoutez de nouvelles sources de données et modifiez les sources existantes.
seo-description: Vue d’une liste de vos sources de données actuellement configurées, ajoutez de nouvelles sources de données et modifiez les sources existantes.
seo-title: Liste et paramètres des sources de données
solution: Audience Manager
title: Liste et paramètres des sources de données
uuid: 280a6acd-fef0-4737-a96d-9e22fbc8bfaf
feature: Data Sources
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1118'
ht-degree: 3%

---


# [!UICONTROL Data Sources] Liste et paramètres  {#data-sources-list-and-settings}

Vue une liste de votre [!UICONTROL data sources] actuellement configuré, ajoutez [!UICONTROL data sources] nouveau  et modifiez [!UICONTROL data sources] existant.

Vous pouvez également gérer [!UICONTROL data sources] à l&#39;aide des méthodes [!DNL API]. Pour plus d’informations, voir [Méthodes d’API de source de données](../api/rest-api-main/aam-api-data-sources.md).

## [!UICONTROL Data Sources] mode Liste {#list-view}

Le tableau de bord [!UICONTROL Data Sources] est un espace de travail centralisé pour la gestion des sources de données.

Le tableau de bord [!UICONTROL Data Sources] (**[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**) contient des fonctionnalités et des outils qui vous aident à :

* Consultez tous vos [!UICONTROL data sources] existants, y compris la description, l’état de chaque source de données et s’il s’agit de [!UICONTROL Inbound], [!UICONTROL Outbound], des deux ou d’un [!UICONTROL Shared Provider].
* Recherchez [!UICONTROL data sources] par nom.
* Créer, modifier et supprimer [!UICONTROL data sources].

## [!DNL Data Source] Paramètres et options de menu  {#settings-menu-options}

Les paramètres des différentes sections de l&#39;interface de gestion [!UICONTROL Data Source] identifient votre [!DNL data source], déterminent comment il est utilisé ou partagé, et vous permettent d&#39;activer le rapports d&#39;erreur pour [!UICONTROL Onboarding Status Report].

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
      <li id="li_1FC97E2B3E2A4289AFB4A3C2F8E84FEF"> <b><span class="uicontrol"> Cookie</span></b> : ID de cookie qui identifie un périphérique. Sélectionnez cette option lorsque votre source de données est un navigateur Web ou lorsque vous travaillez avec des données anonymes ou des données qui ne peuvent pas être associées à une seule personne. </li> 
      <li id="li_4B2C9A7F2A5D49448E6D0A2B354D7EE7"> <b><span class="uicontrol"> ID</span></b> de publicité de périphérique : Identifiant du périphérique mobile. Sélectionnez cette option lorsque la source de données est un périphérique mobile ou un périphérique compatible Internet. </li> 
      <li id="li_063F1B263B3B4D69B8880F7ACCB82450"> <b><span class="uicontrol"> Périphérique</span></b> croisé : Identifiant authentifié fourni par le client. Sélectionnez cette option lorsque vous souhaitez créer : 
       <ul id="ul_D998B4081AD843C2B3B3E642DD011C1F"> 
        <li id="li_C9D2AF70603043D7BE9DF12FD494D7C7">Source de données sur plusieurs périphériques et créez une <span class="wintitle"> règle de fusion de Profils</span>. </li> 
        <li id="li_992BD05E2AFE454CAA4460DDEB2B839B">Source de données qui utilise les liens fournis par le <a href="https://docs.adobe.com/content/help/en/device-co-op/using/about/overview.html" format="https" scope="external"> Adobe Experience Cloud Device Co-op</a> ou un autre graphique de périphérique tiers intégré à <span class="keyword"> Audience Manager</span>. </li> 
       </ul> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Définition d'ID</span></b> </p> </td> 
   <td colname="col2"> <p>Les options <b><span class="uicontrol"> ID Definition</span></b> définissent la relation entre une source de données et une <span class="keyword"> Audience Manager</span> identifiant utilisateur (UUID) et les périphériques associés liés par la <span class="keyword"> Adobe Experience Cloud Device Co-op</span> ou un autre graphique de périphérique tiers intégré à <span class="keyword"> Audience Manager</span>. Les options incluent : </p> <p> 
     <ul id="ul_718ADABF0C0C44E29643C85C69CE294F"> 
      <li id="li_19936095319446698E9A577385CD2A80"> <b><span class="uicontrol"> Personne : </span></b> ID utilisé pour définir une seule personne. Cet ID peut être mappé à plusieurs <span class="keyword"> identifiants d'Audience Manager</span>. </li> 
      <li id="li_3D939AFF34654D618A05D2603F34462D"> <b><span class="uicontrol"> Ménage : </span></b> ID utilisé pour définir un groupe de personnes. Cet ID peut être mappé à plusieurs ID d’Audience Manager. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Data Export Controls] {#export-controls}

[Les ](../features/data-export-controls.md) contrôles d’exportation de données sont des règles de classification facultatives que vous pouvez appliquer à un  [!UICONTROL data source] et  [!UICONTROL destination]à. Ils vous empêchent d&#39;envoyer des données à [!UICONTROL destination] lorsque cette action enfreint un accord de confidentialité ou d&#39;utilisation des données. Ignorez cette section si vous n’utilisez pas [!UICONTROL Data Export Controls].

>[!IMPORTANT]
>
>Les restrictions d&#39;exportation ne fonctionneront que si vous définissez un libellé d&#39;exportation correspondant sur un [!UICONTROL destination].

Les options incluent :

* **[!UICONTROL No Restriction]**
* **[!UICONTROL Cannot be tied to personally identifiable information]**
* **[!UICONTROL Cannot be used for on-site ad targeting]**
* **[!UICONTROL Cannot be used for off-site ad targeting]**
* **[!UICONTROL Cannot be used for on-site personalization]**

## [!UICONTROL Data Source] Paramètres {#data-source-settings}

Le [!UICONTROL Data Source Settings] contient les commandes et options répertoriées ci-dessous. Certains de ces paramètres comportent des sous-options et des options de menu supplémentaires que vous pouvez sélectionner pour modifier une source de données.

### [!UICONTROL Inbound Data Source] Paramètres

Cochez la case **[!UICONTROL Inbound]** lorsque votre source de données est conçue pour recevoir les données entrantes. La sélection de la case à cocher **[!UICONTROL Inbound]** expose deux groupes de contrôles supplémentaires décrits ci-dessous.

>[!NOTE]
>
>La case à cocher **[!UICONTROL Inbound]** n&#39;est destinée qu&#39;à afficher ou masquer les contrôles [!UICONTROL data source] décrits ci-dessous. La dévérification de l&#39;option **[!UICONTROL Inbound]** n&#39;a aucune incidence sur l&#39;assimilation des données. Vos données intégrées seront traitées, quelle que soit l’option sélectionnée.

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
   <td colname="col2"> <p>L'option <b><span class="uicontrol"> Entrant</span></b> nécessite un type d'ID. Les options incluent : </p> <p> 
     <ul id="ul_3BC963CE378B4F6CB1861643A4541634"> 
      <li id="li_B86C5E7847424A2B9C094DF02741DDB8"> <b><span class="uicontrol"> ID</span></b> du client : Identifie les données entrantes avec un ID de client. </li> 
      <li id="li_AD8E440436314902A794CDB11A3D657F"> <b><span class="uicontrol"> ID</span></b> d'Audience Manager : Identifie les données entrantes avec un  <span class="keyword"> ID de gestionnaire d’</span> Audience. </li> 
      <li id="li_B56608334DDA453B9E4E88E53DAF92FA"> <b><span class="uicontrol"> ID</span></b> Experience Cloud : Identifie les données entrantes avec un  <span class="keyword"> Experience </span> CloudID. Voir <a href="https://docs.adobe.com/content/help/fr-FR/id-service/using/intro/cookies.html" format="https" scope="external">Cookies et Experience Cloud ID</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Résolution des problèmes de format de fichier</span></b> </p> </td> 
   <td colname="col2"> <p>Sélectionnez <b><span class="uicontrol"> Activer l’échantillonnage des erreurs de fichier</span></b> lorsque vous devez résoudre les problèmes liés au traitement des fichiers entrants. Cette fonctionnalité génère un exemple de rapport d’erreur qui présente les erreurs de format de fichier et de syntaxe. </p> <p>Voir le rapport <a href="../reporting/onboarding-status-report.md#onboarding-status-about"> État de l'intégration : À propos de </a> pour plus d’informations sur le rapports d’erreur et l’échantillonnage d’erreurs. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Autres paramètres [!UICONTROL Data Source]

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
   <td colname="col1"> <p> <b><span class="uicontrol"> Utiliser comme Profil authentifié</span></b> </p> </td> 
   <td colname="col2"> <p>Votre source de données sur plusieurs périphériques contient un identifiant authentifié. Un ID authentifié est collecté et synchronisé avec un <span class="keyword"> ID d'Audience Manager</span> au cours d'un événement d'authentification (par exemple, un utilisateur se connecte sur site, in-app, etc.). L’identifiant authentifié peut être utilisé pour les données embarquées provenant d’autres sources qui stockent cet identifiant. Il peut également être utilisé pour lier plusieurs ID de périphérique dans <span class="wintitle"> Lien de Profil</span>. </p> <p>Cette option expose un champ de texte qui vous permet de renommer la source de données avec un alias. Si vous utilisez un alias, ce nouveau nom remplace le nom de la source de données et s’affiche dans les <span class="wintitle"> Options de Profil authentifié</span> lorsque vous <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> créez une règle de fusion de Profil</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Utiliser comme graphique de périphérique</span></b> </p> </td> 
   <td colname="col2"> <p>Crée une source de données sous la forme d’un graphique de périphérique que vous pouvez fournir à d’autres clients <span class="keyword"> Audience Manager</span>. Avant de sélectionner cette option, indiquez à votre <span class="keyword"> Audience Manager</span> consultant avec quel client cette <span class="wintitle"> source de données</span> doit être partagée. Votre consultant devra fournir ces sociétés par le biais de nos processus internes. </p> <p>Cette option expose un champ de texte qui vous permet de renommer la source de données avec un alias. Si vous utilisez un alias, ce nouveau nom remplace le nom de la source de données et apparaît dans les <span class="wintitle"> Options de périphérique</span> lorsque vous <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> créez une règle de fusion de Profil</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Partager les ID de visiteur ou de périphérique associés avec des clients d’Audience Manager spécifiques</span></b> </p> </td> 
   <td colname="col2"> <p>Votre source de données sur plusieurs périphériques contient des identifiants issus d’un graphique de périphérique. Un graphique de périphérique est un ensemble d’identifiants qui correspondent à un ou plusieurs <span class="keyword"> identifiants d’Audience Manager</span> d’une grappe. Ce groupe représente généralement une personne ou un groupe familial plus grand. Disponible uniquement pour les comptes répertoriés en tant que "fournisseur de données". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Partage des ID de visiteur ou de périphérique associés sur la plateforme d’Audience Manager</span></b> </p> </td> 
   <td colname="col2"> <p>Votre source de données contient des ID de visiteur ou de périphérique qui peuvent être partagés dans d’autres solutions <span class="keyword"> Experience Cloud</span>. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Conservation des données pour les ID de client inactifs</span></b> </p> </td> 
   <td colname="col2"> <p>Permet de définir la période de rétention des données pour les ID de client inactifs. Cela détermine la durée pendant laquelle l’Audience Manager conserve les ID de client dans notre base de données après leur dernière consultation sur la plateforme d’Audience Manager.</p> <p>La valeur par défaut est de 24 mois (720 jours). La valeur minimale que vous pouvez définir est de 1 mois et la valeur maximale est de 5 ans. Notez que nous comptons tous les mois comme 30 jours.</p> <p>L’Audience Manager exécute un processus qui supprime les ID de client inactifs une fois par semaine, conformément à la rétention de données que vous avez définie pour les ID de client inactifs.</p> <p>L’Audience Manager exécute un processus qui supprime les ID de client inactifs une fois par semaine, conformément à la rétention de données que vous avez définie pour les ID de client inactifs.</p> <p><b>Remarque</b> : Ce contrôle est disponible uniquement pour les sources de données sur plusieurs périphériques. Voir aussi <a href="../features/profile-merge-rules/merge-rules-start.md#settings"> Créer une source de données multiterminaux </a>.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Codes d'intégration de caractéristiques uniques</span></b> </p> </td> 
   <td colname="col2"> <p>Vous souhaitez faire respecter le fait que deux caractéristiques issues de la même source de données n’ont pas le même code d’intégration. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Codes d'intégration de segment unique</span></b> </p> </td> 
   <td colname="col2"> <p>Vous souhaitez imposer que deux segments provenant de la même source de données n’aient pas le même code d’intégration. </p> </td> 
  </tr>
 </tbody>
</table>
