---
UID: NS:wdm._TRANSACTIONMANAGER_LOG_INFORMATION
title: "_TRANSACTIONMANAGER_LOG_INFORMATION"
author: windows-driver-content
description: The TRANSACTIONMANAGER_LOG_INFORMATION structure contains information about a transaction manager object.
old-location: kernel\transactionmanager_log_information.htm
old-project: kernel
ms.assetid: 7d0da54d-54a2-4440-910f-d99716660506
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , *, *PTRANSACTIONMANAGER_LOG_INFORMATION, ,, A, C, E, F, G, I, L, M, N, O, P, PTRANSACTIONMANAGER_LOG_INFORMATION, PTRANSACTIONMANAGER_LOG_INFORMATION structure pointer [Kernel-Mode Driver Architecture], R, S, T, TRANSACTIONMANAGER_LOG_INFORMATION, TRANSACTIONMANAGER_LOG_INFORMATION structure [Kernel-Mode Driver Architecture], _, _TRANSACTIONMANAGER_LOG_INFORMATION, kernel.transactionmanager_log_information, ktm_ref_3cdc0767-5078-43dc-8a25-3e90a4a1483a.xml, wdm/PTRANSACTIONMANAGER_LOG_INFORMATION, wdm/TRANSACTIONMANAGER_LOG_INFORMATION"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wdm.h
apiname:
-	TRANSACTIONMANAGER_LOG_INFORMATION
product: Windows
targetos: Windows
req.typenames: TRANSACTIONMANAGER_LOG_INFORMATION, *PTRANSACTIONMANAGER_LOG_INFORMATION
req.product: Windows 10 or later.
---

# _TRANSACTIONMANAGER_LOG_INFORMATION structure


## -description


The <b>TRANSACTIONMANAGER_LOG_INFORMATION</b> structure contains information about a <a href="https://msdn.microsoft.com/af53cda4-e2ab-47df-9311-a4da2a2ee08d">transaction manager object</a>.


## -syntax


````
typedef struct _TRANSACTIONMANAGER_LOG_INFORMATION {
  GUID LogIdentity;
} TRANSACTIONMANAGER_LOG_INFORMATION, *PTRANSACTIONMANAGER_LOG_INFORMATION;
````


## -struct-fields




### -field LogIdentity

A GUID that KTM uses to identify restart records in a transaction manager object's log stream. For more information about restart records, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff566409">Writing Restart Records to a CLFS Stream</a>.


## -remarks



The <b>TRANSACTIONMANAGER_LOG_INFORMATION</b> structure is used with the <a href="..\wdm\nf-wdm-zwqueryinformationtransactionmanager.md">ZwQueryInformationTransactionManager</a> routine.




## -see-also

<a href="..\wdm\nf-wdm-zwqueryinformationtransactionmanager.md">ZwQueryInformationTransactionManager</a>



<a href="..\wdm\ne-wdm-_transactionmanager_information_class.md">TRANSACTIONMANAGER_INFORMATION_CLASS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20TRANSACTIONMANAGER_LOG_INFORMATION structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

