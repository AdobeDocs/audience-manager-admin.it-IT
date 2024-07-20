---
description: L’ambiente beta è destinato al test delle implementazioni Audience Manager. Le modifiche apportate nella versione beta non influiscono sui dati di produzione. L’ambiente beta di Audience Manager è una versione standalone dell’ambiente di produzione su scala ridotta. Tutti i dati che desideri verificare devono essere immessi e raccolti in questo ambiente.
seo-description: The beta environment is for testing Audience Manager implementations. Changes made in beta do not affect production data. The Audience Manager beta environment is a smaller-scale, standalone version of the production environment. All the data that you want to test must be entered and collected in this environment.
seo-title: Beta Environment
solution: Audience Manager
title: Ambiente Beta
uuid: 6a253f4e-96e7-4395-a783-a8eb213b7daf
exl-id: 78d5a1ff-c016-4366-ba34-9814a0d92067
source-git-commit: 79415eba732c2a6d50f04124774664f788ccc78c
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 1%

---

# Ambiente Beta {#beta-environment}

L’ambiente beta è destinato al test delle implementazioni Audience Manager. Le modifiche apportate nella versione beta non influiscono sui dati di produzione. L’ambiente beta di Audience Manager è una versione standalone dell’ambiente di produzione su scala ridotta. Tutti i dati che desideri verificare devono essere immessi e raccolti in questo ambiente.

## Panoramica {#overview}

<!-- beta_environment_admin.xml -->

| Servizio | URL/Nome host | Passaggi per il provisioning |
|--- |--- |--- |
| S3 | | Consulta [Provisioning dei bucket di Amazon S3](admin-beta-environment.md#provision-s3-buckets). |
| DCS | https&amp;colon;//dcs-beta.demdex.net/... | Non sono necessari ulteriori passi da parte nostra. Vedere [Accesso al DCS nell&#39;ambiente Beta](admin-beta-environment.md#access-dcs-beta-environment). |
| UI | https&amp;colon;//bank-beta.demdex.com | I dati vengono copiati dalla produzione all’ambiente beta su base mensile. Le credenziali di produzione sono valide per la versione beta. |
| API | https&amp;colon;//api-beta.demdex.com/... | I dati vengono copiati dalla produzione all’ambiente beta su base mensile. Le credenziali di produzione sono valide per la versione beta. |

## Provisioning dei bucket di Amazon S3 {#provision-s3-buckets}

>[!NOTE]
>
>Non utilizzeremo più [!DNL FTP/SFTP]. Inoltre, tieni presente che i trasferimenti di dati in uscita non funzionano per l’ambiente beta.

Per eseguire il provisioning di [!DNL S3] bucket per i dati in entrata:

1. Utilizza la funzionalità [**Guida TechOps per richieste SKMS**](https://skms.adobe.com/).
1. Vai a **[!UICONTROL Request TechOps Help]** nella barra di navigazione a sinistra.
1. In **[!UICONTROL Request Search]**, digitare l&#39;Audience Manager nel campo di ricerca.
1. Scorri verso il basso nei risultati della ricerca e fai clic su **Audience Manager - Provisioning account in entrata/in uscita S3**.
1. Compila i campi nella finestra di provisioning e specifica **Ambiente sandbox** nel campo **[!UICONTROL Environment]**.

>[!NOTE]
>
>Si sconsiglia l&#39;utilizzo di [!DNL FTP/SFTP] e si incoraggia l&#39;utilizzo di [!UICONTROL Amazon S3]. I motivi per cui si incoraggia l&#39;utilizzo di [!UICONTROL Amazon S3] sono elencati in [Amazon S3:About](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/amazon-s3.html).

## Accedere al DCS nell’ambiente Beta {#access-dcs-beta-environment}

Per accedere a [!UICONTROL DCS] nell&#39;ambiente beta:

1. Effettuare una chiamata [!UICONTROL DCS] utilizzando il [!DNL curl] [comando](https://curl.haxx.se/docs/manpage.html). [!DNL Curl] è uno strumento per trasferire dati da o verso un server, utilizzando uno dei numerosi protocolli supportati.

   Esempio: `curl -v https://dcs-beta.demdex.net/event`

1. Verificare che la richiesta sia stata servita dalla versione beta [!UICONTROL DCS] cercando &quot;[!DNL sandbox]&quot; nell&#39;intestazione di risposta [!UICONTROL DCS].

   Ad esempio:

   ```
   curl -v http://dcs-beta.demdex.net/?event
   [...]
   < DCS: va6-sandbox-dcs-3.sandbox.demdex.com <release_number>
   [...]
   ```

<!--
1. Determine the load balancer's endpoint IP addresses.

   Run the `dig` [command](https://en.wikipedia.org/wiki/Dig_(command)) to determine the IP address of the nearest load balancer. The `dig` command queries the Domain Name System and returns the name and IP addresses of the Audience Manager [!UICONTROL Data Collection Servers (DCS)].

   ```
   dig dcs-beta.demdex.net
   ...
   dcs-sandbox-1754093861.us-east-1.elb.amazonaws.com. 60 IN A 52.87.15.51
   dcs-sandbox-1754093861.us-east-1.elb.amazonaws.com. 60 IN A 50.16.150.8
   dcs-sandbox-1754093861.us-east-1.elb.amazonaws.com. 60 IN A 52.2.228.100
   ```

1. Using one of the addresses in the above table, add a static DNS entry in the [!DNL `/etc/hosts`] file.

   On Windows, modify [!DNL `c:\WINDOWS\system32\drivers\etc\hosts`].

   For example:

[!DNL `52.87.15.51 samplepartner.demdex.net`]

   >[!NOTE]
   >
   >The addresses change occasionally, so you must keep your [!DNL /etc/hosts] file up to date.

   Additionally, if you need to set up ID synchronization, you must add a similar entry for [!DNL dpm.demdex.net.]

[!DNL `52.87.15.51 dpm.demdex.net`] [!DNL]. 

1. Make a [!UICONTROL DCS] call, using the `curl` [command](https://curl.haxx.se/docs/manpage.html). Curl is a tool to transfer data from or to a server, using one of many supported protocols.

   For example:

[!DNL `https://<domain>/event?product=camera`] 

1. Verify that your request was served by the beta [!UICONTROL DCS] by looking for "sandbox" in the [!UICONTROL DCS] response header.

   For example:

   ```
   curl -v https://dcs-beta.demdex.net/?event
   [...]
   < DCS: va6-sandbox-dcs-3.sandbox.demdex.com <release_number>
   [...]
   ```
-->
