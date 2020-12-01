---
description: Pour créer des règles de fusion de Profil, passez en revue et suivez les étapes décrites dans chacune des procédures décrites dans cette section.
seo-description: Pour créer des règles de fusion de Profil, passez en revue et suivez les étapes décrites dans chacune des procédures décrites dans cette section.
seo-title: Démarrage des stratégies de fusion de profils
solution: Audience Manager
title: Démarrage des stratégies de fusion de profils
uuid: 7d32c60f-467c-42dd-afa9-437fd7c473c5
feature: Profile Merge Rules
translation-type: tm+mt
source-git-commit: dc22ed98b51b5633532bab45a79a14ee14dba5f5
workflow-type: tm+mt
source-wordcount: '1304'
ht-degree: 4%

---


# Démarrage des stratégies de fusion de profils {#getting-started-with-profile-merge-rules}

Pour créer [!UICONTROL Profile Merge Rules], passez en revue et suivez les étapes décrites dans chacune des procédures décrites dans cette section.

<!-- merge-rules-start.xml -->

## Créer une source de données sur plusieurs périphériques {#create-data-source}

Pour créer une source de données sur plusieurs périphériques, accédez à **[!UICONTROL Audience Data > Data Sources > Add New]** et suivez les étapes décrites ici pour chaque section. Les autorisations d’administrateur sont requises pour créer ou modifier une source de données sur plusieurs périphériques.

<!-- create-cross-device-datasource.xml -->

