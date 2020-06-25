---
description: Guide de préparation au RGPD à l'intention des clients d'Audience Manager
seo-description: Guide de préparation au RGPD à l'intention des clients d'Audience Manager
seo-title: Guide de préparation au RGPD à l'intention des clients d'Audience Manager
solution: Audience Manager
title: Guide de préparation au RGPD à l'intention des clients d'Audience Manager
feature: data governance & privacy
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 0%

---


# Guide de préparation au RGPD pour les clients d’Audience Manager (contrôleurs de données) {#gdpr-readiness-guidance}

L&#39;Audience Manager recommande d&#39;être proactif dans les domaines de la gouvernance des données et de la préparation de l&#39;organisation. Cela vous permettra de vous assurer que vos données clients seront organisées pour les processus liés à l&#39;accès ou à la suppression des requêtes, que vos équipes seront autorisées à gérer ces requêtes et que vos clients (objets de données) auront une expérience positive et différenciée de votre marque.

En tant que processeur de données, Adobe ne peut pas fournir de conseils juridiques sur les exigences du RGMD ni sur le processus d&#39;obtention du consentement de vos sujets de données. Veuillez consulter votre conseiller juridique pour obtenir des conseils sur la conformité aux RGD pour votre organisation.

## Gouvernance des données : Début réfléchissant à la façon dont vos données de consommation sont gérées dans votre instance d&#39;Audience Manager

* Examinez les différents identifiants de client utilisés par vos équipes marketing pour identifier les utilisateurs en Audience Manager, ainsi que les sources de données dans lesquelles ils sont stockés. Cela permettra de rationaliser le processus de requêtes (comme la suppression ou l’accès) puisque certains types de données seront hachés par vos équipes avant l’assimilation en Audience Manager.
* Les identifiants de périphérique mobile IDFA/GAID sont utilisés pour plusieurs cas d’utilisation en Audience Manager. Si vous utilisez Adobe Mobile SDK, veillez à envoyer l’ID d’Experience Cloud (MID) avec IDFA/GAID pour vous assurer que les réponses au RMPD sont complètes.
* La définition des données à caractère personnel étant de plus en plus étendue, les adresses IP peuvent être considérées comme des données à caractère personnel dans votre région. Collaborer de manière proactive avec Adobe Consulting pour obscurcir le dernier octet.
* Déterminez une stratégie et un processus de validation/authentification pour confirmer l&#39;identité d&#39;une personne concernée lorsqu&#39;elle fait une demande de RGMD.
* Envisagez d&#39;utiliser les contrôles [d&#39;exportation des](../../features/data-export-controls.md) données pour bloquer l&#39;activation des audiences aux technologies qui hébergent des données personnelles. Par exemple, les segments contenant des données tierces ne doivent pas être regroupés en groupes pour envoyer des prestataires par courriel. Définissez un [!UICONTROL Data Export Control] afin de vous assurer qu’aucun membre de votre organisation ne peut activer accidentellement ces données.
* Commencez à utiliser des Contrôles d&#39;accès [basés sur les](../../features/administration/administration-overview.md) rôles pour s&#39;assurer que les bonnes équipes ont accès aux données prévues.
* Tenez compte des périodes [de](../../faq/faq-privacy.md#data-retention-faq) rétention appropriées pour les données.
* Examiner les politiques et les exigences juridiques relatives au lien d&#39;identité et à la protection des renseignements personnels afin de déterminer quand et où il convient de lier les ensembles d&#39;identité ; utiliser de manière appropriée via les règles [de fusion](../../features/profile-merge-rules/merge-rules-overview.md)Profil de l’Audience Manager.

## Prêt organisationnel : Créer un processus d&#39;entreprise

* Identifiez un processus de réception/réponse aux demandes de sujet de données. Envisagez de créer un outil automatisé pour envoyer des requêtes à l&#39;Audience Manager.
* Nommez un point de contact de confidentialité au sein de votre centre d’excellence DMP. Connectez le point de contact de confidentialité de votre entreprise à votre équipe chargée de l’utilisation des produits d’Audience Manager afin de comprendre comment vous pouvez gérer vos besoins en ID d’entrée.
* Effectuer un examen des données avant de les partager avec la personne concernée. Document les étapes que vous avez mises en place, pour vous aider à établir la responsabilité.
