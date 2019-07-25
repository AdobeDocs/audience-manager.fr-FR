---
description: Questions et problèmes courants liés aux rapports.
seo-description: Questions et problèmes courants liés aux rapports.
seo-title: FAQ sur la création de rapports
solution: Audience Manager
title: FAQ sur la création de rapports
uuid: 78 cd 6 c 86-8 a 4 a -4748-ab 71-b 6 e 8 d 6078 c 94
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# FAQ sur la création de rapports{#reporting-faq}

Questions et problèmes courants liés aux rapports.

<br> 

<!-- 

faq_reports.xml

 -->

**Pour les nouvelles caractéristiques intégrées, pourquoi l'affichage[!UICONTROL Trait Graph]peut-il parfois être inférieur à 0 ou 0 ?**

Sometimes, after you upload traits, the [!UICONTROL Trait Graph] doesn't show any results or shows lower than expected numbers. Cela se produit lorsque le volume des données reçues est tellement important que la tâche de traitement entrant ne peut pas terminer l'assimilation de ces informations avant la date limite de création de rapports pour cette journée.

As a result, this data is sent to the reporting system late and won't show up in the 1-day reporting interval which is used for plotting the [!UICONTROL Trait Graph]. However, you can view this data in the 7, 14, 30, and 60-day report intervals in a [Trend](../reporting/trend-reports.md#trend-report-overview) or [General Report](../reporting/general-reports.md#general-reports-overview) on the following day.

<br> 

**Certains segments sont absents d'un[!UICONTROL Overlap]rapport. Where are they?**

Pour réduire la demande de calcul, ces rapports omettent de données statistiquement insignificatives des résultats. Vos segments ne sont pas manquants, ils sont simplement ignorés car ils ne produisent aucun résultat significatif ou des groupes d'utilisateurs utiles que vous pouvez cibler. Voir également :

* [Rapports et méthodologie d'échantillonnage des données](../reporting/report-sampling.md)
* [Comptabilisation des utilisateurs uniques dans le chevauchement et les rapports généraux](../reporting/unique-user-counts.md).

<br> 

**Si je lance une campagne de marketing par courriel, comment puis-je déterminer si les utilisateurs redirigent vers mon site depuis cette campagne ou d'autres sources ?**

Ajoutez une chaîne de requête spécifique à une campagne à l'URL de la section du site que vous souhaitez surveiller. Ensuite, configurez une règle de caractéristique pour capturer cette variable. For example, if your URL passes in a campaign ID like this, `www.test123.com/electronics?campaign=123`, then create a trait rule to capture that data from the `h_referer` variable with a trait rule that looks for a header like `h_referer = 'campaign=123'`).

<br> 

**Quelle différence y a-t-il entre le nombre total de population de segments et le nombre total de segments ?**

* **Real - time :** Nombre d'utilisateurs uniques qui font partie du segment et actifs sur vos propriétés durant une période donnée (c'est-à-dire [!DNL Audience Manager] doivent avoir une activité enregistrée pour cet utilisateur pendant une période donnée).

* **Population totale de segments :** Regroupement de tous les utilisateurs actuellement classés dans ce segment.

<!-- 

<p> <b>Why is data available for total fires for traits but not segments?</b> </p> 
<p>Total fires correspond to page loads. Total trait fires provide the number of times that specific trait has fired. This number will always be equal to, or greater than, your unique user count. By contrast, segments are audience profiles that represent groups of users. Segments don't correlate to page loads or views because they're tied to logic that classifies users based on rules, not individual traits. </p>

 -->

<br> 

**Je dispose d'un segment composé d'une seule caractéristique. Lorsque je regarde les mesures de création de rapports, leur compte ne correspond pas. Pourquoi ?**

See [Trait and Segment Population Data in Segment Builder](../features/segments/segment-builder-data.md).

<br> 

<!-- 

<p> <b>Why would there be a difference between real-time segment population and the unique values?</b> </p> 
<p>Audience Manager uses different methodologies to count traits and segments. </p> 
<p>For traits, the uniques metric represents receipt of data collection. Every time a visitor realizes a particular trait, either in real-time via the DCS, or offline via Inbound, the uniques for that trait goes up by 1. </p> 
<p>For example, a trait uniques of 2,340 over the range of seven days means that 2,340 unique visitors realized that trait over the last seven days. </p> 
<p>Segments are counted differently because their primary purpose is to help you understand your audience better. Every time Audience Manager sees a visitor in real-time who is a member of a given segment, even if that segment isn’t being newly realized or re-realized on a request, the uniques for that segment goes up by 1. </p> 
<p>For example, a segment uniques of 5,000 over the range of seven days means that Audience Manager saw 5,000 unique users in real-time data-collection events over the last seven days who were members of that segment at the time that Audience Manager saw them, regardless of whether that was a new membership or a pre-existing one. </p>

 -->

**J'ai inbound un fichier et mon reçu entrant indique un nombre élevé d'enregistrements réussis, mais la création de rapports indique un nombre beaucoup moins élevé. Pourquoi ?**

In the backend, onboarded data gets attached only to users that are still active in AAM (user must have had recent [!UICONTROL DCS] activity in the past 120 days). Therefore, if you onboard data for users that have already expired in [!DNL Audience Manager], [!UICONTROL Inbound] might tell you that a certain number of user records were onboarded, but if these users have not had any recent activity, this data is dropped when it reaches our [!UICONTROL User Profile Store] and reporting will surface that.

<br> 

**Pourquoi les caractéristiques uniques pour mes caractéristiques intégrées sur plusieurs périphériques sont-elles beaucoup plus élevées que le nombre total d'enregistrements intégrés ?**

Si vous embarquez un fichier pour un fournisseur de données sur plusieurs périphériques, le gestionnaire d'audience effectue une recherche pour obtenir tous les ID de périphérique associés à chacun des ID de client inclus. Audience Manager attribue ensuite les caractéristiques intégrées à l'ID de périphérique associé à l'ID de client.

Supposons, par exemple, que vous ayez ajouté 100 enregistrements. Pour chacun de ces ID de client, AAM possède en moyenne trois ID de périphérique. Par conséquent, la caractéristique qui était intégrée est affectée à 300 ID de périphérique.

Il existe deux raisons pour lesquelles un ID de client inter-périphériques unique peut être associé à plusieurs ID de périphérique :

* Les utilisateurs se connectent au même compte sur plusieurs périphériques depuis plusieurs ordinateurs/navigateurs.
* Les utilisateurs effacent leurs cookies. Remarque : Les cookies « abandonnés » sont supprimés après 120 jours d'inactivité utilisateur.

<br> 

**Pourquoi mes[!UICONTROL Total Trait Realizations]caractéristiques sont-elles toujours égales à 0 ?**

[!UICONTROL Total Trait Realizations] correspondent aux chargements de page. [!UICONTROL Total Trait Realizations] indiquez le nombre de déclenchements de caractéristiques spécifiques en temps réel. Ce nombre est calculé uniquement pour les caractéristiques basées sur des règles. Onboarded traits always show [!UICONTROL Total Trait Realizations] as 0.

<br> 

**J'ai créé une caractéristique et un[!UICONTROL Trait Graph]nombre plus grand[!UICONTROL Unique Trait Realizations]que la[!UICONTROL Total Trait Population]valeur. Is this normal?**

You are seeing this because the [!UICONTROL Unique Trait Realizations] are real-time metrics, but the reporting jobs we do to calculate the [!UICONTROL Total Trait Population] are not real-time. The [!UICONTROL Total Trait Population] should be larger than the [!UICONTROL Unique Trait Realizations] within a couple of days.
