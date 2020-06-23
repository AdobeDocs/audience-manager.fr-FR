---
description: L'Audience Manager prend très au sérieux la sécurité des données et la protection de la vie privée. Nous travaillons pour garder nos systèmes en sécurité et protéger vos données précieuses.
seo-description: L'Audience Manager prend très au sérieux la sécurité des données et la protection de la vie privée. Nous travaillons pour garder nos systèmes en sécurité et protéger vos données précieuses.
seo-title: Sécurité des données en Audience Manager
solution: Audience Manager
title: Sécurité des données en Audience Manager
uuid: 33ad19ca-4690-4d97-853b-1882d7d4ac01
translation-type: tm+mt
source-git-commit: 0869e016d7f80710cb194449c48675b82fdfa865
workflow-type: tm+mt
source-wordcount: '1025'
ht-degree: 0%

---


# Sécurité des données en Audience Manager {#data-security}

L&#39;Audience Manager prend très au sérieux la sécurité des données et la protection de la vie privée. Nous travaillons pour garder nos systèmes en sécurité et protéger vos données précieuses.

Les pratiques de sécurité des Audiences Manager comprennent des vérifications externes et internes, l&#39;enregistrement des activités, la formation et d&#39;autres procédures conçues pour protéger nos systèmes et vos données précieuses. Nous croyons qu&#39;un produit sécurisé aide à créer et à maintenir la confiance que les clients placent en nous.

En Audience Manager, nous pensons à la sécurité dans trois catégories principales :

| Type de sécurité | Prise En Charge De |
|---|---|
| **Sécurité des informations** | Méthodes d’authentification, de chiffrement et d’enregistrement de données au niveau de l’entreprise |
| **Fuites de données/transparence** | Une connaissance approfondie et pratique des activités sur site qui constituent ou contribuent aux fuites de données |
| **Améliorations des processus/stratégies** | Clients, en collaborant avec les meilleures pratiques du secteur en matière de confidentialité et de sécurité des données |

## Systèmes, formation et accès {#systems-training-access}

Processus qui permettent de protéger notre système et vos données.

**Validation de la sécurité externe :**  L&#39;Audience Manager teste la sécurité sur une base annuelle et trimestrielle.

* Annuel : Une fois par an, l&#39;Audience Manager est soumise à un test de pénétration complet mené par une société tierce indépendante. Le test est conçu pour identifier les vulnérabilités de sécurité dans l&#39;application. Les tests incluent la recherche de scripts intersites, d&#39;injections SQL, de manipulations de paramètres de formulaire et d&#39;autres vulnérabilités au niveau de l&#39;application.
* Trimestriel : Une fois par trimestre, les équipes internes vérifient les vulnérabilités de sécurité. Ces tests incluent des analyses réseau pour détecter les ports ouverts et les vulnérabilités des services.

**Sécurité des systèmes :**  Pour garantir la sécurité et la confidentialité des données, Audience Manager :

* Bloque les requêtes provenant d’adresses IP non autorisées.
* Protège les données derrière les pare-feu, les VPN et avec l&#39;enregistrement Virtual Private Cloud.
* Effectue le suivi des modifications dans les bases de données des clients et des informations de contrôle à l’aide de la journalisation d’audit basée sur les déclencheurs. Ces journaux effectuent le suivi de toutes les modifications au niveau de la base de données, y compris l’ID utilisateur et l’adresse IP à partir desquels les modifications sont effectuées.

**Ressources de sécurité :**  L&#39;Audience Manager dispose d&#39;une équipe d&#39;opérations réseau dédiée qui surveille les pare-feu et les dispositifs de détection des intrusions. Seul le personnel clé a accès à notre technologie de sécurité et à nos données.

**Formation sur la sécurité :**  En interne, notre engagement envers la sécurité s&#39;étend aux développeurs qui travaillent sur notre produit. Adobe offre une formation formelle aux développeurs sur la façon de créer des applications et des services sécurisés.

**Accès sécurisé :**  L&#39;Audience Manager nécessite des mots de passe difficiles à deviner pour se connecter au système. Voir Exigences relatives aux [](../../reference/password-requirements.md)mots de passe.

## Confidentialité et informations d’identification personnelle {#pii}

