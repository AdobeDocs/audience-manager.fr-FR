---
description: 'Cette page comprend des instructions détaillées sur la création de segments d’audience à partir de données client hors ligne uniquement et sur leur envoi vers des destinations basées sur les personnes.  '
seo-description: 'Cette page comprend des instructions détaillées sur la création de segments d’audience à partir de données client hors ligne uniquement et sur leur envoi vers des destinations basées sur les personnes.  '
seo-title: Workflow B - Personnalisation basée sur les données hors ligne uniquement
solution: Audience Manager
title: Workflow B - Personnalisation basée sur les données hors ligne uniquement
feature: People-Based Destinations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1170'
ht-degree: 5%

---


# Workflow B - Personnalisation basée sur les données hors ligne uniquement {#workflow-b}

>[!IMPORTANT]
>Cet article contient la documentation du produit destinée à vous guider tout au long de la configuration et de l’utilisation de cette fonction. Rien dans ce document n&#39;est un conseil juridique. Veuillez consulter votre propre conseiller juridique pour obtenir des conseils juridiques.

Cette page comprend des instructions détaillées sur la création de segments d’audience à partir de données client hors ligne uniquement et sur leur envoi vers des destinations basées sur les personnes.

## Étape 1 - Caractéristiques hors ligne à bord {#step-1-onboard-traits}

La première étape de la création de segments d’audience dans ce scénario consiste à mettre en Audience Manager vos données client hors ligne.

>[!IMPORTANT]
>
> Avant de continuer, assurez-vous que l’activité du client que vous êtes sur le point de rejoindre à bord est déjà définie en Audience Manager avec les caractéristiques [](../traits/trait-and-segment-qualification-reference.md)intégrées correspondantes.

Que vos identifiants de client d’Audience Manager existants ([DPUUID](../../reference/ids-in-aam.md)) soient ou non hachés, vous devez effectuer l’intégration de la caractéristique par rapport à la source de données qui contient vos [DPUUID](../../reference/ids-in-aam.md).

### Exemple

Vous souhaitez définir les identifiants de client dans le tableau ci-dessous pour les identifiants de caractéristiques intégrés correspondants. Imaginons que vos [DPUUID](../../reference/ids-in-aam.md) soient stockés dans une source de données portant l’ID 999999 et que votre ID de partenaire d’Audience Manager soit 123.

| ID de client (DPUUID) | ID de caractéristique embarquée |
| -------------------------------------- | ------------------- |
| 68079982765673198504052656074456196039 | 12345, 23456 |
| 67412682083411995725538770443620307584 | 45678 |
| 89159024796760343733111707646026765593 | 11223, 93342, 27341 |

<br />

Pour définir les identifiants de client dans l’exemple ci-dessus pour les caractéristiques intégrées correspondantes, vous devez télécharger un fichier [de données](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) entrant avec le contenu suivant :

```
68079982765673198504052656074456196039<TAB>d_sid=12345,d_sid=23456
67412682083411995725538770443620307584<TAB>d_sid=45678
89159024796760343733111707646026765593<TAB>d_sid=11223,d_sid=93342,d_sid=27341
```

Le nom de fichier se présenterait comme suit : `ftp_dpm_999999_123_TIMESTAMP.sync.gz`.
Pour plus d’informations sur la structure des noms de fichier, voir Exigences en matière de nom et de taille de fichier [Amazon S3 pour les fichiers](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) de données entrants.

## Étape 2 - Configuration des paramètres de source de données {#configure-data-source-settings}

Selon que vos [DPUUID](../../reference/ids-in-aam.md) sont des adresses électroniques hachées en minuscules, vous devrez peut-être configurer la source de données qui stockera les adresses électroniques hachées.

 

**Scénario 1 : vos[DPUUID](../../reference/ids-in-aam.md)sont déjà des adresses électroniques en minuscules hachées.**

Dans ce cas, vous devez étiqueter la source de données correspondante comme telle :

1. Accédez à **[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]**.
1. Recherchez la source de données contenant vos [DPUUID](../../reference/ids-in-aam.md), puis cliquez dessus.
1. Assurez-vous que l’option **[!UICONTROL Cannot be tied to personally identifiable information]** est désactivée.
1. Enregistrez les paramètres de la source de données.

 

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

## Étape 3 - Correspondance entre les DPUUID et les adresses électroniques hachées via la synchronisation des identifiants basée sur des fichiers {#match-ids-emails}

>[!IMPORTANT]
>
> Cette étape s&#39;applique uniquement au [scénario 2](people-based-destinations-workflow-offline.md#configure-data-source-settings) décrit ci-dessus. Si vos [DPUUID](../../reference/ids-in-aam.md) existants sont déjà des adresses électroniques hachées, passez à l’ [étape 4 - Création d’une règle de fusion de Profils pour la segmentation](#create-profile-merge-rule).

