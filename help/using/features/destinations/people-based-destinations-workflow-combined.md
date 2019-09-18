---
description: 'Cette page comprend des instructions détaillées sur la manière de combiner des données de gestion de la relation client hors ligne avec des données comportementales que vous avez déjà dans Audience Manager pour créer de nouveaux segments d’audience, puis envoyer ces segments d’audience aux destinations basées sur les personnes.  '
seo-description: 'Cette page comprend des instructions détaillées sur la manière de combiner des données de gestion de la relation client hors ligne avec des données comportementales que vous avez déjà dans Audience Manager pour créer de nouveaux segments d’audience, puis envoyer ces segments d’audience aux destinations basées sur les personnes.   '
seo-title: Processus A - Personnalisation basée sur toutes les activités en ligne combinées aux données hors ligne
solution: Audience Manager
title: Processus A - Personnalisation basée sur toutes les activités en ligne combinées aux données hors ligne
translation-type: tm+mt
source-git-commit: 455c198d7a096a620a2cf7c8b728b67335eadc8d

---


# Processus A - Personnalisation basée sur toutes les activités en ligne combinées aux données hors ligne {#workflow-a}

Cette page comprend des instructions détaillées sur la manière de combiner [!DNL CRM] des données hors ligne avec des données comportementales que vous avez déjà dans Audience Manager pour créer de nouveaux segments d’audience, puis envoyer ces segments d’audience à [!DNL People-Based Destinations].

## Étape 1 - Configuration des paramètres de source de données {#configure-data-source-settings}

Selon que vos [DPUUID](../../reference/ids-in-aam.md) sont des adresses électroniques hachées en minuscules, vous devrez peut-être configurer la source de données qui stockera les adresses électroniques hachées.

 

**Scénario 1 : vos[DPUUID](../../reference/ids-in-aam.md)sont déjà des adresses électroniques en minuscules hachées.**

Dans ce cas, vous devez étiqueter la source de données correspondante comme telle :

1. Accédez à [!UICONTROL Audience Data] -&gt; [!UICONTROL Data Sources].
1. Recherchez la source de données contenant vos [DPUUID](../../reference/ids-in-aam.md), puis cliquez dessus.
1. Dans le menu **[!UICONTROL ID Type]** déroulant, sélectionnez **[!UICONTROL Cross Device]**.
1. Vérifiez que l’option [!UICONTROL Cannot be tied to personally identifiable information] est désactivée.
1. Dans la **[!UICONTROL Data Source Settings]** section, sélectionnez les options **[!UICONTROL Inbound]** et **[!UICONTROL Outbound]** , puis activez l’ **[!UICONTROL Share associated cross-device IDs in people-based destinations]** option.
1. Utilisez le menu déroulant pour sélectionner le **[!UICONTROL Emails(SHA256, lowercased)]** libellé de cette source de données.
   >[!IMPORTANT]
   >
   >Cette option désigne uniquement la source de données comme contenant des données hachées avec cet algorithme spécifique. Audience Manager ne hachage pas les données à cette étape. Assurez-vous que les adresses électroniques que vous prévoyez de stocker dans cette source de données sont déjà hachées avec l’ [!DNL SHA256] algorithme. Sinon, vous ne pourrez pas l'utiliser pour [!DNL People-Based Destinations].

   ![pbd-datasource-settings](assets/pbd-ds-config.png)
1. Enregistrez les paramètres de la source de données.

 

**Scénario 2 : vos[DPUUID](../../reference/ids-in-aam.md)ne sont pas des adresses électroniques en minuscules hachées.**

Dans ce cas, vous devez créer une source de données multipériphériques qui stockera vos adresses électroniques hachées. Voici comment procéder :

