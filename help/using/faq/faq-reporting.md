---
description: Questions et problématiques courantes concernant la création de rapports.
seo-description: Questions et problématiques courantes concernant la création de rapports.
seo-title: FAQ sur la création de rapports
solution: Audience Manager
title: FAQ sur la création de rapports
uuid: 78cd6c86-8a4a-4748-ab71-b6e8d6078c94
feature: Reporting
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# FAQ sur la création de rapports {#reporting-faq}

Questions et problématiques courantes concernant la création de rapports.

<br> 

<!-- 

faq_reports.xml

 -->

**En ce qui concerne les nouvelles caractéristiques intégrées, pourquoi les valeurs [!UICONTROL Trait Graph] affichées sont-elles parfois inférieures aux valeurs attendues ou égales à 0 ?**

Après le chargement des caractéristiques, il arrive parfois que [!UICONTROL Trait Graph] n’affiche aucun résultat ou affiche des valeurs inférieures à celles attendues. Cela se produit lorsque le volume de données reçu est tellement important que la tâche de traitement entrante ne peut pas terminer l’ingestion de ces informations avant la date limite de création des rapports pour ce jour.

Par conséquent, ces données sont envoyées tardivement au système de rapports et ne s’affichent pas dans l’intervalle de rapports d’un jour utilisé pour tracer le [!UICONTROL Trait Graph]. Cependant, vous pouvez consulter ces données dans les intervalles de rapports de 7, 14, 30 et 60 jours dans un [rapport de tendance](../reporting/trend-reports.md#trend-report-overview) ou un [rapport général](../reporting/general-reports.md#general-reports-overview) le jour suivant.

<br> 

**Certains segments sont absents d’un rapport [!UICONTROL Overlap]. Où se trouvent-ils ?**

Pour réduire la demande de puissance de calcul, les résultats de ces rapports n’incluent pas de données statistiquement insignifiantes. Vos segments ne sont pas absents : ils sont simplement ignorés car ils ne produisent pas de résultats significatifs ni de pools d’utilisateurs utiles que vous pouvez cibler. Voir également :

* [Rapports et méthodes d’échantillonnage des données](../reporting/report-sampling.md)
* [Comptage des utilisateurs uniques dans les rapports de chevauchement et les rapports généraux](../reporting/unique-user-counts.md).

<br> 

**Si je lance une campagne de marketing par courriel, comment puis-je déterminer si des utilisateurs redirigés sont venus sur mon site à partir de cette campagne ou à partir d’autres sources ?**

Ajoutez une chaîne de requête spécifique à une campagne à l’URL de la section de site à surveiller. Ensuite, configurez une règle de caractéristique pour capturer cette variable. Par exemple, si votre URL transmet un identifiant de campagne similaire à `www.test123.com/electronics?campaign=123`, créez une règle de caractéristique pour capturer ces données de la variable `h_referer` avec une règle de caractéristique qui recherche un en-tête similaire à `h_referer = 'campaign=123'`).

<br> 

**Quelle est la différence entre le nombre en temps réel et le nombre total de la population de segments ?**

* **En temps réel :** le nombre d’utilisateurs uniques qui font partie du segment et sont actifs sur vos propriétés au cours d’une période donnée (c.-à-d. que [!DNL Audience Manager] doit avoir enregistré une activité pour cet utilisateur pendant la période donnée).

* **Population totale de segments :** une agrégation de tous les utilisateurs actuellement classés dans ce segment.

<!-- 

<p> <b>Why is data available for total fires for traits but not segments?</b> </p> 
<p>Total fires correspond to page loads. Total trait fires provide the number of times that specific trait has fired. This number will always be equal to, or greater than, your unique user count. By contrast, segments are audience profiles that represent groups of users. Segments don't correlate to page loads or views because they're tied to logic that classifies users based on rules, not individual traits. </p>

 -->

<br> 

**L’un de mes segments se compose d’une seule caractéristique. Lorsque je consulte les mesures de la création de rapports, leurs nombres ne correspondent pas. Pourquoi ?**

Voir [Données sur la population de segments et de caractéristiques dans le créateur de segments](../features/segments/segment-builder-data.md).

<br> 

<!-- 

