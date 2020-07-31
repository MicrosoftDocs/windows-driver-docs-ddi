---
UID: NS:wdm._TRANSACTIONMANAGER_LOG_INFORMATION
title: _TRANSACTIONMANAGER_LOG_INFORMATION (wdm.h)
description: The TRANSACTIONMANAGER_LOG_INFORMATION structure contains information about a transaction manager object.
old-location: kernel\transactionmanager_log_information.htm
tech.root: kernel
ms.assetid: 7d0da54d-54a2-4440-910f-d99716660506
ms.date: 04/30/2018
keywords: ["_TRANSACTIONMANAGER_LOG_INFORMATION structure"]
ms.keywords: "*PTRANSACTIONMANAGER_LOG_INFORMATION, PTRANSACTIONMANAGER_LOG_INFORMATION, PTRANSACTIONMANAGER_LOG_INFORMATION structure pointer [Kernel-Mode Driver Architecture], TRANSACTIONMANAGER_LOG_INFORMATION, TRANSACTIONMANAGER_LOG_INFORMATION structure [Kernel-Mode Driver Architecture], _TRANSACTIONMANAGER_LOG_INFORMATION, kernel.transactionmanager_log_information, ktm_ref_3cdc0767-5078-43dc-8a25-3e90a4a1483a.xml, wdm/PTRANSACTIONMANAGER_LOG_INFORMATION, wdm/TRANSACTIONMANAGER_LOG_INFORMATION"
f1_keywords:
 - "wdm/TRANSACTIONMANAGER_LOG_INFORMATION"
 - "TRANSACTIONMANAGER_LOG_INFORMATION"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later operating system versions.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Wdm.h
api_name:
- TRANSACTIONMANAGER_LOG_INFORMATION
targetos: Windows
req.typenames: TRANSACTIONMANAGER_LOG_INFORMATION, *PTRANSACTIONMANAGER_LOG_INFORMATION
---

# _TRANSACTIONMANAGER_LOG_INFORMATION structure


## -description


The <b>TRANSACTIONMANAGER_LOG_INFORMATION</b> structure contains information about a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/transaction-manager-objects">transaction manager object</a>.


## -struct-fields




### -field LogIdentity

A GUID that KTM uses to identify restart records in a transaction manager object's log stream. For more information about restart records, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/writing-restart-records-to-a-clfs-stream">Writing Restart Records to a CLFS Stream</a>.


## -remarks



The <b>TRANSACTIONMANAGER_LOG_INFORMATION</b> structure is used with the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntqueryinformationtransactionmanager">ZwQueryInformationTransactionManager</a> routine.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_transactionmanager_information_class">TRANSACTIONMANAGER_INFORMATION_CLASS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntqueryinformationtransactionmanager">ZwQueryInformationTransactionManager</a>
 

 