Processus qui permettent de protéger les renseignements personnels. Pour plus d’informations sur la confidentialité, consultez le Centre [de confidentialité](https://www.adobe.com/privacy/advertising-services.html)Adobe.

**Données d’identification personnelle :**  L’Audience Manager interdit par contrat aux clients et aux partenaires de données d’envoyer des informations d’identification personnelle dans notre système. De plus, l’identifiant utilisateur unique (UUID) ne contient pas ou n’utilise pas les données d’identification personnelle dans le cadre de l’algorithme de génération d’ID.

**Adresses IP :**  L&#39;Audience Manager collecte les adresses IP. Les adresses IP sont utilisées dans les processus de traitement des données et d’agrégation des journaux. Ils sont également requis pour les recherches et le ciblage géographique/géographique. De plus, toutes les adresses IP des fichiers journaux conservés sont masquées dans les 90 jours.

## Partitionnement des données {#data-partitioning}

Processus qui aident à protéger les données détenues par des clients individuels.

**Partitionnement des données de caractéristiques :**  Vos données ([!UICONTROL traits]identifiants, etc.) est partitionné par le client. Cela permet d’éviter une exposition accidentelle aux informations entre différents clients. Par exemple, les données de caractéristiques des cookies sont partitionnées par client et stockées dans un sous-domaine spécifique au client. Il ne peut pas être lu ou utilisé accidentellement par un autre client d&#39;Audience Manager. En outre, les données de caractéristiques stockées dans le [!UICONTROL Profile Cache Servers (PCS)] sont également partitionnées par le client. Ceci empêche d’autres clients d’utiliser accidentellement vos données dans un appel de événement ou une autre demande.

**Partitionnement des données dans les rapports :**  Les identifiants de client font partie de la clé d’identification dans tous les tableaux de rapports et les requêtes de rapports sont filtrées par identifiant. Cela permet d’empêcher l’affichage de vos données dans les rapports d’un autre client d’Audience Manager.

## Transferts de serveur à serveur entrants (S2S) {#inbound-s2s}

Adobe Audience Manager prend en charge deux méthodes principales de transfert de fichiers de données S2S intégrés à nos systèmes :

Les deux méthodes sont conçues en tenant compte de la sécurité des données de nos clients et partenaires pendant que les données sont en vol entre leurs systèmes et notre système.

**SFTP :** Pour l’option SFTP, la plupart des clients choisissent de diffuser des fichiers via le protocole SFTP (Secure FTP), qui utilise le protocole SSH (Secure Shell). Cette méthode garantit que les fichiers sont chiffrés pendant le vol entre les systèmes du client et le système Adobe. Pour chaque client, nous créons un emplacement de liste déroulante sur nos serveurs SFTP, qui est lié à un compte d’utilisateur sur ce système. Seuls les utilisateurs du système interne privilégié et disposant des informations d’identification du client peuvent accéder à cet emplacement de liste déroulante emprisonné. Cette prison n&#39;est jamais accessible à d&#39;autres clients.

**[!UICONTROL Amazon Web Services S3]via HTTPS :**Pour l’option de diffusion S3, nous recommandons que tous les clients configurent leurs clients S3 pour utiliser la méthode de chiffrement HTTPS pour les transferts de fichiers (il ne s’agit pas de la méthode par défaut, elle doit donc être explicitement configurée). L&#39;option HTTPS est prise en charge à la fois par l&#39;outil de ligne de commande s3cmd et par les bibliothèques S3 disponibles dans tous les langages de programmation majeurs. Cette option HTTPS étant activée, les données du client sont chiffrées pendant le vol vers nos systèmes. Pour chaque client, nous créons un sous-répertoire de compartiment S3 distinct accessible uniquement par les informations d’identification de ce client et celles des utilisateurs de notre système interne.

Pour ajouter le chiffrement PGP à vos fichiers de données, voir Chiffrement PGP [de fichier pour les types](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md)de données entrants.

## Protection des données par évitement {#escaping-data}

Notez que [!DNL Audience Manager] n’échappe pas les données sortantes pour les protéger contre un script intersite possible (XSS), etc. Il incombe au client d’échapper aux données entrantes.

## HTTP Strict-Transport-Security {#hsts}

[!DNL HTTP Strict-Transport-Security (HSTS)] est un mécanisme de sécurité web à l&#39;échelle du secteur qui aide à protéger contre le détournement de cookies et les attaques par déclassement de protocole.

La stratégie indique au navigateur Web qu’une fois qu’un [!DNL HTTPS] appel sécurisé a été effectué à un domaine donné, aucun appel non sécurisé ultérieur ([!DNL HTTP]) ne doit être autorisé à ce domaine. Cela protège contre les attaques par intermédiaire, où un attaquant peut essayer de réduire les [!DNL HTTPS] appels à des appels non sécurisés [!DNL HTTP] &quot;.

Cette stratégie améliore la sécurité des données entre les clients et les serveurs Adobe [Edge](../../reference/system-components/components-edge.md) .

### Exemple {#hsts-example}

Supposons que le `yourcompany.demdex.com` domaine envoie du trafic vers le [!DNL DCS] via [!DNL HTTP]. [!DNL HSTS] met à niveau les appels à utiliser [!DNL HTTPS] à la place, et tous les [!DNL DCS] appels ultérieurs provenant `yourcompany.demdex.com` utiliseront [!DNL HTTPS] à la place de [!DNL HTTP].

Pour plus d&#39;informations sur HSTS, consultez [HTTP Strict Transport Security - Wikipedia](https://en.wikipedia.org/wiki/HTTP_Strict_Transport_Security) .
