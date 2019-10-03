---
description: Décrit l’intégration et la conformité d’Audience Manager avec les meilleures pratiques généralement admises concernant la confidentialité des données des clients et les procédures d’exclusion.
seo-description: Décrit l’intégration et la conformité d’Audience Manager avec les meilleures pratiques généralement admises concernant la confidentialité des données des clients et les procédures d’exclusion.
seo-title: Confidentialité des données
solution: Audience Manager
title: Confidentialité des données
uuid: 865e7b4e-fee1-4fa4-8035-1595fc77cd96
translation-type: tm+mt
source-git-commit: 0eb6a6f67d87377a044b18118fac0185219b0347

---


# Confidentialité des données{#data-privacy}

Décrit l’intégration et la conformité d’Audience Manager avec les meilleures pratiques généralement admises concernant la confidentialité des données des clients et les procédures d’exclusion.

## Confidentialité des données {#data-privacy-center}

See the [Adobe Privacy Center](https://www.adobe.com/privacy/opt-out.html).

## Protection de la vie privée des consommateurs {#consumer-privacy-protection}

Audience Manager reconnaît le pacte implicite entre les consommateurs et les marques en ligne avec lesquelles ils interagissent. Both parties benefit from the transparent exchange of anonymous data elements:

* Consumers receive personalized content, discounted product offers, and streamlined user experiences.
* Les marques reçoivent des flux de revenus vitaux qui prennent en charge plusieurs modèles commerciaux en ligne.

Dans notre appui continu à ce modèle, Audience Manager demeure déterminé à assurer la transparence et le contrôle des consommateurs et à respecter ou à dépasser les principes d’autoréglementation de la publicité comportementale en ligne (OBA).

## Gestion des exclusions {#opt-out-management}

La documentation d’exclusion a été étendue et déplacée vers une partie distincte de notre documentation. Voir Gestion des [exclusions](../../overview/data-security-and-privacy/opt-out-management.md).

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

## Collecte des adresses IP et obscurcissement des adresses IP {#collecting-ip-addresses}

<!-- 

Adobe has enabled processes and offers settings that allow customers to use Audience Manager in compliance with applicable data privacy laws.

-->

The [!DNL IP] address of a visitor to a customer’s website is transmitted to an Adobe [!DNL Data Processing Center] ([!DNL DPC]) where the [!DNL IP] address may be stored. Depending on the network configuration for the visitor, the [!DNL IP] address may not necessarily represent the [!DNL IP] address of the visitor’s computer. For example, the [!DNL IP] address could be the external [!DNL IP] address of a Network Address Translation (NAT) firewall, [!DNL HTTP] proxy, or Internet gateway.

**** Méthodologie d’obscurcissement d’IP : Conformément aux principes de "Confidentialité par conception", Adobe Audience Manager permet aux clients d’activer l’ [!DNL IP] obscurcissement à partir de l’interface utilisateur, que ce soit globalement dans toutes les régions géographiques ou pour des pays spécifiques. Lorsque vous activez ce paramètre, le dernier octet (dernière partie) de l’ [!DNL IP] adresse est immédiatement ignoré lorsque l’ [!DNL IP] adresse est assimilée à Audience Manager. Audience Manager ignore cette partie de l’ [!DNL IP] adresse avant le traitement (y compris avant toute recherche géographique ou journalisation facultative de l’ [!DNL IP] adresse). Par exemple :

* Avant que les valeurs de: `255.255.255.255`
* Après: `255.255.255.0`

>[!NOTE]
>
>Voir Obscurcissement d’adresse [IP](/help/using/features/administration/ip-obfuscation.md) pour savoir comment activer l’obscurcissement d’ [!DNL IP] adresse dans l’interface utilisateur d’Audience Manager.

Regardez la vidéo ci-dessous pour comprendre le fonctionnement de l’obscurcissement des [!DNL IP] adresses dans Audience Manager.

[!VIDEO](https://video.tv.adobe.com/v/27218/?captions=fre_fr)

**** Segmentation géographique : Si vous activez l’obscurcissement des [!DNL IP] adresses, les octets restants de l’ [!DNL IP] adresse peuvent toujours être utilisés pour la géosegmentation et la création de rapports dans Audience Manager. Si vous n’activez pas l’obscurcissement d’ [!DNL IP] adresse, Audience Manager utilise l’adresse [!DNL IP] complète. Vous pouvez utiliser la fonction de segmentation géographique qui vous permet d’identifier un [!DNL IP] [!DNL IP] emplacement par zone géographique dans les deux cas, mais avec une légère perte de précision lors de l’utilisation de l’obscurcissement. Obtaining city-level information will likely be significantly impacted by the obfuscation of the [!DNL IP] address. L'obtention d'informations au niveau de la région et du pays ne devrait être que légèrement affectée. Les données de segmentation géographique sont granulaires uniquement au niveau de la ville ou du code postal, et non au niveau individuel. En savoir plus sur le [ciblage](/help/using/features/traits/trait-geotarget-keys.md) géographique et sur la configuration de caractéristiques avec des variables géographiques.

## Concepts associés {#related-concepts}

* [Gestion des exclusions](/help/using/overview/data-security-and-privacy/opt-out-management.md)
* [FAQ sur la confidentialité et la rétention des données](/help/using/faq/faq-privacy.md)