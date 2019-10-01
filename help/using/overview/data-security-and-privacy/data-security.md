---
description: Audience Manager prend très au sérieux la sécurité des données et la confidentialité. Nous nous efforçons de maintenir nos systèmes en sécurité et de protéger vos précieuses données.
seo-description: Audience Manager prend très au sérieux la sécurité des données et la confidentialité. Nous nous efforçons de maintenir nos systèmes en sécurité et de protéger vos précieuses données.
seo-title: Sécurité des données
solution: Audience Manager
title: Sécurité des données
uuid: 33ad19ca-4690-4d97-853b-1882d7d4ac01
translation-type: tm+mt
source-git-commit: b76e905ec890dbe8270177d142dddb351438b039

---


# Sécurité des données {#data-security}

Audience Manager prend très au sérieux la sécurité des données et la confidentialité. Nous nous efforçons de maintenir nos systèmes en sécurité et de protéger vos précieuses données.

Les pratiques de sécurité d’Audience Manager comprennent des audits externes et internes, la journalisation des activités, la formation et d’autres procédures conçues pour aider à protéger nos systèmes et vos précieuses données. Nous croyons qu'un produit sécurisé permet de créer et de maintenir la confiance que les clients placent en nous.

Dans Audience Manager, nous pensons à la sécurité dans trois catégories principales :

| Type de sécurité | Prise En Charge De |
|---|---|
| **Sécurité des informations** | Méthodes d’authentification, de chiffrement et de stockage des données au niveau de l’entreprise |
| **Fuite de données/transparence** | Une connaissance approfondie et pratique des activités sur site qui constituent ou contribuent à la fuite des données |
| **Améliorations des processus et des politiques** | Clients en collaborant avec les meilleures pratiques du secteur en matière de confidentialité et de sécurité des données |

## Systèmes, formation et accès {#systems-training-access}

Processus qui aident à maintenir notre système et vos données en sécurité.

**** Validation de sécurité externe :  Audience Manager teste la sécurité sur une base annuelle et trimestrielle.

* Annuel : Une fois par an, Audience Manager est soumis à un test de pénétration complet effectué par une société tierce indépendante. Le test est conçu pour identifier les vulnérabilités de sécurité dans l’application. Les tests incluent la recherche de scripts intersites, d’injections SQL, de manipulations de paramètres de formulaire et d’autres vulnérabilités au niveau de l’application.
* Trimestriel : Une fois par trimestre, les équipes internes vérifient les vulnérabilités de sécurité. Ces tests incluent des analyses réseau pour détecter les ports ouverts et les vulnérabilités des services.

**** Sécurité des systèmes :  Pour garantir la sécurité et la confidentialité des données, Audience Manager :

* Bloque les requêtes provenant d’adresses IP non autorisées.
* Protège les données derrière les pare-feu, les VPN et avec le stockage Virtual Private Cloud.
* Effectue le suivi des modifications dans les bases de données des clients et des informations de contrôle à l’aide de la journalisation d’audit basée sur les déclencheurs. Ces journaux effectuent le suivi de toutes les modifications au niveau de la base de données, y compris l’ID utilisateur et l’adresse IP à partir desquels les modifications sont effectuées.

**** Ressources de sécurité :  Audience Manager dispose d’une équipe d’opérations réseau dédiée qui surveille les pare-feu et les dispositifs de détection des intrusions. Seul le personnel clé a accès à notre technologie et à nos données de sécurité.

**** Formation à la sécurité :  En interne, notre engagement envers la sécurité s’étend aux développeurs qui travaillent sur notre produit. Adobe offre une formation formelle aux développeurs sur la création d’applications et de services sécurisés.

**** Accès sécurisé :  Audience Manager requiert des mots de passe difficiles à deviner pour se connecter au système. Voir Exigences relatives aux [mots de passe](../../reference/password-requirements.md).

## Confidentialité et informations personnelles identifiables {#pii}

