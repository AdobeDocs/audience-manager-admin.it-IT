---
description: Crea, modifica ed elimina destinazioni Audienci Manager.
seo-description: Create, edit, and delete Audience Manager destinations.
seo-title: Manage Company Destinations
title: Gestire le destinazioni aziendali
uuid: d9a6bfb1-7629-44e0-b7d7-ece44f65ea2b
exl-id: a2e73613-07cd-4ab8-8c6e-be451ed50bfc
source-git-commit: 79415eba732c2a6d50f04124774664f788ccc78c
workflow-type: tm+mt
source-wordcount: '1061'
ht-degree: 0%

---

# Gestire le destinazioni aziendali {#manage-company-destinations}

Crea, modifica ed elimina destinazioni Audienci Manager.

<!-- t_company_destinations.xml -->

Per informazioni dettagliate, consulta [Destinazioni](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/destinations/destinations.html) nella *Guida utente di Audience Manager*.

## Creare o modificare le destinazioni aziendali {#create-edit-company-destinations}

Scorri le sezioni per istruzioni dettagliate su come creare nuove destinazioni [!DNL Audience Manager] o modificare quelle esistenti.

<!-- create-edit-company-destinations.xml -->

Visita la [pagina di integrazione dei partner di Experience Cloud](https://wiki.corp.adobe.com/x/mPIMPw) prima di configurare le destinazioni. La pagina contiene le informazioni specifiche da compilare per ogni integrazione partner [!DNL Audience Manager].

Se il client desidera utilizzare [!DNL Adobe Media Optimizer] come destinazione in [!DNL Audience Manager] , è necessario configurarlo in [!DNL Adobe Media Optimizer].

## Passa alla scheda Destinazioni {#navigate-destinations}

1. Fai clic su **[!UICONTROL Companies]**, quindi individua e fai clic sulla società desiderata per visualizzarne la pagina [!UICONTROL Profile]. È possibile utilizzare la casella [!UICONTROL Search] o i controlli di impaginazione nella parte inferiore dell&#39;elenco per individuare la società desiderata. Puoi ordinare ogni colonna in ordine crescente o decrescente facendo clic sull’intestazione della colonna desiderata.
1. Fare clic sulla scheda **[!UICONTROL Destinations]**.
1. Per creare una nuova destinazione, scegliere **[!UICONTROL Add Destination]**. Per modificare una destinazione esistente, fare clic sul nome della destinazione nella colonna **[!UICONTROL Name]**.

## Impostazioni di base {#basic-settings}

Compila i campi nella finestra **[!UICONTROL Basic Settings]**.

* **[!UICONTROL Name]:** (obbligatorio) Specificare il nome della destinazione.
* **[!UICONTROL Description]:** Specificare informazioni descrittive su questa destinazione.
* **[!UICONTROL Type]:** (obbligatorio) Selezionare il tipo di destinazione desiderato:
   * **[!UICONTROL Bulk ID]**: sincronizza gli ID tra piattaforme diverse.
   * **[!UICONTROL Bulk Trait]**: invia informazioni sulle caratteristiche in blocco a diverse piattaforme.
   * **[!UICONTROL Bulk Segment]**: invia informazioni sui segmenti in blocco a piattaforme diverse.
   * **[!UICONTROL S2S]**: utilizzare le destinazioni server-to-server per inviare dati in tempo reale e batch a piattaforme diverse.
* **[!UICONTROL Auto-Fill Destination Mapping]:** (solo [!UICONTROL S2S]) Selezionare un&#39;opzione:
   * **[!UICONTROL Segment ID]:** Se selezioni questa impostazione, il mapping del valore di destinazione viene compilato con l&#39;ID segmento [!DNL Audience Manager].
   * **[!UICONTROL Integration Code Value]:** Se si seleziona questa impostazione, il mapping del valore di destinazione viene compilato con il codice di integrazione del segmento [!DNL Audience Manager].
* **[!UICONTROL User ID Key]:** (obbligatorio) Selezionare la chiave ID utente desiderata per questa destinazione dall&#39;elenco a discesa.

Questo ID viene utilizzato come ID sorgente dati principale. Questo determina gli ID utente da escludere nel file.

>[!NOTE]
>
>Per il tipo di destinazione [!UICONTROL Bulk ID], non è possibile utilizzare l&#39;ID [!UICONTROL User ID] di tipo [!DNL Audience Manager] o [!DNL Adobe Experience Cloud].

Se l&#39;ID dell&#39;origine dati ( [!UICONTROL DPID]) non viene visualizzato nell&#39;elenco a discesa, è necessario selezionare la casella di controllo **[!UICONTROL Outbound]** a livello dell&#39;origine dati nella [pagina Impostazioni di Data Source](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-sources/manage-datasources.html).

* **[!UICONTROL Target Data Source]:** (obbligatorio) Selezionare l&#39;origine dati desiderata per questa destinazione dall&#39;elenco a discesa. Questa impostazione consente l’etichettatura dei dati in uscita, che consente l’acquisizione in sistemi separati sul lato dei clienti.
* **[!UICONTROL Foreign Account ID]:** Specificare l&#39;ID account esterno per questa destinazione. Si tratta del valore di identificazione nel sistema del destinatario per questi dati in uscita.
* **[!UICONTROL Outbound Sample Rate Denominator]:** Quando la quantità totale di dati restituiti è sconosciuta, utilizzare questa impostazione per restituire solo una quantità campione di dati, anziché la quantità completa. Regolare qui il numero per rappresentare una frazione di dati (ad esempio, un valore di &#39;100&#39; restituisce 1/100 della quantità regolare di dati, un valore di &#39;10&#39; restituisce 1/10 della quantità regolare di dati). Il valore predefinito è &#39;1&#39;, che restituisce tutti i dati.

## Dati in tempo reale (per destinazioni S2S) {#realtime-s2s}

Se stai creando una destinazione [!UICONTROL S2S], compila i campi seguenti:

**[!UICONTROL Servers]**: selezionare il server `HTTP` desiderato per questa destinazione.
**[!UICONTROL Format]**: selezionare il formato desiderato per questa destinazione dall&#39;elenco a discesa: [!UICONTROL HTTP only].

>[!NOTE]
>
>Solo per [!DNL S2S], è possibile abilitare o disabilitare [!UICONTROL Realtime] o [!UICONTROL Batch] destinazioni utilizzando i cursori On/Off sullo schermo. Non è possibile disattivare entrambe le opzioni.

## Dati batch {#batch-data}

Per [!UICONTROL Bulk ID], [!UICONTROL Bulk Trait] o [!UICONTROL Bulk Segment] destinazioni, compila i campi seguenti:

* **[!UICONTROL Protocol]**: (obbligatorio) selezionare il protocollo desiderato per questa destinazione dall&#39;elenco a discesa:
   * **[!UICONTROL FTP]**
   * **[!UICONTROL HTTP]**
   * **[!UICONTROL S3]**
* **[!UICONTROL Servers]**: (obbligatorio) selezionare il server desiderato per questa destinazione dall&#39;elenco a discesa.
* **[!UICONTROL Format]**: (obbligatorio) selezionare il formato desiderato per la destinazione dall&#39;elenco a discesa [!DNL HTTP] o il tipo di file, a seconda del protocollo scelto in precedenza.
* **[!UICONTROL Sync Type]**: (obbligatorio) selezionare il tipo di sincronizzazione desiderato per questa destinazione. Indica il livello di attività utente che i clienti desiderano includere negli ordini in uscita. Selezionare **[!UICONTROL Customer]** se i client sono interessati solo all&#39;analisi delle qualifiche dei segmenti dalle relative proprietà. Selezionare **[!UICONTROL Platform]** se si desidera includere le qualifiche dei segmenti da attività esterne al sito per tutti i clienti [!DNL Audience Manager].
* **[!UICONTROL Customer]**: il file contiene utenti attivi che hanno almeno 1 realizzazione delle caratteristiche solo sulle proprietà del client (associate al [!UICONTROL PID] del client) per il periodo di tempo selezionato. I client devono utilizzare questa opzione per effettuare l&#39;outbound delle qualifiche dei segmenti *in tempo reale* nelle destinazioni.
* **[!UICONTROL Platform]**: il file contiene utenti attivi che hanno almeno 1 interazione in tempo reale, che si tratti della sincronizzazione ID o della realizzazione delle caratteristiche, in qualsiasi punto tra tutte le proprietà dei client [!DNL Audience Manager] (associate a tutti i PID client) per il periodo di tempo selezionato. I client devono utilizzare questa opzione per effettuare l&#39;outbound delle qualifiche dei segmenti *total* nelle destinazioni.
* **[!UICONTROL Lifetime]**: il file contiene utenti attivi visualizzati ovunque in tutte le proprietà dei client [!DNL Audience Manager] dalla creazione della destinazione.
* **[!UICONTROL Sync Type Lookback Period]**: se si seleziona [!UICONTROL Customer] o [!UICONTROL Platform], selezionare un periodo di tempo. I file contengono utenti attivi per il periodo di tempo selezionato.
Quindi, selezionare il tipo di ordine. Indica la frequenza e l’ambito di ogni integrazione in uscita con i partner. Seleziona tra ordini incrementali e ordini completi.
* **[!UICONTROL Incremental Scheduled Run]**: a ogni esecuzione, [!DNL Audience Manager] invierà in uscita solo i nuovi utenti qualificati dall&#39;ordine in uscita precedente. Selezionare il periodo di tempo desiderato per l&#39;esecuzione dei processi di sincronizzazione incrementale da parte di [!DNL Audience Manager]. Ad esempio, puoi selezionare ogni 24 ore, ogni sette giorni, ogni 30 giorni o mai.

<!--
I removed {importance="high"} from note for Exp League rendering. -Bob
-->

>[!NOTE]
>
>Il primo ordine incrementale in assoluto equivale a un ordine completo perché nessun utente precedente è mai stato inviato alla destinazione.

* **[!UICONTROL Full Sync Scheduled Run]**: a ogni esecuzione, [!DNL Audience Manager] eseguirà l&#39;outbound di tutti gli utenti attivi dalla prima configurazione della destinazione. Selezionare la pianificazione desiderata che [!DNL Audience Manager] deve utilizzare per eseguire i processi di sincronizzazione completa. Ad esempio, puoi selezionare ogni 24 ore, ogni sette giorni, ogni 30 giorni o mai.

<!--
I removed {importance="high"} from note for Exp League rendering. -Bob
-->

>[!NOTE]
>
>È consigliabile utilizzare le sincronizzazioni incrementali con maggiore frequenza rispetto alle sincronizzazioni complete. Le sincronizzazioni incrementali inviano solo file che contengono nuove realizzazioni di caratteristiche o sincronizzazioni ID. Le sincronizzazioni complete inviano tutti i file, indipendentemente dal fatto che includano o meno nuove realizzazioni o sincronizzazioni ID. Utilizzare la configurazione [!UICONTROL Full Sync Scheduled Run] solo quando i client necessitano di una copia completa di tutti gli utenti per ridurre il volume di dati in uscita.

## Configurare origini dati {#configure-data-sources}

Per [!UICONTROL Bulk ID], [!UICONTROL Bulk Trait] o [!UICONTROL Bulk Segment] destinazioni, compila i campi seguenti. Queste impostazioni ti consentono di inviare tutti i dati (caratteristiche, segmenti o ID, in base al tipo selezionato) associati alle origini dati.

* **[!UICONTROL All Unrestricted First Party Data]**: selezionare per utilizzare tutte le origini dati di prime parti. Se si seleziona questa opzione, le opzioni [!UICONTROL Available Data Sources] sono disabilitate.
* **[!UICONTROL Available Data Sources]**: utilizzare le frecce per spostare le origini dati tra le caselle **[!UICONTROL Available Data Sources]** e **[!UICONTROL In File Data Sources]**.

## Salva e finalizza {#save-and-finalize}

Il pulsante **[!UICONTROL Save]** viene attivato dopo la compilazione di tutti i campi obbligatori. Fare clic su **[!UICONTROL Save]** per finalizzare il processo di creazione della destinazione.

## Elimina destinazioni società {#delete-company-destinations}

<!-- delete-company-destinations.xml -->

Per eliminare una destinazione:

1. Fare clic su **[!UICONTROL Companies]**, individuare e selezionare la società desiderata, quindi fare clic sulla scheda **[!UICONTROL Destinations]**.
1. Fare clic su ![](assets/icon_delete.png) nella colonna **[!UICONTROL Actions]** della destinazione desiderata.
1. Fare clic su **[!UICONTROL OK]** per confermare l&#39;eliminazione.

>[!NOTE]
>
>Non puoi eliminare una destinazione se ad essa sono mappati dei segmenti.
