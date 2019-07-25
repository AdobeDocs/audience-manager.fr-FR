---
description: Pour créer des règles de fusion de profils, passez en revue les étapes décrites dans chacune des procédures décrites dans cette section.
seo-description: Pour créer des règles de fusion de profils, passez en revue les étapes décrites dans chacune des procédures décrites dans cette section.
seo-title: Prise en main des règles de fusion de profils
solution: Audience Manager
title: Prise en main des règles de fusion de profils
uuid: 7 d 32 c 60 f -467 c -42 dd-afa 9-437 fd 7 c 473 c 5
translation-type: tm+mt
source-git-commit: c785c07a1572e9968e62a1bc753d24780eda64c5

---


# Getting Started with Profile Merge Rules {#getting-started-with-profile-merge-rules}

To create [!UICONTROL Profile Merge Rules], review and complete the steps in each of the procedures described in this section.

<!-- merge-rules-start.xml -->

## Create a Cross-Device Data Source {#create-data-source}

To create a cross-device data source, go to **[!UICONTROL Audience Data > Data Sources > Add New]** and complete the steps for each section described here. Les autorisations d'administrateur sont requises pour créer ou modifier une source de données sur plusieurs périphériques.

<!-- create-cross-device-datasource.xml -->

>[!TIP]
>
>See [Data Source Settings and Menu Options](../../features/datasources-list-and-settings.md#settings-menu-options) for descriptions of these different controls.

## Data Source Details {#details}

To complete the [!UICONTROL Data Source Details] section:

1. Nommez la source de données.
1. *(Facultatif)* Décrivez la source de données. Une description concise permet de définir le rôle ou le rôle de la source de données.
1. Fournissez un code d'intégration. Un code d'intégration est votre propre identifiant unique pour cette source de données.
1. In the **[!UICONTROL ID Type]** list, select **[!UICONTROL Cross Device]**.
1. In the **[!UICONTROL ID Definition]** list, select an option that defines the data source type. Les options incluent :
   * **[!UICONTROL Person]**: Identifiant qui définit une seule personne. This ID can be mapped to multiple [!DNL Audience Manager] IDs.
   * **[!UICONTROL Household]**: Identifiant qui définit un groupe de personnes. This ID can be mapped to multiple [!DNL Audience Manager] IDs.

## Contrôles des exportations de données {#export-controls}

[Les contrôles d'exportation de données](../../features/data-export-controls.md) sont des règles de classification facultatives que vous pouvez appliquer à une source de données et à une destination. Elles vous empêchent d'envoyer des données à une destination lorsque cette action enfreint un accord de confidentialité ou d'utilisation des données. Skip this section if you do not use [!UICONTROL Data Export Controls].

## Data Source Settings {#settings}

[!UICONTROL Data Source Settings] fournit plusieurs options, mais ces deux éléments sont importants pour la création d'une source de données sur plusieurs périphériques :

* **[!UICONTROL Use as Authenticated Profile]**: Sélectionné par défaut, ce paramètre vous permet de créer un [!UICONTROL Profile Merge Rule] rapport avec vos propres données authentifiées.

* **[!UICONTROL Use as a Device Graph]**: Cette commande est disponible uniquement pour les comptes répertoriés comme fournisseur de données. Selecting this check box creates your data source as a device graph and lets you share it with other [!DNL Audience Manager] customers. Work with your [!DNL Audience Manager] consultant to get set up as a data provider and to specify which customers this [!UICONTROL Data Source] should be shared with. Votre conseiller permet de partager votre compte et votre graphique de périphérique via un processus de mise en service interne.

* **[!UICONTROL Data retention for inactive Customer IDs]**: Ce contrôle permet de définir la période de rétention des données pour les ID de client inactifs. Ceci détermine la durée pendant laquelle Audience Manager conserve les ID de client dans notre base de données après leur dernière consultation sur la plate-forme Audience Manager. La valeur par défaut est de 24 mois (720 jours). La valeur minimale est de 1 mois et la valeur maximale est de 5 ans. Notez que nous comptons tous les mois sur 30 jours. Audience Manager exécute un processus qui supprime les identifiants client inactifs une fois par semaine, conformément à la rétention des données que vous avez définie pour les ID de client inactifs.

The text fields associated with these settings let you rename the [!UICONTROL Data Source] with an alias that appears in the [Profile Merge Rule options](../../features/profile-merge-rules/merge-rule-definitions.md). For example, if you add an alias to **[!UICONTROL Use as Authenticated Profile]**, that name appears in the [!UICONTROL Authenticated Profile Options] list. If you add an alias to **[!UICONTROL Use as a Device Graph]**, that name appears in the [!UICONTROL Device Options] list.

>[!MORE_ LIKE_ THIS]
>
>* [Création d'une source de données](../../features/manage-datasources.md#create-data-source)


## Create a Profile Merge Rule {#create-profile-merge-rule}

To create a [!UICONTROL Profile Merge Rule], go to **[!UICONTROL Audience Data > Profile Merge Rules > Add New Rule]** and complete the steps for each section described here. Vous pouvez créer jusqu'à trois règles de fusion après avoir défini la source de données sur plusieurs périphériques. Les autorisations d'administrateur sont requises pour créer, modifier ou supprimer une règle. All users can view and use existing [!UICONTROL Profile Merge Rules].

<!-- create-profile-merge-rule.xml -->

**Conditions préalables :** Une source de données sur plusieurs périphériques est requise pour créer un [!UICONTROL Profile Merge Rule]élément. See [Create a Data Source](../../features/manage-datasources.md#create-data-source).

>[!TIP]
>
>See [Profile Merge Rule Options Defined](../../features/profile-merge-rules/merge-rule-definitions.md) for descriptions of these different controls.

## Informations fondamentales {#basic-info}

To complete the [!UICONTROL Basic Information] section:

1. Name the [!UICONTROL Profile Merge Rule].
2. *(Facultatif)* Décrivez [!UICONTROL Profile Merge Rule]la variable. Une description concise permet de définir le rôle ou l'objectif de la règle.
3. *(Facultatif)* Sélectionnez **[!UICONTROL Set as default]** si vous souhaitez que cette valeur soit la valeur par défaut [!UICONTROL Profile Merge Rule]. Les nouveaux segments sont automatiquement associés à la règle par défaut.

## Contrôles des exportations de données {#data-export-controls}

[Les contrôles d'exportation de données](../../features/data-export-controls.md) sont des règles de classification facultatives que vous pouvez appliquer à votre [!UICONTROL Profile Merge Rule]. Elles vous empêchent d'envoyer des données à une destination lorsque cette action enfreint un accord de confidentialité ou d'utilisation des données. Skip this section if you do not use [!UICONTROL Data Export Controls].

## Profile Merge Rule Setup {#profile-merge-rule-setup}

To complete the [!UICONTROL Proflie Merge Rule Setup] section:

1. Select an **[!UICONTROL Authenticated Option]**. Les options incluent :
   * **[!UICONTROL No Authenticated Profile]**
   * **[!UICONTROL Current Authenticated Profile]**
   * **[!UICONTROL Last Authenticated Profile]**
2. Select an **[!UICONTROL Authenticated Profile Option]** (up to 3, maximum). These are the [cross-device data sources](../../features/profile-merge-rules/merge-rules-start.md) you have created previously.
3. Sélectionnez **[!UICONTROL Device Option]**. Les options incluent :
   * **[!UICONTROL No Device Profile]**
   * **[!UICONTROL Current Device Profile]**
   * **[!UICONTROL Profile Link Device Graph]**
   * **[!UICONTROL Device Co-op]**
4. Cliquez sur **[!UICONTROL Save]**.

## Configure Merge Rule Code {#configure-merge-rule-code}

Follow these instructions to set up the [!UICONTROL Experience Cloud ID Service], [!UICONTROL DIL], and mobile [!DNL SDK] code to work with your merge rules.

<!-- merge-rules-configure-code.xml -->

### Conditions préalables

You must set up a [cross-device data source](#create-data-source) and [profile merge rules](#create-profile-merge-rule) *before* completing these procedures.

## For Experience Cloud ID Service Customers {#id-service-customers}

The [!UICONTROL Experience Cloud ID Service] and the latest version of [DIL](../../dil/dil-overview.md) are recommended when working with [!UICONTROL Profile Merge Rules]. However, you don't have to use the [!UICONTROL Experience Cloud ID Service] to work with this feature. If you're just using [!UICONTROL DIL], see the [legacy DIL section](../../features/profile-merge-rules/merge-rules-start.md#legacy-dil) below.

### Configuration de la fonction Définir l'ID du client

When working with the [!UICONTROL Experience Cloud ID Service], the `setCustomerIDs` function passes declared IDs to [!DNL Audience Manager]. To use a profile merge rule, you must modify `setCustomerIDs` to use the integration code specified when you created a cross-device data source. For example, say you've created a cross-device data source with the integration code `my_datasource_ic`. Pour transmettre un ID déclaré, vous ajoutez le code d'intégration à la fonction d'identification des visiteurs, comme indiqué dans l'exemple de code modifié ci-dessous.

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

For more information, see [Create a Cross-Device Data Source](#create-data-source) and [Customer IDs and Authentication States](https://marketing.adobe.com/resources/help/en_US/mcvid/?f=mcvid_customer_ids.html).

### Configure `DIL.create` function

The latest versions of [!UICONTROL DIL] now automatically pick up the [!UICONTROL declared ID] from the `visitorService` function in `DIL.create` (see [Declared ID Variables](../../features/declared-ids.md#declared-id-variables)). Check your `DIL.create` function to make sure this is set up properly as shown in the code sample below.

<pre class="js"><code>var vdil = DIL. create ({partner
 : « nom du partenaire »,
 visitorservice : {namespace
 : « <i>INSERT-MCORG-ID-HERE</i> »}})
 ;</code>
</pre>

In the namespace key-value pair, the `*`MCORG`*` variable is your [!DNL Experience Cloud] Organization ID. If you don't have this ID, you can find it in the [!UICONTROL Administration] section of the [!DNL Experience Cloud] dashboard. Vous devez disposer des autorisations d'administrateur pour afficher ce tableau de bord. See [Administration: Core Services](https://marketing.adobe.com/resources/help/en_US/mcloud/?f=admin_getting_started.html).

### Configuration de SDK

See the [Configure SDKs](../../features/profile-merge-rules/merge-rules-start.md#configure-sdks) section below.

## Legacy DIL {#legacy-dil}

If you're not using [!DNL Experience Cloud ID Service] yet, you really ought to. Cependant, nous comprenons que le passage au nouveau code requiert des réflexions et des tests minutieux. In these cases, check your `DIL.create` function to make sure this is set up properly as shown in the code sample below.

<pre class="js"><code>DIL. create ({partner
 : « nom du partenaire »,
 declaredid : {dpuuid
 :<i>dpuuid</i>,
 dpid :<i>dpid</i>}})
 ;</code>
</pre>

For more information, see the legacy [!UICONTROL DIL] section in [Declared ID Variables](../../features/declared-ids.md#declared-id-variables).

### Configure SDKs {#configure-sdks-legacy-dil}

Check the methods in your [!DNL SDK] code that let you pass [!UICONTROL declared IDs] from [!DNL Android] and [!DNL iOS] mobile devices. The variable names for the [!DNL Android] and [!DNL iOS] code libraries are the same:

* `dpid`: ID de source de données sur plusieurs périphériques.
* `dpuuid`: Le [!UICONTROL declared ID] (c.-à-d. l'utilisateur - id).

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
   <td colname="col2"> <p> <code> setDpidAndDpuuid </code> </p> <p> <b>Syntaxe :</b> </p> <p> <pre> public static void setdpidanddpuuid (String dpid, String dpuuid) ; </pre> </p> <p> <b>Exemple :</b> </p> <p> <pre> Audiencemanager. setdpidanddpuuid (« mydpid », « mydpuuid ») ; </pre> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b> iOS </b> </p> </td> 
   <td colname="col2"> <p> <code> Audiencesetdpid : dpuuid </code> </p> <p> <b>Syntaxe :</b> </p><p>
    <code class="javascript">+ (void) audiencesetdpid : (Nsstring *) dpid 
 dpuuid : (Nsstring *) dpuuid ; </code>
 </p>
    <p> <b>Exemple :</b> </p><p>
    <code class="javascript">[Adbmobile audiencesetdpid : @ « 290 » dpuuid : @ « 99301393923940 »] ; </code>
 </p>
    </td>
  </tr>
 </tbody>
</table>

See also, [Audience Manager Methods for Android](https://marketing.adobe.com/resources/help/en_US/mobile/android/?f=c_audience_manager_methods.html) and [Audience Manager Methods for iOS](https://marketing.adobe.com/resources/help/en_US/mobile/ios/?f=aam_methods.html).
