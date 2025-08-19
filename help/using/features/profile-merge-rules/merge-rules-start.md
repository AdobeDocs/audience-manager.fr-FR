---
description: Pour créer des règles de fusion de profils, passez en revue les étapes de chacune des procédures décrites dans cette section et suivez-les.
seo-description: To create Profile Merge Rules review and complete the steps in each of the procedures described in this section.
seo-title: Getting Started with Profile Merge Rules
solution: Audience Manager
title: Prise en main des règles de fusion de profils
uuid: 7d32c60f-467c-42dd-afa9-437fd7c473c5
feature: Profile Merge
exl-id: 11f397dd-1f23-4b14-be6f-60ce8b77ab12
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '1263'
ht-degree: 1%

---

# Prise en main des règles de fusion de profils {#getting-started-with-profile-merge-rules}

Pour créer des [!UICONTROL Profile Merge Rules], passez en revue et suivez les étapes de chacune des procédures décrites dans cette section.

<!-- merge-rules-start.xml -->

## Création d’une Source de données entre appareils {#create-data-source}

Pour créer une source de données entre appareils, accédez à **[!UICONTROL Audience Data > Data Sources > Add New]** et suivez les étapes de chaque section décrite ici. Les autorisations d’administrateur sont requises pour créer ou modifier une source de données entre appareils.

<!-- create-cross-device-datasource.xml -->

