---
description: Audience Manager takes data security and privacy very seriously. We work to keep our systems secure and protect your valuable data.
seo-description: Audience Manager takes data security and privacy very seriously. We work to keep our systems secure and protect your valuable data.
seo-title: Sécurité des données
solution: Audience Manager
title: Sécurité des données
uuid: 33ad19ca-4690-4d97-853b-1882d7d4ac01
translation-type: tm+mt
source-git-commit: 9e1abb305c66a4adf6a42a7873144222491692f9

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

**** Security Assets:  Audience Manager has a dedicated network operations team that monitors firewalls and intrusion-detection devices. Only key personnel have access to our security technology and data.

**** Security Training:  Internally, our commitment to security extends to developers who work on our product. Adobe provides formal training to developers on how to build secure applications and services.

**** Secure Access:  Audience Manager requires strong passwords to log on to the system. See password requirements.[](../../reference/password-requirements.md)

## Privacy and Personally Identifiable Information (PII) {#pii}

Processes that help keep personal information safe. For additional privacy information, see the Adobe Privacy Center.[](https://www.adobe.com/privacy/advertising-services.html)

**** PII Data:  Audience Manager contractually prohibits customers and data partners from sending PII information into our system. Additionally, the Unique User ID (UUID) does not contain or use PII data as part of the ID-generation algorithm.

**** IP Addresses:  Audience Manager does collect IP addresses. IP addresses are used in data-processing and log-aggregation processes. They are also required for geographic/location look-ups and targeting. Additionally, all IP addresses within retained log files are obfuscated within 90 days.

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

[!DNL HTTP Strict-Transport-Security (HSTS)] est un mécanisme de stratégie de sécurité Web qui aide à protéger contre le détournement de cookies et les attaques par rétrogradation de protocole en n’autorisant pas [!DNL HTTP] le trafic et en mettant à niveau de manière transparente tout le [!DNL HTTP] trafic vers [!DNL HTTPS].

Cette stratégie améliore la sécurité des données entre les clients et les serveurs Adobe Edge.

### Exemple {#hsts-example}

When trying to access ,  will automatically upgrade the request to  , in case the browser doesn’t automatically request the  domain.`http://bank.demdex.com`[!DNL HSTS]`https://bank.demdex.com`[!DNL HTTPS]

See HTTP Strict Transport Security - Wikipedia for more information about HSTS.[](https://en.wikipedia.org/wiki/HTTP_Strict_Transport_Security)
