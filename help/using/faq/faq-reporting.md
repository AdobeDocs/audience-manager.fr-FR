---
description: Questions et problèmes communs liés aux rapports.
seo-description: Questions et problèmes communs liés aux rapports.
seo-title: FAQ sur la création de rapports
solution: Audience Manager
title: FAQ sur la création de rapports
uuid: 78cd6c86-8a4a-4748-ab71-b6e8d6078c94
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# FAQ sur la création de rapports{#reporting-faq}

Questions et problèmes communs liés aux rapports.

<br> 

<!-- 

faq_reports.xml

 -->

**Pour les nouvelles caractéristiques intégrées, pourquoi les valeurs[!UICONTROL Trait Graph]affichées sont-elles parfois inférieures aux valeurs attendues ou égales à 0 ?**

Parfois, après avoir téléchargé des caractéristiques, le n’ [!UICONTROL Trait Graph] affiche aucun résultat ou des chiffres inférieurs aux chiffres attendus. Cela se produit lorsque le volume de données que nous recevons est tellement important que le travail de traitement entrant ne peut pas terminer l’assimilation de ces informations avant la date limite de création des rapports pour cette journée.

Par conséquent, ces données sont envoyées en retard au système de création de rapports et ne s’affichent pas dans l’intervalle de création de rapports d’une journée utilisé pour tracer le [!UICONTROL Trait Graph]. Toutefois, vous pouvez afficher ces données dans les intervalles des rapports de 7, 14, 30 et 60 jours dans un rapport [de tendance](../reporting/trend-reports.md#trend-report-overview) ou [général](../reporting/general-reports.md#general-reports-overview) le lendemain.

<br> 

**Certains segments sont absents d’un[!UICONTROL Overlap]rapport. Où sont-ils ?**

Pour réduire la demande de calcul, ces rapports omettent des données statistiquement insignifiantes des résultats. Vos segments ne sont pas manquants, ils sont simplement supprimés parce qu’ils ne produisent pas de résultats significatifs ou de pools d’utilisateurs utiles que vous pouvez cibler. Voir également :

* [Rapports et méthodes d’échantillonnage des données](../reporting/report-sampling.md)
* [Comptabilisation des utilisateurs uniques dans le chevauchement et les rapports](../reporting/unique-user-counts.md)généraux.

<br> 

**Si j’exécute une campagne de marketing par courrier électronique, comment puis-je déterminer si des utilisateurs redirigés viennent sur mon site à partir de cette campagne ou d’autres sources ?**

Ajoutez une chaîne de requête spécifique à une campagne à l’URL de la section du site à surveiller. Configurez ensuite une règle de caractéristique pour capturer cette variable. Par exemple, si votre URL transmet un ID de campagne comme celui-ci, `www.test123.com/electronics?campaign=123`créez une règle de caractéristique pour capturer ces données de la `h_referer` variable avec une règle de caractéristique qui recherche un en-tête comme `h_referer = 'campaign=123'`).

<br> 

**Quelle est la différence entre le nombre de segments en temps réel et le nombre total de segments ?**

* **** Temps réel : Nombre d’utilisateurs uniques qui font partie du segment et sont actifs sur vos propriétés au cours d’une période donnée (c.-à-d. [!DNL Audience Manager] qui doivent avoir enregistré l’activité pour cet utilisateur pendant une période donnée).

* **** Population totale des segments : Agrégation de tous les utilisateurs qui sont actuellement classés dans ce segment.

<!-- 

<p> <b>Why is data available for total fires for traits but not segments?</b> </p> 
<p>Total fires correspond to page loads. Total trait fires provide the number of times that specific trait has fired. This number will always be equal to, or greater than, your unique user count. By contrast, segments are audience profiles that represent groups of users. Segments don't correlate to page loads or views because they're tied to logic that classifies users based on rules, not individual traits. </p>

 -->

<br> 

**J'ai un segment composé d'un seul trait. Lorsque je regarde les mesures de création de rapports, leur nombre ne correspond pas. Pourquoi ?**

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

**Je suis entré dans un fichier et mon reçu entrant montre un nombre élevé d'enregistrements traités avec succès, mais les rapports montrent des nombres beaucoup plus faibles. Pourquoi ?**

Dans le serveur principal, les données intégrées sont uniquement jointes aux utilisateurs qui sont toujours actifs dans AAM (l’utilisateur doit avoir eu une activité récente au cours des 120 derniers jours). [!UICONTROL DCS] Par conséquent, si vous embarquez des données pour des utilisateurs qui ont déjà expiré dans [!DNL Audience Manager], [!UICONTROL Inbound] vous pouvez vous dire qu’un certain nombre d’enregistrements d’utilisateurs ont été intégrés, mais que si ces utilisateurs n’ont pas eu d’activité récente, ces données sont ignorées lorsqu’elles atteignent notre [!UICONTROL User Profile Store] site et la création de rapports en fera état.

<br> 

**Pourquoi les caractéristiques uniques de mes caractéristiques intégrées inter-périphériques sont-elles bien supérieures au nombre total d’enregistrements intégrés ?**

Si vous embarquez un fichier pour un fournisseur de données sur plusieurs périphériques et que vous l’ignorez, Audience Manager effectue une recherche pour obtenir tous les ID de périphérique associés à chacun des ID de client intégrés. Audience Manager affecte ensuite les caractéristiques intégrées à l’ID de périphérique associé à l’ID de client.

Par exemple, supposons que vous ayez intégré 100 enregistrements. Pour chacun de ces ID de client, AAM a associé trois ID de périphérique en moyenne. Par conséquent, la caractéristique intégrée est affectée à 300 ID de périphérique.

Il existe deux raisons pour lesquelles un seul ID client sur plusieurs périphériques peut être associé à plusieurs ID de périphérique :

* Les utilisateurs se connectent au même compte sur plusieurs périphériques depuis plusieurs ordinateurs/navigateurs.
* Les utilisateurs effacent leurs cookies. Remarque : Les cookies "abandonnés" sont supprimés après 120 jours d’inactivité de l’utilisateur.

<br> 

**Pourquoi est-ce que[!UICONTROL Total Trait Realizations]pour mes caractéristiques embarquées il y a toujours 0 ?**

[!UICONTROL Total Trait Realizations] correspondent aux chargements de page. [!UICONTROL Total Trait Realizations] indiquez le nombre de fois où ce trait spécifique a été déclenché en temps réel. Ce nombre est calculé uniquement pour les caractéristiques basées sur des règles. Les caractéristiques intégrées présentent toujours [!UICONTROL Total Trait Realizations] la valeur 0.

<br> 

**J'ai créé un trait et le[!UICONTROL Trait Graph]montre un plus grand nombre de[!UICONTROL Unique Trait Realizations]caractères que le[!UICONTROL Total Trait Population]. Est-ce normal ?**

Vous voyez cela parce que [!UICONTROL Unique Trait Realizations] il s’agit de mesures en temps réel, mais les tâches de création de rapports que nous effectuons pour calculer le [!UICONTROL Total Trait Population] sont pas en temps réel. La taille [!UICONTROL Total Trait Population] devrait être supérieure à la taille [!UICONTROL Unique Trait Realizations] dans quelques jours.
