---
description: 'Cette page comprend des instructions détaillées sur la manière de combiner des données de gestion de la relation client hors ligne avec des données comportementales en temps réel pour que les utilisateurs authentifiés puissent créer des segments d’audience, puis envoyer ces segments d’audience vers des destinations basées sur les personnes. '
seo-description: 'Cette page comprend des instructions détaillées sur la manière de combiner des données de gestion de la relation client hors ligne avec des données comportementales en temps réel pour que les utilisateurs authentifiés puissent créer des segments d’audience, puis envoyer ces segments d’audience vers des destinations basées sur les personnes.  '
seo-title: 'Processus C : personnalisation basée sur l’activité authentifiée associée aux données hors ligne'
solution: Audience Manager
title: 'Processus C : personnalisation basée sur l’activité authentifiée associée aux données hors ligne'
feature: People-Based Destinations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '918'
ht-degree: 5%

---


# Processus C : personnalisation basée sur l’activité authentifiée associée aux données hors ligne {#workflow-c}

>[!IMPORTANT]
>Cet article contient la documentation du produit destinée à vous guider tout au long de la configuration et de l’utilisation de cette fonction. Rien dans ce document n&#39;est un conseil juridique. Veuillez consulter votre propre conseiller juridique pour obtenir des conseils juridiques.

Cette page comprend des instructions détaillées sur la manière de combiner des données hors ligne [!DNL CRM] avec des données comportementales en temps réel pour que les utilisateurs authentifiés puissent créer des segments d’audience, puis envoyer ces segments d’audience à [!DNL People-Based Destinations].

## Etape 1 - Configuration des paramètres de source de données {#configure-data-source-settings}

Selon que vos [DPUUID](../../reference/ids-in-aam.md) sont des adresses électroniques hachées en minuscules, vous devrez peut-être configurer la source de données qui stockera les adresses électroniques hachées.

 

**Scénario 1 : vos[DPUUID](../../reference/ids-in-aam.md)sont déjà des adresses électroniques en minuscules hachées.**

