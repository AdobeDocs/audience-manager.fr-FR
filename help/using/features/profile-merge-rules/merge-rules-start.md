---
description: Pour créer des règles de fusion de profils, passez en revue et suivez les étapes de chacune des procédures décrites dans cette section.
seo-description: To create Profile Merge Rules review and complete the steps in each of the procedures described in this section.
seo-title: Getting Started with Profile Merge Rules
solution: Audience Manager
title: Prise en main des stratégies de fusion de profils
uuid: 7d32c60f-467c-42dd-afa9-437fd7c473c5
feature: Profile Merge
exl-id: 11f397dd-1f23-4b14-be6f-60ce8b77ab12
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '1263'
ht-degree: 1%

---

# Prise en main des stratégies de fusion de profils {#getting-started-with-profile-merge-rules}

Pour créer [!UICONTROL Profile Merge Rules], passez en revue et suivez les étapes de chacune des procédures décrites dans cette section.

<!-- merge-rules-start.xml -->

## Création d’une Source de données sur plusieurs appareils {#create-data-source}

Pour créer une source de données multi-appareils, accédez à **[!UICONTROL Audience Data > Data Sources > Add New]** et suivez les étapes de chaque section décrite ici. Des autorisations d’administrateur sont requises pour créer ou modifier une source de données multi-appareils.

<!-- create-cross-device-datasource.xml -->

