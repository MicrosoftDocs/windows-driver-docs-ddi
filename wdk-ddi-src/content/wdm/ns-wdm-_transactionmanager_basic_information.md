---
UID: NS:wdm._TRANSACTIONMANAGER_BASIC_INFORMATION
title: "_TRANSACTIONMANAGER_BASIC_INFORMATION"
author: windows-driver-content
description: The TRANSACTIONMANAGER_BASIC_INFORMATION structure contains information about a transaction manager object.
old-location: kernel\transactionmanager_basic_information.htm
tech.root: kernel
ms.assetid: bffa1bd2-143c-4d32-a886-0a2e82320dc8
ms.date: 04/30/2018
ms.keywords: "*PTRANSACTIONMANAGER_BASIC_INFORMATION, PTRANSACTIONMANAGER_BASIC_INFORMATION, PTRANSACTIONMANAGER_BASIC_INFORMATION structure pointer [Kernel-Mode Driver Architecture], TRANSACTIONMANAGER_BASIC_INFORMATION, TRANSACTIONMANAGER_BASIC_INFORMATION structure [Kernel-Mode Driver Architecture], _TRANSACTIONMANAGER_BASIC_INFORMATION, kernel.transactionmanager_basic_information, ktm_ref_0b404d6e-efa9-4f37-a14f-4e8fcdc2c6e5.xml, wdm/PTRANSACTIONMANAGER_BASIC_INFORMATION, wdm/TRANSACTIONMANAGER_BASIC_INFORMATION"
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	TRANSACTIONMANAGER_BASIC_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: TRANSACTIONMANAGER_BASIC_INFORMATION, *PTRANSACTIONMANAGER_BASIC_INFORMATION
---

# _TRANSACTIONMANAGER_BASIC_INFORMATION structure


## -description


The <b>TRANSACTIONMANAGER_BASIC_INFORMATION</b> structure contains information about a <a href="https://msdn.microsoft.com/af53cda4-e2ab-47df-9311-a4da2a2ee08d">transaction manager object</a>.


## -struct-fields




### -field TmIdentity

A GUID that KTM has assigned to a transaction manager object.


### -field VirtualClock

The <a href="https://msdn.microsoft.com/de01b0f1-86b1-4e7d-af22-84dbbe3a3f83">virtual clock value</a> that is currently associated with a transaction manager object.


## -remarks



The <b>TRANSACTIONMANAGER_BASIC_INFORMATION</b> structure is used with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567058">ZwQueryInformationTransactionManager</a> routine.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564762">TRANSACTIONMANAGER_INFORMATION_CLASS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567058">ZwQueryInformationTransactionManager</a>
 

 