Dans ce cas, passez à l’ [étape 5 - Configurer l’authentification](#configure-authentication)Platform basée sur les personnes.

 

**Scénario 2 : vos[DPUUID](../../reference/ids-in-aam.md)ne sont pas des adresses électroniques en minuscules hachées.**

Dans ce cas, vous devez créer une source de données multipériphériques qui stockera vos adresses électroniques hachées. Voici comment procéder :

1. Connectez-vous à votre compte d’Audience Manager et accédez à **[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]**, puis cliquez sur **[!UICONTROL Add New]**.
1. Saisissez un **[!UICONTROL Name]** et **[!UICONTROL Description]** pour votre nouvelle source de données.
1. Dans le menu **[!UICONTROL ID Type]** déroulant, sélectionnez **[!UICONTROL Cross Device]**.
1. Dans la **[!UICONTROL Data Source Settings]** section, sélectionnez les options **[!UICONTROL Inbound]** et **[!UICONTROL Outbound]** , puis activez l’ **[!UICONTROL Share associated cross-device IDs in people-based destinations]** option.
1. Utilisez le menu déroulant pour sélectionner le **[!UICONTROL Emails(SHA256, lowercased)]** libellé de cette source de données.
   >[!IMPORTANT]
   >
   >Cette option étiquette uniquement la source de données comme contenant des données hachées avec cet algorithme spécifique. L’Audience Manager ne hachage pas les données à cette étape. Assurez-vous que les adresses électroniques que vous prévoyez de stocker dans cette source de données sont déjà hachées avec l’ [!DNL SHA256] algorithme. Sinon, vous ne pourrez pas l&#39;utiliser pour [!DNL People-Based Destinations].

   ![pbd-datasource-settings](assets/pbd-ds-config.png)

   >[!NOTE]
   >
   > Pour obtenir des questions fréquentes sur la manière d’importer vos données hors ligne dans l’Audience Manager des destinations basées sur les personnes, reportez-vous à la section Intégration [des](people-based-destinations-prerequisites.md#data-onboarding) données.

Regardez la vidéo ci-dessous pour découvrir comment créer une source de données pour [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/29006/)

## Étape 2 - Utilisation d’identifiants déclarés pour faire correspondre des identifiants DPUUID à des adresses électroniques hachées via des appels HTTP en temps réel {#match-email-addresses}

Pour qualifier les utilisateurs authentifiés pour les caractéristiques basées sur des règles, vous devez envoyer la qualification de caractéristique par le biais d’identifiants [](../declared-ids.md)déclarés.

### Exemple

Supposons que vous ayez créé les deux sources de données suivantes.

| ID de source de données | Contenu de la source de données |
| -------------- | -------------------------- |
| 999999 | Identifiants DPUUID existants (CRM ID) |
| 987654 | Adresses électroniques hachées |

 

Ensuite, vous souhaitez définir les ID CRM ci-dessous pour la caractéristique du tableau.

| DPUUID (CRM ID) | Adresse électronique | Adresse électronique hachée | Caractéristique |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- | ------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 | location = US |

 

Votre ID déclaré doit respecter la syntaxe suivante :

`https://yourDomain.demdex.net/event?d_cid_ic=HashedEmailDataSourceIntegrationCode%01myHashedEmail&d_cid_ic=CRMDataSourceIntegrationCode%01myCRMID&key=value`

 

Dans l’exemple ci-dessus, l’appel d’ID déclaré doit se présenter comme suit :

`https://yourDomain.demdex.net/event?d_cid_ic=MyHashedEmailDataSource%0155e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149&d_cid_ic=MyCRMDataSource%0168079982765673198504052656074456196039&location=US`

## Etape 3 - Création d’une règle de fusion de Profils pour la segmentation {#create-profile-merge-rule-segmentation}

L’étape suivante consiste à créer une règle de fusion qui vous aidera à créer les segments d’audience à envoyer à votre [!DNL People-Based Destinations]utilisateur.

>[!IMPORTANT]
>
>Si une règle est déjà définie avec les options **[!UICONTROL Current Authenticated Profiles]** ou **[!UICONTROL Last Authenticated Profiles]** , vous pouvez passer à l’ [étape 4 - Créer des segments](#create-audience-segments)d’Audience.

1. Connectez-vous à votre compte d’Audience Manager et accédez à **[!UICONTROL Audience Data]** -> **[!UICONTROL Profile Merge Rules]**.
2. Cliquez sur **[!UICONTROL Add New Rule]**.
3. Saisissez une règle de fusion de profil **[!UICONTROL Name]** et **[!UICONTROL Description]**.
4. Dans la **[!UICONTROL Profile Merge Rule Setup]** section, sélectionnez la **[!UICONTROL Current Authenticated Profiles]** règle ou **[!UICONTROL Last Authenticated Profiles]** dans la **[!UICONTROL Cross-Device Options]** liste.
5. Dans la **[!UICONTROL Cross-Device Profile Options]** liste, sélectionnez les sources de données sur lesquelles vous souhaitez exécuter la segmentation. Il doit s’agir des sources de données contenant vos DPUUID existants.
   ![fusion-règle-configuration](assets/pbd-pmr-combined.png)

## Étape 4 - Création de segments d’Audience {#create-audience-segments}

Pour créer de nouveaux segments, utilisez le créateur [de](../segments/segment-builder.md)segments. Si vous souhaitez envoyer des segments d’audience existants à [!DNL People-Based Destinations]l’étape 5 - Configuration de l’authentification [Platform basée sur les personnes, passez à l’](#configure-authentication)étape 5.

## Étape 5 - Configuration de l’authentification Platform basée sur les personnes {#configure-authentication}

1. Connectez-vous à votre compte d’Audience Manager et accédez à **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**. Si vous disposez d’une intégration précédemment configurée avec une plateforme sociale, vous devriez la voir répertoriée dans cette page. Sinon, la page est vide.
   ![intégration basée sur les personnes](assets/pbd-config.png)
2. Cliquez sur **[!UICONTROL Add Account]**.
3. Utilisez le menu **[!UICONTROL People-Based Platform]** déroulant pour sélectionner la plate-forme avec laquelle vous souhaitez configurer l’intégration.
   ![plate-forme à base de personnes](assets/pbd-add.png)
4. Cliquez sur **[!UICONTROL Confirm]** pour être redirigé vers la page d&#39;authentification de la plateforme sélectionnée.
5. Une fois que vous êtes authentifié sur votre compte de plateforme sociale, vous êtes redirigé vers l’Audience Manager où vous devriez voir vos comptes d’annonceurs associés. Sélectionnez le compte publicitaire à utiliser, puis cliquez sur **[!UICONTROL Confirm]**.
6. L’Audience Manager affiche une notification en haut de la page pour vous indiquer si le compte a bien été ajouté. La notification vous permet également d’ajouter une adresse électronique de contact pour recevoir des notifications lorsque l’authentification de la plateforme sociale est sur le point d’expirer.

>[!IMPORTANT]
>
>L’Audience Manager gère l’intégration aux plateformes sociales au moyen de jetons d’authentification qui expirent après un certain temps. Voir Renouvellement du jeton d’authentification pour en savoir plus sur la manière de renouveler les jetons expirés.

## Etape 6 - Création d’une destination basée sur les personnes {#create-destination}

1. Connectez-vous à votre compte d’Audience Manager, accédez à **[!UICONTROL Audience Data]** > **[!UICONTROL Destinations]**, puis cliquez sur **[!UICONTROL Create Destination]**.
1. Dans la **[!UICONTROL Basic Information]** section, saisissez un **[!UICONTROL Name]** et **[!UICONTROL Description]** pour votre nouvelle source de données, puis utilisez les paramètres suivants :
   * **[!UICONTROL Category]**: Plateformes intégrées ;
   * **[!UICONTROL Type]**: basé sur les personnes ;
   * **[!UICONTROL Platform]**: sélectionnez la plateforme basée sur les personnes à laquelle vous souhaitez envoyer des segments d’audience ;
   * **[!UICONTROL Account]**: sélectionnez le compte publicitaire souhaité associé à la plateforme sélectionnée.
      ![create-destination](assets/pbd-create-destination.png)
1. Cliquez sur **[!UICONTROL Next]**.
1. Sélectionnez la destination **[!UICONTROL Data Export Labels]** que vous souhaitez définir.
1. Dans la **[!UICONTROL Configuration]** section, sélectionnez la source de données qui contient vos sources de données hachées.
1. Dans la **[!UICONTROL Segment Mappings]** section, sélectionnez les segments à envoyer à cette destination. Il s’agit des segments que vous avez créés à l’ [étape 4 - Créer des segments](#create-audience-segments)d’Audience.
1. Enregistrez la destination.