>[!TIP]
>
>Voir [Paramètres de Source de données et options de menu](../datasources-list-and-settings.md#settings-menu-options) pour obtenir des descriptions de ces différents contrôles.

## Détails du Source de données {#details}

Pour terminer la section [!UICONTROL Data Source Details] :

1. Nommez la source de données.
2. *(Facultatif)* Décrivez la source de données. Une description concise vous permet de définir le rôle ou l’objectif de la source de données.
3. Fournissez un code d’intégration. Un code d’intégration est votre propre identifiant unique pour cette source de données.
4. Dans la liste **[!UICONTROL ID Type]**, sélectionnez **[!UICONTROL Cross Device]**.
5. Dans la liste **[!UICONTROL ID Definition]**, sélectionnez une option qui définit le type de source de données. Les options incluent :
   * **[!UICONTROL Person]** : identifiant qui définit une seule personne. Cet ID peut être mappé à plusieurs [!DNL Audience Manager] ID.
   * **[!UICONTROL Household]** : identifiant qui définit un groupe de personnes. Cet ID peut être mappé à plusieurs [!DNL Audience Manager] ID.

## Contrôles des exportations de données {#export-controls}

[Les contrôles des exportations de données](../data-export-controls.md) sont des règles de classification facultatives que vous pouvez appliquer à une source et à une destination de données. Elles vous empêchent d’envoyer des données vers une destination lorsque cette action enfreint un accord de confidentialité ou d’utilisation des données. Ignorez cette section si vous n’utilisez pas [!UICONTROL Data Export Controls].

## Paramètres de Source de données {#settings}

La section [!UICONTROL Data Source Settings] propose plusieurs options, mais ces 2 options sont importantes pour créer une source de données multi-appareils :

* **[!UICONTROL Use as Authenticated Profile]** : sélectionné par défaut, ce paramètre vous permet de créer un [!UICONTROL Profile Merge Rule] avec vos propres données authentifiées.

* **[!UICONTROL Use as a Device Graph]** : ce contrôle est disponible uniquement pour les comptes répertoriés en tant que fournisseur de données. Si vous cochez cette case, votre source de données est créée sous la forme d’une représentation graphique des appareils et vous pouvez la partager avec d’autres clients [!DNL Audience Manager]. Contactez votre consultant [!DNL Audience Manager] pour être configuré en tant que fournisseur de données et spécifier avec quels clients cet [!UICONTROL Data Source] doit être partagé. Votre conseiller va configurer le partage de graphiques de votre compte et de votre périphérique au moyen de processus d’approvisionnement internes.

* **[!UICONTROL Data retention for inactive Customer IDs]** : ce contrôle vous permet de définir la période de conservation des données pour les ID de client inactifs. Cela détermine la durée pendant laquelle l’Audience Manager conserve les ID de client dans notre base de données après leur dernière consultation sur la plateforme d’Audience Manager. La valeur par défaut est de 24 mois (720 jours). La valeur minimale est de 1 mois et la valeur maximale est de 5 ans. Notez que nous comptabilisons tous les mois comme 30 jours. Audience Manager exécute un processus qui supprime les ID de client inactifs une fois par semaine, conformément à la rétention de données que vous avez définie pour les ID de client inactifs.

Les champs de texte associés à ces paramètres vous permettent de renommer l’élément [!UICONTROL Data Source] avec un alias qui apparaît dans les [ options de stratégie de fusion de profils](merge-rule-definitions.md). Par exemple, si vous ajoutez un alias à **[!UICONTROL Use as Authenticated Profile]**, ce nom apparaît dans la liste [!UICONTROL Authenticated Profile Options]. Si vous ajoutez un alias à **[!UICONTROL Use as a Device Graph]**, ce nom apparaît dans la liste [!UICONTROL Device Options].

## Création d’une stratégie de fusion de profils {#create-profile-merge-rule}

Pour créer un [!UICONTROL Profile Merge Rule], accédez à **[!UICONTROL Audience Data > Profile Merge Rules > Add New Rule]** et suivez les étapes de chaque section décrite ici.

Vous pouvez créer jusqu’à 3 règles de fusion après la configuration d’une source de données multi-appareils. Vous avez accès à une 4e règle de fusion de profils ([!UICONTROL All Cross-Device Profiles]) si vous vous abonnez à [Destinations basées sur les personnes](../destinations/people-based-destinations-overview.md).

Les autorisations d’administrateur sont requises pour créer, modifier ou supprimer une règle. Tous les utilisateurs peuvent afficher et utiliser les [!UICONTROL Profile Merge Rules] existants.

<!-- create-profile-merge-rule.xml -->

**Conditions préalables :** Une source de données multi-appareils est nécessaire pour créer un [!UICONTROL Profile Merge Rule]. Voir [Création d’une Source de données](../manage-datasources.md#create-data-source).

>[!TIP]
>
>Voir [Options de stratégie de fusion de profils définies](merge-rule-definitions.md) pour obtenir des descriptions de ces différents contrôles.

## Informations fondamentales {#basic-info}

Pour terminer la section [!UICONTROL Basic Information] :

1. Nommez le [!UICONTROL Profile Merge Rule].
2. *(Facultatif)* Décrivez le [!UICONTROL Profile Merge Rule]. Une description concise vous permet de définir le rôle ou l’objectif de votre règle.
3. *(Facultatif)* Sélectionnez **[!UICONTROL Set as default]** si vous souhaitez faire de ce paramètre la valeur par défaut [!UICONTROL Profile Merge Rule]. Les nouveaux segments sont automatiquement associés à la règle par défaut.

## Contrôles des exportations de données {#data-export-controls}

[Les contrôles des exportations de données](../data-export-controls.md) sont des règles de classification facultatives que vous pouvez appliquer à votre [!UICONTROL Profile Merge Rule]. Elles vous empêchent d’envoyer des données vers une destination lorsque cette action enfreint un accord de confidentialité ou d’utilisation des données. Ignorez cette section si vous n’utilisez pas [!UICONTROL Data Export Controls].

## Configuration des règles de fusion de profils {#profile-merge-rule-setup}

Pour terminer la section [!UICONTROL Proflie Merge Rule Setup] :

1. Sélectionnez un **[!UICONTROL Authenticated Option]**. Les options incluent :
   * **[!UICONTROL No Authenticated Profile]**
   * **[!UICONTROL Current Authenticated Profile]**
   * **[!UICONTROL Last Authenticated Profile]**
2. Sélectionnez un **[!UICONTROL Authenticated Profile Option]** (jusqu’à 3, maximum). Il s’agit des [ sources de données multi-appareils](merge-rules-start.md) que vous avez créées précédemment.
3. Sélectionnez un **[!UICONTROL Device Option]**. Les options incluent :
   * **[!UICONTROL No Device Profile]**
   * **[!UICONTROL Current Device Profile]**
   * **[!UICONTROL Profile Link Device Graph]**
4. Cliquez sur **[!UICONTROL Save]**.

### Points à prendre en compte pour les destinations Adobe Campaign à l’aide des identifiants multi-appareils comme clés d’identifiant utilisateur {#considerations}

Fin 2019, nous avons publié une série d’améliorations des règles de fusion de profils afin d’améliorer la précision des fichiers de lots générés à l’aide des identifiants multi-appareils. Ces améliorations seront strictement honorées dans votre instance d’Audience Manager à compter du lundi 16 mars 2020. Par conséquent, les segments mappés à une destination à l’aide d’identifiants multi-appareils cesseront de produire des exportations dans certaines configurations de stratégies de fusion de profils.

Pour garantir la bonne intégration entre l’instance d’Audience Manager et les destinations à l’aide d’identifiants multi-appareils, tels qu’Adobe Campaign, assurez-vous de respecter les conditions suivantes :

1. Examinez la règle de fusion de profils utilisée par les segments mappés à votre destination d’identifiant déclaré Adobe Campaign. La stratégie de fusion de profils doit utiliser l’option [!UICONTROL Last Authenticated Profile] afin que tous les profils authentifiés puissent être inclus dans les exportations. Si votre stratégie de fusion de profils utilise une autre option, basculez-la sur [!UICONTROL Last Authenticated Profile].
2. Sélectionnez la source de données Adobe Campaign Declared ID dans les paramètres de la stratégie de fusion de profils.

>[!NOTE]
>
> Si vous avez atteint votre nombre maximum de [!UICONTROL Profile Merge Rules] et avez besoin d’aide pour les configurer en suivant les instructions ci-dessus, contactez l’assistance clientèle.

## Configuration du code de règle de fusion {#configure-merge-rule-code}

Suivez ces instructions pour configurer le code [!UICONTROL Adobe Experience Platform Identity Service], [!UICONTROL DIL] et mobile [!DNL SDK] afin qu’il fonctionne avec vos règles de fusion.

<!-- merge-rules-configure-code.xml -->

### Conditions préalables

Vous devez configurer une [ source de données multi-appareils](#create-data-source) et des [règles de fusion de profils](#create-profile-merge-rule) *avant* d’exécuter ces procédures.

## Pour les clients du service Adobe Experience Platform Identity {#id-service-customers}

[!UICONTROL Adobe Experience Platform Identity Service] et la dernière version de [DIL](../../dil/dil-overview.md) sont recommandés lorsque vous utilisez [!UICONTROL Profile Merge Rules]. Cependant, vous n’avez pas besoin d’utiliser le [!UICONTROL Adobe Experience Platform Identity Service] pour utiliser cette fonctionnalité. Si vous utilisez uniquement [!UICONTROL DIL], reportez-vous à la [section de DIL hérité](#legacy-dil) ci-dessous.

### Configuration de la fonction Set Customer ID

Lorsque vous utilisez [!UICONTROL Adobe Experience Platform Identity Service], la fonction `setCustomerIDs` transmet les identifiants déclarés à [!DNL Audience Manager]. Pour utiliser une règle de fusion de profils, vous devez modifier `setCustomerIDs` afin d’utiliser le code d’intégration spécifié lors de la création d’une source de données multi-appareils. Par exemple, supposons que vous ayez créé une source de données multi-appareils avec le code d’intégration `my_datasource_ic`. Pour transmettre un ID déclaré, vous devez ajouter le code d’intégration à la fonction d’identification des visiteurs, comme illustré dans l’exemple de code modifié ci-dessous.

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

Pour plus d’informations, voir [Création d’une Source de données multi-appareils](#create-data-source) et [ID de client et états d’authentification](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html).

### Configurer la fonction `DIL.create`

Les dernières versions de [!UICONTROL DIL] récupèrent désormais automatiquement la fonction [!UICONTROL declared ID] de `visitorService` dans `DIL.create` (voir [Variables d&#39;ID déclarées](../declared-ids.md#declared-id-variables)). Vérifiez votre fonction `DIL.create` pour vous assurer que celle-ci est configurée correctement, comme illustré dans l’exemple de code ci-dessous.

```js
var vDil = DIL.create({
   partner:"partner name",
   visitorService:{
      namespace:"INSERT-MCORG-ID-HERE"
   }
});
```

Dans la paire clé-valeur de l’espace de noms, la variable `*`MCORG`*` est votre ID d’organisation [!DNL Experience Cloud]. Si vous ne possédez pas cet identifiant, vous pouvez le trouver dans la section [!UICONTROL Administration] du tableau de bord [!DNL Experience Cloud]. Vous avez besoin des autorisations d’administrateur pour afficher ce tableau de bord. Voir [Administration : services principaux](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html).

### Configuration des SDK

Voir la section [Configuration des SDK](#configure-sdks-legacy-dil) ci-dessous.

## DIL hérité {#legacy-dil}

Si vous n&#39;utilisez pas encore [!DNL Adobe Experience Platform Identity Service], vous devriez vraiment le faire. Mais nous comprenons que passer à un nouveau code nécessite une réflexion et des tests minutieux. Dans ce cas, vérifiez votre fonction `DIL.create` pour vous assurer que celle-ci est configurée correctement, comme illustré dans l’exemple de code ci-dessous.

```js
DIL.create({
   partner: "partner name",
   declaredId:{
      dpuuid: YOUR_DPUUID,
      dpid: YOUR_DPID
   }
});
```

Pour plus d’informations, reportez-vous à la section [!UICONTROL DIL] héritée dans la section [Variables d’identifiant déclaré](../declared-ids.md#declared-id-variables).

### Configuration des SDK {#configure-sdks-legacy-dil}

Vérifiez les méthodes de votre code [!DNL SDK] qui vous permettent de transmettre [!UICONTROL declared IDs] à partir des appareils mobiles [!DNL Android] et [!DNL iOS]. Les noms de variable des bibliothèques de code [!DNL Android] et [!DNL iOS] sont identiques :

* `dpid` : identifiant de source de données multi-appareils.
* `dpuuid` : [!UICONTROL declared ID] (c’est-à-dire l’identifiant utilisateur).

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

Voir aussi [Méthodes d’Audience Manager pour Android](https://experienceleague.adobe.com/docs/mobile-services/android/audience-manager-android/c-audience-manager-methods.html) et [Méthodes d’Audience Manager pour iOS](https://experienceleague.adobe.com/docs/mobile-services/ios/aam-methods.html).

>[!MORELIKETHIS]
>
>* [Création d’une source de données](../manage-datasources.md#create-data-source)
