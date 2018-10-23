---
UID: NS:wdm._TRANSACTIONMANAGER_RECOVERY_INFORMATION
title: "_TRANSACTIONMANAGER_RECOVERY_INFORMATION"
author: windows-driver-content
description: The TRANSACTIONMANAGER_RECOVERY_INFORMATION structure contains information about a transaction manager object.
old-location: kernel\transactionmanager_recovery_information.htm
tech.root: kernel
ms.assetid: 76701df3-8e7d-43fa-8caf-6cbf89504aad
ms.date: 04/30/2018
ms.keywords: "*PTRANSACTIONMANAGER_RECOVERY_INFORMATION, PTRANSACTIONMANAGER_RECOVERY_INFORMATION, PTRANSACTIONMANAGER_RECOVERY_INFORMATION structure pointer [Kernel-Mode Driver Architecture], TRANSACTIONMANAGER_RECOVERY_INFORMATION, TRANSACTIONMANAGER_RECOVERY_INFORMATION structure [Kernel-Mode Driver Architecture], _TRANSACTIONMANAGER_RECOVERY_INFORMATION, kernel.transactionmanager_recovery_information, ktm_ref_9efce7e2-3965-4659-8659-4f8262aad962.xml, wdm/PTRANSACTIONMANAGER_RECOVERY_INFORMATION, wdm/TRANSACTIONMANAGER_RECOVERY_INFORMATION"
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntifs.h
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdm.h
api_name:
-	TRANSACTIONMANAGER_RECOVERY_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: TRANSACTIONMANAGER_RECOVERY_INFORMATION, *PTRANSACTIONMANAGER_RECOVERY_INFORMATION
---

# _TRANSACTIONMANAGER_RECOVERY_INFORMATION structure


## -description


The TRANSACTIONMANAGER_RECOVERY_INFORMATION structure contains information about a <a href="https://msdn.microsoft.com/af53cda4-e2ab-47df-9311-a4da2a2ee08d">transaction manager object</a>.


## -struct-fields




### -field LastRecoveredLsn

The last <a href="https://msdn.microsoft.com/4637fa0c-2f19-4f0c-bf13-f4ccac2e7284">log sequence number</a> of the last log record that KTM obtained from <a href="https://msdn.microsoft.com/a9685648-b08c-48ca-b020-e683068f2ea2">CLFS</a> during the most recent recovery operation.


## -remarks



The TRANSACTIONMANAGER_RECOVERY_INFORMATION structure is used with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567058">ZwQueryInformationTransactionManager</a> routine.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564762">TRANSACTIONMANAGER_INFORMATION_CLASS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567058">ZwQueryInformationTransactionManager</a>
 

 

