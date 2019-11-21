---
description: Guide de préparation GDPR pour les clients d’Audience Manager
seo-description: Guide de préparation GDPR pour les clients d’Audience Manager
seo-title: Guide de préparation GDPR pour les clients d’Audience Manager
solution: Audience Manager
title: Guide de préparation GDPR pour les clients d’Audience Manager
translation-type: tm+mt
source-git-commit: caa5207bc2955ee18b40d6a51613340001cbd92f

---


# Guide de préparation GDPR pour les clients d’Audience Manager (contrôleurs de données) {#gdpr-readiness-guidance}

Audience Manager recommande d’être proactif dans les domaines de la gouvernance des données et de la préparation de l’organisation. Cela vous permettra de vous assurer que vos données sur les consommateurs seront organisées pour les processus liés aux demandes d’accès ou de suppression, que vos équipes seront autorisées à gérer ces demandes et que vos clients (objets de données) auront une expérience positive et différenciée de votre marque.

En tant que processeur de données, Adobe ne peut pas fournir de conseils juridiques sur les exigences GDPR et le processus d’obtention du consentement de vos sujets de données. Veuillez consulter votre conseiller juridique pour obtenir des conseils sur la conformité aux RMR pour votre organisation.

## Gouvernance des données : Commencez à réfléchir à la manière dont vos données de consommation sont gérées dans votre instance d’Audience Manager.

* Examinez les différents ID de client utilisés par vos équipes marketing pour identifier les utilisateurs dans Audience Manager, ainsi que les sources de données dans lesquelles ils sont stockés. Cela simplifiera le processus des demandes (suppression ou accès, par exemple), car certains types de données seront hachés par vos équipes avant leur assimilation dans Audience Manager.
* Les ID de périphérique mobile IDFA/GAID sont utilisés pour plusieurs cas d’utilisation dans Audience Manager. Si vous utilisez Adobe Mobile SDK, veillez à envoyer le MID (Experience Cloud ID) avec IDFA/GAID pour vous assurer que les réponses au GDPR sont complètes.
* La définition des données personnelles devenant de plus en plus étendue, les adresses IP peuvent être considérées comme des données personnelles dans votre région. Collaborez de manière proactive avec le service de conseil d’Adobe pour obscurcir le dernier octet.
* Déterminez une politique et un processus de validation/authentification pour confirmer l'identité d'un sujet de données lorsqu'il fait une demande de RDMD.
* Envisagez d’utiliser des contrôles [d’exportation de](../../features/data-export-controls.md) données pour bloquer l’activation de l’audience sur les technologies qui hébergent des données personnelles. Par exemple, les segments contenant des données tierces ne doivent pas être regroupés en réseaux avec les fournisseurs de services de messagerie. Définissez un [!UICONTROL Data Export Control] afin de vous assurer que personne dans votre entreprise ne peut activer accidentellement ces données.
* Commencez à utiliser les contrôles [d'accès basés sur les](../../features/administration/administration-overview.md) rôles pour vous assurer que les équipes appropriées ont accès aux données prévues.
* Tenez compte des périodes [de](../../faq/faq-privacy.md#data-retention-faq) rétention appropriées pour les données.
* Examiner les politiques et les exigences juridiques relatives au lien entre l'identité et la vie privée afin de déterminer quand et où il convient de lier les ensembles d'identité; utilisez correctement via les règles [de fusion de](../../features/profile-merge-rules/merge-rules-overview.md)profil d’Audience Manager.

## Préparation organisationnelle : Établir un processus d’entreprise

* Identifiez un processus pour recevoir ou répondre aux demandes des sujets de données. Envisagez de créer un outil automatisé pour envoyer des requêtes à Audience Manager.
* Nommez un point de contact de confidentialité au sein de votre centre d’excellence DMP. Connectez le point de contact de confidentialité de votre entreprise à votre équipe d’utilisation du produit d’Audience Manager pour comprendre comment vous pouvez gérer vos besoins en ID d’entrée.
* Effectuez un examen des données avant de les partager avec la personne concernée. Documentez les étapes que vous avez mises en place, pour vous aider à établir la responsabilisation.