>[!TIP]
>
>Voir [Paramètres de la source de données et Options de menu](../datasources-list-and-settings.md#settings-menu-options) pour la description de ces différents contrôles.

## Détails de la source de données {#details}

Pour compléter la section [!UICONTROL Data Source Details] :

1. Nommez la source de données.
2. *(Facultatif)* Décrivez la source de données. Une description concise vous permet de définir le rôle ou l’objectif de la source de données.
3. Fournissez un code d’intégration. Un code d’intégration est votre propre identifiant unique pour cette source de données.
4. Dans la liste **[!UICONTROL ID Type]**, sélectionnez **[!UICONTROL Cross Device]**.
5. Dans la liste **[!UICONTROL ID Definition]**, sélectionnez une option qui définit le type de source de données. Les options incluent :
   * **[!UICONTROL Person]**: ID qui définit une seule personne. Cet ID peut être mappé à plusieurs [!DNL Audience Manager] ID.
   * **[!UICONTROL Household]**: ID qui définit un groupe de personnes. Cet ID peut être mappé à plusieurs [!DNL Audience Manager] ID.

## Contrôles des exportations de données {#export-controls}

[Les ](../data-export-controls.md) contrôles d’exportation de données sont des règles de classification facultatives que vous pouvez appliquer à une source de données et à une destination. Ils vous empêchent d’envoyer des données vers une destination lorsque cette action enfreint un accord de confidentialité ou d’utilisation des données. Ignorez cette section si vous n’utilisez pas [!UICONTROL Data Export Controls].

## Paramètres de source de données {#settings}

[!UICONTROL Data Source Settings] offre plusieurs options, mais ces 2 options sont importantes pour la création d’une source de données sur plusieurs périphériques :

* **[!UICONTROL Use as Authenticated Profile]**: Sélectionné par défaut, ce paramètre vous permet de créer un fichier  [!UICONTROL Profile Merge Rule] avec vos propres données authentifiées.

* **[!UICONTROL Use as a Device Graph]**: Ce contrôle n’est disponible que pour les comptes répertoriés en tant que fournisseur de données. Cette case à cocher crée votre source de données sous forme de graphique de périphérique et vous permet de la partager avec d&#39;autres [!DNL Audience Manager] clients. Contactez votre consultant [!DNL Audience Manager] pour être configuré en tant que fournisseur de données et pour spécifier avec quels clients ce [!UICONTROL Data Source] doit être partagé. Votre consultant va configurer le partage des graphiques de votre compte et de votre périphérique au moyen d&#39;un processus de mise en service interne.

* **[!UICONTROL Data retention for inactive Customer IDs]**: Ce contrôle vous permet de définir la période de rétention des données pour les ID de client inactifs. Cela détermine la durée pendant laquelle l’Audience Manager conserve les ID de client dans notre base de données après leur dernière consultation sur la plateforme d’Audience Manager. La valeur par défaut est de 24 mois (720 jours). La valeur minimale que vous pouvez définir est de 1 mois et la valeur maximale est de 5 ans. Notez que nous comptons tous les mois comme 30 jours. L’Audience Manager exécute un processus qui supprime les ID de client inactifs une fois par semaine, conformément à la rétention de données que vous avez définie pour les ID de client inactifs.

Les champs de texte associés à ces paramètres vous permettent de renommer [!UICONTROL Data Source] avec un alias qui apparaît dans les options [Règle de fusion de Profil](merge-rule-definitions.md). Par exemple, si vous ajoutez un alias à **[!UICONTROL Use as Authenticated Profile]**, ce nom apparaît dans la liste [!UICONTROL Authenticated Profile Options]. Si vous ajoutez un alias à **[!UICONTROL Use as a Device Graph]**, ce nom apparaît dans la liste [!UICONTROL Device Options].

## Créer une règle de fusion de Profil {#create-profile-merge-rule}

Pour créer un [!UICONTROL Profile Merge Rule], accédez à **[!UICONTROL Audience Data > Profile Merge Rules > Add New Rule]** et suivez les étapes décrites ici pour chaque section.

Vous pouvez créer jusqu’à 3 règles de fusion après avoir configuré une source de données sur plusieurs périphériques. Vous avez accès à une règle de fusion du 4e Profil ([!UICONTROL All Cross-Device Profiles]) si vous vous abonnez à [Destinations basées sur les personnes](../destinations/people-based-destinations-overview.md).

Les autorisations d’administrateur sont requises pour créer, modifier ou supprimer une règle. Tous les utilisateurs peuvent vue et utiliser [!UICONTROL Profile Merge Rules] existant.

<!-- create-profile-merge-rule.xml -->

**Conditions préalables :** une source de données sur plusieurs périphériques est requise pour créer une  [!UICONTROL Profile Merge Rule]variable. Voir [Création d’une source de données](../manage-datasources.md#create-data-source).

>[!TIP]
>
>Voir [Options de règle de fusion de Profils définies](merge-rule-definitions.md) pour obtenir la description de ces différents contrôles.

## Informations fondamentales {#basic-info}

Pour compléter la section [!UICONTROL Basic Information] :

1. Nommez [!UICONTROL Profile Merge Rule].
2. *(Facultatif)* Décrivez le  [!UICONTROL Profile Merge Rule]. Une description concise vous aide à définir le rôle ou l’objectif de votre règle.
3. *(Facultatif)* Sélectionnez  **[!UICONTROL Set as default]** si vous souhaitez que cette option soit utilisée par défaut  [!UICONTROL Profile Merge Rule]. Les nouveaux segments sont automatiquement associés à la règle par défaut.

## Contrôles des exportations de données {#data-export-controls}

[Les ](../data-export-controls.md) contrôles d’exportation de données sont des règles de classification facultatives que vous pouvez appliquer à votre  [!UICONTROL Profile Merge Rule]application. Ils vous empêchent d’envoyer des données vers une destination lorsque cette action enfreint un accord de confidentialité ou d’utilisation des données. Ignorez cette section si vous n’utilisez pas [!UICONTROL Data Export Controls].

## Configuration des règles de fusion de profils {#profile-merge-rule-setup}

Pour compléter la section [!UICONTROL Proflie Merge Rule Setup] :

1. Sélectionnez un **[!UICONTROL Authenticated Option]**. Les options incluent :
   * **[!UICONTROL No Authenticated Profile]**
   * **[!UICONTROL Current Authenticated Profile]**
   * **[!UICONTROL Last Authenticated Profile]**
2. Sélectionnez un **[!UICONTROL Authenticated Profile Option]** (jusqu’à 3, maximum). Il s’agit des [sources de données inter-périphériques](merge-rules-start.md) que vous avez créées précédemment.
3. Sélectionnez **[!UICONTROL Device Option]**. Les options incluent :
   * **[!UICONTROL No Device Profile]**
   * **[!UICONTROL Current Device Profile]**
   * **[!UICONTROL Profile Link Device Graph]**
   * **[!UICONTROL Device Co-op]**
4. Cliquez sur **[!UICONTROL Save]**.

### Considérations relatives aux destinations Adobe Campaign utilisant des identifiants de plusieurs périphériques comme clés d’ID utilisateur {#considerations}

À la fin de 2019, nous avons publié une série d’améliorations des règles de fusion de Profil afin d’améliorer la précision des fichiers de commandes générés à l’aide d’ID d’ensemble de périphériques. Ces améliorations seront strictement respectées dans votre instance d’Audience Manager à compter du lundi 16 mars 2020. Par conséquent, les segments mappés à une destination à l’aide d’un ID inter-périphériques cesseront de produire des exportations dans certaines configurations de règles de fusion de Profil.

Pour garantir l’intégration correcte entre votre instance d’Audience Manager et vos destinations à l’aide d’identifiants inter-périphériques, tels que Adobe Campaign, assurez-vous de respecter les exigences suivantes :

1. Examinez la règle de fusion de Profils utilisée par les segments mappés à votre destination d’identifiant déclaré Adobe Campaign. La règle de fusion du Profil doit utiliser l&#39;option [!UICONTROL Last Authenticated Profile], de sorte que tous les profils authentifiés puissent être inclus dans les exportations. Si votre règle de fusion de Profil utilise une autre option, passez-la à [!UICONTROL Last Authenticated Profile].
2. Sélectionnez la source de données d’ID déclarés Adobe Campaign dans les paramètres de la règle de fusion de Profils.

>[!NOTE]
>
> Si vous avez atteint le nombre maximal de [!UICONTROL Profile Merge Rules] et avez besoin d’aide pour les configurer en fonction des instructions ci-dessus, contactez le service à la clientèle.

## Configurer le code de règle de fusion {#configure-merge-rule-code}

Suivez ces instructions pour configurer le code [!UICONTROL Adobe Experience Platform Identity Service], [!UICONTROL DIL] et mobile [!DNL SDK] pour qu&#39;il fonctionne avec vos règles de fusion.

<!-- merge-rules-configure-code.xml -->

### Conditions préalables

Vous devez configurer une [source de données multipériphériques](#create-data-source) et des [règles de fusion de profil](#create-profile-merge-rule) *avant d&#39;exécuter ces procédures.*

## Pour les clients du service d&#39;identité Adobe Experience Platform {#id-service-customers}

[!UICONTROL Adobe Experience Platform Identity Service] et la dernière version de [DIL](../../dil/dil-overview.md) sont recommandés lorsque vous utilisez [!UICONTROL Profile Merge Rules]. Cependant, vous n’avez pas besoin d’utiliser [!UICONTROL Adobe Experience Platform Identity Service] pour utiliser cette fonctionnalité. Si vous utilisez uniquement [!UICONTROL DIL], consultez la section [DIL hérité](#legacy-dil) ci-dessous.

### Configurer la fonction Définir l’ID de client

Lorsque vous utilisez [!UICONTROL Adobe Experience Platform Identity Service], la fonction `setCustomerIDs` transmet les ID déclarés à [!DNL Audience Manager]. Pour utiliser une règle de fusion de profil, vous devez modifier `setCustomerIDs` pour utiliser le code d&#39;intégration spécifié lors de la création d&#39;une source de données sur plusieurs périphériques. Supposons, par exemple, que vous ayez créé une source de données sur plusieurs périphériques avec le code d’intégration `my_datasource_ic`. Pour transmettre un ID déclaré, vous devez ajouter le code d’intégration à la fonction d’ID de visiteur, comme indiqué dans l’exemple de code modifié ci-dessous.

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

Pour plus d’informations, voir [Création d’une source de données sur plusieurs périphériques](#create-data-source) et [ID de client et états d’authentification](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html).

### Configurer la fonction `DIL.create`

Les dernières versions de [!UICONTROL DIL] récupèrent désormais automatiquement [!UICONTROL declared ID] de la fonction `visitorService` dans `DIL.create` (voir [Variables d&#39;ID déclarées](../declared-ids.md#declared-id-variables)). Vérifiez votre fonction `DIL.create` pour vous assurer que celle-ci est correctement configurée, comme le montre l&#39;exemple de code ci-dessous.

```js
var vDil = DIL.create({
   partner:"partner name",
   visitorService:{
      namespace:"INSERT-MCORG-ID-HERE"
   }
});
```

Dans la paire clé-valeur de l’espace de nommage, la variable `*`MCORG`*` correspond à votre [!DNL Experience Cloud] ID d’organisation. Si vous ne possédez pas cet identifiant, vous pouvez le trouver dans la section [!UICONTROL Administration] du tableau de bord [!DNL Experience Cloud]. Vous avez besoin d&#39;autorisations d&#39;administrateur pour vue ce tableau de bord. Voir [Administration : Services principaux](https://docs.adobe.com/content/help/fr-FR/core-services/interface/manage-users-and-products/admin-getting-started.html).

### Configuration des SDK

Voir la section [Configurer les SDK](#configure-sdks-legacy-dil) ci-dessous.

## DIL hérité {#legacy-dil}

Si vous n&#39;utilisez pas encore [!DNL Adobe Experience Platform Identity Service], vous devriez vraiment le faire. Mais nous comprenons que passer à un nouveau code nécessite une réflexion et des tests minutieux. Dans ce cas, vérifiez votre fonction `DIL.create` pour vous assurer que celle-ci est correctement configurée, comme le montre l&#39;exemple de code ci-dessous.

```js
DIL.create({
   partner: "partner name",
   declaredId:{
      dpuuid: YOUR_DPUUID,
      dpid: YOUR_DPID
   }
});
```

Pour plus d’informations, voir la section héritée [!UICONTROL DIL] dans [Variables d’ID déclarées](../declared-ids.md#declared-id-variables).

### Configuration des SDK {#configure-sdks-legacy-dil}

Vérifiez les méthodes de votre code [!DNL SDK] qui vous permettent de transmettre [!UICONTROL declared IDs] des périphériques mobiles [!DNL Android] et [!DNL iOS]. Les noms de variable des bibliothèques de code [!DNL Android] et [!DNL iOS] sont identiques :

* `dpid`: ID de source de données sur plusieurs périphériques.
* `dpuuid`: Le  [!UICONTROL declared ID] (c’est-à-dire l’ID utilisateur).

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
   <td colname="col2"> <p> <code> setDpidAndDpuuid </code> </p> <p> <b>Syntaxe :</b> </p> <p> <pre> public static void setDpidAndDpuuid(String dpid, String dpuuid); </pre> </p> <p> <b>Exemple:</b> </p> <p> <pre> AudienceManager.setDpidAndDpuuid("myDpid","myDpuuid"); </pre> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b> iOS </b> </p> </td> 
   <td colname="col2"> <p> <code> audienceSetDpid:dpuuid </code> </p> <p> <b>Syntaxe :</b> </p><p>
    <code class="javascript">
      +&nbsp;(void)&nbsp;audienceSetDpid:(NSString&nbsp;*)dpid 
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;dpuuid:(NSString&nbsp;*)dpuuid; 
    </code></p>
    <p> <b>Exemple:</b> </p><p>
    <code class="javascript">
      [ADBMobile&nbsp;audienceSetDpid:@"290"
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;dpuuid:@"99301393923940"];
    </code></p>
    </td>
  </tr>
 </tbody>
</table>

Voir aussi [Méthodes d’Audience Manager pour Android](hhttps://docs.adobe.com/content/help/en/mobile-services/android/audience-manager-android/c-audience-manager-methods.html) et [Méthodes d’Audience Manager pour iOS](https://docs.adobe.com/content/help/en/mobile-services/ios/aam-methods.html).

>[!MORELIKETHIS]
>
>* [Création d’une source de données](../manage-datasources.md#create-data-source)

