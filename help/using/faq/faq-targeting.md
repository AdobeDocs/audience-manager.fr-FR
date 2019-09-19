---
description: Questions et problèmes communs liés au ciblage.
seo-description: Questions et problèmes communs liés au ciblage.
seo-title: FAQ sur le ciblage
solution: Audience Manager
title: FAQ sur le ciblage
uuid: ee96ef71-b903-4953-afc4-8ec8e48bd49e
translation-type: tm+mt
source-git-commit: f9a12cf38833cf243edf4bc4c4f4e91f83ee0ca2

---


# FAQ sur le ciblage{#targeting-faq}

Questions et problèmes communs liés au ciblage.

<br> 

<!-- 

faq_targeting.xml

 -->

**Où puis-je trouver une liste complète des fournisseurs de données tiers pris en charge par Audience Manager ?**

Voir [Adobe Exchange Marketplace](https://marketing.adobe.com/resources/content/resources/en/exchange/marketplace/audience.html) (https://marketing.adobe.com/resources/content/resources/en/exchange/marketplace/audience.html) pour obtenir la liste complète des fournisseurs de données tiers [!DNL Audience Manager] pris en charge.

<br> 

**Pour cibler les utilisateurs que je n’ai jamais vus sur mon site avec des données tierces, dois-je utiliser des données tierces dans Audience Manager ou dans un DSP ?**

La réponse dépend de vos objectifs. Si, par exemple, votre campagne est conçue pour rechercher de nouveaux clients avec des données tierces, travaillez directement avec un fournisseur de services de données. N’oubliez pas qu’Audience Manager synchronise les données avec un fournisseur de données tiers uniquement lorsque cet utilisateur est visible. Si nous n'avons jamais vu d'utilisateur auparavant, notre système n'aura aucune information pour ce visiteur du site. Pour les campagnes qui souhaitent uniquement utiliser des données tierces afin de cibler les utilisateurs qui n’ont jamais visité aucune de vos propriétés, créez ces segments par l’intermédiaire du fournisseur de services partagés.

<br> 

**Puis-je vendre aux particuliers ?**

Audience Manager vous permet d’agréger les utilisateurs et de les commercialiser en fonction d’attributs ou de caractéristiques partagés. Toutefois, pour se conformer aux réglementations de l'industrie, [!DNL Audience Manager] les clients ne peuvent pas envoyer d'informations d'identification personnelle à nos systèmes. Par conséquent, vous ne pouvez pas utiliser d’adresses électroniques, de noms individuels, d’adresses physiques, etc. pour le ciblage.

<br> 

**Comment puis-je sécuriser le reciblage des données ?**

Nous vous recommandons d’utiliser une connexion serveur à serveur pour échanger des données avec votre plateforme de reciblage préférée. Audience Manager échange des données avec la plupart des principaux DSP par le biais de connexions serveur à serveur. Les transferts de données serveur à serveur empêchent d’autres acteurs d’intercepter vos données et de revendre ces informations d’audience.

<br> 

**L’ID utilisateur unique d’Audience Manager (UUID) est-il lié à l’ID utilisateur unique d’un serveur d’annonces en synchronisant directement l’ID sur la page ?**

Non. Les synchronisations d’ID ne sont pas effectuées sur la page pour les éditeurs ou serveurs sur site. L’UUID Audience Manager est inséré dans le `u=` champ des fichiers journaux du serveur d’annonces. Cela se produit lorsque le segment est transmis pour le ciblage. Le module de code DIL exécute cette fonction. Il s’agit du même mécanisme qui nous permet de mapper l’ID utilisateur du serveur à un utilisateur d’Audience Manager pour la création de rapports sur les performances des segments. Toutefois, si un serveur d’annonces est présent sur le site, nous synchronisons les ID directement sur la page.

<br> 

**Audience Manager compte-t-il un utilisateur qui se connecte à partir de différents périphériques comme un utilisateur unique ou comme des utilisateurs uniques différents ?**

[Le ciblage](../features/declared-ids.md#declared-id-targeting) d’ID déclaré permet à Audience Manager d’identifier un visiteur sur plusieurs périphériques à l’aide d’un identifiant unique. Toutefois, du point de vue du ciblage ou de la destination, il s’agit toujours de deux (ou plus) utilisateurs, car les DSP ne peuvent pas concilier ces identifiants multiples.

<br> 

**Audience Manager peut-il identifier un utilisateur à partir de périphériques mobiles et d’affichage ?**

Oui. Voir Ciblage des identifiants [déclarés](../features/declared-ids.md#declared-id-targeting).

<br> 

**Puis-je marquer les utilisateurs avec les données collectées en ligne et les recibler en fonction de ce score de modèle ?**

Oui. Audience Manager peut fournir des fichiers de données pour vous aider à noter les utilisateurs, mais vous devez travailler avec d’autres fournisseurs ou logiciels pour analyser et classer ces informations. Envoyez ces données à Audience Manager sous la forme de paires clé-valeur. Nous pouvons prendre ces informations et les ajouter aux profils utilisateur existants. Contactez votre représentant Solutions partenaires pour consulter ce processus.

<br> 

**Quels sont les taux de suppression des cookies sur une période de 1 à 2 mois donnée ?**

La suppression des cookies est difficile à mesurer. La plupart des suppressions de cookies proviennent de quelques visiteurs qui suppriment fréquemment les cookies. Cependant, la plupart des cookies de navigateur sont stables pendant au moins 30 jours, même si certains peuvent avoir une durée de vie limitée. Certaines études suggèrent que le ciblage des entonnoirs supérieurs, supérieur à 30 jours, éliminerait effectivement 7 % du public cible du navigateur sur une période de 30 jours. Comme vous le savez, les campagnes de 30 jours pour un message créatif donné sont la norme dans le secteur. D’après ce que nous avons vu, cette baisse de 7 % est exacte.

La suppression des cookies a un effet négatif sur les calculs de portée et de fréquence. Par conséquent, nous insistons sur la valeur des données comportementales lorsque nous tentons de comprendre la véritable nature des tendances des consommateurs pour la planification des campagnes d’affichage. Nos clients peuvent exploiter les rapports de chevauchement de segments d’Audience Manager, les rapports de fréquence d’impression optimale et les tendances utilisateur uniques sur des périodes spécifiques pour être plus scientifiques sur la planification des campagnes et les plages de dates optimales pour l’exécution des campagnes.

<br> 

**Quelle est la fenêtre d’expiration des cookies d’Audience Manager ?**

L’interface utilisateur vous permet de déterminer l’intervalle d’expiration des cookies. Vous pouvez définir les cookies pour qu’ils expirent après *un nombre* de jours ou jamais.

<br> 

**La mise en oeuvre d’un élément créatif de campagne dans un appel d’événement nous coûte-t-elle plus cher ?**

Ça dépend. Le coût est basé sur des utilisateurs uniques. Si une campagne génère de nouveaux utilisateurs nets, alors oui, cela coûtera plus cher. Si votre campagne atteint des endroits où nous collectons déjà des données, il n’y a aucun coût supplémentaire. Si votre campagne s’exécute sur des sites connexes où il existe un chevauchement important, les nouveaux utilisateurs uniques que nous voyons devront supporter des coûts supplémentaires.

<br> 

**Audience Manager affiche[!UICONTROL Addressable Audiences]les mesures et les taux de correspondance pour les[!UICONTROL Server-to-Server]destinations uniquement. Pouvez-vous expliquer pourquoi nous ne voyons pas ces chiffres pour les destinations de cookies et d'URL ?**

Cela se résume à la synchronisation des identifiants. Pour [!UICONTROL Server-to-Server] les destinations, nous transférons les données hors ligne (en temps réel ou par lot) et nous devons envoyer l’ID que le partenaire de destination comprend, afin qu’il puisse le mapper au navigateur. Le nombre adressable de segments est un sous-ensemble de la population totale de segments.

Dans le cas des destinations de cookie et d’URL, l’utilisateur se trouve déjà dans le navigateur et ce [!DNL Audience Manager] qui est envoyé est uniquement les segments pour lesquels l’utilisateur est qualifié. Le partenaire de destination peut simplement sélectionner les mappages de segments et utiliser ces informations. Tenez donc compte des taux de correspondance pour les destinations de cookie et d’URL toujours 100 %.
