---
description: Configurez un groupe Google pour importer vos fichiers de données Google Campaign Manager dans Audience Manager. Le contenu de cette section résume le processus d’intégration et vous fournit des liens vers les ressources du Gestionnaire de campagnes Google pour vous aider à démarrer.
seo-description: Set up a Google group to bring your Google Campaign Manager data files into Audience Manager. The content in this section summarizes the integration process and provides you with links to Google Campaign Manager resources to help you get started.
seo-title: Import Google Campaign Manager Data Files Into Audience Manager
solution: Audience Manager
title: Importation des fichiers de données Google Campaign Manager dans Audience Manager
uuid: 3578cfe1-6d30-4a73-ab75-8d272bebcd60
feature: Audience Optimization Reports
exl-id: 045eed94-100f-460d-83bb-78fbd7beb51c
source-git-commit: 95b7b4347f3da16be05be60cbefc0e236022a4a7
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 3%

---

# Importation des fichiers de données Google Campaign Manager dans Audience Manager {#import-dcm-data-files-into-audience-manager}

Configurez une [!DNL Google] pour amener votre [!DNL Google Campaign Manager] fichiers de données dans Audience Manager. Le contenu de cette section résume le processus d’intégration et vous fournit des liens vers [!DNL Google Campaign Manager] ressources pour vous aider à démarrer.

## Synthèse de l’intégration

[!DNL Google Campaign Manager] est le remplacement de [!DNL Google] pour [!DNL DoubleClick for Advertisers] (DFA). Semblable à DFA, [!DNL Google Campaign Manager] Les clients peuvent importer, afficher et utiliser leurs données dans [!DNL Audience Manager]. Mais [!DNL Audience Manager] ne peut pas accéder directement à et importer votre [!UICONTROL Data Transfer] et [!UICONTROL Match Table] fichiers . C’est au client qu’il incombe d’importer ces fichiers.

Toutefois, la procédure de configuration est bien documentée dans la section [Aide de DoubleClick Campaign Manager](https://support.google.com/dcm/partner/answer/2941575?hl=en&amp;ref_topic=6107456). Vous pouvez également passer en revue les étapes répertoriées ci-dessous pour commencer.

>[!CAUTION]
>
>[!DNL Google Campaign Manager] Les fichiers de données contiennent des données pour tous vos publicitaires ou clients. Si vous devez omettre des clients spécifiques, vous devez modifier les fichiers avant de les rendre disponibles pour [!DNL Audience Manager].

## Fréquence et disponibilité des transferts de données

[!DNL Audience Manager] recherche et transfère des données une fois par jour. Les données sont généralement disponibles dans [!DNL Audience Manager] après 24 heures.

## Étapes

1. [Créer un groupe](https://support.google.com/dcm/partner/answer/3370419?hl=en&amp;ref_topic=6107456).

   Les groupes contrôlent l’accès à votre [!DNL Google Campaign Manager] data. Vous inviterez et ajouterez éventuellement des [!DNL Audience Manager] à ce groupe.

1. [Vérification de l’état du stockage dans le cloud Google](https://support.google.com/dcm/partner/answer/3370481?hl=en&amp;ref_topic=6107456).

   Le stockage dans le cloud Google contient le compartiment de données qui contient votre [!UICONTROL Data Transfer] et [!UICONTROL Match Tables]. Vous devrez configurer un compartiment ou vous assurer que votre nouveau groupe a accès à un compartiment de stockage de données existant.

1. [Obtention d’une URL de fichier de données](https://support.google.com/dcm/partner/answer/3370482?hl=en&amp;ref_topic=6107456).

   Travaillez avec votre [!DNL Google Campaign Manager] Responsable de compte ou consultant en solutions Platform. Il vous fournira une URL vers vos fichiers de données. [!DNL Google] peut modifier le format des noms de compartiment et de fichier dans les prochaines versions. Encore une fois, travaillez avec votre [!DNL Google Campaign Manager] Gestionnaire de compte pour vous assurer que vous utilisez les formats appropriés.

1. [Définition des autorisations de compartiment](https://cloud.google.com/storage/docs/cloud-console?csw=1#_bucketpermission).

   Le [!DNL Cloud Storage Manager] vous permet de contrôler le partage des données et l’accès aux compartiments. Donnez à votre groupe un accès en lecture au compartiment qui contient votre [!UICONTROL Data Transfer] et [!UICONTROL Match Table] fichiers .

1. [Configuration du partage de données](https://support.google.com/dcm/partner/answer/6206106?hl=en).

   Partagé [!DNL Google Campaign Manager] les identifiants d’utilisateur sont chiffrés pour protéger la confidentialité. Encryption ajoute 2 colonnes à la fin du fichier de transfert de données, `PartnerId1` et `PartnerId2`. Ces colonnes contiennent des ID utilisateur codés spécifiques à chaque entreprise qui reçoit ces fichiers.

   En tant que tiers autorisé, [!DNL Audience Manager] peut recevoir [!DNL Google Campaign Manager] mais ne peut pas décoder les identifiants. Toutefois, sur la variable [!DNL Audience Manager] côté, nous savons comment les identifiants codés correspondent à nos identifiants. Cela signifie que nous pouvons faire correspondre et synchroniser les utilisateurs avec confiance et précision.

   >[!NOTE]
   >Vous ne pouvez pas importer [!DNL Google Campaign Manager] fichiers dans [!DNL Audience Manager] si vous partagez déjà des données avec 2 autres partenaires tiers.

1. Invitation [!DNL Audience Manager] pour rejoindre le groupe.

   Après avoir créé un groupe et lui avoir donné accès à un compartiment de données, invitez [!DNL Audience Manager] pour rejoindre le groupe. Envoyez un courrier électronique d’invitation à dfaaam@adobe.com. Veillez à inclure l’URL du fichier de données de l’étape 3. Nos équipes internes vous aideront à vérifier l’accès après avoir accepté l’invitation. 1. Configurez deux sources de données pour [!DNL Google Campaign Manager] des [!DNL Audience Manager] Interface utilisateur.

   Nommer les sources de données `Advertiser Analytics: DCM Platform` et `Advertiser Analytics: AAM+DCM Platform`. Dans le [Création de sources de données](../../../features/manage-datasources.md#create-data-source) workflow, définissez le type d’ID sur `Cookie`. Partagez les identifiants des deux nouvelles sources de données avec nos équipes internes.

1. Vous pouvez facilement créer des caractéristiques à partir du [!DNL Google Campaign Manager] fichiers que vous importez dans [!DNL Audience Manager]. Voir [Fichiers journaux pratiques](../../../integration/media-data-integration/actionable-log-files.md) et demandez à votre [!DNL Audience Manager] consultant ou assistance clientèle pour activer la fonctionnalité à votre place.
