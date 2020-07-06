---
description: Questions et problèmes courants concernant le ciblage.
seo-description: Questions et problèmes courants concernant le ciblage.
seo-title: FAQ sur le ciblage
solution: Audience Manager
title: FAQ sur le ciblage
uuid: ee96ef71-b903-4953-afc4-8ec8e48bd49e
feature: Match Rates
translation-type: tm+mt
source-git-commit: 27ce94084e35ffa770858027d12235ca9f1f8430
workflow-type: tm+mt
source-wordcount: '920'
ht-degree: 100%

---


# FAQ sur le ciblage {#targeting-faq}

Questions et problèmes courants concernant le ciblage.

<br> 

<!-- 

faq_targeting.xml

 -->

**Où puis-je trouver une liste complète des fournisseurs de données tiers pris en charge par Audience Manager ?**

Consultez [Adobe Exchange Marketplace](https://exchange.adobe.com/experiencecloud.html) pour obtenir une liste complète des fournisseurs de données tiers pris en charge par [!DNL Audience Manager].

<br> 

**Pour cibler les utilisateurs que je n’ai jamais vus sur mon site avec des données tierces, dois-je utiliser des données tierces dans Audience Manager ou dans une plateforme DSP ?**

La réponse dépend de vos objectifs. Par exemple, si votre campagne est conçue pour rechercher de nouveaux clients grâce aux données tierces, travaillez directement avec une plateforme DSP. Souvenez-vous qu’Audience Manager synchronise les données avec un fournisseur de données tiers uniquement lorsque cet utilisateur est visible. Si nous n’avons jamais vu un utilisateur particulier auparavant, notre système ne disposera d’aucune information concernant ce visiteur de site. Pour les campagnes qui souhaitent uniquement utiliser des données tierces pour cibler les utilisateurs qui n’ont jamais visité aucune des propriétés, créez ces segments par le biais de la plateforme DSP.

<br> 

**Puis-je vendre aux particuliers ?**

Audience Manager vous permet d’agréger les utilisateurs et de leur vendre des produits en fonction de caractéristiques ou d’attributs partagés. Toutefois, pour se conformer aux réglementations de l’industrie, les clients d’[!DNL Audience Manager] ne peuvent pas envoyer des informations d’identification personnelle (PII) à nos systèmes. Par conséquent, vous ne pouvez pas utiliser d’adresses électroniques, de noms individuels, d’adresses physiques, etc. pour le ciblage.

<br> 

**Comment garantir la sécurité du reciblage des données ?**

Nous vous recommandons d’utiliser une connexion serveur à serveur pour échanger des données avec votre plateforme de reciblage préférée. Audience Manager échange des données avec la plupart des principales plateformes DSP par le biais de connexions serveur à serveur. Les transferts de données de serveur à serveur permettent d’éviter que d’autres acteurs n’interceptent vos données et ne revendent ces informations sur l’audience.

<br> 

**L’identifiant utilisateur unique d’Audience Manager (UUID) est-il lié à l’identifiant utilisateur unique d’un serveur de publicités en synchronisant directement les identifiants sur la page ?**

Non. Les synchronisations des identifiants ne sont pas effectuées sur la page pour les serveurs ou éditeurs sur site. L’UUID d’Audience Manager est inséré dans le champ `u=` des fichiers journaux du serveur de publicités. Cela se produit lorsque le segment est transmis pour le ciblage. Le module de code DIL exécute cette fonction. Il s’agit du même mécanisme qui nous permet de mapper l’identifiant utilisateur du serveur à un utilisateur d’Audience Manager pour les rapports de performances des segments. Cependant, si un serveur de publicités est présent sur le site, nous synchronisons les identifiants directement sur la page.

<br> 

**Audience Manager considère-t-il qu’un utilisateur qui se connecte à partir de différents appareils correspond à un utilisateur unique ou à différents utilisateurs uniques ?**

[Le ciblage des identifiants déclarés](../features/declared-ids.md#declared-id-targeting) permet à Audience Manager d’identifier un visiteur sur plusieurs appareils à l’aide d’un identifiant unique. Toutefois, du point de vue du ciblage ou de la destination, il s’agit toujours de 2 utilisateurs (ou plus), car les plateformes DSP ne peuvent pas concilier ces différents identifiants.

<br> 

**Audience Manager peut-il identifier un utilisateur à partir d’appareils mobiles et display ?**

Oui. Voir [Ciblage des identifiants déclarés](../features/declared-ids.md#declared-id-targeting).

<br> 

**Puis-je noter les utilisateurs avec les données collectées en ligne et les recibler en fonction de cette note de modèle ?**

Oui. Audience Manager peut fournir des fichiers de données pour vous aider à noter les utilisateurs, mais vous devez travailler avec d’autres fournisseurs ou logiciels pour analyser et classer ces informations. Envoyez ces données à Audience Manager sous la forme de paires clé-valeur. Nous pouvons prendre ces informations et les ajouter aux profils utilisateur existants. Contactez votre représentant des solutions partenaires pour examiner ce processus.

<br> 

**Quels sont les taux de suppression des cookies sur une période de 1 à 2 mois donnée ?**

La suppression des cookies est difficile à mesurer. La plupart des suppressions de cookies proviennent de quelques visiteurs qui suppriment fréquemment les cookies. Cependant, la plupart des cookies de navigateur sont stables pendant au moins 30 jours, même si certains ont une durée de vie limitée. Certaines études suggèrent que le ciblage des entonnoirs supérieurs, supérieur à 30 jours, éliminerait effectivement 7 % de l’audience cible du navigateur sur une période de 30 jours. Comme vous le savez, les campagnes de 30 jours pour un message créatif donné sont la norme dans le secteur. Nous avons constaté que cette baisse de 7 % est exacte.

La suppression des cookies a un impact négatif sur les calculs de portée et de fréquence. Par conséquent, nous insistons sur la valeur des données comportementales lorsque nous tentons d’identifier la véritable nature des tendances des consommateurs pour la planification des campagnes display. Nos clients peuvent exploiter les rapports de chevauchement de segments d’Audience Manager, les rapports de fréquence d’impression optimale et les tendances des utilisateurs uniques sur des périodes spécifiques pour adopter une approche plus scientifique de la planification des campagnes et des périodes optimales pour l’exécution des campagnes.

<br> 

**Quel est le délai d’expiration des cookies d’Audience Manager ?**

L’interface utilisateur vous permet de déterminer l’intervalle d’expiration des cookies. Vous pouvez définir les cookies pour qu’ils expirent après *n* jours ou jamais.

<br> 

**La mise en œuvre d’une campagne créative dans un appel d’événement coûte-t-elle plus cher ?**

Cela dépend. Le coût est basé sur les utilisateurs uniques. Si une campagne génère de nouveaux utilisateurs nets, cela coûtera plus cher. Si votre campagne atteint des zones où nous collectons déjà des données, aucun coût supplémentaire n’est à prévoir. Si votre campagne s’exécute sur des sites connexes présentant un chevauchement important, les nouveaux utilisateurs uniques que nous voyons entraîneront des coûts supplémentaires.

<br> 

**Audience Manager affiche les mesures [!UICONTROL Addressable Audiences] et les taux de correspondance pour les destinations [!UICONTROL Server-to-Server] uniquement. Pouvez-vous expliquer pourquoi nous ne voyons pas ces chiffres pour les destinations de cookie et d’URL ?**

Cela se résume à la synchronisation des identifiants. Pour les destinations [!UICONTROL Server-to-Server], nous transférons les données hors ligne (en temps réel ou par lots) et nous devons envoyer l’identifiant que le partenaire de destination comprend, afin qu’il puisse le mapper à nouveau au navigateur. Le nombre adressable de segments est un sous-ensemble de la population totale de segments.

Dans le cas des destinations de cookie et d’URL, l’utilisateur se trouve déjà dans le navigateur et [!DNL Audience Manager] envoie uniquement les segments pour lesquels l’utilisateur a rempli les critères. Le partenaire de destination peut simplement sélectionner les mappages de segments et utiliser ces informations. Considérez donc que les taux de correspondance pour les destinations de cookie et d’URL correspondent toujours à 100 %.
