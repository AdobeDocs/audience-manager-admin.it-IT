---
description: Aspetti di cui dovresti incoraggiare i tuoi clienti a essere consapevoli quando utilizzano le API di Audience Manager.
seo-description: Things you should encourage your clients to be aware of when they're working with the Audience Manager APIs.
seo-title: API Requirements and Recommendations
title: Raccomandazioni e requisiti per l’utilizzo delle API
uuid: eba9cf92-f0c8-4394-8532-0de9a2e7b103
exl-id: 24f90732-31a6-436d-862b-e6871d279c7a
TQID: https://experienceleague.adobe.com/mm5-TOwj8WckXoG4-E4wzuEF-1oBbxbBUvRLOoA--As
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
source-git-commit: d2bed13a6ac7d38ae79b65d492b6de0ca6b6d488
workflow-type: tm+mt
source-wordcount: 350
ht-degree: 0%

---

# Raccomandazioni e requisiti per l’utilizzo delle API {#api-requirements-and-recommendations}

Cose di cui dovresti incoraggiare i tuoi clienti a essere consapevoli quando lavorano con i [!DNL API] di Audience Manager.

## Requisiti {#requirements}

Quando si lavora con il codice [!DNL Audience Manager] [!DNL API], tenere presente quanto segue:

* **Parametri di richiesta:** Tutti i parametri di richiesta sono obbligatori se non diversamente specificato.
* Tipo di contenuto **[!DNL JSON]:** Specificare `content-type: application/json` *e* `accept: application/json` nel codice.

* **Richieste e risposte:** Inviare richieste come oggetto [!DNL JSON] formattato correttamente. [!DNL Audience Manager] risponde con [!DNL JSON] dati formattati. Le risposte del server possono contenere i dati richiesti, un codice di stato o entrambi.

* **Accesso:** Il consulente [!DNL Audience Manager] ti fornirà un ID client e una chiave che ti consente di effettuare [!DNL API] richieste.

* **Esempi di documentazione e codice:** Il testo in *corsivo* rappresenta una variabile fornita o trasmessa quando si creano o si ricevono dati [!DNL API]. Sostituisci il testo *in corsivo* con il tuo codice, i tuoi parametri o altre informazioni richieste.

## Recommendations: Creare un utente API generico {#recommendations}

È consigliabile creare un account utente tecnico separato per l&#39;utilizzo di Audience Manager [!DNL API]. Si tratta di un account generico non associato o associato a un utente specifico nell’organizzazione del cliente. Questo tipo di account utente [!DNL API] consente di eseguire 2 operazioni:

* Identifica il servizio che chiama [!DNL API] (ad esempio, chiamate da un&#39;app client che utilizzano [!DNL API] o che eseguono modifiche in blocco).
* Fornisci accesso ininterrotto a [!DNL API]. Un account associato a uno specifico dipendente può essere cancellato quando lascia l&#39;azienda. Questo impedirà ai tuoi clienti di utilizzare il codice [!DNL API] disponibile. Un account generico non legato a un dipendente specifico aiuta a evitare questo problema.

Come esempio o caso d&#39;uso per questo tipo di account, supponiamo che i tuoi clienti vogliano cambiare molti segmenti contemporaneamente con i [Strumenti di gestione in blocco](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/bulk-management-tools/bulk-management-intro.html?lang=en). Per eseguire questa operazione, è necessario l&#39;accesso [!DNL API]. Anziché aggiungere le autorizzazioni a un utente specifico, creare un account utente [!DNL API] non specifico con credenziali, chiave e segreto appropriati per effettuare chiamate a [!DNL API]. Questa funzione è utile anche se i client sviluppano applicazioni proprie che utilizzano [!DNL Audience Manager] [!DNL API].
