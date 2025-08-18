---
description: Utilizzare la pagina Server dello strumento di amministrazione di Audience Manager per creare un nuovo server FTP o per modificare un server esistente.
seo-description: Use the Servers page in the Audience Manager Admin tool to create a new FTP server or to edit an existing server.
seo-title: Create or Edit an FTP Server
title: Creare o modificare un server FTP
uuid: 9273abb2-963d-4d83-bf5a-b3817f0b90e6
exl-id: 9eae4ecf-ccde-483a-ae53-1cbac033d8d6
source-git-commit: 8af040e49b881302315e0b66baa73db47c5eee28
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 1%

---

# Creare o modificare un server FTP {#create-or-edit-an-ftp-server}

Utilizzare la pagina [!UICONTROL Servers] dello strumento di amministrazione di Audience Manager per creare un nuovo server FTP o per modificare un server esistente.

>[!NOTE]
>
>È necessario disporre del ruolo [!UICONTROL DEXADMIN] per creare nuovi server o modificare quelli esistenti.

1. Per creare un nuovo server, scegliere **[!UICONTROL Servers]** > **[!UICONTROL Create Server]**. Per modificare un server esistente, fare clic sul server desiderato nella colonna **[!UICONTROL Label]**.
1. Specificare l&#39;etichetta desiderata per il server.
1. Dall&#39;elenco a discesa **[!UICONTROL Protocol]**, selezionare il protocollo desiderato: **FTP**.

   >[!NOTE]
   >
   >Come best practice, si consiglia di utilizzare [!DNL Amazon S3] come metodo per ottenere file da e consegnarli ai partner. [!DNL Amazon S3] fornisce una semplice interfaccia per i servizi Web che può essere utilizzata per archiviare e recuperare qualsiasi quantità di dati, in qualsiasi momento, da qualsiasi punto del Web. Per ulteriori informazioni, vedere [Informazioni su Amazon S3](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/amazon-s3.html) nella *Guida utente di Audience Manager*.

1. Compila i campi:

   * **[!UICONTROL Type]:** Selezionare il tipo di crittografia desiderato: **[!UICONTROL SFTP]** o **[!UICONTROL FTPs/TLS]**.
   * **[!UICONTROL Domain]:** Specificare il dominio (host) desiderato per il server.
   * **[!UICONTROL Port]:** Specificare la porta desiderata per il server. Viene visualizzata la porta predefinita per ogni tipo di crittografia. Se necessario, è possibile modificare la porta predefinita.
   * **[!UICONTROL Remote Path]:** Specificare il percorso remoto desiderato per il server. Se lasci vuoto questo campo, Audience Manager inserisce i file nella directory predefinita.
   * **[!UICONTROL .tmp File Rename on Completion]:** Abilitare questa opzione per rinominare il file `.tmp` al completamento.
   * **[!UICONTROL Filename Suffix]:** Specificare il testo che si desidera aggiungere per trasferire i file.
   * **[!UICONTROL Moved to When Finished]:** Specificare il percorso del percorso in cui si desidera spostare il file di trasferimento al completamento.
   * **[!UICONTROL Authentication]:** Specificare il metodo di autenticazione server desiderato: **[!UICONTROL Username/Password]** o **[!UICONTROL SSH Key]**.

   >[!NOTE]
   >
   >Ricorda di aggiungere il nostro [!DNL FTP] [!DNL IP] in uscita all&#39;elenco degli IP consentiti: **54.204.116.43**.

1. Per l&#39;autenticazione **[!UICONTROL SSH Key]**:
   >[!NOTE]
   >
   >Durante la configurazione dell’autenticazione della chiave SSH, assicurati di generare sempre le chiavi pubbliche e private solo in formato OpenSSH.
   1. Generare la coppia di chiavi pubblica/privata da qualsiasi computer [!DNL Linux] o [!DNL Mac].
   1. Assegnare la **chiave pubblica** al client per l&#39;aggiornamento nel server [!DNL SFTP]. Devono includere tutto il testo della chiave pubblica sul server, inclusi `-----BEGIN RSA PRIVATE KEY-----` e `-----END RSA PRIVATE KEY-----`. In cambio, devono fornire il nome utente con cui stanno installando la chiave.
   1. Aggiorna il campo del nome utente con quello fornito dal client e il campo della chiave con la **chiave privata**.
1. Fare clic su **[!UICONTROL Create]** se si sta creando un nuovo server oppure fare clic su **[!UICONTROL Update]** se si sta modificando un server esistente.
