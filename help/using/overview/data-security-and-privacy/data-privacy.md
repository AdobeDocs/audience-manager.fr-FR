---
description: Décrit l'intégration et la conformité d'Audience Manager aux bonnes pratiques généralement acceptées concernant la confidentialité des données et les procédures d'exclusion.
seo-description: Décrit l'intégration et la conformité d'Audience Manager aux bonnes pratiques généralement acceptées concernant la confidentialité des données et les procédures d'exclusion.
seo-title: Confidentialité des données
solution: Audience Manager
title: Confidentialité des données
uuid: 865 e 7 b 4 e-fee 1-4 fa 4-8035-1595 fc 77 cd 96
translation-type: tm+mt
source-git-commit: e6dcd0a33489ae388df25a95d3ad4841030afe31

---


# Confidentialité des données{#data-privacy}

Décrit l'intégration et la conformité d'Audience Manager aux bonnes pratiques généralement acceptées concernant la confidentialité des données et les procédures d'exclusion.

## Confidentialité des données {#data-privacy-center}

See the [Adobe Privacy Center](https://www.adobe.com/privacy/opt-out.html).

## Consumer Privacy Protection {#consumer-privacy-protection}

Audience Manager reconnaît le pacte implicite entre les consommateurs et les marques en ligne avec lesquelles ils interagissent. Les deux parties tirent avantage de l'échange transparent d'éléments de données anonymes :

* Les clients reçoivent du contenu personnalisé, des offres de produit réduites et des expériences utilisateur rationalisées.
* Les marques reçoivent des revenus importants qui prennent en charge plusieurs modèles métier en ligne.

Grâce à la poursuite de ce modèle, Audience Manager reste soucieux de renforcer la transparence et le contrôle des consommateurs, et de répondre ou de dépasser les principes de la publicité comportementale en ligne (OBA).

## Opt-Out Management {#opt-out-management}

La documentation d'exclusion a été étendue et déplacée vers une partie distincte de notre documentation. See [Opt-out Management](../../overview/data-security-and-privacy/opt-out-management.md).

<!-- 

<p>  </p>
<table id="table_A1FF33B328BD451FAFF6C6B8422F928B"> 
 <tgroup cols="2">
  <colspec colnum="1" colname="col1" colwidth="1.00*" />
  <colspec colnum="2" colname="col2" colwidth="2.74*" />
  <thead> 
   <tr> 
    <th colname="col1" class="entry"> Opt-Out For </th> 
    <th colname="col2" class="entry"> Description </th> 
   </tr>
  </thead> 
  <tbody> 
   <tr> 
    <td colname="col1"> <p>Adobe Experience Cloud </p> </td> 
    <td colname="col2"> <p>The <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> Your Privacy Choices page</a> provides 1-click features that let you control and opt-out of data collection by the Adobe Experience Cloud advertising solutions (including Audience Manager). Specifically, see the <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> business customer section</a> of the Privacy Choices page. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p>Browsers that do not support third-party cookies </p> </td> 
    <td colname="col2"> <p>See <a href="../../features/declared-ids.md#declared-id-targeting"> Declared ID Targeting</a>. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p>Mobile devices </p> </td> 
    <td colname="col2"> <p>See the opt-out and privacy settings for: </p> <p> 
      <ul id="ul_86EFAB879215403D937B5148C26A41D9"> 
       <li id="li_C0B544E8F4FE473B94A5436D3A60BDB1"><a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/privacy.html" format="https" scope="external"> Android devices</a> </li> 
       <li id="li_26C787BAB729499A9FEDF055E9AB0637"><a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/privacy.html" format="https" scope="external"> iOS devices</a> </li> 
      </ul> </p> </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table>

 -->

## Collecting IP Addresses and IP Address Obfuscation {#collecting-ip-addresses}

<!-- 

Adobe has enabled processes and offers settings that allow customers to use Audience Manager in compliance with applicable data privacy laws.

-->

L’adresse IP d’un visiteur sur le site Web d’un client est transmise à un centre de traitement des données Adobe où elle peut être stockée. Selon la configuration réseau du visiteur, l'adresse IP peut ne pas nécessairement représenter l'adresse IP de l'ordinateur du visiteur. Il peut par exemple s’agir de l’adresse IP externe d’un pare-feu NAT (traduction d’adresses réseau), d’un proxy HTTP ou d’une passerelle Internet.

**Méthodologie d'obscurcissement d'IP :** Conformément aux principes de « Respect de la vie privée par conception », Adobe Audience Manager permet aux clients d'activer l'obscurcissement des adresses IP depuis l'interface utilisateur, soit globalement dans toutes les régions géographiques, soit pour des pays spécifiques. Lorsque vous activez ce paramètre, le dernier octet (la dernière partie) de l'adresse IP est immédiatement ignoré lorsque l'adresse IP est assimilée dans Audience Manager. Audience Manager ignore cette partie de l'adresse IP avant le traitement (y compris avant toute recherche ou journalisation géographique facultative de l'adresse IP). Par exemple :

* Avant que les valeurs de: `255.255.255.255`
* Après: `255.255.255.0`

>[!NOTE]
>
>See [IP Address Obfuscation](/help/using/features/administration/ip-obfuscation.md) to learn how to enable IP address obfuscation in the Audience Manager UI.

**Segmentation géographique :** Si vous activez l'obscurcissement des adresses IP, les octets restants de l'adresse IP peuvent toujours être utilisés pour la géosegmentation et la création de rapports dans Audience Manager. Si vous n'activez pas l'obscurcissement d'adresses IP, Audience Manager utilise l'adresse IP complète. Vous pouvez utiliser la fonctionnalité de segmentation géographique qui vous permet d'identifier un emplacement IP par zone géographique dans tous les cas, mais avec une légère perte de précision lorsque l'obscurcissement d'IP est utilisé. L’obtention d’informations sur les villes sera considérablement entravée par l’obscurcissement de l’adresse IP, L'obtention d'informations de région et de pays ne devrait être que légèrement compromise. Les données de segmentation géographique sont granulaires uniquement au niveau de la ville ou du code postal, et non au niveau individuel. Read more about [geo-targeting](/help/using/features/traits/trait-geotarget-keys.md) and how to set up traits with geographic variables.

## Concepts associés {#related-concepts}

* [Gestion d'exclusion](/help/using/overview/data-security-and-privacy/opt-out-management.md)
* [FAQ sur la confidentialité et la rétention des données](/help/using/faq/faq-privacy.md)