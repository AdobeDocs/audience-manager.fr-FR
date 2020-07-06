---
description: Audience Manager prend très au sérieux la sécurité et la confidentialité des données. Nous nous efforçons d’assurer la sécurité de nos systèmes et de protéger vos données importantes.
seo-description: Audience Manager prend très au sérieux la sécurité et la confidentialité des données. Nous nous efforçons d’assurer la sécurité de nos systèmes et de protéger vos données importantes.
seo-title: Sécurité des données dans Audience Manager
solution: Audience Manager
title: Sécurité des données dans Audience Manager
uuid: 33ad19ca-4690-4d97-853b-1882d7d4ac01
feature: data governance & privacy
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '1025'
ht-degree: 94%

---


# Sécurité des données dans Audience Manager {#data-security}

Audience Manager prend très au sérieux la sécurité et la confidentialité des données. Nous nous efforçons d’assurer la sécurité de nos systèmes et de protéger vos données importantes.

Les pratiques de sécurité d’Audience Manager incluent des audits externes et internes, l’enregistrement des activités, la formation ainsi que d’autres procédures conçues pour protéger nos systèmes et vos données importantes. Nous croyons qu’un produit sécurisé aide à créer et à entretenir le lien de confiance que nous partageons avec nos clients.

Dans Audience Manager, nous envisageons la sécurité sous trois grands angles :

| Type de sécurité | Fournit une assistance pour |
|---|---|
| **Sécurité des informations** | Méthodes d’authentification, de chiffrement et de stockage des données au niveau de l’entreprise |
| **Fuite/transparence des données** | Une connaissance approfondie et pratique des activités sur site qui constituent ou contribuent à la fuite de données |
| **Améliorations des processus/politiques** | Clients, en adoptant les bonnes pratiques du secteur en matière de confidentialité et de sécurité des données |

## Systèmes, formation et accès {#systems-training-access}

Processus qui assurent la sécurité de notre système et de vos données.

**Validation de la sécurité en externe :** Audience Manager contrôle le niveau de sécurité sur une base annuelle et trimestrielle.

* Annuellement : une fois par an, Audience Manager est soumis à un test d’intrusion complet effectué par une société tierce indépendante. Ce test est conçu pour identifier les failles de sécurité dans l’application. Les tests incluent la recherche de scripts intersites, d’injections SQL, de manipulations de paramètres de formulaire et d’autres vulnérabilités au niveau de l’application.
* Trimestriellement : une fois par trimestre, les équipes internes recherchent des failles de sécurité. Ces tests incluent des analyses réseau pour détecter les ports ouverts et les vulnérabilités des services.

**Sécurité des systèmes :** pour maintenir la sécurité et la confidentialité des données, Audience Manager :

* bloque les requêtes provenant d’adresses IP non autorisées ;
* protège les données derrière des pare-feux, des VPN et grâce au stockage dans le cloud privé virtuel ;
* effectue le suivi des modifications dans les bases de données des clients et des informations de contrôle à l’aide de la journalisation d’audit basée sur des déclencheurs. Ces journaux effectuent le suivi de toutes les modifications au niveau de la base de données, y compris l’identifiant utilisateur et l’adresse IP à partir desquels les modifications sont effectuées.

**Ressources pour la sécurité :** Audience Manager dispose d’une équipe affectée aux opérations réseau qui surveille les pare-feux et les dispositifs de détection d’intrusion. Seul le personnel clé a accès à notre technologie de sécurité et à nos données.

**Formation sur la sécurité :** en interne, notre engagement envers la sécurité s’étend aux développeurs qui travaillent sur notre produit. Adobe offre aux développeurs une formation formelle portant sur la création d’applications et de services sécurisés.

**Accès sécurisé :** Audience Manager requiert des mots de passe difficiles à deviner pour se connecter au système. Voir les [exigences en matière de mot de passe](../../reference/password-requirements.md).

## Confidentialité et informations d’identification personnelle (PII) {#pii}