>[!TIP]
>
>Voir [Paramètres du Source de données et options de menu](../datasources-list-and-settings.md#settings-menu-options) pour obtenir une description de ces différents contrôles.

## Détails du Source de données {#details}

Pour remplir la section [!UICONTROL Data Source Details] :

1. Nommez la source de données.
2. *(Facultatif)* Décrivez la source de données. Une description concise permet de définir le rôle ou l’objectif de la source de données.
3. Fournissez un code d’intégration. Un code d’intégration est votre propre ID unique pour cette source de données.
4. Dans la liste **[!UICONTROL ID Type]**, sélectionnez **[!UICONTROL Cross Device]**.
5. Dans la liste **[!UICONTROL ID Definition]**, sélectionnez une option qui définit le type de source de données. Les options incluent :
   * **[!UICONTROL Person]** : ID qui définit une seule personne. Cet identifiant peut être mappé à plusieurs identifiants [!DNL Audience Manager].
   * **[!UICONTROL Household]** : ID qui définit un groupe de personnes. Cet identifiant peut être mappé à plusieurs identifiants [!DNL Audience Manager].

## Contrôles des exportations de données {#export-controls}

Les [ Contrôles d’exportation de données ](../data-export-controls.md) sont des règles de classification facultatives que vous pouvez appliquer à une source de données et à une destination. Ils vous empêchent d’envoyer des données à une destination lorsque cette action enfreint un accord d’utilisation ou de confidentialité des données. Ignorez cette section si vous n’utilisez pas [!UICONTROL Data Export Controls].

## Paramètres du Source de données {#settings}

[!UICONTROL Data Source Settings] section fournit plusieurs options, mais ces deux éléments sont importants pour la création d’une source de données entre appareils :

* **[!UICONTROL Use as Authenticated Profile]** : sélectionné par défaut, ce paramètre vous permet de créer un [!UICONTROL Profile Merge Rule] avec vos propres données authentifiées.

* **[!UICONTROL Use as a Device Graph]** : ce contrôle est disponible uniquement pour les comptes répertoriés en tant que fournisseur de données. Si vous cochez cette case, votre source de données est créée sous la forme d’un graphique d’appareil et vous pouvez la partager avec d’autres clients [!DNL Audience Manager]. Collaborez avec votre consultant [!DNL Audience Manager] pour configurer en tant que fournisseur de données et pour spécifier les clients avec lesquels ce [!UICONTROL Data Source] doit être partagé. Votre consultant approvisionnera votre compte et le partage de graphiques d’appareils par le biais d’un processus d’approvisionnement interne.

* **[!UICONTROL Data retention for inactive Customer IDs]** : ce contrôle permet de définir la période de conservation des données pour les ID de client inactifs. Cela détermine la durée pendant laquelle Audience Manager conserve les ID de client dans notre base de données après leur dernière consultation sur la plateforme Audience Manager. La valeur par défaut est de 24 mois (720 jours). La valeur minimale que vous pouvez définir est de 1 mois et la valeur maximale est de 5 ans. Notez que tous les mois comptent comme 30 jours. Audience Manager exécute un processus qui supprime les ID de client inactifs une fois par semaine, conformément à la conservation des données que vous avez définie pour les ID de client inactifs.

Les champs de texte associés à ces paramètres vous permettent de renommer le [!UICONTROL Data Source] avec un alias qui apparaît dans les options [Règle de fusion de profil](merge-rule-definitions.md). Par exemple, si vous ajoutez un alias à **[!UICONTROL Use as Authenticated Profile]**, ce nom apparaît dans la liste [!UICONTROL Authenticated Profile Options]. Si vous ajoutez un alias à **[!UICONTROL Use as a Device Graph]**, ce nom apparaît dans la liste des [!UICONTROL Device Options].

## Créer une règle de fusion de profil {#create-profile-merge-rule}

Pour créer un [!UICONTROL Profile Merge Rule], accédez à **[!UICONTROL Audience Data > Profile Merge Rules > Add New Rule]** et suivez les étapes de chaque section décrite ici.

Vous pouvez créer jusqu’à 3 règles de fusion après avoir configuré une source de données entre appareils. Vous avez accès à une 4e règle de fusion de profil ([!UICONTROL All Cross-Device Profiles]) si vous vous inscrivez à des [Destinations basées sur les personnes](../destinations/people-based-destinations-overview.md).

Les autorisations d’administrateur sont requises pour créer, modifier ou supprimer une règle. Tous les utilisateurs peuvent afficher et utiliser des [!UICONTROL Profile Merge Rules] existants.

<!-- create-profile-merge-rule.xml -->

**Conditions préalables** une source de données entre appareils est nécessaire pour créer un [!UICONTROL Profile Merge Rule]. Voir [Création d’une Source de données](../manage-datasources.md#create-data-source).

>[!TIP]
>
>Voir [Options de la règle de fusion de profil définies](merge-rule-definitions.md) pour obtenir une description de ces différents contrôles.

## Informations fondamentales {#basic-info}

Pour remplir la section [!UICONTROL Basic Information] :

1. Nommez le [!UICONTROL Profile Merge Rule] .
2. *(Facultatif)* Décrivez le [!UICONTROL Profile Merge Rule]. Une description concise vous permet de définir le rôle ou l’objectif de votre règle.
3. *(Facultatif)* Sélectionnez **[!UICONTROL Set as default]** si vous souhaitez en faire l’[!UICONTROL Profile Merge Rule] par défaut. Les nouveaux segments sont automatiquement associés à la règle par défaut.

## Contrôles des exportations de données {#data-export-controls}

Les [ Contrôles d’exportation de données ](../data-export-controls.md) sont des règles de classification facultatives que vous pouvez appliquer à vos [!UICONTROL Profile Merge Rule]. Ils vous empêchent d’envoyer des données à une destination lorsque cette action enfreint un accord d’utilisation ou de confidentialité des données. Ignorez cette section si vous n’utilisez pas [!UICONTROL Data Export Controls].

## Configuration de la règle de fusion de profils {#profile-merge-rule-setup}

Pour remplir la section [!UICONTROL Proflie Merge Rule Setup] :

1. Sélectionnez un **[!UICONTROL Authenticated Option]**. Les options incluent :
   * **[!UICONTROL No Authenticated Profile]**
   * **[!UICONTROL Current Authenticated Profile]**
   * **[!UICONTROL Last Authenticated Profile]**
2. Sélectionnez une **[!UICONTROL Authenticated Profile Option]** (jusqu’à 3, maximum). Il s’agit des [ sources de données inter-appareils](merge-rules-start.md) que vous avez créées précédemment.
3. Sélectionnez un **[!UICONTROL Device Option]**. Les options incluent :
   * **[!UICONTROL No Device Profile]**
   * **[!UICONTROL Current Device Profile]**
   * **[!UICONTROL Profile Link Device Graph]**
4. Cliquez sur **[!UICONTROL Save]**.

### Considérations relatives aux destinations Adobe Campaign utilisant des identifiants sur plusieurs appareils en tant que clés d’ID utilisateur {#considerations}

Fin 2019, nous avons publié une série d’améliorations des règles de fusion de profils pour améliorer la précision des fichiers de lots générés à l’aide d’identifiants entre appareils. Ces améliorations seront strictement appliquées à votre instance Audience Manager à compter du lundi 16 mars 2020. Par conséquent, les segments mappés à une destination à l’aide d’identifiants sur plusieurs appareils cesseront de produire des exportations dans certaines configurations de règles de fusion de profils.

Pour garantir la bonne intégration entre votre instance Audience Manager et les destinations à l’aide d’identifiants entre appareils, tels qu’Adobe Campaign, assurez-vous de respecter les exigences suivantes :

1. Examinez la Règle de fusion de profils utilisée par les segments mappés à votre destination Adobe Campaign avec identifiant Declared ID. La règle de fusion de profils doit utiliser l’option [!UICONTROL Last Authenticated Profile] afin que tous les profils authentifiés puissent être inclus dans les exportations. Si votre règle de fusion de profils utilise une autre option, passez-la à [!UICONTROL Last Authenticated Profile].
2. Sélectionnez la source de données Adobe Campaign Declared ID dans les paramètres de la règle de fusion de profils.

>[!NOTE]
>
> Si vous avez atteint le nombre maximal de [!UICONTROL Profile Merge Rules] et que vous avez besoin d’aide pour les configurer en fonction des instructions ci-dessus, contactez l’assistance clientèle.

## Configurer le code de la règle de fusion {#configure-merge-rule-code}

Suivez ces instructions pour configurer le code [!UICONTROL Adobe Experience Platform Identity Service], [!UICONTROL DIL] et de [!DNL SDK] mobile pour qu’il fonctionne avec vos règles de fusion.

<!-- merge-rules-configure-code.xml -->

### Conditions préalables

Vous devez configurer une [source de données entre appareils](#create-data-source) et [règles de fusion de profils](#create-profile-merge-rule) *avant d’effectuer* procédures suivantes.

## Pour les clients Adobe Experience Platform Identity Service {#id-service-customers}

La [!UICONTROL Adobe Experience Platform Identity Service] et la dernière version de [DIL](../../dil/dil-overview.md) sont recommandées lorsque vous utilisez [!UICONTROL Profile Merge Rules]. Toutefois, il n’est pas nécessaire d’utiliser le [!UICONTROL Adobe Experience Platform Identity Service] pour utiliser cette fonctionnalité. Si vous utilisez uniquement [!UICONTROL DIL], reportez-vous à la section [DIL hérité](#legacy-dil) ci-dessous.

### Configuration de la fonction Définition de l’ID du client

Lorsque vous utilisez le [!UICONTROL Adobe Experience Platform Identity Service], la fonction `setCustomerIDs` transmet les identifiants déclarés aux [!DNL Audience Manager]. Pour utiliser une règle de fusion de profil, vous devez modifier `setCustomerIDs` pour utiliser le code d’intégration spécifié lors de la création d’une source de données inter-appareils. Supposons, par exemple, que vous ayez créé une source de données inter-appareils avec le code d’intégration `my_datasource_ic`. Pour transmettre un ID déclaré, vous devez ajouter le code d’intégration à la fonction d’identifiant visiteur, comme illustré dans l’exemple de code modifié ci-dessous.

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

Pour plus d’informations, consultez [Création d’une Source de données entre appareils](#create-data-source) et [ID de client et états d’authentification](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html).

### Configuration de la fonction `DIL.create`

Les dernières versions d’[!UICONTROL DIL] récupèrent désormais automatiquement les [!UICONTROL declared ID] de la fonction `visitorService` dans `DIL.create` (voir [Variables d’ID déclarées](../declared-ids.md#declared-id-variables)). Vérifiez votre fonction `DIL.create` pour vous assurer qu’elle est correctement configurée, comme illustré dans l’exemple de code ci-dessous.

```js
var vDil = DIL.create({
   partner:"partner name",
   visitorService:{
      namespace:"INSERT-MCORG-ID-HERE"
   }
});
```

Dans la paire clé-valeur d’espace de noms, la variable `*`MCORG`*` est votre identifiant d’organisation [!DNL Experience Cloud]. Si vous ne disposez pas de cet identifiant, vous pouvez le trouver dans la section [!UICONTROL Administration] du tableau de bord [!DNL Experience Cloud]. Vous avez besoin d’autorisations d’administrateur pour afficher ce tableau de bord. Voir [Administration : services principaux](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html).

### Configuration des SDK

Consultez la section [Configurer les SDK](#configure-sdks-legacy-dil) ci-dessous.

## DIL hérité {#legacy-dil}

Si vous n’utilisez pas encore [!DNL Adobe Experience Platform Identity Service], c’est ce que vous devez faire. Mais nous comprenons que le passage à un nouveau code nécessite une réflexion et des tests attentifs. Dans ce cas, vérifiez votre fonction `DIL.create` pour vous assurer qu’elle est correctement configurée, comme illustré dans l’exemple de code ci-dessous.

```js
DIL.create({
   partner: "partner name",
   declaredId:{
      dpuuid: YOUR_DPUUID,
      dpid: YOUR_DPID
   }
});
```

Pour plus d’informations, consultez la section sur les [!UICONTROL DIL] hérités dans [Variables d’ID déclarés](../declared-ids.md#declared-id-variables).

### Configuration des SDK {#configure-sdks-legacy-dil}

Vérifiez les méthodes dans votre code [!DNL SDK] qui vous permettent de transmettre des [!UICONTROL declared IDs] à partir d’appareils mobiles [!DNL Android] et [!DNL iOS]. Les noms des variables pour les bibliothèques de code [!DNL Android] et [!DNL iOS] sont identiques :

* `dpid` : identifiant de source de données sur l’ensemble des appareils.
* `dpuuid` : le [!UICONTROL declared ID] (c’est-à-dire l’identifiant utilisateur).

<table id="table_2ACA3E5F316D4413B10A4403B786CC23"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type d’appareil </th> 
   <th colname="col2" class="entry"> Méthode </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b> Android </b> </p> </td> 
   <td colname="col2"> <p> <code> setDpidAndDpuuid </code> </p> <p> <b>Syntaxe :</b> </p> <p> <pre> void statique public setDpidAndDpuuid(String dpid, String dpuuid); </pre> </p> <p> <b>Exemple :</b> </p> <p> <pre> AudienceManager.setDpidAndDpuuid(« myDpid »,« myDpuuid »); </pre> </p> </td> 
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
      &lbrack;ADBMobile&nbsp;audienceSetDpid:@"290"
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;dpuuid:@"99301393923940"&rbrack;;
    </code></p>
    </td>
  </tr>
 </tbody>
</table>

Voir aussi [Méthodes Audience Manager pour Android](https://experienceleague.adobe.com/docs/mobile-services/android/audience-manager-android/c-audience-manager-methods.html) et [Méthodes Audience Manager pour iOS](https://experienceleague.adobe.com/docs/mobile-services/ios/aam-methods.html).

>[!MORELIKETHIS]
>
>* [Création d’une source de données](../manage-datasources.md#create-data-source)
