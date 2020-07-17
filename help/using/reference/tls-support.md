---
description: 'Transport Layer Security (TLS) est un protocole cryptographique utilisé pour établir un canal de communication sécurisé entre deux systèmes. Il sert à authentifier un ou les deux systèmes et à protéger la confidentialité et l''intégrité de l''information transmise entre les systèmes. En mai 2018, il y avait trois versions du protocole TLS en cours d''utilisation : TLS 1.0, 1.1 et 1.2.'
seo-description: 'Transport Layer Security (TLS) est un protocole cryptographique utilisé pour établir un canal de communication sécurisé entre deux systèmes. Il sert à authentifier un ou les deux systèmes et à protéger la confidentialité et l''intégrité de l''information transmise entre les systèmes. En mai 2018, il y avait trois versions du protocole TLS en cours d''utilisation : TLS 1.0, 1.1 et 1.2.'
seo-title: Dépréciation de TLS 1.0 et 1.1
solution: Audience Manager
title: Dépréciation de TLS 1.0 et 1.1
uuid: 6a820e63-dd49-4689-9596-940aabba18ec
feature: reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '606'
ht-degree: 31%

---


# Dépréciation de TLS 1.0 et 1.1{#tls-deprecation}

Transport Layer Security (TLS) est un protocole cryptographique utilisé pour établir un canal de communication sécurisé entre deux systèmes. Il sert à authentifier un ou les deux systèmes et à protéger la confidentialité et l&#39;intégrité de l&#39;information transmise entre les systèmes. En mai 2018, trois versions du protocole TLS étaient utilisées : TLS 1.0, 1.1 et 1.2.

En mars 2019, [!DNL Adobe] le soutien au [!DNL TLS 1.0] protocole a pris fin. La fonctionnalité d’Adobe Audience Manager ne fonctionne pas pour les utilisateurs finaux qui utilisent des navigateurs qui ne prennent en charge que [!DNL TLS 1.0].

En mars 2020, [!DNL Adobe] [!DNL TLS 1.1] le protocole cessera d&#39;être soutenu. La fonctionnalité d’Adobe Audience Manager cessera de fonctionner pour les utilisateurs finaux qui utilisent des navigateurs qui ne prennent en charge que [!DNL TLS 1.1].

Nous recommandons fortement l&#39;utilisation de [!DNL TLS 1.2], qui est, au moment de la rédaction du présent rapport, la dernière version du protocole. Tous les navigateurs modernes utilisent [!DNL TLS 1.2]. Nous avons collecté pour vous une liste de navigateurs, de versions et de leur [!DNL TLS] support. Pour plus d&#39;informations, visitez [ce lien](https://en.wikipedia.org/wiki/Transport_Layer_Security#Web_browsers)Wikipédia.

