---
description: Audience Manager prend très au sérieux la sécurité des données et la confidentialité. We work to keep our systems secure and protect your valuable data.
seo-description: Audience Manager prend très au sérieux la sécurité des données et la confidentialité. Nous nous efforçons de maintenir nos systèmes en sécurité et de protéger vos précieuses données.
seo-title: Sécurité des données
solution: Audience Manager
title: Sécurité des données
uuid: 33ad19ca-4690-4d97-853b-1882d7d4ac01
translation-type: tm+mt
source-git-commit: 34884e3212d50237c73fdc6aa163d90c29a642f5

---


# Sécurité des données {#data-security}

Audience Manager takes data security and privacy very seriously. Nous nous efforçons de maintenir nos systèmes en sécurité et de protéger vos précieuses données.

Les pratiques de sécurité d’Audience Manager comprennent des audits externes et internes, la journalisation des activités, la formation et d’autres procédures conçues pour aider à protéger nos systèmes et vos précieuses données. We believe a secure product helps build and maintain the trust customers place in us.

In Audience Manager, we think about security in three main categories:

| Type de sécurité | Prise En Charge De |
|---|---|
| **Information security** | Méthodes d’authentification, de chiffrement et de stockage des données au niveau de l’entreprise |
| **Data leakage/transparency** | Une connaissance approfondie et pratique des activités sur site qui constituent ou contribuent à la fuite des données |
| **Améliorations des processus et des politiques** | Clients, by working with industry best practices for privacy and data security |

## Systems, Training, and Access {#systems-training-access}

Processus qui aident à maintenir notre système et vos données en sécurité.

**External Security Validation:**  Audience Manager tests security on an annual and quarterly basis.

* Annuel : Une fois par an, Audience Manager est soumis à un test de pénétration complet effectué par une société tierce indépendante. Le test est conçu pour identifier les vulnérabilités de sécurité dans l’application. The tests include scanning for cross-site scripting, SQL injections, form parameter manipulation, and other application-level vulnerabilities.
* Trimestriel : Une fois par trimestre, les équipes internes vérifient les vulnérabilités de sécurité. Ces tests incluent des analyses réseau pour détecter les ports ouverts et les vulnérabilités des services.

**** Sécurité des systèmes :  Pour garantir la sécurité et la confidentialité des données, Audience Manager :

* Bloque les requêtes provenant d’adresses IP non autorisées.
* Protège les données derrière les pare-feu, les VPN et avec le stockage Virtual Private Cloud.
* Effectue le suivi des modifications dans les bases de données des clients et des informations de contrôle à l’aide de la journalisation d’audit basée sur les déclencheurs. Ces journaux effectuent le suivi de toutes les modifications au niveau de la base de données, y compris l’ID utilisateur et l’adresse IP à partir desquels les modifications sont effectuées.

**** Ressources de sécurité :  Audience Manager dispose d’une équipe d’opérations réseau dédiée qui surveille les pare-feu et les dispositifs de détection des intrusions. Seul le personnel clé a accès à notre technologie et à nos données de sécurité.

**** Formation à la sécurité :  En interne, notre engagement envers la sécurité s’étend aux développeurs qui travaillent sur notre produit. Adobe offre une formation formelle aux développeurs sur la création d’applications et de services sécurisés.

**** Accès sécurisé :  Audience Manager requiert des mots de passe difficiles à deviner pour se connecter au système. Voir Exigences relatives aux [mots de passe](../../reference/password-requirements.md).

## Privacy and Personally Identifiable Information (PII) {#pii}