<p> <b>Why would there be a difference between real-time segment population and the unique values?</b> </p> 
<p>Audience Manager uses different methodologies to count traits and segments. </p> 
<p>For traits, the uniques metric represents receipt of data collection. Every time a visitor realizes a particular trait, either in real-time via the DCS, or offline via Inbound, the uniques for that trait goes up by 1. </p> 
<p>For example, a trait uniques of 2,340 over the range of seven days means that 2,340 unique visitors realized that trait over the last seven days. </p> 
<p>Segments are counted differently because their primary purpose is to help you understand your audience better. Every time Audience Manager sees a visitor in real-time who is a member of a given segment, even if that segment isn’t being newly realized or re-realized on a request, the uniques for that segment goes up by 1. </p> 
<p>For example, a segment uniques of 5,000 over the range of seven days means that Audience Manager saw 5,000 unique users in real-time data-collection events over the last seven days who were members of that segment at the time that Audience Manager saw them, regardless of whether that was a new membership or a pre-existing one. </p>

 -->

**J’ai entré un fichier et mon reçu d’entrée indique qu’un grand nombre d’enregistrements a été traité avec succès, mais le rapport affiche un décompte beaucoup moins élevé. Pourquoi ?**

Dans le serveur principal, les données intégrées sont uniquement associées aux utilisateurs toujours actifs dans AAM (l’utilisateur doit présenter une activité [!DNL DCS] récente au cours des 120 derniers jours). Par conséquent, si vous intégrez des données pour des utilisateurs qui ont déjà expiré dans [!DNL Audience Manager], [!UICONTROL Inbound] peut vous indiquer qu’un certain nombre d’enregistrements d’utilisateurs ont été intégrés, mais si ces utilisateurs n’ont présenté aucune activité récente, ces données sont ignorées lorsqu’elles atteignent notre [!UICONTROL User Profile Store], et cela apparaîtra lors de la création de rapports.

<br> 

**Pourquoi le nombre de caractéristiques uniques de mes caractéristiques intégrées multi-appareils est-il beaucoup plus élevé que le nombre total d’enregistrements intégrés ?**

Si vous intégrez un fichier pour un fournisseur de données multi-appareils en renseignant l’identifiant client, Audience Manager effectue une recherche pour obtenir tous les identifiants d’appareil associés à chacun des identifiants client intégrés. Audience Manager attribue ensuite les caractéristiques intégrées à l’identifiant d’appareil associé à l’identifiant client.

Par exemple, supposons que vous ayez intégré 100 enregistrements. Pour chacun de ces identifiants client, en moyenne, AAM a associé trois identifiants d’appareil. Par conséquent, la caractéristique intégrée est affectée à 300 identifiants d’appareil.

Un seul identifiant de client multi-appareils peut être associé à plusieurs identifiants d’appareil pour deux raisons :

* Les utilisateurs se connectent au même compte multi-appareils à partir de plusieurs ordinateurs/navigateurs.
* Les utilisateurs effacent leurs cookies. Remarque : les cookies « abandonnés » sont supprimés après 120 jours d’inactivité de l’utilisateur.

<br> 

**Pourquoi la valeur [!UICONTROL Total Trait Realizations] de mes caractéristiques intégrées affiche-t-elle toujours 0 ?**

[!UICONTROL Total Trait Realizations] correspondent aux chargements de page. [!UICONTROL Total Trait Realizations] indiquent le nombre de fois où cette caractéristique spécifique a été déclenchée en temps réel. Ce nombre est calculé uniquement pour les caractéristiques basées sur des règles. La valeur [!UICONTROL Total Trait Realizations] des caractéristiques intégrées affiche toujours 0.

<br> 

**J’ai créé une caractéristique et la valeur [!UICONTROL Trait Graph] affiche un nombre de [!UICONTROL Unique Trait Realizations] plus élevé que la valeur [!UICONTROL Total Trait Population]. Est-ce normal ?**

Cela s’affiche parce que les mesures [!UICONTROL Unique Trait Realizations] sont prises en temps réel, tandis que les tâches de rapports effectuées pour calculer la valeur [!UICONTROL Total Trait Population] ne le sont pas. [!UICONTROL Total Trait Population] devrait être supérieur à [!UICONTROL Unique Trait Realizations] après quelques jours.
