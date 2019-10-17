---
description: Pour créer des règles de fusion de profils, passez en revue et suivez les étapes de chacune des procédures décrites dans cette section.
seo-description: Pour créer des règles de fusion de profils, passez en revue et suivez les étapes de chacune des procédures décrites dans cette section.
seo-title: Prise en main des règles de fusion de profils
solution: Audience Manager
title: Prise en main des règles de fusion de profils
uuid: 7d32c60f-467c-42dd-afa9-437fd7c473c5
translation-type: tm+mt
source-git-commit: f53e091b8c069221837af01ad54deeb731cd48e2

---


# Prise en main des règles de fusion de profils {#getting-started-with-profile-merge-rules}

Pour créer [!UICONTROL Profile Merge Rules], revoir et terminer les étapes de chacune des procédures décrites dans cette section.

<!-- merge-rules-start.xml -->

## Création d’une source de données sur plusieurs périphériques {#create-data-source}

Pour créer une source de données sur plusieurs périphériques, suivez **[!UICONTROL Audience Data > Data Sources > Add New]** les étapes décrites ici. Des autorisations d’administrateur sont requises pour créer ou modifier une source de données sur plusieurs périphériques.

<!-- create-cross-device-datasource.xml -->

>[!TIP]
>
>Voir Paramètres de source de [données et Options](../datasources-list-and-settings.md#settings-menu-options) de menu pour obtenir des descriptions de ces différents contrôles.

## Détails de la source de données {#details}

Pour compléter la [!UICONTROL Data Source Details] section :

1. Nommez la source de données.
2. *(Facultatif)* Décrivez la source de données. Une description concise permet de définir le rôle ou l’objectif de la source de données.
3. Fournissez un code d’intégration. Un code d’intégration est votre propre ID unique pour cette source de données.
4. Dans la **[!UICONTROL ID Type]** liste, sélectionnez **[!UICONTROL Cross Device]**.
5. Dans la **[!UICONTROL ID Definition]** liste, sélectionnez une option qui définit le type de source de données. Les options incluent :
   * **[!UICONTROL Person]**: ID qui définit une personne unique. Cet ID peut être mappé à plusieurs [!DNL Audience Manager] ID.
   * **[!UICONTROL Household]**: ID qui définit un groupe de personnes. Cet ID peut être mappé à plusieurs [!DNL Audience Manager] ID.

## Contrôles des exportations de données {#export-controls}

[Les contrôles](../data-export-controls.md) d’exportation de données sont des règles de classification facultatives que vous pouvez appliquer à une source de données et à une destination. Elles vous empêchent d’envoyer des données vers une destination lorsque cette action enfreint un accord de confidentialité ou d’utilisation des données. Ignorez cette section si vous n’utilisez pas [!UICONTROL Data Export Controls].

## Data Source Settings {#settings}

[!UICONTROL Data Source Settings] fournit plusieurs options, mais ces deux options sont importantes pour la création d’une source de données sur plusieurs périphériques :

* **[!UICONTROL Use as Authenticated Profile]**: Sélectionné par défaut, ce paramètre vous permet de créer un fichier [!UICONTROL Profile Merge Rule] avec vos propres données authentifiées.

* **[!UICONTROL Use as a Device Graph]**: Ce contrôle n’est disponible que pour les comptes répertoriés comme fournisseur de données. Cette case à cocher crée votre source de données sous forme de graphique de périphérique et vous permet de la partager avec d’autres [!DNL Audience Manager] clients. Contactez votre [!DNL Audience Manager] consultant pour être configuré en tant que fournisseur de données et pour spécifier avec quels clients il [!UICONTROL Data Source] faut partager. Votre conseiller vous fournira le partage des graphiques de votre compte et de votre périphérique par le biais d’un processus d’approvisionnement interne.

* **[!UICONTROL Data retention for inactive Customer IDs]**: Ce contrôle vous permet de définir la période de rétention des données pour les ID de client inactifs. Cela détermine la durée pendant laquelle Audience Manager conserve les ID de client dans notre base de données après leur dernière consultation sur la plateforme Audience Manager. La valeur par défaut est de 24 mois (720 jours). La valeur minimale que vous pouvez définir est de 1 mois et la valeur maximale est de 5 ans. Notez que nous comptons tous les mois comme 30 jours. Audience Manager exécute un processus qui supprime les ID de client inactifs une fois par semaine, conformément à la rétention de données que vous avez définie pour les ID de client inactifs.

Les champs de texte associés à ces paramètres vous permettent de renommer le fichier [!UICONTROL Data Source] avec un alias qui apparaît dans les options [Règle de fusion de](merge-rule-definitions.md)profil. Par exemple, si vous ajoutez un alias à **[!UICONTROL Use as Authenticated Profile]**, ce nom apparaît dans la [!UICONTROL Authenticated Profile Options] liste. Si vous ajoutez un alias à **[!UICONTROL Use as a Device Graph]**, ce nom apparaît dans la [!UICONTROL Device Options] liste.

>[!MORE_LIKE_This]
>
>* [Création d’une source de données](../manage-datasources.md#create-data-source)


## Création d’une règle de fusion de profil {#create-profile-merge-rule}

Pour créer une [!UICONTROL Profile Merge Rule], accédez à **[!UICONTROL Audience Data > Profile Merge Rules > Add New Rule]** et suivez les étapes de chaque section décrite ici.

Vous pouvez créer jusqu’à 3 règles de fusion après avoir configuré une source de données sur plusieurs périphériques. Vous avez accès à une quatrième règle de fusion de profil ([!UICONTROL All Cross-Device Profiles]) si vous vous inscrivez pour des destinations basées sur [les personnes](../destinations/people-based-destinations-overview.md).

Les autorisations d’administrateur sont requises pour créer, modifier ou supprimer une règle. Tous les utilisateurs peuvent afficher et utiliser des données existantes [!UICONTROL Profile Merge Rules].

<!-- create-profile-merge-rule.xml -->

**** Conditions préalables : Une source de données sur plusieurs périphériques est requise pour créer une [!UICONTROL Profile Merge Rule]variable. Voir [Création d’une source](../manage-datasources.md#create-data-source)de données.

>[!TIP]
>
>Voir Options des règles de fusion [de profil définies](merge-rule-definitions.md) pour obtenir des descriptions de ces différents contrôles.

## Informations fondamentales {#basic-info}

Pour compléter la [!UICONTROL Basic Information] section :

1. Nommez le [!UICONTROL Profile Merge Rule].
2. *(Facultatif)* Décrivez le [!UICONTROL Profile Merge Rule]. Une description concise vous aide à définir le rôle ou l’objectif de votre règle.
3. *(Facultatif)* Sélectionnez **[!UICONTROL Set as default]** si vous souhaitez que cette option soit utilisée par défaut [!UICONTROL Profile Merge Rule]. Les nouveaux segments sont automatiquement associés à la règle par défaut.

## Contrôles des exportations de données {#data-export-controls}

[Les contrôles](../data-export-controls.md) d’exportation de données sont des règles de classification facultatives que vous pouvez appliquer à votre [!UICONTROL Profile Merge Rule]entreprise. Elles vous empêchent d’envoyer des données vers une destination lorsque cette action enfreint un accord de confidentialité ou d’utilisation des données. Ignorez cette section si vous n’utilisez pas [!UICONTROL Data Export Controls].

## Configuration des règles de fusion de profils {#profile-merge-rule-setup}

Pour compléter la [!UICONTROL Proflie Merge Rule Setup] section :

1. Sélectionnez un **[!UICONTROL Authenticated Option]**. Les options incluent :
   * **[!UICONTROL No Authenticated Profile]**
   * **[!UICONTROL Current Authenticated Profile]**
   * **[!UICONTROL Last Authenticated Profile]**
2. Sélectionnez un **[!UICONTROL Authenticated Profile Option]** (3 au maximum). Il s’agit des sources [de données](merge-rules-start.md) inter-périphériques que vous avez créées précédemment.
3. Sélectionnez **[!UICONTROL Device Option]**. Les options incluent :
   * **[!UICONTROL No Device Profile]**
   * **[!UICONTROL Current Device Profile]**
   * **[!UICONTROL Profile Link Device Graph]**
   * **[!UICONTROL Device Co-op]**
4. Cliquez sur **[!UICONTROL Save]**.

## Configuration du code de règle de fusion {#configure-merge-rule-code}

Suivez ces instructions pour configurer le code [!UICONTROL Experience Cloud ID Service], [!UICONTROL DIL]et mobile [!DNL SDK] afin qu’il fonctionne avec vos règles de fusion.

<!-- merge-rules-configure-code.xml -->

### Conditions préalables

Vous devez configurer une source [de données](#create-data-source) inter-périphériques et des règles [de fusion de](#create-profile-merge-rule) profil avant ** d’exécuter ces procédures.

## Pour les clients du service Experience Cloud ID {#id-service-customers}

Il est recommandé d’utiliser la version [!UICONTROL Experience Cloud ID Service] et la dernière version de [DIL](../../dil/dil-overview.md) lorsque vous travaillez avec [!UICONTROL Profile Merge Rules]. Cependant, vous n’avez pas besoin d’utiliser la [!UICONTROL Experience Cloud ID Service] pour utiliser cette fonctionnalité. Si vous utilisez simplement [!UICONTROL DIL], reportez-vous à la section [DIL](#legacy-dil) héritée ci-dessous.

### Configuration de la fonction Set Customer ID

Lorsque vous travaillez avec [!UICONTROL Experience Cloud ID Service], la `setCustomerIDs` fonction transmet les ID déclarés à [!DNL Audience Manager]. Pour utiliser une règle de fusion de profil, vous devez la modifier `setCustomerIDs` pour utiliser le code d’intégration spécifié lors de la création d’une source de données sur plusieurs périphériques. Supposons, par exemple, que vous ayez créé une source de données inter-périphériques avec le code d’intégration `my_datasource_ic`. Pour transmettre un identifiant déclaré, vous devez ajouter le code d’intégration à la fonction d’identification des visiteurs, comme illustré dans l’exemple de code modifié ci-dessous.

#### Exemple de code générique

```javascript
visitor.setCustomerIDs({
  "userid":{
      "id":"12345",
      "authState":Visitor.AuthState.AUTHENTICATED
```

#### Exemple de code modifié

```javascript
visitor.setCustomerIDs({
  "my_datasource_ic":{
     "id":"12345",
     "authState":Visitor.AuthState.AUTHENTICATED
```

Pour plus d’informations, voir [Création d’une source](#create-data-source) de données sur plusieurs périphériques et d’identifiants [de client et d’états](https://marketing.adobe.com/resources/help/en_US/mcvid/?f=mcvid_customer_ids.html)d’authentification.

### Configurer la `DIL.create` fonction

Les versions les plus récentes de [!UICONTROL DIL] désormais sélectionnent automatiquement la [!UICONTROL declared ID] dans la `visitorService` fonction (voir Variables `DIL.create` d’ID [](../declared-ids.md#declared-id-variables)déclarées). Vérifiez votre `DIL.create` fonction pour vous assurer qu’elle est correctement configurée, comme le montre l’exemple de code ci-dessous.

```js
var vDil = DIL.create({
   partner:"partner name",
   visitorService:{
      namespace:"INSERT-MCORG-ID-HERE"
   }
});
```

Dans la paire clé-valeur de l’espace de noms, la variable `*`MCORG`*` est votre [!DNL Experience Cloud] ID d’organisation. Si vous ne possédez pas cet ID, vous le trouverez dans la [!UICONTROL Administration] section du [!DNL Experience Cloud] tableau de bord. Vous avez besoin d’autorisations d’administrateur pour afficher ce tableau de bord. See [Administration: Core Services](https://marketing.adobe.com/resources/help/en_US/mcloud/?f=admin_getting_started.html).

### Configuration des SDK

Voir la section [Configuration des SDK](#configure-sdks-legacy-dil) ci-dessous.

## DIL hérité {#legacy-dil}

Si vous n'utilisez pas [!DNL Experience Cloud ID Service] encore, vous devriez vraiment le faire. Mais nous comprenons que passer à un nouveau code nécessite une réflexion et des tests minutieux. Dans ce cas, vérifiez votre `DIL.create` fonction pour vous assurer qu’elle est correctement configurée, comme le montre l’exemple de code ci-dessous.

```js
DIL.create({
   partner: "partner name",
   declaredId:{
      dpuuid: YOUR_DPUUID,
      dpid: YOUR_DPID
   }
});
```

Pour plus d’informations, voir la [!UICONTROL DIL] section héritée dans Variables [d’ID](../declared-ids.md#declared-id-variables)déclarées.

### Configuration des SDK {#configure-sdks-legacy-dil}

Vérifiez les méthodes de votre [!DNL SDK] code qui vous permettent de passer [!UICONTROL declared IDs] des périphériques [!DNL Android] et [!DNL iOS] mobiles. Les noms des variables pour les bibliothèques [!DNL Android] et [!DNL iOS] de code sont identiques :

* `dpid`: ID de source de données sur plusieurs périphériques.
* `dpuuid`: Le [!UICONTROL declared ID] (c’est-à-dire l’ID utilisateur).

<table id="table_2ACA3E5F316D4413B10A4403B786CC23"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type de périphérique </th> 
   <th colname="col2" class="entry"> Méthode </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b> Android </b> </p> </td> 
   <td colname="col2"> <p> <code> setDpidAndDpuuid </code> </p> <p> <b>Syntaxe :</b> </p> <p> <pre> public static void setDpidAndDpuuid(String dpid, String dpuuid); </pre> </p> <p> <b>Exemple :</b> </p> <p> <pre> AudienceManager.setDpidAndDpuuid("myDpid","myDpuuid"); </pre> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b> iOS </b> </p> </td> 
   <td colname="col2"> <p> <code> audienceSetDpid:dpuuid </code> </p> <p> <b>Syntaxe :</b> </p><p>
    <code class="javascript">
      +&nbsp;(void)&nbsp;audienceSetDpid:(NSString&nbsp;*)dpid 
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;dpuuid:(NSString&nbsp;*)dpuuid; 
    </code></p>
    <p> <b>Exemple :</b> </p><p>
    <code class="javascript">
      [ADBMobile&nbsp;audienceSetDpid:@"290"
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;dpuuid:@"99301393923940"];
    </code></p>
    </td>
  </tr>
 </tbody>
</table>

Voir aussi Méthodes d’ [Audience Manager pour Android](https://marketing.adobe.com/resources/help/en_US/mobile/android/?f=c_audience_manager_methods.html) et Méthodes d’ [Audience Manager pour iOS](https://marketing.adobe.com/resources/help/en_US/mobile/ios/?f=aam_methods.html).
