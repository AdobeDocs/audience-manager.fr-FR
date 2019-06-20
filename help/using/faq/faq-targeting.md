---
description: Questions et problèmes courants liés au ciblage.
seo-description: Questions et problèmes courants liés au ciblage.
seo-title: FAQ sur le ciblage
solution: Audience Manager
title: FAQ sur le ciblage
uuid: ee 96 ef 71-b 903-4953-afc 4-8 ec 8 e 48 bd 49 e
translation-type: tm+mt
source-git-commit: f9a12cf38833cf243edf4bc4c4f4e91f83ee0ca2

---


# Targeting FAQ{#targeting-faq}

Questions et problèmes courants liés au ciblage.

<br> 

<!-- 

faq_targeting.xml

 -->

**Où trouver la liste complète des fournisseurs de données tiers pris en charge par Audience Manager ?**

See the [Adobe Exchange Marketplace](https://marketing.adobe.com/resources/content/resources/en/exchange/marketplace/audience.html) (https://marketing.adobe.com/resources/content/resources/en/exchange/marketplace/audience.html) for a complete list of third-party data providers that [!DNL Audience Manager] supports.

<br> 

**Pour cibler les utilisateurs que je n&#39;ai jamais vus sur mon site avec des données tierces, dois-je utiliser des données tierces dans Audience Manager ou dans un DSP ?**

La réponse dépend de vos objectifs. Par exemple, si votre campagne est conçue pour trouver de nouveaux clients avec des données tierces, travaillez directement avec un DSP. Souvenez-vous que Audience Manager synchronise les données avec un fournisseur de données tiers uniquement lorsque nous le visualisons. Si aucun utilisateur n&#39;a déjà été vu, notre système n&#39;aura aucune information pour ce visiteur de site. Pour les campagnes qui ne souhaitent utiliser que des données tierces, ciblez les utilisateurs qui n&#39;ont jamais visité vos propriétés, puis créez ces segments via le DSP.

<br> 

**Puis-je commercialiser des individus ?**

Audience Manager vous permet d&#39;agréger les utilisateurs et de leur proposer un marketing en fonction des attributs ou caractéristiques partagés. However, to comply with industry regulations, [!DNL Audience Manager] customers may not send personally identifiable information (PII) to our systems. Par conséquent, vous ne pouvez pas utiliser d&#39;adresses électroniques, de noms individuels, d&#39;adresses physiques, etc. pour le ciblage.

<br> 

**Comment conserver les données de reciblage en toute sécurité ?**

Nous vous recommandons d&#39;utiliser une connexion serveur à serveur pour échanger des données avec votre plateforme de reciblage préférée. Audience Manager échange les données avec la plupart des principaux DSP par le biais de connexions serveur à serveur. Les transferts de données serveur à serveur permettent d&#39;éviter que d&#39;autres acteurs interceptent vos données et ne vendent à nouveau ces informations d&#39;audience.

<br> 

**L&#39;utilisateur unique Audience Manager - id (UUID) est-il lié à l&#39;utilisateur unique du serveur d&#39;annonces - id par synchronisation des identifiants directement sur la page ?**

Non. Les synchronisations d&#39;ID ne sont pas effectuées sur la page pour les éditeurs ou les serveurs sur site. The Audience Manager UUID is inserted into the `u=` field of the ad server log files. Cela se produit lorsque le segment est transmis pour le ciblage. Le module de code DIL effectue cette fonction. Il s&#39;agit du mécanisme qui nous permet de mapper l&#39;utilisateur du serveur - id à un utilisateur Audience Manager pour la création de rapports sur les performances des segments. Cependant, si un serveur d&#39;annonces est présent sur le site, nous synchronisons les identifiants directement sur la page.

<br> 

**Audience Manager comptabilise-t-il un utilisateur qui se connecte à partir de différents périphériques en tant qu&#39;utilisateur unique ou utilisateurs uniques différents ?**

[Le ciblage d&#39;ID déclaré](../features/declared-ids.md#declared-id-targeting) aide Audience Manager à identifier un visiteur sur plusieurs périphériques avec un identifiant unique unique. Cependant, du point de vue du ciblage ou de la destination, il s&#39;agit toujours de 2 utilisateurs (ou plus) car les DSP ne peuvent pas rapprocher ces différents ID.

<br> 

**Audience Manager peut identifier un utilisateur provenant de périphériques mobiles et d&#39;affichage.**

Oui. See [Declared ID Targeting](../features/declared-ids.md#declared-id-targeting).

<br> 

**Puis-je identifier les utilisateurs dont les données sont collectées en ligne et les retraiter en fonction de ce score ?**

Oui. Audience Manager peut fournir des fichiers de données pour vous aider à identifier les utilisateurs, mais vous devez collaborer avec d&#39;autres fournisseurs ou logiciels pour analyser et classer ces informations. Envoyez ces données à Audience Manager sous la forme de paires clé-valeur. Nous pouvons prendre ces informations et les ajouter aux profils d&#39;utilisateurs existants. Contactez votre représentant Solutions partenaires pour examiner ce processus.

<br> 

**Quels sont les taux de suppression des cookies sur une période comprise entre 1 et 2 mois ?**

La suppression des cookies est difficile à mesurer. La plupart des cookies de cookie proviennent de quelques visiteurs qui suppriment fréquemment des cookies. Cependant, la plupart des cookies de navigateur sont stables pendant au moins 30 jours, même si certains peuvent avoir une vie limitée. Certaines études suggèrent que le ciblage de l&#39;entonnoir supérieur à 30 jours éliminerait efficacement 7 % du public cible du navigateur pendant une période de 30 jours. Comme vous le savez, les campagnes de 30 jours pour un message créatif donné sont standard dans le secteur. D&#39;après ce que nous avons vu, la réduction de 7 % est exacte.

La suppression des cookies a un impact négatif sur les calculs de portée et de fréquence. Par conséquent, nous soulignons la valeur des données comportementales lors de la tentative de compréhension de la vraie nature des tendances des consommateurs pour la planification des campagnes d&#39;affichage. Nos clients peuvent exploiter les rapports de chevauchement des segments d&#39;Audience Manager, les rapports de fréquence d&#39;impression optimaux et les tendances d&#39;utilisateurs uniques sur des périodes spécifiques afin d&#39;être plus scientifiques sur la planification de campagne et les plages de dates optimales pour l&#39;exécution de campagnes.

<br> 

**Quelle est la fenêtre d&#39;expiration des cookies Audience Manager ?**

L&#39;interface utilisateur vous permet de déterminer l&#39;intervalle d&#39;expiration des cookies. You can set cookies to expire after *n* number of days or never.

<br> 

**La mise en œuvre d&#39;un élément créatif de campagne dans un appel d&#39;événement est-elle plus chère ?**

Cela dépend. Le coût est basé sur des utilisateurs uniques. Si une campagne produit de nouveaux utilisateurs, alors oui, cela coûte plus. Si votre campagne atteint les endroits où nous collectons déjà des données, il n&#39;y a pas de frais supplémentaires. Si votre campagne s&#39;exécute sur les sites associés où un chevauchement important se chevauche, les nouveaux utilisateurs uniques seront coûts.

<br> 

**Audience Manager affiche[!UICONTROL Addressable Audiences]les mesures et les taux de correspondance pour[!UICONTROL Server-to-Server]les destinations uniquement. Can you explain why we don&#39;t see these figures for Cookie and URL destinations?**

Il se termine par la synchronisation des identifiants. For [!UICONTROL Server-to-Server] destinations, we transfer data offline (either real-time or batch) and we need to send the ID that the destination partner understands, so they can map it back to the browser. Le nombre adressable de segment est un sous-ensemble de la population totale de segments.

In the case of Cookie and URL destinations, the user is already on the browser, and what [!DNL Audience Manager] sends is just the segments that the user qualified for. Le partenaire de destination peut simplement sélectionner les correspondances de segments et utiliser ces informations. Considérez donc les taux de correspondance pour les destinations de cookie et d&#39;URL toujours 100 %.
