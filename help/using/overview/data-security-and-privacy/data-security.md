---
description: Audience Manager prend très au sérieux la sécurité des données et la confidentialité. Nous nous efforçons de maintenir nos systèmes en sécurité et de protéger vos précieuses données.
seo-description: Audience Manager prend très au sérieux la sécurité des données et la confidentialité. Nous nous efforçons de maintenir nos systèmes en sécurité et de protéger vos précieuses données.
seo-title: Sécurité des données
solution: Audience Manager
title: Sécurité des données
uuid: 33ad19ca-4690-4d97-853b-1882d7d4ac01
translation-type: tm+mt
source-git-commit: 91444ad943fcd020c83e522922d67ef400bf8824

---


# Sécurité des données {#data-security}

Audience Manager prend très au sérieux la sécurité des données et la confidentialité. Nous nous efforçons de maintenir nos systèmes en sécurité et de protéger vos précieuses données.

Les pratiques de sécurité d’Audience Manager comprennent des audits externes et internes, la journalisation des activités, la formation et d’autres procédures conçues pour aider à protéger nos systèmes et vos précieuses données. Nous croyons qu'un produit sécurisé permet de créer et de maintenir la confiance que les clients placent en nous.

Dans Audience Manager, nous pensons à la sécurité dans trois catégories principales :

| Type de sécurité | Provides Support For |
|---|---|
| **Information security** | Enterprise-level authentication, encryption, and data storage practices |
| **Data leakage/transparency** | Deep and actionable insight into on-site activities that constitute or contribute to data leakage |
| **Process/policy enhancements** | Clients, by working with industry best practices for privacy and data security |

## Systems, Training, and Access {#systems-training-access}

Processus qui aident à maintenir notre système et vos données en sécurité.

**External Security Validation:**  Audience Manager tests security on an annual and quarterly basis.

* Annuel : Une fois par an, Audience Manager est soumis à un test de pénétration complet effectué par une société tierce indépendante. The test is designed to identify security vulnerabilities in the application. The tests include scanning for cross-site scripting, SQL injections, form parameter manipulation, and other application-level vulnerabilities.
* Trimestriel : Une fois par trimestre, les équipes internes vérifient les vulnérabilités de sécurité. Ces tests incluent des analyses réseau pour détecter les ports ouverts et les vulnérabilités des services.

**** Systems Security:  To help keep data safe and private, Audience Manager:

* Blocks requests from unauthorized IP addresses.
* Protects data behind firewalls, VPNs, and with Virtual Private Cloud storage.
* Effectue le suivi des modifications dans les bases de données des clients et des informations de contrôle à l’aide de la journalisation d’audit basée sur les déclencheurs. Ces journaux effectuent le suivi de toutes les modifications au niveau de la base de données, y compris l’ID utilisateur et l’adresse IP à partir desquels les modifications sont effectuées.

**** Ressources de sécurité :  Audience Manager dispose d’une équipe d’opérations réseau dédiée qui surveille les pare-feu et les dispositifs de détection des intrusions. Only key personnel have access to our security technology and data.

**** Formation à la sécurité :  En interne, notre engagement envers la sécurité s’étend aux développeurs qui travaillent sur notre produit. Adobe offre une formation formelle aux développeurs sur la création d’applications et de services sécurisés.

**** Accès sécurisé :  Audience Manager requiert des mots de passe difficiles à deviner pour se connecter au système. Voir Exigences relatives aux [mots de passe](../../reference/password-requirements.md).

## Confidentialité et informations personnelles identifiables {#pii}