Processus qui assurent la protection des informations personnelles. Pour plus d’informations sur la confidentialité, voir le [Centre de traitement des données personnelles d’Adobe](https://www.adobe.com/fr/privacy/experience-cloud.html).

**Informations d’identification personnelle :** le contrat d’Audience Manager interdit aux clients et aux partenaires de données d’envoyer des informations d’identification personnelle vers notre système. De plus, l’identifiant unique de l’utilisateur (UUID) ne contient ou n’utilise aucune donnée d’identification personnelle dans le cadre de l’algorithme de génération d’identifiant.

**Adresses IP :** Audience Manager collecte les adresses IP. Les adresses IP sont utilisées dans les processus de traitement des données et d’agrégation des journaux. Elles sont également requises pour les recherches et le ciblage géographiques. De plus, toutes les adresses IP des fichiers journaux conservés sont masquées dans les 90 jours.

## Partitionnement de données {#data-partitioning}

Processus qui assurent la protection des données détenues par des clients individuels.

**Partitionnement des données de caractéristiques :**  Vos données ([!UICONTROL traits]identifiants, etc.) sont partitionnées par client. Cela permet d’éviter l’exposition accidentelle de différents clients aux informations. Par exemple, les données de caractéristiques des cookies sont partitionnées par client et stockées dans un sous-domaine spécifique au client. Elles ne peuvent pas être lues ni utilisées accidentellement par un autre client d’Audience Manager. En outre, les données de caractéristiques stockées dans les [!UICONTROL Profile Cache Servers (PCS)] sont également partitionnées par client. Cela empêche d’autres clients d’utiliser accidentellement vos données dans un appel d’événement ou une autre requête.

**Partitionnement des données dans les rapports :** les identifiants client font partie de la clé d’identification dans tous les tableaux de rapports, et les requêtes de rapport sont filtrées par identifiant. Cela permet d’empêcher l’affichage de vos données dans les rapports d’un autre client d’Audience Manager.

## Transferts entrants serveur à serveur (S2S) {#inbound-s2s}

Adobe Audience Manager prend en charge deux méthodes principales de transfert de fichiers de données intégrés S2S vers nos systèmes :

Les deux méthodes sont conçues en tenant compte de la sécurité des données de nos clients et partenaires pendant que les données sont en cours de transfert entre leurs systèmes et notre système.

**SFTP :** pour l’option SFTP, la plupart des clients choisissent de diffuser des fichiers au moyen du protocole sécurisé FTP (SFTP), qui utilise le protocole SSH (Secure Shell). Cette méthode garantit que les fichiers sont chiffrés pendant leur transfert entre les systèmes du client et ceux d’Adobe. Pour chaque client, nous créons un emplacement de dépôt sécurisé sur nos serveurs SFTP, lié à un compte d’utilisateur sur ce système. Seuls les utilisateurs privilégiés du système interne disposant des informations d’identification du client peuvent accéder à cet emplacement de dépôt sécurisé. Cet emplacement de dépôt n’est accessible à aucun autre client.

**[!UICONTROL Amazon Web Services S3]via HTTPS :**Pour l’option de diffusion S3, nous recommandons que tous les clients configurent leurs clients S3 pour utiliser la méthode de chiffrement HTTPS pour les transferts de fichiers (il ne s’agit pas de la méthode par défaut, elle doit donc être explicitement configurée). L’option HTTPS est prise en charge à la fois par l’outil de ligne de commande s3cmd et par les bibliothèques S3 disponibles dans tous les langages de programmation fréquemment employés. Une fois cette option HTTPS activée, les données du client sont chiffrées pendant leur transfert vers nos systèmes. Pour chaque client, nous créons un sous-répertoire de compartiment S3 distinct accessible uniquement par les informations d’identification de ce client et celles des utilisateurs de notre système interne.

Pour ajouter un chiffrement PGP à vos fichiers de données, voir [Chiffrement PGP de fichier pour les types de données entrants](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md).

## Protection des données par échappement {#escaping-data}

Il faut souligner que [!DNL Audience Manager] n’échappe pas les données sortantes pour les protéger contre un éventuel script intersite (XSS), etc. L’échappement des données entrantes relève de la responsabilité du client.

## HTTP Strict Transport Security {#hsts}

[!DNL HTTP Strict-Transport-Security (HSTS)] est un mécanisme de sécurité web employé dans tout le secteur qui améliore la protection contre le détournement de session et les attaques par rétrogradation.

La politique indique au navigateur web qu’une fois qu’un appel [!DNL HTTPS] sécurisé a été passé vers un domaine donné, aucun appel non sécurisé ultérieur ([!DNL HTTP]) ne doit être autorisé vers ce domaine. Cette pratique offre une protection contre les attaques de l’homme du milieu, lorsqu’un attaquant est susceptible de tenter de rétrograder les appels [!DNL HTTPS] et les changer en appels [!DNL HTTP] non sécurisés.

Cette politique améliore la sécurité des données entre les clients et les serveurs Adobe [Edge](../../reference/system-components/components-edge.md).

### Exemple {#hsts-example}

Let&#39;s say the `yourcompany.demdex.com` domain sends traffic to the [!DNL DCS] via [!DNL HTTP]. [!DNL HSTS] surclasse les appels de manière à ce qu’ils utilisent [!DNL HTTPS] à la place, et tous les appels [!DNL DCS] ultérieurs provenant de `yourcompany.demdex.com` utiliseront [!DNL HTTPS] à la place de [!DNL HTTP].

Pour plus d’informations sur HSTS, consultez [HTTP Strict Transport Security — Wikipédia](https://fr.wikipedia.org/wiki/HTTP_Strict_Transport_Security).