1. Connectez-vous à votre compte Audience Manager, accédez à **[!UICONTROL Audience Data]** &gt; **[!UICONTROL Data Sources]**, puis cliquez sur **[!UICONTROL Add New]**.
1. Entrez un [!UICONTROL Name] et [!UICONTROL Description] pour votre nouvelle source de données.
1. Dans le menu **[!UICONTROL ID Type]** déroulant, sélectionnez **[!UICONTROL Cross Device]**.
1. Dans la **[!UICONTROL Data Source Settings]** section, sélectionnez les options **[!UICONTROL Inbound]** et **[!UICONTROL Outbound]** , puis activez l’ **[!UICONTROL Share associated cross-device IDs in people-based destinations]** option.
1. Utilisez le menu déroulant pour sélectionner le **[!UICONTROL Emails(SHA256, lowercased)]** libellé de cette source de données.
   >[!IMPORTANT]
   >
   >Cette option désigne uniquement la source de données comme contenant des données hachées avec cet algorithme spécifique. Audience Manager ne hachage pas les données à cette étape. Assurez-vous que les adresses électroniques que vous prévoyez de stocker dans cette source de données sont déjà hachées avec l’ [!DNL SHA256] algorithme. Sinon, vous ne pourrez pas l'utiliser pour [!DNL People-Based Destinations].

   ![pbd-datasource-settings](assets/pbd-ds-config.png)
1. Enregistrez les paramètres de la source de données.

