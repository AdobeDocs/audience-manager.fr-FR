---
description: Pour créer des règles de fusion de profils, passez en revue et suivez les étapes de chacune des procédures décrites dans cette section.
seo-description: To create Profile Merge Rules review and complete the steps in each of the procedures described in this section.
seo-title: Getting Started with Profile Merge Rules
solution: Audience Manager
title: Démarrage des stratégies de fusion de profils
uuid: 7d32c60f-467c-42dd-afa9-437fd7c473c5
feature: Profile Merge
exl-id: 11f397dd-1f23-4b14-be6f-60ce8b77ab12
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '1280'
ht-degree: 3%

---

# Démarrage des stratégies de fusion de profils {#getting-started-with-profile-merge-rules}

Pour créer [!UICONTROL Profile Merge Rules], passez en revue et suivez les étapes de chacune des procédures décrites dans cette section.

<!-- merge-rules-start.xml -->

## Création d’une source de données multi-appareils {#create-data-source}

Pour créer une source de données multi-appareils, accédez à **[!UICONTROL Audience Data > Data Sources > Add New]** et suivez les étapes décrites ici pour chaque section. Des autorisations d’administrateur sont requises pour créer ou modifier une source de données multi-appareils.

<!-- create-cross-device-datasource.xml -->

>[!TIP]
>
>Voir [Paramètres de source de données et options de menu](../datasources-list-and-settings.md#settings-menu-options) pour obtenir des descriptions de ces différents contrôles.

## Détails de la source de données {#details}

Pour terminer la [!UICONTROL Data Source Details] section :

1. Nommez la source de données.
2. *(Facultatif)* Décrivez la source de données. Une description concise vous permet de définir le rôle ou l’objectif de la source de données.
3. Fournissez un code d’intégration. Un code d’intégration est votre propre identifiant unique pour cette source de données.
4. Dans le **[!UICONTROL ID Type]** list, select **[!UICONTROL Cross Device]**.
5. Dans le **[!UICONTROL ID Definition]** sélectionnez une option qui définit le type de source de données. Les options incluent :
   * **[!UICONTROL Person]**: Identifiant qui définit une seule personne. Cet identifiant peut être mappé à plusieurs [!DNL Audience Manager] ID.
   * **[!UICONTROL Household]**: Identifiant qui définit un groupe de personnes. Cet identifiant peut être mappé à plusieurs [!DNL Audience Manager] ID.

## Contrôles des exportations de données {#export-controls}

[Contrôles des exportations de données](../data-export-controls.md) sont des règles de classification facultatives que vous pouvez appliquer à une source de données et à une destination. Elles vous empêchent d’envoyer des données vers une destination lorsque cette action enfreint un accord de confidentialité ou d’utilisation des données. Ignorer cette section si vous n’utilisez pas [!UICONTROL Data Export Controls].

## Paramètres de source de données {#settings}

[!UICONTROL Data Source Settings] propose plusieurs options, mais ces deux options sont importantes pour créer une source de données multi-appareils :

* **[!UICONTROL Use as Authenticated Profile]**: Sélectionné par défaut, ce paramètre permet de créer une [!UICONTROL Profile Merge Rule] avec vos propres données authentifiées.

* **[!UICONTROL Use as a Device Graph]**: Ce contrôle est disponible uniquement pour les comptes répertoriés en tant que fournisseur de données. Si vous cochez cette case, votre source de données est créée sous la forme d’une représentation graphique des appareils et vous pouvez la partager avec d’autres utilisateurs. [!DNL Audience Manager] clients. Travaillez avec votre [!DNL Audience Manager] consultant pour être configuré en tant que fournisseur de données et spécifier les clients que [!UICONTROL Data Source] doivent être partagées avec . Votre conseiller va configurer le partage de graphiques de votre compte et de votre périphérique au moyen de processus d’approvisionnement internes.

* **[!UICONTROL Data retention for inactive Customer IDs]**: Ce contrôle vous permet de définir la période de conservation des données pour les ID de client inactifs. Cela détermine la durée pendant laquelle l’Audience Manager conserve les ID de client dans notre base de données après leur dernière consultation sur la plateforme d’Audience Manager. La valeur par défaut est de 24 mois (720 jours). La valeur minimale est de 1 mois et la valeur maximale est de 5 ans. Notez que nous comptabilisons tous les mois comme 30 jours. Audience Manager exécute un processus qui supprime les ID de client inactifs une fois par semaine, conformément à la rétention de données que vous avez définie pour les ID de client inactifs.

Les champs de texte associés à ces paramètres permettent de renommer la variable [!UICONTROL Data Source] avec un alias qui apparaît dans la variable [Options des stratégies de fusion de profils](merge-rule-definitions.md). Par exemple, si vous ajoutez un alias à **[!UICONTROL Use as Authenticated Profile]**, ce nom apparaît dans la variable [!UICONTROL Authenticated Profile Options] liste. Si vous ajoutez un alias à **[!UICONTROL Use as a Device Graph]**, ce nom apparaît dans la variable [!UICONTROL Device Options] liste.

## Création d’une stratégie de fusion de profils {#create-profile-merge-rule}

Pour créer une [!UICONTROL Profile Merge Rule], accédez à **[!UICONTROL Audience Data > Profile Merge Rules > Add New Rule]** et suivez les étapes décrites ici pour chaque section.

Vous pouvez créer jusqu’à 3 règles de fusion après la configuration d’une source de données multi-appareils. Vous avez accès à une 4e stratégie de fusion de profils ([!UICONTROL All Cross-Device Profiles]) si vous vous abonnez à [Destinations basées sur les personnes](../destinations/people-based-destinations-overview.md).

Les autorisations d’administrateur sont requises pour créer, modifier ou supprimer une règle. Tous les utilisateurs peuvent afficher et utiliser les [!UICONTROL Profile Merge Rules].

<!-- create-profile-merge-rule.xml -->

**Conditions préalables :** Une source de données multi-appareils est nécessaire pour créer une [!UICONTROL Profile Merge Rule]. Voir [Création d’une source de données](../manage-datasources.md#create-data-source).

>[!TIP]
>
>Voir [Définition des options des règles de fusion de profils](merge-rule-definitions.md) pour obtenir des descriptions de ces différents contrôles.

## Informations fondamentales {#basic-info}

Pour terminer la [!UICONTROL Basic Information] section :

1. Attribuez un nom au [!UICONTROL Profile Merge Rule].
2. *(Facultatif)* Décrivez la variable [!UICONTROL Profile Merge Rule]. Une description concise vous permet de définir le rôle ou l’objectif de votre règle.
3. *(Facultatif)* Sélectionner **[!UICONTROL Set as default]** si vous souhaitez que cette valeur soit la valeur par défaut [!UICONTROL Profile Merge Rule]. Les nouveaux segments sont automatiquement associés à la règle par défaut.

## Contrôles des exportations de données {#data-export-controls}

[Contrôles des exportations de données](../data-export-controls.md) sont des règles de classification facultatives que vous pouvez appliquer à votre [!UICONTROL Profile Merge Rule]. Elles vous empêchent d’envoyer des données vers une destination lorsque cette action enfreint un accord de confidentialité ou d’utilisation des données. Ignorer cette section si vous n’utilisez pas [!UICONTROL Data Export Controls].

## Configuration des règles de fusion de profils {#profile-merge-rule-setup}

Pour terminer la [!UICONTROL Proflie Merge Rule Setup] section :

1. Sélectionnez une **[!UICONTROL Authenticated Option]**. Les options incluent :
   * **[!UICONTROL No Authenticated Profile]**
   * **[!UICONTROL Current Authenticated Profile]**
   * **[!UICONTROL Last Authenticated Profile]**
2. Sélectionnez une **[!UICONTROL Authenticated Profile Option]** (jusqu’à 3, maximum). Voici les [sources de données multi-appareils](merge-rules-start.md) vous avez créé précédemment.
3. Sélectionnez **[!UICONTROL Device Option]**. Les options incluent :
   * **[!UICONTROL No Device Profile]**
   * **[!UICONTROL Current Device Profile]**
   * **[!UICONTROL Profile Link Device Graph]**
4. Cliquez sur **[!UICONTROL Save]**.

### Points à prendre en compte pour les destinations Adobe Campaign à l’aide des identifiants multi-appareils comme clés d’identifiant utilisateur {#considerations}

Fin 2019, nous avons publié une série d’améliorations des règles de fusion de profils afin d’améliorer la précision des fichiers de lots générés à l’aide des identifiants multi-appareils. Ces améliorations seront strictement honorées dans votre instance d’Audience Manager à compter du lundi 16 mars 2020. Par conséquent, les segments mappés à une destination à l’aide d’identifiants multi-appareils cesseront de produire des exportations dans certaines configurations de stratégies de fusion de profils.

Pour garantir la bonne intégration entre l’instance d’Audience Manager et les destinations à l’aide d’identifiants multi-appareils, tels qu’Adobe Campaign, assurez-vous de respecter les conditions suivantes :

1. Examinez la règle de fusion de profils utilisée par les segments mappés à votre destination d’identifiant déclaré Adobe Campaign. La stratégie de fusion de profils doit utiliser la variable [!UICONTROL Last Authenticated Profile] afin que tous les profils authentifiés puissent être inclus dans les exportations. Si votre stratégie de fusion de profils utilise une autre option, basculez-la sur [!UICONTROL Last Authenticated Profile].
2. Sélectionnez la source de données Adobe Campaign Declared ID dans les paramètres de la stratégie de fusion de profils.

>[!NOTE]
>
> Si vous avez atteint le nombre maximal de [!UICONTROL Profile Merge Rules] et si vous avez besoin d’aide pour les configurer en fonction des instructions ci-dessus, contactez l’assistance clientèle.

## Configuration du code de règle de fusion {#configure-merge-rule-code}

Suivez ces instructions pour configurer la variable [!UICONTROL Adobe Experience Platform Identity Service], [!UICONTROL DIL], et mobile [!DNL SDK] pour utiliser vos règles de fusion.

<!-- merge-rules-configure-code.xml -->

### Conditions préalables

Vous devez configurer une [source de données multi-appareils](#create-data-source) et [règles de fusion de profils](#create-profile-merge-rule) *before* l’exécution de ces procédures.

## Pour les clients du service Adobe Experience Platform Identity {#id-service-customers}

Le [!UICONTROL Adobe Experience Platform Identity Service] et la dernière version de [DIL](../../dil/dil-overview.md) sont recommandés lorsque vous utilisez des [!UICONTROL Profile Merge Rules]. Cependant, vous n’avez pas besoin d’utiliser la variable [!UICONTROL Adobe Experience Platform Identity Service] pour utiliser cette fonctionnalité. Si vous utilisez simplement [!UICONTROL DIL], reportez-vous à la section [section DIL hérité](#legacy-dil) ci-dessous.

### Configuration de la fonction Set Customer ID

Lorsque vous utilisez l’objet [!UICONTROL Adobe Experience Platform Identity Service], la variable `setCustomerIDs` transmet les identifiants déclarés à [!DNL Audience Manager]. Pour utiliser une règle de fusion de profils, vous devez modifier `setCustomerIDs` pour utiliser le code d’intégration spécifié lors de la création d’une source de données multi-appareils. Supposons, par exemple, que vous ayez créé une source de données multi-appareils avec le code d’intégration. `my_datasource_ic`. Pour transmettre un ID déclaré, vous devez ajouter le code d’intégration à la fonction d’identification des visiteurs, comme illustré dans l’exemple de code modifié ci-dessous.

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

Pour plus d’informations, voir [Création d’une source de données multi-appareils](#create-data-source) et [ID de client et états d’authentification](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html).

### Configurer `DIL.create` function

Les dernières versions d’ [!UICONTROL DIL] récupère maintenant automatiquement la variable [!UICONTROL declared ID] de la `visitorService` fonction dans `DIL.create` (voir [Variables d’ID déclarées](../declared-ids.md#declared-id-variables)). Vérifiez vos `DIL.create` pour vous assurer qu’elle est configurée correctement, comme illustré dans l’exemple de code ci-dessous.

```js
var vDil = DIL.create({
   partner:"partner name",
   visitorService:{
      namespace:"INSERT-MCORG-ID-HERE"
   }
});
```

Dans la paire clé-valeur de l’espace de noms, la variable `*`MCORG`*` est votre variable [!DNL Experience Cloud] ID d’organisation. Si vous ne possédez pas cet identifiant, vous pouvez le trouver dans la variable [!UICONTROL Administration] de la section [!DNL Experience Cloud] tableau de bord. Vous avez besoin des autorisations d’administrateur pour afficher ce tableau de bord. Voir [Administration : Services principaux](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html).

### Configuration des SDK

Voir [Configuration des SDK](#configure-sdks-legacy-dil) ci-dessous.

## DIL hérité {#legacy-dil}

Si vous n’utilisez pas [!DNL Adobe Experience Platform Identity Service] pourtant, vous devriez vraiment le faire. Mais nous comprenons que passer à un nouveau code nécessite une réflexion et des tests minutieux. Dans ce cas, vérifiez vos `DIL.create` pour vous assurer qu’elle est configurée correctement, comme illustré dans l’exemple de code ci-dessous.

```js
DIL.create({
   partner: "partner name",
   declaredId:{
      dpuuid: YOUR_DPUUID,
      dpid: YOUR_DPID
   }
});
```

Pour plus d’informations, voir la page héritée de [!UICONTROL DIL] dans [Variables d’ID déclarées](../declared-ids.md#declared-id-variables).

### Configuration des SDK {#configure-sdks-legacy-dil}

Vérifiez les méthodes de votre [!DNL SDK] code qui permet de transmettre [!UICONTROL declared IDs] de [!DNL Android] et [!DNL iOS] périphériques mobiles. Les noms de variable pour la variable [!DNL Android] et [!DNL iOS] les bibliothèques de code sont les mêmes :

* `dpid`: Identifiant de source de données multi-appareils.
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

Voir aussi [Méthodes d’Audience Manager pour Android](https://experienceleague.adobe.com/docs/mobile-services/android/audience-manager-android/c-audience-manager-methods.html) et [Méthodes d’Audience Manager pour iOS](https://experienceleague.adobe.com/docs/mobile-services/ios/aam-methods.html).

>[!MORELIKETHIS]
>
>* [Création d’une source de données](../manage-datasources.md#create-data-source)

