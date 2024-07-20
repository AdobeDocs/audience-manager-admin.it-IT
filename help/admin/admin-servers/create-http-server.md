---
description: Utilizzare la pagina Server dello strumento di amministrazione Audience Manager per creare un nuovo server HTTP o per modificare un server esistente.
seo-description: Use the Servers page in the Audience Manager Admin tool to create a new HTTP server or to edit an existing server.
seo-title: Create or Edit an HTTP Server
title: Creare o modificare un server HTTP
uuid: 1ef0e751-e239-4dc6-a4f6-73cc05686807
exl-id: 8b3dfb1e-2dee-4a05-835e-3c32643336bc
source-git-commit: c7c5da62b32f6a56152e1c09a965facfc601cade
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 2%

---

# Creare o modificare un server HTTP {#create-or-edit-an-http-server}

Utilizzare la pagina [!UICONTROL Servers] nello strumento di amministrazione Audience Manager per creare un nuovo server HTTP o per modificare un server esistente.

>[!NOTE]
>
>È necessario disporre del ruolo [!UICONTROL DEXADMIN] per creare nuovi server o modificare quelli esistenti.

1. Per creare un nuovo server, passare a **[!UICONTROL Servers]** > **[!UICONTROL Create Server]**. Per modificare un server esistente, fare clic sul server desiderato nella colonna **[!UICONTROL Label]**.
1. Specificare l&#39;etichetta desiderata per il server.
1. Dall&#39;elenco a discesa **[!UICONTROL Protocol]**, selezionare il protocollo desiderato: [!DNL HTTP].
1. Compila i campi:

   * **[!UICONTROL Domain]:** Specificare il dominio (host) desiderato per il server.
   * **[!UICONTROL Port]:** Specificare la porta desiderata per il server. Viene visualizzata la porta predefinita per ogni tipo di crittografia. Se necessario, è possibile modificare la porta predefinita
   * **[!UICONTROL Maximum Users Per Request]:** Specificare il numero massimo di utenti per richiesta consentito per questo server.
   * **[!UICONTROL URL Prefix]:** Specificare il prefisso [!DNL URL] da utilizzare per questo server.
   * **[!UICONTROL Authentication URL]:** Specificare [!UICONTROL Authentication URL] per questo server `HTTP`.
   * **[!UICONTROL Authentication]:** Specificare il metodo di autenticazione desiderato: **[!UICONTROL None]**, **[!UICONTROL Username/Password]** o **[!UICONTROL SSH Key]**.
   * **[!UICONTROL HTTP Signature Header]:** Il nome dell&#39;intestazione [!DNL HTTP], fornito dal cliente, che contiene la chiave di firma [!DNL HTTP]. Il valore predefinito è [!UICONTROL X-Signature], come illustrato nell&#39;esempio seguente:

     ```
     * Connected to partner.website.com (127.0.0.1) port 80 (#0)
     > POST /webpage HTTP/1.1
     > Host: partner.host.com
     > Accept: */*
     > Content-Type: application/json
     > Content-Length: 20
     > X-Signature: wxa2ByMWhhP328EvHQsVlOD5jTc=
     POST message content
     ```

   * **[!UICONTROL HTTP Signature Key]:** Chiave utilizzata per firmare la richiesta [!DNL HTTP], fornita dal cliente.
   * **[!UICONTROL Show Signature Key]:** Attiva o disattiva la visualizzazione della firma nel browser.
   * **[!UICONTROL HTTP Signature Encryption Method]:** Specificare il metodo utilizzato per crittografare la firma. Usa [!UICONTROL SHA1] a meno che il cliente non preferisca diversamente.

   >[!NOTE]
   >
   >Se desideri abilitare l&#39;autenticazione [OAuth 2.0 per i trasferimenti di dati in tempo reale](https://experienceleague.adobe.com/docs/audience-manager/user-guide/implementation-integration-guides/receiving-audience-data/real-time-outbound-transfers/oauth-in-outbound-transfers.html?lang=en) per un partner, compila i campi come nella tabella seguente. I campi in *corsivo* devono essere compilati esattamente come nella tabella.

   | Nome | Valore |
   |---|---|
   | [!UICONTROL Label] | [!UICONTROL Server with OAuth 2.0 enabled] |
   | [!UICONTROL Protocol] | [!UICONTROL HTTP] |
   | [!UICONTROL Domain] | [!UICONTROL api.partner.com] |
   | [!UICONTROL Port] | [!UICONTROL 443] |
   | [!UICONTROL Maximum Users per Request] | [!UICONTROL 10] |
   | [!UICONTROL URL Prefix] | [!UICONTROL /segments/aam] |
   | [!UICONTROL Authentication URL] | [!UICONTROL api.partner.com/oauth2/token] |
   | [!UICONTROL Authentication] | [!UICONTROL Username/Password] |
   | [!UICONTROL Username] | [!UICONTROL *Autorizzazione*] |
   | [!UICONTROL Password] | your_password_here |
   | [!UICONTROL HTTP Signature Header] | [!UICONTROL Leave this field blank] |
   | [!UICONTROL HTTP Signature Key] | [!UICONTROL Leave this field blank] |
   | [!UICONTROL HTTP Signature Encryption Method] | [!UICONTROL None] |

1. Fare clic su **[!UICONTROL Create]** se si sta creando un nuovo server oppure fare clic su **[!UICONTROL Update]** se si sta modificando un server esistente.
