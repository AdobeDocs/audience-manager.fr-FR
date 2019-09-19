---
description: Configurez un groupe Google pour importer vos fichiers de données DoubleClick Campaign Manager (DCM) dans Audience Manager. Le contenu de cette section résume le processus d’intégration et vous fournit des liens vers les ressources DCM pour vous aider à démarrer.
seo-description: Configurez un groupe Google pour importer vos fichiers de données DoubleClick Campaign Manager (DCM) dans Audience Manager. Le contenu de cette section résume le processus d’intégration et vous fournit des liens vers les ressources DCM pour vous aider à démarrer.
seo-title: Importation Des Fichiers De Données DCM Dans Audience Manager
solution: Audience Manager
title: ' Importation Des Fichiers De Données DCM Dans Audience Manager'
uuid: 3578cfe1-6d30-4a73-ab75-8d272bebcd60
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Import DCM Data Files Into Audience Manager {#import-dcm-data-files-into-audience-manager}

Configurez un groupe Google pour importer vos fichiers de données DoubleClick Campaign Manager (DCM) dans Audience Manager. Le contenu de cette section résume le processus d’intégration et vous fournit des liens vers les ressources DCM pour vous aider à démarrer.

## Résumé de l’intégration

DCM est le remplacement de [!DNL Google] pour [!DNL DoubleClick for Advertisers] (DFA). Tout comme avec DFA, les clients DCM peuvent importer, visualiser et manipuler leurs données dans [!DNL Audience Manager]. Mais [!DNL Audience Manager] vous ne pouvez pas accéder directement à vos [!UICONTROL Data Transfer] fichiers et à vos [!UICONTROL Match Table] fichiers et les importer. C’est au client qu’il incombe d’importer ces fichiers.

Toutefois, la procédure de configuration est bien documentée dans l’aide [du gestionnaire de campagnes](https://support.google.com/dcm/partner/answer/2941575?hl=en&ref_topic=6107456)DoubleClick. Vous pouvez également passer en revue les étapes ci-dessous pour commencer.

>[!CAUTION]
>
>Les fichiers de données DCM contiennent des données pour tous vos annonceurs ou clients. Si vous devez omettre des clients spécifiques, vous devez modifier les fichiers avant de les rendre accessibles [!DNL Audience Manager].

## Fréquence et disponibilité des transferts de données

[!DNL Audience Manager] vérifie et transfère les données une fois par jour. Les données sont généralement disponibles au [!DNL Audience Manager] bout de 24 heures.

## Étapes

1. [Créer un groupe](https://support.google.com/dcm/partner/answer/3370419?hl=en&ref_topic=6107456).

   Les groupes contrôlent l’accès à vos données DCM. Finalement, vous inviterez et ajouterez [!DNL Audience Manager] à ce groupe.

1. [Vérifiez votre état](https://support.google.com/dcm/partner/answer/3370481?hl=en&ref_topic=6107456)de stockage Google Cloud.

   Le stockage Google Cloud contient le compartiment de données qui contient votre [!UICONTROL Data Transfer] et [!UICONTROL Match Tables]. Vous devez configurer un compartiment ou vous assurer que votre nouveau groupe a accès à un compartiment de stockage de données existant.

1. [Obtenez une URL](https://support.google.com/dcm/partner/answer/3370482?hl=en&ref_topic=6107456)de fichier de données.

   Travaillez avec votre gestionnaire de compte DCM ou votre consultant en solutions de plateformes. Ils vous fourniront une URL vers vos fichiers de données. [!DNL Google] peut modifier le format des noms de fichier et de compartiment dans les versions ultérieures. Là encore, demandez à votre gestionnaire de compte DCM de vous assurer que vous utilisez les formats appropriés.

1. [Définissez les autorisations](https://cloud.google.com/storage/docs/cloud-console?csw=1#_bucketpermission)du compartiment.

   Le [!DNL Cloud Storage Manager] permet de contrôler le partage des données et l’accès au compartiment. Donnez à votre groupe un accès en lecture au compartiment contenant vos [!UICONTROL Data Transfer] fichiers et [!UICONTROL Match Table] .

1. [Configurez le partage](https://support.google.com/dcm/partner/answer/6206106?hl=en)des données.

   Les ID utilisateur DCM partagés sont chiffrés pour protéger la confidentialité. Encryption ajoute 2 colonnes à la fin de votre fichier de transfert de données, `PartnerId1` et `PartnerId2`. Ces colonnes contiennent des ID utilisateur codés propres à chaque entreprise qui reçoit ces fichiers.

   En tant que tiers autorisé, [!DNL Audience Manager] peut recevoir des données DCM, mais ne peut pas décoder les ID. Cependant, [!DNL Audience Manager] nous savons comment les ID codés correspondent à nos ID. Cela signifie que nous pouvons associer et synchroniser les utilisateurs avec confiance et précision.

   >[!NOTE]
   >Vous ne pouvez pas importer de fichiers DCM dans [!DNL Audience Manager] si vous partagez déjà des données avec deux autres partenaires tiers.

1. Invitez [!DNL Audience Manager] à rejoindre le groupe.

   Après avoir créé un groupe et lui avoir donné accès à un compartiment de données, invitez-le [!DNL Audience Manager] à rejoindre le groupe. Envoyez une invitation par courrier électronique à DFA-AAM@adobe.com. Veillez à inclure l’URL du fichier de données à l’étape 3. Nos équipes internes travailleront avec vous pour vérifier l'accès après avoir accepté l'invitation. 1. Configurez deux sources de données pour les données DCM dans l’interface [!DNL Audience Manager] utilisateur.

   Nommez les sources de données `Advertiser Analytics: DCM Platform` et `Advertiser Analytics: AAM+DCM Platform`. Dans le flux de travail [Créer des sources](../../../features/manage-datasources.md#create-data-source) de données, définissez le type d’ID sur `Cookie`. Partagez les ID des deux nouvelles sources de données avec nos équipes internes.

1. Vous pouvez facilement créer des caractéristiques à partir des fichiers DCM dans lesquels vous importez [!DNL Audience Manager]. Reportez-vous à la section Fichiers [journaux](../../../integration/media-data-integration/actionable-log-files.md) exploitables et demandez à votre [!DNL Audience Manager] consultant ou au service à la clientèle d’activer cette fonction pour vous.
