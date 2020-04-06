---
description: ' d’utilisation  de l’vous aide à et à suivre l’utilisation des de l’instance du Gestionnaire de de votre, afin que vous puissiez comparer votre utilisation réelle à votre engagement contractuel.'
keywords: activity, usage, reporting, commitment
seo-description: ' d’utilisation  de l’vous aide à et à suivre l’utilisation des de l’instance du Gestionnaire de de votre, afin que vous puissiez comparer votre utilisation réelle à votre engagement contractuel.'
seo-title: '   d''utilisation'
solution: Audience Manager
title: '   d''utilisation'
topic: Activity Usage Reporting
translation-type: tm+mt
source-git-commit: 75fe1e0f7321107930a28e354ca2f4a256a477ac

---


#    d&#39;utilisation

## Aperçu {#overview}

Le [!UICONTROL Activity Usage Report] guide vous aide à  et à suivre l&#39;utilisation  des de votre instance de Gestionnaire dede votre, ce qui vous donne une idée claire de la façon dont votre utilisation de vos est comparée à votre engagement contractuel.

De plus, vous pouvez télécharger le [!UICONTROL Activity Usage Report] cas échéant, pour la conservation des enregistrements et les  de  personnalisés.

## Considérations {#considerations}

Ce [!UICONTROL Activity Usage Report] module est accessible à tous les utilisateurs   Manager disposant de droits [d’](edit-account-settings.md)administrateur.

>[!IMPORTANT]
>
>Le [!UICONTROL Activity Usage Report] montre les statistiques d&#39;utilisation  du  de votre instance du Gestionnaire de de votre site Web. Pour toute demande de facturation liée à l’utilisation de votre  de , contactez votre représentant Adobe.

## Cas d’utilisation {#use-cases}

Il existe deux principaux cas d’utilisation du [!UICONTROL Activity Usage Report]:

* **Suivi de l’instance réelle  l’utilisation  des par rapport à votre engagement** d’utilisation des de   : La plupart des clients ont un engagement de  estimé par mois par instance du Gestionnaire de de , qui est ensuite cumulé dans un engagement de annuel pour toutes les instances. Bien que ce rapport ne soit pas un rapport de facturation, il peut vous aider à déterminer si vous dépassez l&#39;utilisation de  de  engagée.
* **Validation des modifications** d’implémentation : Si vous avez récemment mis à jour votre mise en oeuvre, par exemple en configurant le transfert côté serveur d’Analytics ou en modifiant les paramètres d’appel du serveur de , ce rapport peut vous aider à vérifier si le nouveau volume  de est conforme au volume deattendu.

## Utilisation du rapport d&#39; d&#39;utilisation des {#using}

Pour voir le [!UICONTROL Activity Usage Report], connectez-vous à votre compte   Manager, puis accédez à **[!UICONTROL Administration]** > **[!UICONTROL Usage]**.

![aur-ui](assets/aur-ui.png)

Ensuite, utilisez le **[!UICONTROL Reporting Interval]** filtre pour sélectionner l&#39;intervalle de génération du rapport. Vous pouvez choisir entre 30, 60, 90 jours ou une plage de dates personnalisée.

Une fois le rapport chargé, vous pouvez voir la ventilation de votre rapport [!UICONTROL Activities] pour la période sélectionnée.

[!UICONTROL Activities] définissez le   total de toutes les interactions sur site et hors site avec le Gestionnaire de  de , fractionné en un seul et même :

* **[!UICONTROL Server Calls]**: Tout de collecte ou de récupération de données envoyé à  Gestionnaire de  à partir de sites Web, de serveurs, de courriels, d’applications mobiles ou d’autres systèmes.
* **[!UICONTROL Pixel Calls](anciennement[!UICONTROL Impression Server Calls])**: Données collectées à partir de publicités (telles que le volume d’impression d’une plateforme de ciblage) ou appels d’impression par courrier électronique envoyés à  Gestionnaire de  de. Pour ce faire, il est nécessaire que le`d_event`paramètre soit présent dans la chaîne de  du.
* **[!UICONTROL On-Boarded Records]**: Enregistrements uniques assimilés à partir de votre propre système de gestion de la relation client (CRM) ou d’autres fichiers de données hors ligne, tels que les enregistrements du centre d’appels, les ID de périphérique et les flux de données personnalisés provenant de fournisseurs de données externes.
* **[!UICONTROL Log File Records]**: Enregistrements uniques provenant de fichiers journaux assimilés dans  Gestionnaire de  de à partir d’une plateforme de ciblage.

>[!NOTE]
>
>Un enregistrement unique définit chaque enregistrement individuel de données dans un fichier stocké par Adobe au nom d’un client   Manager.

De plus, vous pouvez utiliser les types de [!UICONTROL Activity Usage Trends] graphique pour basculer entre deux types de graphiques.

![aur-ui-graphes](assets/aur-ui-graphs.png)

Vous pouvez également placer le curseur sur une date spécifique du plan de montage chronologique pour voir l’utilisation détaillée de cette date.

![aur-hover](assets/aur-hover.png)

## Exportation  rapports  d&#39;utilisation des {#export}

Pour une meilleure vue d’ensemble du niveau d’utilisation de votre  Gestionnaire de   de, vous pouvez exporter le  en fonction du type d’enregistrement que vous souhaitez inclure. [!UICONTROL Activity Usage Report]

![aur-export](assets/aur-export.png)

Les **[!UICONTROL Onboarded Records Breakdown]** rapports et **[!UICONTROL Onsite Server Calls Breakdown]** les rapports fournissent la meilleure vue d’ensemble des données source disponibles pour ces  de . Le volume attribué à ces ventilations est basé sur votre implémentation.

### Ventilation des enregistrements intégrés {#onboarded-breakdown}

Ce rapport contient des enregistrements intégrés ventilés par source de données.

### Ventilation des appels au serveur Onsite {#onsite-breakdown}

Ce rapport contient une ventilation des appels serveur provenant de trois sources : [!UICONTROL Analytics], [!UICONTROL Target]et [!UICONTROL Other].

* **[!UICONTROL Analytics]**: Il s’agit d’appels serveur facturables transmis de toutes les instances d’Adobe Analytics à  Gestionnaire de , y compris le transfert côté serveur. Les appels serveur secondaires ou les appels serveur  (comme dans le cas du transfert côté serveur à partir de plusieurs suites de rapports) ne sont pas facturables , ils ne sont donc pas inclus dans cette ventilation.
* **[!UICONTROL Target]**: Il s’agit d’appels côté serveur d’Adobe  à  Gestionnaire de  de pour récupérer les données de segments du Gestionnaire de de dans le cadre d’une intégration serveur à serveur.
* **[!UICONTROL Other]**: Inclut les appels en provenance de tout autre site Web ou système (sites partenaires, appels directs au serveur, etc.), les appels au navigateur ou à l’application mobile via les [!DNL SDK], [!DNL DIL], les appels  et [!DNL DCS] les appels. Inclut également les appels de [!DNL Target] s’ils sont configurés en tant qu’intégration de cookie (plutôt que de serveur à serveur).