Processes that help keep personal information safe. For additional privacy information, see the Adobe Privacy Center.[](https://www.adobe.com/privacy/advertising-services.html)

**** PII Data:  Audience Manager contractually prohibits customers and data partners from sending PII information into our system. De plus, l’ID utilisateur unique (UUID) ne contient pas de données d’identification personnelle ou n’en utilise pas dans le cadre de l’algorithme de génération d’ID.

**** IP Addresses:  Audience Manager does collect IP addresses. IP addresses are used in data-processing and log-aggregation processes. Elles sont également requises pour les recherches et le ciblage géographique/géographique. De plus, toutes les adresses IP des fichiers journaux conservés sont obscurcies dans les 90 jours.

## Partitionnement des données {#data-partitioning}

Processus qui aident à protéger les données détenues par des clients individuels.

**** Partitionnement des données de caractéristiques :  Vos données (caractéristiques, identifiants, etc.) est partitionnée par le client. Cela permet d’éviter une exposition accidentelle aux informations entre différents clients. Par exemple, les données de caractéristiques des cookies sont partitionnées par client et stockées dans un sous-domaine spécifique au client. It cannot be read or used accidentally by another Audience Manager client. En outre, les données de caractéristiques stockées dans le [!UICONTROL Profile Cache Servers (PCS)] sont également partitionnées par le client. This prevents other clients from accidentally using your data in an event call or other request.

**** Data Partitioning in Reports:  Client IDs are part of the identifying key in all reporting tables and report queries are filtered by ID. Cela permet d’empêcher l’affichage de vos données dans les rapports d’un autre client d’Audience Manager.

## Transferts de serveur à serveur entrants (S2S) {#inbound-s2s}

Adobe Audience Manager supports two main methods of transferring S2S on-boarded data files to our systems:

Les deux méthodes sont conçues en tenant compte de la sécurité des données de nos clients et partenaires pendant que les données sont en vol entre leurs systèmes et notre système.

**** SFTP : Pour l’option SFTP, la plupart des clients choisissent de diffuser des fichiers via le protocole SFTP (Secure FTP), qui utilise le protocole SSH (Secure Shell). This method ensures that files are encrypted while in flight between the customer's systems and Adobe's system. Pour chaque client, nous créons une zone de dépôt emprisonnée sur nos serveurs SFTP, qui est liée à un compte utilisateur sur ce système. Only the customer's credentialed and privileged internal system users can access this jailed drop-box location. This jail is never accessible to other customers.

**** Amazon Web Services S3 via HTTPS: For the S3 delivery option, we recommend that all customers configure their S3 clients to use the HTTPS encryption method for file transfers (this is not the default, so it must be explicitly configured). The HTTPS option is supported both by the s3cmd command line tool as well as the S3 libraries available in every major programming language. Avec cette option HTTPS activée, les données du client sont chiffrées en vol vers nos systèmes. Pour chaque client, nous créons un sous-répertoire de compartiment S3 distinct accessible uniquement par les informations d’identification de ce client et celles des utilisateurs de notre système interne.

Pour ajouter le chiffrement PGP à vos fichiers de données, voir Chiffrement PGP [de fichier pour les types](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md)de données entrants.

## Protection des données par fuite {#escaping-data}

Notez que [!DNL Audience Manager] n’échappe pas les données sortantes afin de les protéger contre un éventuel script intersite (XSS), etc. Il incombe au client d’échapper aux données entrantes.

## HTTP Strict-Transport-Security {#hsts}

[!DNL HTTP Strict-Transport-Security (HSTS)] est un mécanisme de sécurité Web à l’échelle de l’industrie qui aide à protéger contre le détournement de cookies et les attaques par rétrogradation de protocole.

La stratégie indique au navigateur Web qu’une fois qu’un [!DNL HTTPS] appel sécurisé a été effectué à un domaine donné, aucun appel non sécurisé ultérieur ([!DNL HTTP]) ne doit être autorisé à ce domaine. Cela protège contre les attaques par l'homme au milieu, lorsqu'un attaquant peut essayer de rétrograder [!DNL HTTPS] les appels vers des [!DNL HTTP] appels non sécurisés."

Cette stratégie améliore la sécurité des données entre les clients et les serveurs Adobe [Edge](../../reference/system-components/components-edge.md) .

### Exemple {#hsts-example}

Supposons que le `yourcompany.demdex.com` domaine envoie du trafic vers le [!DNL DCS] via [!DNL HTTP]. [!DNL HSTS] met à niveau les appels à utiliser [!DNL HTTPS] à la place, et tous les [!DNL DCS] appels suivants provenant `yourcompany.demdex.com` utiliseront [!DNL HTTPS] au lieu de [!DNL HTTP].

Voir [HTTP Strict Transport Security - Wikipedia](https://en.wikipedia.org/wiki/HTTP_Strict_Transport_Security) pour plus d'informations sur HSTS.
