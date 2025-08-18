---
description: Per evitare l’onboarding accidentale di file e dati nelle origini dati di destinazione di proprietà di altri partner o clienti, Audience Manager ha aggiunto un requisito di mappatura tra l’ID partner (PID) e le origini dati di proprietà di altri partner.
title: Gestire l’accesso all’onboarding per i dati di seconde parti
exl-id: 03bec978-dd31-41cc-a3aa-d67fbb98963c
source-git-commit: cc04863272005964cfbf1bb2319cc0dd86863680
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 0%

---

# Gestire l’accesso all’onboarding per i dati di seconde parti {#manage-onboarding-access-for-second-party-data}

>[!IMPORTANT]
>
> Il pubblico per questa pagina è composto da dipendenti interni ad Adobe. Se sei un cliente di Audience Manager che richiede una mappatura di origine dati di seconde parti come descritto in questa pagina, contatta l’Assistenza clienti o il tuo Technical Account Manager.
> &#x200B;> Non è necessario per richiedere la mappatura per le relazioni di condivisione dei dati esistenti. Inoltre, la mappatura non è necessaria quando si inseriscono dati in origini dati di destinazione che appartengono al tuo PID.

Per evitare l’onboarding accidentale di file e dati nelle origini dati di destinazione di proprietà di altri partner, Audience Manager ha aggiunto un requisito di mappatura tra l’ID partner (PID) e le origini dati (DPID) di proprietà di altri partner. Ulteriori informazioni su PID e DPID sono disponibili nell&#39;[indice degli ID di Audience Manager](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/ids-in-aam.html?lang=it).

Ai fini della condivisione dei dati di seconde parti, se un partner o un cliente di Audience Manager desidera acquisire i file in un’origine dati di destinazione di cui non è proprietario, deve richiedere la mappatura tra il proprio ID partner (PID) e tale origine dati specifica (DPID). Se manca la mappatura, i file non verranno elaborati dal processo di dati in entrata e i dati non verranno inseriti in Audience Manager.

Per creare tale mappatura, invia un ticket Jira al team di progettazione di Audience Manager. Visualizza un ticket Jira di esempio [qui](https://jira.corp.adobe.com/browse/AAM-60353). Non è necessario richiedere la creazione di mappature per le relazioni di condivisione dei dati esistenti.
