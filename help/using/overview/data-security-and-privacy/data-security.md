---
description: Audience Manager prend très au sérieux la sécurité des données et la confidentialité. Nous nous efforçons de protéger nos systèmes et de protéger vos précieuses données.
seo-description: Audience Manager prend très au sérieux la sécurité des données et la confidentialité. Nous nous efforçons de protéger nos systèmes et de protéger vos précieuses données.
seo-title: Sécurité des données
solution: Audience Manager
title: Sécurité des données
uuid: 33 ad 19 ca -4690-4 d 97-853 b -1882 d 7 d 4 ac 01
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Data Security {#data-security}

Audience Manager prend très au sérieux la sécurité des données et la confidentialité. Nous nous efforçons de protéger nos systèmes et de protéger vos précieuses données.

Les pratiques de sécurité d'Audience Manager comprennent les contrôles externes et internes, la journalisation des activités, la formation et d'autres procédures visant à protéger nos systèmes et vos données précieuses. Nous pensons qu'un produit sécurisé permet de créer et de gérer les clients qui nous ont fait confiance.

Dans Audience Manager, nous considérons la sécurité en trois catégories principales :

| Type de protection | Fournit une assistance pour |
|---|---|
| **Sécurité des informations** | Pratiques d'authentification, de chiffrement et de stockage de données au niveau de l'entreprise |
| **Fuite de données/transparence** | Informations approfondies et exploitables sur les activités sur site qui constituent ou contribuent aux fuites de données |
| **Améliorations des processus/stratégies** | Clients, en appliquant les meilleures pratiques du secteur pour la confidentialité et la sécurité des données |

## Systems, Training, and Access {#systems-training-access}

Ces processus permettent de sécuriser notre système et vos données.

**Validation de la sécurité externe :** Audience Manager teste la sécurité sur une base annuelle et trimestrielle.

* Annuel : Une fois par an, Audience Manager effectue un test de pénétration complet réalisé par une société tierce indépendante. Le test est conçu pour identifier les vulnérabilités de sécurité dans l'application. Les tests incluent l'analyse de scripts intersites, d'injections SQL, de manipulations de paramètres de formulaire et d'autres vulnérabilités au niveau de l'application.
* Trimestriel : Une fois chaque trimestre, les équipes internes vérifient les vulnérabilités de sécurité. Ces tests incluent les analyses réseau pour les ports ouverts et les vulnérabilités de service.

**Sécurité système :** Pour maintenir les données sécurisées et privées, Audience Manager :

* Bloque les requêtes d'adresses IP non autorisées.
* Protège les données derrière les pare-feu, les VPAT et l'espace de stockage virtuel Private Cloud.
* Effectue le suivi des modifications dans les bases de données client et de contrôle avec la journalisation basée sur un trigger. Ces journaux effectuent le suivi de toutes les modifications au niveau de la base de données, y compris l'utilisateur - id et adresse IP à partir desquels les modifications sont effectuées.

**Ressources de sécurité :** Audience Manager est une équipe dédiée aux opérations réseau qui contrôle les pare-feu et les périphériques de détection d'intrusion. Seul le personnel clé a accès à nos technologies et données de sécurité.

**Formation sur la sécurité :** En interne, notre engagement envers la sécurité s'étend aux développeurs qui travaillent sur notre produit. Adobe fournit une formation formelle aux développeurs sur la création d'applications et de services sécurisés.

**Secure Access :** Audience Manager requiert des mots de passe difficiles à deviner pour se connecter au système. See [password requirements](../../reference/password-requirements.md).

## Privacy and Personally Identifiable Information (PII) {#pii}

Processus qui permettent de protéger les informations personnelles. For additional privacy information, see the [Adobe Privacy Center](https://www.adobe.com/privacy/advertising-services.html).

**Données d'identification personnelle :** Audience Manager interdit en fait aux clients et aux partenaires de données d'envoyer des informations d'identification personnelle dans notre système. De plus, l'ID unique (UUID) ne contient ni n'utilise les données d'identification personnelle dans le cadre de l'algorithme de génération d'identifiant.

**Adresses IP :** Audience Manager collecte les adresses IP. Les adresses IP sont utilisées dans les processus de traitement des données et d'agrégation des journaux. Elles sont également requises pour les recherches et le ciblage géographique/géographique. De plus, toutes les adresses IP contenues dans les fichiers journaux conservés sont obscurcies dans les 90 jours.

## Data Partitioning {#data-partitioning}

Processus qui permettent de protéger les données détenues par des clients individuels.

**Partitionnement des données de caractéristique :** Vos données (caractéristiques, ID, etc.) est partitionnement par client. Ceci permet d'éviter l'exposition accidentelle d'informations entre différents clients. Par exemple, les données de caractéristique dans les cookies sont partitionnées par client et stockées dans un sous-domaine spécifique au client. Il ne peut pas être lu ou utilisé accidentellement par un autre client Audience Manager. Furthermore, trait data stored in the [!UICONTROL Profile Cache Servers (PCS)] is also partitioned by customer. Cela empêche d'autres clients d'utiliser accidentellement vos données dans un appel d'événement ou une autre requête.

**Partitionnement de données dans les rapports :** Les identifiants client font partie de la clé d'identification dans tous les tableaux de rapport et les requêtes de rapport sont filtrées par identifiant. Cela permet d'éviter que vos données ne figurent dans les rapports d'un autre client Audience Manager.

## Inbound Server-to-Server (S2S) Transfers {#inbound-s2s}

Adobe Audience Manager prend en charge deux méthodes principales de transfert des fichiers de données S 2 S en interne vers nos systèmes :

Les deux méthodes sont conçues en tenant compte de la sécurité de nos données client et des données partenaires lorsque les données sont en vol entre les systèmes et notre système.

**SFTP :** Pour l'option SFTP, la plupart des clients choisissent de diffuser des fichiers via le protocole SFTP sécurisé, qui utilise le protocole Secure Shell (SSH). Cette méthode garantit que les fichiers sont chiffrés lors de leur vol entre les systèmes du client et le système Adobe. Pour chaque client, nous créons un emplacement de zone de dépôt avec serveur suspendu sur nos serveurs SFTP, qui est lié à un compte utilisateur sur ce système. Seuls les utilisateurs d'informations d'identification et de système interne privilégiés d'un client peuvent accéder à cet emplacement de zone de dépôt. Cette prison n'est jamais accessible aux autres clients.

**Amazon Web Services S 3 via HTTPS :** Pour l'option de remise S 3, nous recommandons à tous les clients de configurer leurs clients S 3 pour qu'ils utilisent la méthode de chiffrement HTTPS pour les transferts de fichiers (il ne s'agit pas de la valeur par défaut). L'option HTTPS est prise en charge à la fois par l'outil de ligne de commande s 3 cmd et par les bibliothèques S 3 disponibles dans chaque langage de programmation majeure. Lorsque cette option HTTPS est activée, les données du client sont chiffrées lors du vol vers nos systèmes. Pour chaque client, nous créons un sous-répertoire de compartiment S 3 distinct qui sera accessible uniquement par les informations d'identification de ce client et par celles de nos utilisateurs système internes.

To add PGP encryption to your data files, see [File PGP Encryption for Inbound Data Types](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md).

## Protecting Data by Escaping {#escaping-data}

Note that [!DNL Audience Manager] does not escape outgoing data to secure it against possible cross-site scripting (XSS), etc. Il incombe au client d'éviter les données entrantes d'entrée.
