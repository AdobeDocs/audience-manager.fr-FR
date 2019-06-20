---
description: Configurez un groupe Google pour importer vos fichiers de données doubleclick Campaign Manager (DCM) dans Audience Manager. Le contenu de cette section résume le processus d'intégration et fournit des liens vers les ressources DCM pour vous aider à démarrer.
seo-description: Configurez un groupe Google pour importer vos fichiers de données doubleclick Campaign Manager (DCM) dans Audience Manager. Le contenu de cette section résume le processus d'intégration et fournit des liens vers les ressources DCM pour vous aider à démarrer.
seo-title: Importer des fichiers de données DCM dans Audience Manager
solution: Audience Manager
title: Importer des fichiers de données DCM dans Audience Manager
uuid: 3578 cfe 1-6 d 30-4 a 73-ab 75-8 d 272 bebcd 60
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Import DCM Data Files Into Audience Manager {#import-dcm-data-files-into-audience-manager}

Configurez un groupe Google pour importer vos fichiers de données doubleclick Campaign Manager (DCM) dans Audience Manager. Le contenu de cette section résume le processus d&#39;intégration et fournit des liens vers les ressources DCM pour vous aider à démarrer.

## Résumé de l&#39;intégration

DCM est le remplacement de [!DNL Google] pour [!DNL DoubleClick for Advertisers] (DFA). Tout comme avec DFA, les clients DCM peuvent importer, visualiser et manipuler leurs données dans [!DNL Audience Manager]. But [!DNL Audience Manager] cannot directly access and import your [!UICONTROL Data Transfer] and [!UICONTROL Match Table] files. C’est au client qu’il incombe d’importer ces fichiers.

However, the set up procedure is well documented in the [DoubleClick Campaign Manager Help](https://support.google.com/dcm/partner/answer/2941575?hl=en&ref_topic=6107456). Vous pouvez également consulter les étapes répertoriées ci-dessous pour commencer.

>[!CAUTION]
>
>Les fichiers de données DCM contiennent des données pour tous vos annonceurs ou clients. If you need to omit specific clients, then you must edit the files before making them available to [!DNL Audience Manager].

## Fréquence et disponibilité des transferts de données

[!DNL Audience Manager] recherche et transfère les données une fois par jour. Data is usually available in [!DNL Audience Manager] after 24-hours.

## Étapes

1. [Créer un groupe](https://support.google.com/dcm/partner/answer/3370419?hl=en&ref_topic=6107456).

   Les groupes contrôlent l&#39;accès aux données DCM. Eventually, you&#39;ll invite and add [!DNL Audience Manager] to this group.

1. [Vérifiez l&#39;état de stockage de Google Cloud](https://support.google.com/dcm/partner/answer/3370481?hl=en&ref_topic=6107456).

   Google Cloud Storage contains the data bucket that holds your [!UICONTROL Data Transfer] and [!UICONTROL Match Tables]. Vous devez configurer un compartiment ou vous assurer que votre nouveau groupe a accès à un compartiment de stockage de données existant.

1. [Obtenez une URL de fichier de données](https://support.google.com/dcm/partner/answer/3370482?hl=en&ref_topic=6107456).

   Travaillez avec votre gestionnaire de compte DCM ou votre conseiller de solutions de plate-forme. Ils vous fourniront une URL vers vos fichiers de données. [!DNL Google] peut changer le format des noms de compartiment et de fichier dans les versions ultérieures. De nouveau, demandez à votre gestionnaire de compte DCM de vous assurer que vous utilisez les formats appropriés.

1. [Définissez les autorisations](https://cloud.google.com/storage/docs/cloud-console?csw=1#_bucketpermission)de compartiment.

   The [!DNL Cloud Storage Manager] lets you control data sharing and bucket access. Give your group read access to the bucket that contains your [!UICONTROL Data Transfer] and [!UICONTROL Match Table] files.

1. [Configurez le partage des données](https://support.google.com/dcm/partner/answer/6206106?hl=en).

   Utilisateur DCM partagé - les identifiants sont chiffrés pour protéger la confidentialité. Encryption adds 2 columns to the end of your Data Transfer file, `PartnerId1` and `PartnerId2`. Ces colonnes contiennent un utilisateur codé - identifiants spécifiques à chaque entreprise qui reçoit ces fichiers.

   As an authorized third-party, [!DNL Audience Manager] can receive DCM data, but cannot decode the IDs. However, on the [!DNL Audience Manager] side, we know how the encoded IDs match our IDs. Cela signifie que nous pouvons établir une correspondance et synchroniser les utilisateurs avec confiance et précision.

   >[!NOTE]
   >You cannot import DCM files into [!DNL Audience Manager] if you&#39;re already sharing data with 2 other third-party partners.

1. Invite [!DNL Audience Manager] to join the group.

   After you create a group and give it access to a data bucket, invite [!DNL Audience Manager] to join the group. Envoyez un courrier électronique d&#39;invitation à DFA-AAM@adobe.com. Veillez à inclure l&#39;URL du fichier de données à l&#39;étape 3. Nos équipes internes collaboreront avec vous pour vérifier l&#39;accès après acceptation de l&#39;invitation. 1. Set up two data sources for DCM data in the [!DNL Audience Manager] User Interface.

   Name the data sources `Advertiser Analytics: DCM Platform` and `Advertiser Analytics: AAM+DCM Platform`. In the [Create Data Sources](../../../features/manage-datasources.md#create-data-source) workflow, set the ID type to `Cookie`. Partagez les identifiants des deux nouvelles sources de données avec nos équipes internes.

1. You can easily create traits from the DCM files you import into [!DNL Audience Manager]. See [Actionable Log Files](../../../integration/media-data-integration/actionable-log-files.md) and ask your [!DNL Audience Manager] consultant or Customer Care to enable the feature for you.