Processus qui permettent de protéger les renseignements personnels. Pour plus d’informations sur la confidentialité, consultez le Centre [de confidentialité](https://www.adobe.com/privacy/advertising-services.html)Adobe.

**** Données PII :  Audience Manager interdit par contrat aux clients et aux partenaires de données d’envoyer des informations d’identification personnelle dans notre système. De plus, l’ID utilisateur unique (UUID) ne contient pas de données d’identification personnelle ou n’en utilise pas dans le cadre de l’algorithme de génération d’ID.

**** IP Addresses:  Audience Manager does collect IP addresses. Les adresses IP sont utilisées dans les processus de traitement des données et d’agrégation des journaux. They are also required for geographic/location look-ups and targeting. De plus, toutes les adresses IP des fichiers journaux conservés sont obscurcies dans les 90 jours.

## Data Partitioning {#data-partitioning}

Processus qui aident à protéger les données détenues par des clients individuels.

**** Partitionnement des données de caractéristiques :  Vos données (caractéristiques, identifiants, etc.) est partitionnée par le client. Cela permet d’éviter une exposition accidentelle aux informations entre différents clients. Par exemple, les données de caractéristiques des cookies sont partitionnées par client et stockées dans un sous-domaine spécifique au client. Il ne peut pas être lu ou utilisé accidentellement par un autre client Audience Manager. Furthermore, trait data stored in the  is also partitioned by customer. [!UICONTROL Profile Cache Servers (PCS)] This prevents other clients from accidentally using your data in an event call or other request.

**** Partitionnement des données dans les rapports :  Les ID client font partie de la clé d’identification dans tous les tableaux de rapports et les requêtes de rapport sont filtrées par ID. This helps prevent your data from appearing in the reports of another Audience Manager customer.

## Inbound Server-to-Server (S2S) Transfers {#inbound-s2s}

Adobe Audience Manager prend en charge deux méthodes principales de transfert des fichiers de données S2S intégrés vers nos systèmes :

Les deux méthodes sont conçues en tenant compte de la sécurité des données de nos clients et partenaires pendant que les données sont en vol entre leurs systèmes et notre système.

**** SFTP : Pour l’option SFTP, la plupart des clients choisissent de diffuser des fichiers via le protocole SFTP (Secure FTP), qui utilise le protocole SSH (Secure Shell). This method ensures that files are encrypted while in flight between the customer's systems and Adobe's system. Pour chaque client, nous créons une zone de dépôt emprisonnée sur nos serveurs SFTP, qui est liée à un compte utilisateur sur ce système. Seuls les utilisateurs du système interne autorisé et privilégié du client peuvent accéder à cet emplacement de la liste déroulante emprisonnée. Cette prison n'est jamais accessible aux autres clients.

**** Amazon Web Services S3 via HTTPS : Pour l’option de remise S3, nous recommandons à tous les clients S3 de configurer leurs clients S3 pour utiliser la méthode de chiffrement HTTPS pour les transferts de fichiers (il ne s’agit pas de la méthode par défaut, il doit donc être explicitement configuré). L'option HTTPS est prise en charge à la fois par l'outil de ligne de commande s3cmd et par les bibliothèques S3 disponibles dans tous les langages de programmation majeurs. Avec cette option HTTPS activée, les données du client sont chiffrées en vol vers nos systèmes. Pour chaque client, nous créons un sous-répertoire de compartiment S3 distinct accessible uniquement par les informations d’identification de ce client et celles des utilisateurs de notre système interne.

To add PGP encryption to your data files, see File PGP Encryption for Inbound Data Types.[](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md)

## Protecting Data by Escaping {#escaping-data}

Notez que [!DNL Audience Manager] n’échappe pas les données sortantes afin de les protéger contre un éventuel script intersite (XSS), etc. Il incombe au client d’échapper aux données entrantes.

## HTTP Strict-Transport-Security (#hsts)

[!DNL HTTP Strict-Transport-Security (HSTS)] is a web security policy mechanism that helps protect against cookie hijacking and protocol downgrade attacks by not permitting  traffic and transparently upgrading all  traffic to .[!DNL HTTP][!DNL HTTP][!DNL HTTPS]

This policy improves data security between clients and Adobe Edge servers.

### Exemple {#hsts-example}

When trying to access ,  will automatically upgrade the request to  , in case the browser doesn’t automatically request the  domain.`http://bank.demdex.com`[!DNL HSTS]`https://bank.demdex.com`[!DNL HTTPS]

See HTTP Strict Transport Security - Wikipedia for more information about HSTS.[](https://en.wikipedia.org/wiki/HTTP_Strict_Transport_Security)
