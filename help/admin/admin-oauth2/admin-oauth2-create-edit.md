---
description: Utilizza la pagina Client OAuth2 per visualizzare un elenco di client OAuth2 nella configurazione di Audience Manager. È possibile modificare o eliminare i client esistenti o crearne di nuovi, purché siano stati assegnati i ruoli utente appropriati.
seo-description: Use the OAuth2 Clients page to view a list of OAuth2 clients in your Audience Manager configuration. You can edit or delete existing clients or create new clients, providing that you have the appropriate user roles assigned.
seo-title: OAuth2 Clients
title: Client OAuth2
uuid: 3e654053-fb2f-4d8f-a53c-b5c3b8dbdaaa
exl-id: 993eae04-02e8-4554-a6fe-cf599053bfc9
source-git-commit: 79415eba732c2a6d50f04124774664f788ccc78c
workflow-type: tm+mt
source-wordcount: '550'
ht-degree: 0%

---

# Client OAuth2 {#oauth-clients}

Utilizzare la pagina [!UICONTROL OAuth2 Clients] per visualizzare un elenco di [!UICONTROL OAuth2] client nella configurazione di [!DNL Audience Manager]. È possibile modificare o eliminare i client esistenti o crearne di nuovi, purché siano stati assegnati i ruoli utente appropriati.

## Panoramica {#overview}

<!-- c_oauth.xml -->

>[!NOTE]
>
>Assicurati che il cliente legga la documentazione di [OAuth2](https://experienceleague.adobe.com/docs/audience-manager/user-guide/api-and-sdk-code/rest-apis/aam-api-getting-started.html#oauth) nella Guida utente di Audience Manager.

[!DNL OAuth2] è uno standard aperto per l&#39;autorizzazione a fornire accesso delegato protetto alle risorse [!DNL Audience Manager] per conto di un proprietario di risorse.

![](assets/oauth.png)

Puoi ordinare ogni colonna in ordine crescente o decrescente facendo clic sull’intestazione della colonna desiderata.

Utilizzare la casella [!UICONTROL Search] o i controlli di impaginazione nella parte inferiore dell&#39;elenco per trovare il client desiderato.

## Creare o modificare un client OAuth2 {#create-edit-client}

<!-- t_create_edit_auth.xml -->

Utilizzare la pagina [!UICONTROL OAuth2 Clients] nello strumento Audience Manager [!UICONTROL Admin] per creare un nuovo client [!UICONTROL Oauth2] o per modificare un client esistente.

1. Per creare un nuovo client [!UICONTROL OAuth2], fare clic su **[!UICONTROL OAuth2 Clients]** > **[!UICONTROL Add OAuth2 Client]**. Per modificare un client [!UICONTROL OAuth2] esistente, fare clic sul client desiderato nella colonna **[!UICONTROL Client ID]**.
1. Specificare il nome desiderato per il client [!UICONTROL OAuth2]. Tieni presente che questo è un nome solo per il record.
1. Specificare l&#39;indirizzo di posta elettronica del client [!UICONTROL OAuth2]. Esiste un limite di un indirizzo e-mail.
1. Selezionare il partner desiderato dall&#39;elenco a discesa **[!UICONTROL Partner]**.
1. Nella casella **[!UICONTROL Client ID]**, specifica l&#39;ID desiderato. Questo è il valore utilizzato per l&#39;invio di [!DNL API] richieste. Il prefisso si compila automaticamente quando si inizia a digitare dopo aver scelto un [!UICONTROL Partner] dall&#39;elenco a discesa nel passaggio precedente. Il formato corretto è &lt; *`partner subdomain`*> - &lt; *`Audience Manager username`*>.
1. Selezionare o deselezionare la casella di controllo **[!UICONTROL Restrict to Partner Users]**, come desiderato. Se questa casella di controllo è selezionata, l&#39;utente deve essere un utente [!DNL Audience Manager] elencato per il partner selezionato. Come best practice, è consigliabile selezionare questa opzione.
1. Nella sezione **[!UICONTROL Scope]** selezionare o deselezionare le caselle di controllo **[!UICONTROL Read]** e **[!UICONTROL Write]**, come desiderato.
1. Nella sezione **[!UICONTROL Grant Type]** selezionare il mezzo desiderato per l&#39;autorizzazione. È consigliabile utilizzare le impostazioni predefinite delle opzioni [!UICONTROL Password] e [!UICONTROL Refresh-token].

   * **[!UICONTROL Implicit]**: se si seleziona questa opzione, la casella [!UICONTROL Redirect URI] è abilitata. L&#39;utente riceve un token di accesso automatico dopo l&#39;autenticazione e viene immediatamente inviato al reindirizzamento [!DNL URI].
   * **[!UICONTROL Authorization Code]**: se si seleziona questa opzione, la casella [!UICONTROL Redirect URI] è abilitata. L&#39;utente viene restituito al client dopo essere stato autenticato e quindi inviato al reindirizzamento [!DNL URI].
   * **[!UICONTROL Password]**: l&#39;utente è autenticato con una password inserita dall&#39;utente anziché con un tentativo di convalida automatica tramite un server di autorizzazione.
   * **[!UICONTROL Refresh_token]**: utilizzato per aggiornare un token di accesso scaduto per un periodo di tempo prolungato.

1. Nella casella **[!UICONTROL Redirect URI]**, specificare [!DNL URI] desiderato. Questa opzione è abilitata solo se si selezionano i tipi di concessione **[!UICONTROL Implicit]** e **[!UICONTROL Authorization_code]**. La casella **[!UICONTROL Redirect URI]** consente di specificare un valore separato da virgole di valori [!DNL URI] accettabili. Questo è [!DNL URI] a cui un utente di un client viene reindirizzato dopo aver approvato il client per l&#39;accesso [!DNL API].
1. Specifica il tempo di scadenza (in secondi) desiderato per l’accesso e la scadenza del token di aggiornamento.

   * **[!UICONTROL Access Token Expiration Time]**: numero di secondi di validità di un token di accesso dopo il rilascio. Può essere null per utilizzare il valore predefinito della piattaforma (12 ore). Inoltre, può essere -1 per indicare che il token di accesso non scade.
   * **[!UICONTROL Refresh Token Expiration Time]**: numero di secondi di validità di un token di aggiornamento dopo l&#39;emissione. Può essere null per utilizzare il valore predefinito della piattaforma (30 giorni).

1. Fare clic su **[!UICONTROL Save]**.

Per eliminare un client [!UICONTROL OAuth2], fare clic su **[!UICONTROL OAuth2 Clients]**, quindi su ![](assets/icon_delete.png) nella colonna **[!UICONTROL Actions]** per il client desiderato.

>[!MORELIKETHIS]
>
>* [Raccomandazioni e requisiti per l’utilizzo delle API](../admin-oauth2/aam-admin-api-requirements.md)
