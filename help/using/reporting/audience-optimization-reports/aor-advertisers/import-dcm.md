---
description: Configurez un groupe Google pour importer vos fichiers de données Google Campaign Manager dans Audience Manager. Le contenu de cette section résume le processus d’intégration et vous fournit des liens vers des ressources Google Campaign Manager pour vous aider à démarrer.
seo-description: Set up a Google group to bring your Google Campaign Manager data files into Audience Manager. The content in this section summarizes the integration process and provides you with links to Google Campaign Manager resources to help you get started.
seo-title: Import Google Campaign Manager Data Files Into Audience Manager
solution: Audience Manager
title: Importer Les Fichiers De Données Google Campaign Manager Dans Audience Manager
uuid: 3578cfe1-6d30-4a73-ab75-8d272bebcd60
feature: Audience Optimization Reports
exl-id: 045eed94-100f-460d-83bb-78fbd7beb51c
source-git-commit: 95b7b4347f3da16be05be60cbefc0e236022a4a7
workflow-type: tm+mt
source-wordcount: '556'
ht-degree: 2%

---

# Importer Les Fichiers De Données Google Campaign Manager Dans Audience Manager {#import-dcm-data-files-into-audience-manager}

Configurez un groupe de [!DNL Google] pour importer vos fichiers de données [!DNL Google Campaign Manager] dans Audience Manager. Le contenu de cette section résume le processus d’intégration et vous fournit des liens vers des ressources [!DNL Google Campaign Manager] pour vous aider à démarrer.

## Résumé de l’intégration

[!DNL Google Campaign Manager] remplace [!DNL Google] pour [!DNL DoubleClick for Advertisers] (DFA). Tout comme DFA, [!DNL Google Campaign Manager] clients peuvent importer, afficher et utiliser leurs données dans [!DNL Audience Manager]. Cependant, [!DNL Audience Manager] ne pouvez pas accéder directement à vos fichiers [!UICONTROL Data Transfer] et [!UICONTROL Match Table] ni les importer. C’est au client qu’il incombe d’importer ces fichiers.

Toutefois, la procédure de configuration est bien documentée dans l&#39;aide [DoubleClick Campaign Manager](https://support.google.com/dcm/partner/answer/2941575?hl=en&ref_topic=6107456). Vous pouvez également consulter les étapes répertoriées ci-dessous pour commencer.

>[!CAUTION]
>
>[!DNL Google Campaign Manager] fichiers de données contiennent des données pour tous vos annonceurs ou clients. Si vous devez omettre des clients spécifiques, vous devez modifier les fichiers avant de les rendre disponibles pour [!DNL Audience Manager].

## Fréquence et disponibilité des transferts de données

[!DNL Audience Manager] vérifie et transfère les données une fois par jour. Les données sont généralement disponibles en [!DNL Audience Manager] après 24 heures.

## Étapes

1. [Créer un groupe](https://support.google.com/dcm/partner/answer/3370419?hl=en&ref_topic=6107456).

   Les groupes contrôlent l’accès à vos données [!DNL Google Campaign Manager]. Vous finirez par inviter et ajouter des [!DNL Audience Manager] à ce groupe.

1. [Vérification du statut de votre espace de stockage dans le cloud Google](https://support.google.com/dcm/partner/answer/3370481?hl=en&ref_topic=6107456).

   L’espace de stockage dans le cloud Google contient le compartiment de données qui contient vos [!UICONTROL Data Transfer] et [!UICONTROL Match Tables]. Vous devez configurer un compartiment ou vous assurer que votre nouveau groupe a accès à un compartiment de stockage de données existant.

1. [Obtenir une URL de fichier de données](https://support.google.com/dcm/partner/answer/3370482?hl=en&ref_topic=6107456).

   Collaborez avec votre gestionnaire de compte [!DNL Google Campaign Manager] ou votre consultant en solutions Platform. Ils vous fourniront une URL vers vos fichiers de données. [!DNL Google] peut modifier le format des noms de compartiment et de fichier dans les prochaines versions. Là encore, contactez votre gestionnaire de compte [!DNL Google Campaign Manager] pour vous assurer que vous utilisez les formats appropriés.

1. [Définissez les autorisations du compartiment](https://cloud.google.com/storage/docs/cloud-console?csw=1#_bucketpermission).

   Le [!DNL Cloud Storage Manager] vous permet de contrôler le partage de données et l’accès aux compartiments. Donnez à votre groupe un accès en lecture au compartiment qui contient vos fichiers [!UICONTROL Data Transfer] et [!UICONTROL Match Table].

1. [Configurer le partage de données](https://support.google.com/dcm/partner/answer/6206106?hl=en).

   Les ID d’utilisateur [!DNL Google Campaign Manager] partagés sont chiffrés afin de protéger la confidentialité. Le chiffrement ajoute 2 colonnes à la fin de votre fichier de transfert de données, `PartnerId1` et `PartnerId2`. Ces colonnes contiennent des identifiants d’utilisateur codés spécifiques à chaque société qui reçoit ces fichiers.

   En tant que tiers autorisé, [!DNL Audience Manager] pouvez recevoir des données [!DNL Google Campaign Manager], mais ne pouvez pas décoder les identifiants. Cependant, du côté [!DNL Audience Manager], nous savons comment les identifiants codés correspondent à nos identifiants. Cela signifie que nous pouvons apparier et synchroniser les utilisateurs avec confiance et précision.

   >[!NOTE]
   >Vous ne pouvez pas importer [!DNL Google Campaign Manager] fichiers dans [!DNL Audience Manager] si vous partagez déjà des données avec 2 autres partenaires tiers.

1. Invitez [!DNL Audience Manager] à rejoindre le groupe.

   Après avoir créé un groupe et lui avoir donné accès à un compartiment de données, invitez les [!DNL Audience Manager] à rejoindre le groupe. Envoyez une invitation par e-mail à dfaaam@adobe.com. Veillez à inclure l’URL du fichier de données de l’étape 3. Nos équipes internes travailleront avec vous pour vérifier l&#39;accès après avoir accepté l&#39;invitation. 1. Configurez deux sources de données pour les données [!DNL Google Campaign Manager] dans l’interface utilisateur [!DNL Audience Manager].

   Nommez les sources de données `Advertiser Analytics: DCM Platform` et `Advertiser Analytics: AAM+DCM Platform`. Dans le workflow [Créer des sources de données](../../../features/manage-datasources.md#create-data-source), définissez le type d’identifiant sur `Cookie`. Partagez les identifiants des deux nouvelles sources de données avec nos équipes internes.

1. Vous pouvez facilement créer des caractéristiques à partir des fichiers [!DNL Google Campaign Manager] que vous importez dans [!DNL Audience Manager]. Voir [Fichiers journaux exploitables](../../../integration/media-data-integration/actionable-log-files.md) et demandez à votre consultant [!DNL Audience Manager] ou à l’assistance clientèle d’activer la fonctionnalité pour vous.