<table id="table_C273E20039074BB7B6CFB1B877A086B8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Navigateur </p> </th> 
   <th colname="col2" class="entry"> <p>Version </p> </th> 
   <th colname="col03" class="entry"> <p>Plate-forme </p> </th> 
   <th colname="col3" class="entry"> <p>TLS 1.0 </p> </th> 
   <th colname="col4" class="entry"> <p>TLS 1.1 </p> </th> 
   <th colname="col5" class="entry"> <p>TLS 1.2 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="2"> <p>Google Chrome (Chrome pour Android) </p> </td> 
   <td colname="col2"> <p>1 - 21 </p> </td> 
   <td colname="col03" morerows="2"> <p> 
     <ul id="ul_73F2C4C645E1411ABB3AD7ABD1013C59"> 
      <li id="li_EBFC73DCEF3342DDADFF2CBA716DFE93">Windows (7+) </li> 
      <li id="li_75D0A27BB3B246AC8456B0A984BD5DBD">OS X (10.9+) </li> 
      <li id="li_60C1FA4C61EF4AD68719384CDEFC2CF0">Linux Android (4.1+) </li> 
      <li id="li_761665B51622486FA0D6ABBDAA1DCA60">iOS (9.0+) </li> 
      <li id="li_9E19588870DA4EFB963C0C650116DC94">Chrome OS </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p>Oui </p> </td> 
   <td colname="col4"> <p>Non </p> </td> 
   <td colname="col5"> <p>Non </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>22 - 29 </p> </td> 
   <td colname="col3"> <p>Oui </p> </td> 
   <td colname="col4"> <p>Oui </p> </td> 
   <td colname="col5"> <p>Non </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>30 - version actuelle </p> </td> 
   <td colname="col3"> <p>Oui </p> </td> 
   <td colname="col4"> <p>Oui </p> </td> 
   <td colname="col5"> <p>Oui </p> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_B34D89BF3C7646208D353CD55D1F4851"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Navigateur </p> </th> 
   <th colname="col2" class="entry"> <p>Version </p> </th> 
   <th colname="col3" class="entry"> <p>Plate-forme </p> </th> 
   <th colname="col4" class="entry"> <p>TLS 1.0 </p> </th> 
   <th colname="col5" class="entry"> <p>TLS 1.1 </p> </th> 
   <th colname="col6" class="entry"> <p>TLS 1.2 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="2"> <p>Navigateur du système d’exploitation Google Android </p> </td> 
   <td colname="col2"> <p>Android 1.0 - 4.0.4 </p> </td> 
   <td colname="col3" morerows="2"> S.O. </td> 
   <td colname="col4"> <p>Oui </p> </td> 
   <td colname="col5"> <p>Non </p> </td> 
   <td colname="col6"> <p>Non </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Android 4.1 - 4.4.4 </p> </td> 
   <td colname="col4"> <p>Oui </p> </td> 
   <td colname="col5"> <p>Option désactivée par défaut </p> </td> 
   <td colname="col6"> <p>Option désactivée par défaut </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Android 5.0 - version actuelle </p> </td> 
   <td colname="col4"> <p>Oui </p> </td> 
   <td colname="col5"> <p>Oui </p> </td> 
   <td colname="col6"> <p>Oui </p> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_A33FD2FE756641DE8881EEE930CAA244"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Navigateur </p> </th> 
   <th colname="col2" class="entry"> <p>Version </p> </th> 
   <th colname="col3" class="entry"> <p>Plate-forme </p> </th> 
   <th colname="col4" class="entry"> <p>TLS 1.0 </p> </th> 
   <th colname="col5" class="entry"> <p>TLS 1.1 </p> </th> 
   <th colname="col6" class="entry"> <p>TLS 1.2 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="3"> <p>Mozilla Firefox (Firefox pour Mobile) </p> </td> 
   <td colname="col2"> <p>1.0 - ESR 17.0.11 </p> </td> 
   <td colname="col3" morerows="3"> <p> 
     <ul id="ul_617CE841EC7743A08BE004E309A3B0D7"> 
      <li id="li_1A189B9BE2AD4305AF786FBC41A321AC">Windows (7+) </li> 
      <li id="li_E5EF7410AEE948A68F4E3D6D1290B5A4">OS X (10.9+) </li> 
      <li id="li_320467E34FC44492877283935553B87A">Linux Android (4.1+) </li> 
      <li id="li_6827CD3D51B24B54BDCA0DAE7DD43696">iOS (9.0+) </li> 
      <li id="li_B4C08937A5BD47188A97E03AF2F3689B">Chrome OS </li> 
     </ul> </p> <p>ESR uniquement pour : 
     <ul id="ul_6AF06AEC2B494912BA480EA8FF54BF80"> 
      <li id="li_DB30E35051474FBEABE70C69292037DE">Windows (XP SP2+) </li> 
      <li id="li_B412EDEF4FEC4AC9A17C7152BA493768">OS X (10.9+) </li> 
      <li id="li_C2E18F13BFE24C55A7C14488F115810C"> Linux </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p>Oui </p> </td> 
   <td colname="col5"> <p>Non </p> </td> 
   <td colname="col6"> <p>Non </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>23 </p> </td> 
   <td colname="col4"> <p>Oui </p> </td> 
   <td colname="col5"> <p>Option désactivée par défaut </p> </td> 
   <td colname="col6"> <p>Non </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>24 - 26 </p> </td> 
   <td colname="col4"> <p>Oui </p> </td> 
   <td colname="col5"> <p>Option désactivée par défaut </p> </td> 
   <td colname="col6"> <p>Option désactivée par défaut </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>27 - version actuelle </p> </td> 
   <td colname="col4"> <p>Oui </p> </td> 
   <td colname="col5"> <p>Oui </p> </td> 
   <td colname="col6"> <p>Oui </p> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_3BF8A559A263482B9CEF991C13C3F379"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Navigateur </p> </th> 
   <th colname="col2" class="entry"> <p>Version </p> </th> 
   <th colname="col3" class="entry"> <p>Plate-forme </p> </th> 
   <th colname="col4" class="entry"> <p>TLS 1.0 </p> </th> 
   <th colname="col5" class="entry"> <p>TLS 1.1 </p> </th> 
   <th colname="col6" class="entry"> <p>TLS 1.2 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="4"> <p>Microsoft Internet Explorer </p> </td> 
   <td colname="col2"> <p>1 - 3 </p> </td> 
   <td colname="col3"> <p> 
     <ul id="ul_D42AB0C3FEFA4F75805EA82A45185BB9"> 
      <li id="li_53C5453187E34007B8FD32FF88A83C9B">Windows 3.1, 95, NT </li> 
      <li id="li_C8D9FAD1C46E4CE882EAFCD0B3CD1A27">Mac OS 7,8 </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p>Non </p> </td> 
   <td colname="col5"> <p>Non </p> </td> 
   <td colname="col6"> <p>Non </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>4 - 6 </p> </td> 
   <td colname="col3"> <p> 
     <ul id="ul_D6D27EA393334376B9F69880A77AE557"> 
      <li id="li_4BC6C41C2EF546A797122B746F4D943E">Windows 3.1, 95, 98, NT, 2000, XP, Server 2003 </li> 
      <li id="li_2890B5044BBA4F3CA37ECED8A38D6C1B">Mac OS 7.1, 8, X, Solaris, HP-UX </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p>Option désactivée par défaut </p> </td> 
   <td colname="col5"> <p>Non </p> </td> 
   <td colname="col6"> <p>Non </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>7 - 9 </p> </td> 
   <td colname="col3"> <p> 
     <ul id="ul_FC9362377F534C799E4EA4BA84FB604C"> 
      <li id="li_3E572C90A0BD41A68A2E4B8C0CAE1AAB">Windows XP </li> 
      <li id="li_41CAFC08AFC04D85A04BE9CE55D92AE5">Windows Server 2003 </li> 
      <li id="li_983D588A30CD4B4E8BB00E70C669CED2">Windows Vista </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p>Oui </p> </td> 
   <td colname="col5"> <p>Non </p> </td> 
   <td colname="col6"> <p>Non </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>7 - 10 </p> </td> 
   <td colname="col3"> <p> 
     <ul id="ul_7DB290171B744FC6A45E999A7F85265D"> 
      <li id="li_B69400528CB64CB2994F4FB8CF3B4A2A">Windows 7, 8 </li> 
      <li id="li_B759C917E04F4A12826C9ABAE4A7C476">Windows Server 2002, Server 2008, Server 2008 R2 </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p>Oui </p> </td> 
   <td colname="col5"> <p>Option désactivée par défaut </p> </td> 
   <td colname="col6"> <p>Option désactivée par défaut </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>11 </p> </td> 
   <td colname="col3"> <p> 
     <ul id="ul_66FB6A2D1ADD447FB58BE9A8550CB34F"> 
      <li id="li_CA93F2471EEE404992792918E46D27A0">Windows 7, 8.1, 10 </li> 
      <li id="li_97CE6072071748318B9A33ECD7009F8A">Windows Server 2008, Server 2012, Server 2012 R2, Server 2016, Server 2019 </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p>Oui </p> </td> 
   <td colname="col5"> <p>Oui </p> </td> 
   <td colname="col6"> <p>Oui </p> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_08DB65F6A7F24D6B93303549BDE40D8D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Navigateur </p> </th> 
   <th colname="col2" class="entry"> <p>Version </p> </th> 
   <th colname="col3" class="entry"> <p>Plate-forme </p> </th> 
   <th colname="col4" class="entry"> <p>TLS 1.0 </p> </th> 
   <th colname="col5" class="entry"> <p>TLS 1.1 </p> </th> 
   <th colname="col6" class="entry"> <p>TLS 1.2 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="2"> <p>Microsoft Internet Explorer Mobile </p> </td> 
   <td colname="col2"> <p>7, 9 </p> </td> 
   <td colname="col3"> <p>Windows Phone 7, 7.5, 7.8 </p> </td> 
   <td colname="col4"> <p>Oui </p> </td> 
   <td colname="col5"> <p>Non </p> </td> 
   <td colname="col6"> <p>Non </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>10 </p> </td> 
   <td colname="col3"> <p>Windows Phone 8 </p> </td> 
   <td colname="col4"> <p>Oui </p> </td> 
   <td colname="col5"> <p>Option désactivée par défaut </p> </td> 
   <td colname="col6"> <p>Option désactivée par défaut </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>11 </p> </td> 
   <td colname="col3"> <p>Windows Phone 8.1 </p> </td> 
   <td colname="col4"> <p>Oui </p> </td> 
   <td colname="col5"> <p>Oui </p> </td> 
   <td colname="col6"> <p>Oui </p> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_330DA31AD79547E3969A5600AE47A19D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Navigateur </p> </th> 
   <th colname="col2" class="entry"> <p>Version </p> </th> 
   <th colname="col3" class="entry"> <p>Plate-forme </p> </th> 
   <th colname="col4" class="entry"> <p>TLS 1.0 </p> </th> 
   <th colname="col5" class="entry"> <p>TLS 1.1 </p> </th> 
   <th colname="col6" class="entry"> <p>TLS 1.2 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Microsoft Edge et Microsoft Edge pour Mobile </p> </td> 
   <td colname="col2"> <p>Toutes les versions </p> </td> 
   <td colname="col3"> <p> 
     <ul id="ul_87B9CD9D72CA43A1A4DC824C5DEA3638"> 
      <li id="li_23DE8D894B0C43DF8420E8B49E5F8FCE">Windows 10 </li> 
      <li id="li_8EB5AD9689004767A58563AE6AF41AAF">Windows 10 Mobile </li> 
      <li id="li_9257BBAE90914E97A6244F22FCE0F9FE">Windows Server 2016 </li> 
      <li id="li_10940F64FA9349159A88305BE303CC37">Windows Server 2019 </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p>Oui </p> </td> 
   <td colname="col5"> <p>Oui </p> </td> 
   <td colname="col6"> <p>Oui </p> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_2857B874FA714925AC51E6690365F504"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Navigateur </p> </th> 
   <th colname="col2" class="entry"> <p>Version </p> </th> 
   <th colname="col3" class="entry"> <p>Plate-forme </p> </th> 
   <th colname="col4" class="entry"> <p>TLS 1.0 </p> </th> 
   <th colname="col5" class="entry"> <p>TLS 1.1 </p> </th> 
   <th colname="col6" class="entry"> <p>TLS 1.2 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="7"> <p>Navigateur Opera (Opera Mobile) </p> </td> 
   <td colname="col2"> <p>1 - 4 </p> </td> 
   <td colname="col3" morerows="7"> <p> 
     <ul id="ul_0B243815FE07488F934B61C1ABF30F38"> 
      <li id="li_73A74B30C935451FA0870177E7DE91AC">Windows (7+) </li> 
      <li id="li_E0CC0A99244443488026F4EA82027EE0">OS X (10.9+) </li> 
      <li id="li_F04CA1BD8DAD473CABCD64221883FA56">Linux Android (4.0+) </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p>Non </p> </td> 
   <td colname="col5"> <p>Non </p> </td> 
   <td colname="col6"> <p>Non </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>5 - 7 </p> </td> 
   <td colname="col4"> <p>Oui </p> </td> 
   <td colname="col5"> <p>Non </p> </td> 
   <td colname="col6"> <p>Non </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>8 </p> </td> 
   <td colname="col4"> <p>Oui </p> </td> 
   <td colname="col5"> <p>Option désactivée par défaut </p> </td> 
   <td colname="col6"> <p>Non </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>9 </p> </td> 
   <td colname="col4"> <p>Oui </p> </td> 
   <td colname="col5"> <p>Oui </p> </td> 
   <td colname="col6"> <p>Non </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>10 - 12.17 </p> </td> 
   <td colname="col4"> <p>Oui </p> </td> 
   <td colname="col5"> <p>Option désactivée par défaut </p> </td> 
   <td colname="col6"> <p>Option désactivée par défaut </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>12.18 </p> </td> 
   <td colname="col4"> <p>Oui </p> </td> 
   <td colname="col5"> <p>Oui </p> </td> 
   <td colname="col6"> <p>Oui </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>14 - 16 </p> </td> 
   <td colname="col4"> <p>Oui </p> </td> 
   <td colname="col5"> <p>Oui </p> </td> 
   <td colname="col6"> <p>Non </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>17 - version actuelle </p> </td> 
   <td colname="col4"> <p>Oui </p> </td> 
   <td colname="col5"> <p>Oui </p> </td> 
   <td colname="col6"> <p>Oui </p> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_E68FEFB9CAA248B8938918EF2D9AF1E0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Navigateur </p> </th> 
   <th colname="col2" class="entry"> <p>Version </p> </th> 
   <th colname="col3" class="entry"> <p>Plate-forme </p> </th> 
   <th colname="col4" class="entry"> <p>TLS 1.0 </p> </th> 
   <th colname="col5" class="entry"> <p>TLS 1.1 </p> </th> 
   <th colname="col6" class="entry"> <p>TLS 1.2 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p>Apple Safari </p> </td> 
   <td colname="col2"> <p>1 - 6 </p> </td> 
   <td colname="col3"> <p> 
     <ul id="ul_5092A542107E4300955D65A23E647054"> 
      <li id="li_44A6D54B5BC64724B9FF853D3F7D7EAE">Mac OS X 10.2 - 10.8 </li> 
      <li id="li_C0EE310C369444F4AA8F5D22912554B5">Windows XP) </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p>Oui </p> </td> 
   <td colname="col5"> <p>Non </p> </td> 
   <td colname="col6"> <p>Non </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>7 - version actuelle </p> </td> 
   <td colname="col3"> <p>Mac OS X 10.9 - 10.13 </p> </td> 
   <td colname="col4"> <p>Oui </p> </td> 
   <td colname="col5"> <p>Oui </p> </td> 
   <td colname="col6"> <p>Oui </p> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_8A1A4DCB22A949D697B37A96F86FDE7F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Navigateur </p> </th> 
   <th colname="col2" class="entry"> <p>Version </p> </th> 
   <th colname="col3" class="entry"> <p>Plate-forme </p> </th> 
   <th colname="col4" class="entry"> <p>TLS 1.0 </p> </th> 
   <th colname="col5" class="entry"> <p>TLS 1.1 </p> </th> 
   <th colname="col6" class="entry"> <p>TLS 1.2 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p>Apple Safari (mobile) </p> </td> 
   <td colname="col2"> <p>3 - 5 </p> </td> 
   <td colname="col3"> <p>iOS 1 à 4 </p> </td> 
   <td colname="col4"> <p>Oui </p> </td> 
   <td colname="col5"> <p>Non </p> </td> 
   <td colname="col6"> <p>Non </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>5 - version actuelle </p> </td> 
   <td colname="col3"> <p>iOS 5 - 11 </p> </td> 
   <td colname="col4"> <p>Oui </p> </td> 
   <td colname="col5"> <p>Oui </p> </td> 
   <td colname="col6"> <p>Oui </p> </td> 
  </tr> 
 </tbody> 
</table>

