---
description: Seguire queste istruzioni per generare un file di sincronizzazione completo che includa solo gli utenti attivi di recente. Puoi filtrare i dati per consentire agli utenti attivi di inviarli a un sistema di targeting interno al sito o per limitare le dimensioni dei file inviati a un DSP. Impossibile utilizzare questo filtro con la sincronizzazione incrementale.
seo-description: Follow these instructions to generate a full synchronization file that includes recently active users only. You may want to filter for active users to push relevant data to an on-site targeting system or to limit the size of the files sent to a DSP. You cannot use this filter with incremental synchronization.
seo-title: Filter Outbound Data by Active Users Only
title: Filtrare i dati in uscita solo per gli utenti attivi
uuid: a2b4a385-eee3-458c-b978-09509cacb397
exl-id: d501cfd1-64dd-448e-92c5-180c0081d3e5
TQID: https://experienceleague.adobe.com/rr6ABB4pgrhkWG88VenqIcbyAaPQfbg258M6SVdE28k
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: c814092e-2730-45e8-a12d-e084529f52cb
source-git-commit: d2bed13a6ac7d38ae79b65d492b6de0ca6b6d488
workflow-type: tm+mt
source-wordcount: 219
ht-degree: 0%

---

# Filtrare i dati in uscita solo per gli utenti attivi {#filter-outbound-data-by-active-users-only}

Seguire queste istruzioni per generare un file di sincronizzazione completo che includa solo gli utenti attivi di recente. Puoi filtrare i dati per consentire agli utenti attivi di inviarli a un sistema di targeting interno al sito o per limitare le dimensioni dei file inviati a un DSP. Impossibile utilizzare questo filtro con la sincronizzazione incrementale.

>[!NOTE]
>
>Per essere considerato &quot;attivo&quot;, un visitatore non deve necessariamente essere visualizzato sul sito di un cliente selezionato o nel relativo traffico pubblicitario. Possono essere visualizzati da qualsiasi cliente o partner di [!DNL Audience Manager] per essere considerati &quot;attivi&quot;.

Per filtrare solo in base agli utenti attivi:

1. Fare clic su **[!UICONTROL Companies]**.
1. Selezionare la società con cui si desidera lavorare e fare clic su **[!UICONTROL Destinations]**.
1. Nella sezione [!UICONTROL Batch Data], impostare le opzioni seguenti:

   * **[!UICONTROL Sync Type]**: selezionare **[!UICONTROL Customer]** o **[!UICONTROL Platform]**.
   * **[!UICONTROL Sync Type Lookback Period]**: questo intervallo di tempo definisce l&#39;intervallo del file di dati. Le scelte includono **[!UICONTROL 24 hours]**, **[!UICONTROL 7 days]**, **[!UICONTROL 30 days]**.
   * **[!UICONTROL Incremental Sync Scheduled Run]**: Selezionare **[!UICONTROL Never]**. Questo filtro si applica solo ai file di sincronizzazione completa.
   * **[!UICONTROL Full Sync Scheduled Run]**: determina la frequenza con cui desideri ricevere questo file. Le opzioni disponibili sono **[!UICONTROL 24 hours]**, **[!UICONTROL 7 days]**, **[!UICONTROL 30 days]** o **[!UICONTROL Never]** (da disattivare).

1. Fare clic su **[!UICONTROL Save]**.