Processus qui permettent de protéger les renseignements personnels. Pour plus d’informations sur la confidentialité, consultez le Centre [de confidentialité](https://www.adobe.com/privacy/advertising-services.html)Adobe.

**** Données PII :  Audience Manager interdit par contrat aux clients et aux partenaires de données d’envoyer des informations d’identification personnelle dans notre système. De plus, l’ID utilisateur unique (UUID) ne contient pas de données d’identification personnelle ou n’en utilise pas dans le cadre de l’algorithme de génération d’ID.

**** Adresses IP :  Audience Manager collecte les adresses IP. Les adresses IP sont utilisées dans les processus de traitement des données et d’agrégation des journaux. Elles sont également requises pour les recherches et le ciblage géographique/géographique. De plus, toutes les adresses IP des fichiers journaux conservés sont obscurcies dans les 90 jours.

## Partitionnement des données {#data-partitioning}

Processus qui aident à protéger les données détenues par des clients individuels.

**** Partitionnement des données de caractéristiques :  Vos données (caractéristiques, identifiants, etc.) est partitionnée par le client. Cela permet d’éviter une exposition accidentelle aux informations entre différents clients. Par exemple, les données de caractéristiques des cookies sont partitionnées par client et stockées dans un sous-domaine spécifique au client. Il ne peut pas être lu ou utilisé accidentellement par un autre client Audience Manager. En outre, les données de caractéristiques stockées dans le [!UICONTROL Profile Cache Servers (PCS)] sont également partitionnées par le client. Cela empêche d’autres clients d’utiliser accidentellement vos données dans un appel d’événement ou une autre requête.

**** Partitionnement des données dans les rapports :  Les ID client font partie de la clé d’identification dans tous les tableaux de rapports et les requêtes de rapport sont filtrées par ID. Cela permet d’empêcher l’affichage de vos données dans les rapports d’un autre client d’Audience Manager.

## Transferts de serveur à serveur entrants (S2S) {#inbound-s2s}

Adobe Audience Manager prend en charge deux méthodes principales de transfert des fichiers de données S2S intégrés vers nos systèmes :

Les deux méthodes sont conçues en tenant compte de la sécurité des données de nos clients et partenaires pendant que les données sont en vol entre leurs systèmes et notre système.

**** SFTP : Pour l’option SFTP, la plupart des clients choisissent de diffuser des fichiers via le protocole SFTP (Secure FTP), qui utilise le protocole SSH (Secure Shell). Cette méthode garantit que les fichiers sont chiffrés pendant leur vol entre les systèmes du client et ceux d’Adobe. Pour chaque client, nous créons une zone de dépôt emprisonnée sur nos serveurs SFTP, qui est liée à un compte utilisateur sur ce système. Seuls les utilisateurs du système interne autorisé et privilégié du client peuvent accéder à cet emplacement de la liste déroulante emprisonnée. Cette prison n'est jamais accessible aux autres clients.

**** Amazon Web Services S3 via HTTPS : Pour l’option de remise S3, nous recommandons à tous les clients S3 de configurer leurs clients S3 pour utiliser la méthode de chiffrement HTTPS pour les transferts de fichiers (il ne s’agit pas de la méthode par défaut, il doit donc être explicitement configuré). L'option HTTPS est prise en charge à la fois par l'outil de ligne de commande s3cmd et par les bibliothèques S3 disponibles dans tous les langages de programmation majeurs. Avec cette option HTTPS activée, les données du client sont chiffrées en vol vers nos systèmes. Pour chaque client, nous créons un sous-répertoire de compartiment S3 distinct accessible uniquement par les informations d’identification de ce client et celles des utilisateurs de notre système interne.

Pour ajouter le chiffrement PGP à vos fichiers de données, voir Chiffrement PGP [de fichier pour les types](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md)de données entrants.

## Protection des données par fuite {#escaping-data}

Notez que [!DNL Audience Manager] n’échappe pas les données sortantes afin de les protéger contre un éventuel script intersite (XSS), etc. Il incombe au client d’échapper aux données entrantes.

## HTTP Strict-Transport-Security {#hsts}

[!DNL HTTP Strict-Transport-Security (HSTS)] est un mécanisme de sécurité Web à l’échelle de l’industrie qui aide à protéger contre le détournement de cookies et les attaques par rétrogradation de protocole.

La stratégie indique au navigateur Web qu’une fois qu’un [!DNL HTTPS] appel sécurisé a été effectué à un domaine donné, aucun appel non sécurisé ultérieur ([!DNL HTTP]) ne doit être autorisé à ce domaine. Cela protège contre les attaques par l'homme au milieu, lorsqu'un attaquant peut essayer de rétrograder [!DNL HTTPS] les appels vers des [!DNL HTTP] appels non sécurisés."

Cette stratégie améliore la sécurité des données entre les clients et les serveurs Adobe [Edge](../../reference/system-components/components-edge.md) .

### Exemple {#hsts-example}

Lorsque vous tentez d’accéder `http://bank.demdex.com`, [!DNL HSTS] met automatiquement à niveau la requête vers `https://bank.demdex.com`, au cas où le navigateur ne demanderait pas automatiquement le [!DNL HTTPS] domaine.

Voir [HTTP Strict Transport Security - Wikipedia](https://en.wikipedia.org/wiki/HTTP_Strict_Transport_Security) pour plus d'informations sur HSTS.