Supposons que vous souhaitiez faire correspondre vos [DPUUID](../../reference/ids-in-aam.md) existants de l’exemple de l’étape 1 aux adresses électroniques hachées du tableau ci-dessous (colonne de droite) et stocker les adresses électroniques hachées dans la nouvelle source de données que vous avez créée à l’ [étape 2 - Configurer les paramètres](#configure-data-source-settings)de la source de données.

Pour rappel, vous disposez désormais de deux sources de données :

| ID de source de données | Contenu de la source de données |
| -------------- | -------------------------- |
| 999999 | Identifiants DPUUID existants (CRM ID) |
| 987654 | Adresses électroniques hachées |

| DPUUIDs (ID CRM) | Adresse électronique | Adresse électronique hachée |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 |
| 67412682083411995725538770443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 89159024796760343733111707646026765593 | `name@mydomain.com` | feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

 

Dans notre exemple, le fichier [de synchronisation des](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) identifiants contient le contenu suivant :

```
68079982765673198504052656074456196039<TAB>55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149
67412682083411995725538770443620307584<TAB>16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a
89159024796760343733111707646026765593<TAB>feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6
```

 

Le fichier [de synchronisation des](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) identifiants doit suivre la structure de dénomination suivante :

`c2c_id_<DPUUID_DATA_SOURCE_ID>_<HASHED_EMAIL_DATA_SOURCE_ID>_TIMESTAMP.sync`

 

Dans l’exemple ci-dessus, le nom de fichier se présenterait comme suit :
`c2c_id_999999_987654_1560431657.sync`

[Téléchargez un exemple de fichier ici](assets/c2c_id_999999_987654_1560431657.sync).

Une fois que vous avez créé votre fichier de synchronisation des identifiants, vous devez le télécharger dans un [!DNL Amazon S3] compartiment. Pour savoir comment télécharger des fichiers de synchronisation des identifiants, voir [Envoyer des données de lot à l’Audience Manager](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md).

## Étape 4 - Création d’une règle de fusion de Profils pour la segmentation {#create-profile-merge-rule}

L’étape suivante consiste à créer une règle de fusion qui vous aidera à créer les segments d’audience à envoyer à votre [!DNL People-Based Destinations]utilisateur.

1. Connectez-vous à votre compte d’Audience Manager et accédez à **[!UICONTROL Audience Data]** -> **[!UICONTROL Profile Merge Rules]**.
2. Cliquez sur [!UICONTROL Add New Rule].
3. Saisissez une règle de fusion de profil **[!UICONTROL Name]** et **[!UICONTROL Description]**.
4. Dans la **[!UICONTROL Profile Merge Rule Setup]** section, sélectionnez la **[!UICONTROL All Cross-Device Profiles]** règle dans la **[!UICONTROL Cross-Device Options]** liste.
5. Dans la **[!UICONTROL Cross-Device Profile Options]** liste, sélectionnez la source de données sur laquelle vos caractéristiques sont intégrées.
   ![fusion-règle-configuration](assets/pbd-pmr.png)

## Etape 5 - Création de segments d’Audience {#create-audience-segments}

Pour créer de nouveaux segments à partir de données hors ligne uniquement, utilisez le créateur [de](../segments/segment-builder.md) segments et veillez à utiliser la nouvelle règle de fusion de profils que vous avez créée à l’étape précédente lors de la création du segment.

## Étape 6 - Configuration de l’authentification Platform basée sur les personnes {#configure-authentication}

1. Connectez-vous à votre compte d’Audience Manager et accédez à **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**. Si vous disposez d’une intégration précédemment configurée avec une plateforme sociale, vous devriez la voir répertoriée dans cette page. Sinon, la page est vide.
   ![intégration basée sur les personnes](assets/pbd-config.png)
1. Cliquez sur **[!UICONTROL Add Account]**.
1. Utilisez le menu **[!UICONTROL People-Based Platform]** déroulant pour sélectionner la plate-forme avec laquelle vous souhaitez configurer l’intégration.
   ![plate-forme à base de personnes](assets/pbd-add.png)
1. Cliquez sur **[!UICONTROL Confirm]** pour être redirigé vers la page d&#39;authentification de la plateforme sélectionnée.
1. Une fois que vous êtes authentifié sur votre compte de plateforme sociale, vous êtes redirigé vers l’Audience Manager où vous devriez voir vos comptes d’annonceurs associés. Sélectionnez le compte publicitaire à utiliser, puis cliquez sur **[!UICONTROL Confirm]**.
1. L’Audience Manager affiche une notification en haut de la page pour vous indiquer si le compte a bien été ajouté. La notification vous permet également d’ajouter une adresse électronique de contact pour recevoir des notifications lorsque l’authentification de la plateforme sociale est sur le point d’expirer.

>[!IMPORTANT]
>
>L’Audience Manager gère l’intégration aux plateformes sociales au moyen de jetons d’authentification qui expirent après un certain temps. Voir Renouvellement du jeton d’authentification pour en savoir plus sur la manière de renouveler les jetons expirés.

## Etape 7 - Création d’une destination basée sur les personnes {#create-destination}

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
1. Dans la **[!UICONTROL Segment Mappings]** section, sélectionnez les segments à envoyer à cette destination. Il s’agit des segments que vous avez créés à l’ [étape 5 - Créer des segments](people-based-destinations-workflow-offline.md#create-audience-segments)d’Audience.
1. Enregistrez la destination.
