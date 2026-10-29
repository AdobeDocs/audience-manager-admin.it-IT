---
description: L’ambiente beta è destinato al test delle implementazioni di Audience Manager. Le modifiche apportate nella versione beta non influiscono sui dati di produzione. L’ambiente beta di Audience Manager è una versione standalone dell’ambiente di produzione su scala ridotta. Tutti i dati che desideri verificare devono essere immessi e raccolti in questo ambiente.
seo-description: The beta environment is for testing Audience Manager implementations. Changes made in beta do not affect production data. The Audience Manager beta environment is a smaller-scale, standalone version of the production environment. All the data that you want to test must be entered and collected in this environment.
seo-title: Beta Environment
solution: Audience Manager
title: Ambiente Beta
uuid: 6a253f4e-96e7-4395-a783-a8eb213b7daf
exl-id: 78d5a1ff-c016-4366-ba34-9814a0d92067
TQID: https://experienceleague.adobe.com/Y6hON41v53cSXtuTYMW8UMgimwyewWHvfcBvMYDnBa4
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
    internal-label: Implementation
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
source-git-commit: d2bed13a6ac7d38ae79b65d492b6de0ca6b6d488
workflow-type: tm+mt
source-wordcount: 366
ht-degree: 1%

---

# Ambiente Beta {#beta-environment}

L’ambiente beta è destinato al test delle implementazioni di Audience Manager. Le modifiche apportate nella versione beta non influiscono sui dati di produzione. L’ambiente beta di Audience Manager è una versione standalone dell’ambiente di produzione su scala ridotta. Tutti i dati che desideri verificare devono essere immessi e raccolti in questo ambiente.

## Panoramica {#overview}

<!-- beta_environment_admin.xml -->

| Servizio | URL/Nome host | Passaggi per il provisioning |
|--- |--- |--- |
| S3 | | Consulta [Provisioning dei bucket di Amazon S3](admin-beta-environment.md#provision-s3-buckets). |
| DCS | https&colon;//dcs-beta.demdex.net/... | Non sono necessari ulteriori passi da parte nostra. Vedere [Accesso al DCS nell&#39;ambiente Beta](admin-beta-environment.md#access-dcs-beta-environment). |
| UI | https&colon;//bank-beta.demdex.com | I dati vengono copiati dalla produzione all’ambiente beta su base mensile. Le credenziali di produzione sono valide per la versione beta. |
| API | http&colon;//api-beta.demdex.com/... | I dati vengono copiati dalla produzione all’ambiente beta su base mensile. Le credenziali di produzione sono valide per la versione beta. |

## Provisioning dei bucket di Amazon S3 {#provision-s3-buckets}

>[!NOTE]
>
>Non utilizzeremo più [!DNL FTP/SFTP]. Inoltre, tieni presente che i trasferimenti di dati in uscita non funzionano per l’ambiente beta.

Per eseguire il provisioning di [!DNL S3] bucket per i dati in entrata:

1. Utilizza la funzionalità [**Guida TechOps per richieste SKMS**](https://skms.adobe.com/).
1. Vai a **[!UICONTROL Request TechOps Help]** nella barra di navigazione a sinistra.
1. In **[!UICONTROL Request Search]**, digitare Audience Manager nel campo di ricerca.
1. Scorri verso il basso nei risultati della ricerca e fai clic su **Audience Manager - S3 in entrata / In uscita**.
1. Compila i campi nella finestra di provisioning e specifica **Ambiente sandbox** nel campo **[!UICONTROL Environment]**.

>[!NOTE]
>
>Si sconsiglia l&#39;utilizzo di [!DNL FTP/SFTP] e si incoraggia l&#39;utilizzo di [!UICONTROL Amazon S3]. I motivi per cui si incoraggia l&#39;utilizzo di [!UICONTROL Amazon S3] sono elencati in [Amazon S3:About](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/amazon-s3.html?lang=it).

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