>[!NOTE]
>
> Pour obtenir des questions fréquentes sur la manière d’importer vos données hors ligne dans Audience Manager pour les destinations basées sur les personnes, reportez-vous à la section [Intégration](people-based-destinations-prerequisites.md#data-onboarding) des données.

## Étape 2 - Correspondance des DPUUID avec des adresses électroniques hachées via la synchronisation des identifiants basée sur des fichiers {#match-ids-emails}

>[!IMPORTANT]
>
> Cette étape s'applique uniquement au [scénario 2](people-based-destinations-workflow-combined.md#configure-data-source-settings) décrit ci-dessus. Si vos [DPUUID](../../reference/ids-in-aam.md) existants sont déjà des adresses électroniques hachées, passez à l’ [étape 3 - Création d’une règle de fusion de profil pour la segmentation](people-based-destinations-workflow-combined.md#create-merge-rule).

Supposons que vous souhaitiez faire correspondre vos [DPUUID](../../reference/ids-in-aam.md) existants aux adresses électroniques hachées du tableau ci-dessous (colonne de droite) et stocker les adresses électroniques hachées dans la nouvelle source de données que vous avez créée à l’ [étape 1 - Configuration des paramètres](people-based-destinations-workflow-combined.md#configure-data-source-settings)de la source de données.

| DPUUID (ID CRM) | Adresse électronique | Adresse électronique hachée |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 |
| 67412682083411995725538770443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 89159024796760343733111707646026765593 | `name@mydomain.com` | feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

 

Vous pouvez lier jusqu’à 10 adresses électroniques hachées à un seul [PUUID](../../reference/ids-in-aam.md). Pour ce faire, séparez les adresses électroniques hachées par une virgule dans le fichier de synchronisation.

Dans notre exemple, vous avez maintenant deux sources de données.

| ID de source de données | Contenu de la source de données |
| -------------- | -------------------------- |
| 999999 | Identifiants DPUUID (CRM) existants |
| 987654 | Adresses électroniques hachées |

 

Votre fichier [de synchronisation des](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) identifiants aurait le contenu suivant :

```
68079982765673198504052656074456196039<TAB>55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149
67412682083411995725538770443620307584<TAB>16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a
89159024796760343733111707646026765593<TAB>feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6
```

 

Le fichier [de synchronisation des](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) identifiants doit suivre la structure d’appellation suivante :

`c2c_id_<DPUUID_DATA_SOURCE_ID>_<HASHED_EMAIL_DATA_SOURCE_ID>_TIMESTAMP.sync`

 

Dans l’exemple ci-dessus, le nom de fichier se présente comme suit :
`c2c_id_999999_987654_1560431657.sync`

[Téléchargez un exemple de fichier ici](https://marketing.adobe.com/resources/help/en_US/aam/downloads/c2c_id_999999_987654_1560431657.sync).

## Etape 3 - Création d’une règle de fusion de profil pour la segmentation {#create-merge-rule}

L’étape suivante consiste à créer une règle de fusion qui vous aidera à créer les segments d’audience à envoyer vers vos destinations basées sur les personnes.

>[!IMPORTANT]
>
> Si une règle est déjà définie avec les options [!UICONTROL Current Authenticated Profiles] ou [!UICONTROL Last Authenticated Profiles] , vous pouvez passer à l’ [étape 4 - Créer des segments](people-based-destinations-workflow-combined.md#create-audience-segments)d’audience.

1. Connectez-vous à votre compte Audience Manager et accédez à **[!UICONTROL Audience Data]** &gt; **[!UICONTROL Profile Merge Rules]**.
1. Cliquez sur **[!UICONTROL Add New Rule]**.
1. Entrez une règle de fusion de profil **[!UICONTROL Name]** et **[!UICONTROL Description]**.
1. Dans la **[!UICONTROL Profile Merge Rule Setup]** section, sélectionnez les **[!UICONTROL Current Authenticated Profiles]** ou **[!UICONTROL Last Authenticated Profiles]** options.
1. Dans la **[!UICONTROL Cross-Device Profile Options]** liste, sélectionnez les sources de données sur lesquelles vous souhaitez exécuter la segmentation. Il doit s’agir des sources de données contenant vos [DPUUID](../../reference/ids-in-aam.md)existants.

## Étape 4 - Création de segments d’audience {#create-audience-segments}

Pour créer de nouveaux segments d’audience, utilisez le créateur de [segments](../segments/segment-builder.md). Si vous souhaitez envoyer à des segments d’audience existants, passez à l’ [!DNL People-Based Destinations]étape 5 - Configuration de l’authentification [](people-based-destinations-workflow-combined.md#configure-authentication)de plateformes basées sur les personnes.

## Étape 5 - Configuration de l’authentification de plateformes basées sur les personnes {#configure-authentication}

1. Connectez-vous à votre compte Audience Manager et accédez à **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**. Si vous avez déjà configuré une intégration avec une plateforme sociale, elle doit apparaître dans cette page. Sinon, la page est vide.
   ![intégration basée sur les personnes](assets/pbd-config.png)
1. Cliquez sur **[!UICONTROL Add Account]**.
1. Utilisez le menu **[!UICONTROL People-Based Platform]** déroulant pour sélectionner la plateforme avec laquelle vous souhaitez configurer l’intégration.
   ![plate-forme à base de personnes](assets/pbd-add.png)
1. Cliquez **[!UICONTROL Confirm]** pour être redirigé vers la page d'authentification de la plateforme sélectionnée.
1. Une fois que vous êtes authentifié sur votre compte de plateforme sociale, vous êtes redirigé vers Audience Manager où vous devriez voir les comptes publicitaires associés. Sélectionnez le compte publicitaire à utiliser, puis cliquez sur **[!UICONTROL Confirm]**.
1. Audience Manager affiche une notification en haut de la page pour vous indiquer si le compte a bien été ajouté. La notification vous permet également d’ajouter une adresse électronique de contact pour recevoir des notifications lorsque l’authentification de la plateforme sociale est sur le point d’expirer.

>[!IMPORTANT]
>
>Un gestionnaire de contenu gère l’intégration aux plateformes sociales au moyen de jetons d’authentification qui expirent après un certain temps. Voir Renouvellement du jeton d’authentification pour plus d’informations sur la manière de renouveler les jetons expirés.

## Etape 6 - Création d’une destination basée sur les personnes {#create-destination}

1. Connectez-vous à votre compte Audience Manager, accédez à **[!UICONTROL Audience Data]** &gt; **[!UICONTROL Destinations]**, puis cliquez sur **[!UICONTROL Create Destination]**.
1. Dans la **[!UICONTROL Basic Information]** section, saisissez un **[!UICONTROL Name]** et **[!UICONTROL Description]** pour votre nouvelle source de données, puis utilisez les paramètres suivants :
   * **[!UICONTROL Category]**: Plateformes intégrées;
   * **[!UICONTROL Type]**: En fonction des personnes;
   * **[!UICONTROL Platform]**: sélectionnez la plateforme basée sur les personnes à laquelle vous souhaitez envoyer des segments d’audience ;
   * **[!UICONTROL Account]**: sélectionnez le compte publicitaire souhaité associé à la plateforme sélectionnée.
      ![create-destination](assets/pbd-create-destination.png)
1. Cliquez sur **[!UICONTROL Next]**.
1. Sélectionnez la destination **[!UICONTROL Data Export Labels]** que vous souhaitez définir.
1. Dans la **[!UICONTROL Configuration]** section, sélectionnez la source de données qui contient vos sources de données hachées.
1. Dans la **[!UICONTROL Segment Mappings]** section, sélectionnez les segments à envoyer à cette destination. Il s’agit des segments que vous avez créés à l’ [étape 4 - Création de segments](people-based-destinations-workflow-combined.md#create-audience-segments)d’audience.
1. Enregistrez la destination.
