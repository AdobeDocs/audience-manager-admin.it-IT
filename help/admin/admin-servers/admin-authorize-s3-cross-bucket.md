---
description: Alcuni clienti potrebbero non voler fornire al proprio Amazon Simple Storage Service (Amazon S3) l’accesso o le chiavi segrete ad Adobe per autorizzare il caricamento dei dati di destinazione nei propri bucket.
seo-description: Some customers may not want to provide their Amazon Simple Storage Service (Amazon S3) access or secret keys to Adobe to authorize destination data upload to their buckets.
seo-title: How To  Authorize Cross-Account Amazon S3 Bucket Access for Batch Destinations
title: Autorizzare l’accesso multiaccount al bucket Amazon S3 per le destinazioni batch
uuid: da2bcbda-a765-437a-bfe9-4355383a4730
exl-id: f3b97c31-714f-4841-884b-bc507267a932
TQID: https://experienceleague.adobe.com/KFc06xetyatq5n-F8Uu-6nmepyjbFyQ3nYB-vXkdPdE
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: c814092e-2730-45e8-a12d-e084529f52cb
source-git-commit: d2bed13a6ac7d38ae79b65d492b6de0ca6b6d488
workflow-type: tm+mt
source-wordcount: 168
ht-degree: 0%

---

# Autorizzare l’accesso multiaccount al bucket Amazon S3 per le destinazioni batch{#authorize-cross-account-bucket-batch}

Alcuni clienti potrebbero non voler fornire l&#39;accesso [!DNL Amazon S3] o le chiavi segrete ad Adobe per autorizzare il caricamento dei dati di destinazione nei propri bucket.

Un&#39;alternativa che possiamo offrire ai nostri clienti è [!UICONTROL Cross-Account Bucket Permissions] in [!DNL Amazon S3]. Questo processo è descritto nella [documentazione di AWS](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-walkthroughs-managing-access-example2.html). Per abilitare questa alternativa in Audience Manager, effettua le seguenti operazioni:

1. Vai a **[!UICONTROL Servers]** e seleziona **[!UICONTROL Create Server]**.
1. Selezionare **[!UICONTROL S3]** nella maschera a discesa **[!UICONTROL Protocol/Credentials]**.
1. Selezionare l&#39;opzione **[!UICONTROL Use Internal Adobe Key]**.
1. Usa il nome dell&#39;account e del bucket del cliente in [!DNL Amazon S3].
1. Assicurati che il tuo cliente inserisca in white list l&#39;account [!DNL Amazon S3] `975822914085` nel suo bucket [!DNL S3].

>[!NOTE]
>
>Il nostro editore in uscita garantisce che il livello di autorizzazione `bucket-owner-full-control` sia impostato sui dati caricati, in modo che il cliente possa essere proprietario di tali dati.
