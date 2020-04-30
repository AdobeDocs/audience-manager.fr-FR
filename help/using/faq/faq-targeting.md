---
description: Questions et problèmes communs liés au ciblage.
seo-description: Questions et problèmes communs liés au ciblage.
seo-title: FAQ sur le ciblage
solution: Audience Manager
title: FAQ sur le ciblage
uuid: ee96ef71-b903-4953-afc4-8ec8e48bd49e
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# FAQ sur le ciblage{#targeting-faq}

Questions et problèmes communs liés au ciblage.

<br> 

<!-- 

faq_targeting.xml

 -->

**Où puis-je trouver une liste complète de fournisseurs de données tiers pris en charge par Audience Manager ?**

Consultez [Adobe Exchange Marketplace](https://exchange.adobe.com/experiencecloud.html) pour obtenir une liste complète des fournisseurs de données tiers qui [!DNL Audience Manager] prennent en charge.

<br> 

**Pour cible les utilisateurs que je n’ai jamais vus sur mon site avec des données tierces, dois-je utiliser des données tierces dans Audience Manager ou dans un DSP ?**

La réponse dépend de vos objectifs. Par exemple, si votre campagne est conçue pour rechercher de nouveaux clients avec des données tierces, travaillez directement avec un fournisseur de services de sécurité. N’oubliez pas que Audience Manager synchronise les données avec un fournisseur de données tiers uniquement lorsque cet utilisateur est visible. Si nous n&#39;avons jamais vu d&#39;utilisateur auparavant, notre système n&#39;aura aucune information pour ce visiteur de site. Pour les campagnes qui souhaitent uniquement utiliser des données tierces pour les utilisateurs de cible qui n’ont jamais visité aucune de vos propriétés, créez ces segments par le biais du fournisseur de services de sécurité.

<br> 

**Puis-je vendre aux particuliers ?**

Audience Manager vous permet d’agrégat aux utilisateurs et de les commercialiser en fonction d’attributs ou de caractéristiques partagés. Toutefois, pour se conformer aux réglementations de l&#39;industrie, [!DNL Audience Manager] les clients ne peuvent pas envoyer d&#39;informations d&#39;identification personnelle à nos systèmes. Par conséquent, vous ne pouvez pas utiliser d’adresses électroniques, de noms individuels, d’adresses physiques, etc. pour le ciblage.

<br> 

**Comment puis-je sécuriser le reciblage des données ?**

Nous vous recommandons d’utiliser une connexion serveur à serveur pour échanger des données avec votre plateforme de reciblage préférée. Audience Manager échange des données avec la plupart des principaux DSP par le biais de connexions serveur à serveur. Les transferts de données de serveur à serveur empêchent d&#39;autres acteurs d&#39;intercepter vos données et de revendre ces informations d&#39;audience.

<br> 

**L’identifiant utilisateur unique d’Audience Manager (UUID) est-il lié à l’identifiant utilisateur unique d’un serveur d’annonces en synchronisant directement l’identifiant sur la page ?**

Non. Les synchronisations d’identifiants ne sont pas effectuées sur la page pour les éditeurs ou serveurs sur site. L’identifiant UUID d’Audience Manager est inséré dans le `u=` champ des fichiers journaux du serveur d’annonces. Cela se produit lorsque le segment est transmis pour le ciblage. Le module de code DIL exécute cette fonction. Il s’agit du même mécanisme qui nous permet de mapper l’ID utilisateur du serveur à un utilisateur d’Audience Manager pour le rapports de performances des segments. Cependant, si un serveur d’annonces est présent sur le site, nous synchronisons les identifiants directement sur la page.

<br> 

**Audience Manager comptabilise-t-il un utilisateur qui se connecte à partir de différents périphériques comme un utilisateur unique ou comme différents utilisateurs uniques ?**

[Le ciblage](../features/declared-ids.md#declared-id-targeting) d’ID déclaré permet à Audience Manager d’identifier un visiteur sur plusieurs périphériques à l’aide d’un identifiant unique. Toutefois, du point de vue du ciblage ou de la destination, il s’agit toujours de 2 utilisateurs (ou plus), car les DSP ne peuvent pas concilier ces multiples identifiants.

<br> 

**Le Gestionnaire d’Audiences peut-il identifier un utilisateur à partir de périphériques mobiles et d’affichage ?**

Oui. Voir Ciblage [des identifiants](../features/declared-ids.md#declared-id-targeting)déclarés.

<br> 

**Puis-je marquer les utilisateurs avec les données collectées en ligne et les recibler en fonction de ce score de modèle ?**

Oui. Audience Manager peut fournir des fichiers de données pour vous aider à marquer les utilisateurs, mais vous devez travailler avec d&#39;autres fournisseurs ou logiciels pour analyser et classer ces informations. Envoyez ces données à Audience Manager sous la forme de paires clé-valeur. Nous pouvons prendre ces informations et les ajouter aux profils utilisateurs existants. Contactez votre représentant Solutions partenaires pour examiner ce processus.

<br> 

**Quels sont les taux de suppression des cookies sur une période de 1 à 2 mois donnée ?**

La suppression des cookies est difficile à mesurer. La plupart des suppressions de cookies proviennent de quelques visiteurs qui suppriment fréquemment les cookies. Cependant, la plupart des cookies de navigateur sont stables pendant au moins 30 jours, même si certains ont une durée de vie limitée. Certaines études suggèrent que le ciblage des entonnoirs supérieurs, supérieur à 30 jours, éliminerait effectivement 7 % de l&#39;audience de cible du navigateur sur une période de 30 jours. Comme vous le savez, les campagnes de 30 jours pour un message créatif donné sont la norme dans le secteur. D&#39;après ce que nous avons vu, cette baisse de 7 % est exacte.

La suppression des cookies a un effet négatif sur les calculs de portée et de fréquence. Par conséquent, nous insistons sur la valeur des données comportementales lorsque nous tentons de comprendre la véritable nature des tendances des consommateurs pour la planification des campagnes d’affichage. Nos clients peuvent exploiter les rapports de chevauchement de segments du Gestionnaire d’Audiences, les rapports de fréquence d’impression optimale et les tendances utilisateur uniques sur des périodes spécifiques pour être plus scientifiques sur la planification des campagnes et les plages de dates optimales pour l’exécution des campagnes.

<br> 

**Quelle est la fenêtre d’expiration des cookies d’Audience Manager ?**

L’interface utilisateur vous permet de déterminer l’intervalle d’expiration des cookies. Vous pouvez définir les cookies pour qu’ils expirent après *un* nombre de jours ou jamais.

<br> 

**La mise en oeuvre d’un créatif de campagne dans un appel de événement nous coûte-t-elle plus cher ?**

Ça dépend. Le coût est basé sur les utilisateurs uniques. Si une campagne génère de nouveaux utilisateurs nets, alors oui, cela coûtera plus cher. Si votre campagne atteint les endroits où nous collectons déjà des données, il n’y a aucun coût supplémentaire. Si votre campagne s’exécute sur des sites apparentés où il y a un chevauchement important, les nouveaux utilisateurs uniques que nous voyons devront supporter des coûts supplémentaires.

<br> 

**Audience Manager affiche[!UICONTROL Addressable Audiences]les mesures et les taux de correspondance pour les[!UICONTROL Server-to-Server]destinations uniquement. Pouvez-vous expliquer pourquoi nous ne voyons pas ces chiffres pour les destinations de cookies et d&#39;URL ?**

Cela se résume à la synchronisation des identifiants. Pour [!UICONTROL Server-to-Server] les destinations, nous transférons les données hors ligne (en temps réel ou par lot) et nous devons envoyer l’identifiant que le partenaire de destination comprend, afin qu’il puisse le mapper à nouveau au navigateur. Le nombre adressable de segments est un sous-ensemble de la population totale de segments.

Dans le cas des destinations de cookie et d’URL, l’utilisateur se trouve déjà dans le navigateur et ce [!DNL Audience Manager] qui est envoyé correspond uniquement aux segments pour lesquels l’utilisateur est qualifié. Le partenaire de destination peut simplement sélectionner les mappages de segments et utiliser ces informations. Tenez donc compte des taux de correspondance pour les destinations de cookie et d’URL toujours à 100 %.
