---
UID: NS:wdm._TRANSACTIONMANAGER_LOGPATH_INFORMATION
title: "_TRANSACTIONMANAGER_LOGPATH_INFORMATION"
author: windows-driver-content
description: The TRANSACTIONMANAGER_LOGPATH_INFORMATION structure contains information about a transaction manager object.
old-location: kernel\transactionmanager_logpath_information.htm
old-project: kernel
ms.assetid: 53d7e8a9-fc89-4b11-8bbb-e9b5b0504f5e
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PTRANSACTIONMANAGER_LOGPATH_INFORMATION, PTRANSACTIONMANAGER_LOGPATH_INFORMATION, PTRANSACTIONMANAGER_LOGPATH_INFORMATION structure pointer [Kernel-Mode Driver Architecture], TRANSACTIONMANAGER_LOGPATH_INFORMATION, TRANSACTIONMANAGER_LOGPATH_INFORMATION structure [Kernel-Mode Driver Architecture], _TRANSACTIONMANAGER_LOGPATH_INFORMATION, kernel.transactionmanager_logpath_information, ktm_ref_2e3d26b5-525c-4953-a871-7eb6535d926e.xml, wdm/PTRANSACTIONMANAGER_LOGPATH_INFORMATION, wdm/TRANSACTIONMANAGER_LOGPATH_INFORMATION"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	TRANSACTIONMANAGER_LOGPATH_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: TRANSACTIONMANAGER_LOGPATH_INFORMATION, *PTRANSACTIONMANAGER_LOGPATH_INFORMATION
req.product: Windows 10 or later.
---

# _TRANSACTIONMANAGER_LOGPATH_INFORMATION structure


## -description


The <b>TRANSACTIONMANAGER_LOGPATH_INFORMATION</b> structure contains information about a <a href="https://msdn.microsoft.com/af53cda4-e2ab-47df-9311-a4da2a2ee08d">transaction manager object</a>.


## -struct-fields




### -field LogPathLength

The number of elements in the <b>LogPath</b> member's character array.


### -field LogPath

A caller-allocated character array that receives the path and file name of the <a href="https://msdn.microsoft.com/d7ad0e16-d1f2-4c41-b647-95b5445c2708">log file stream</a> that is associated with a transaction manager.


## -remarks



The <b>TRANSACTIONMANAGER_LOGPATH_INFORMATION</b> structure is used with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567058">ZwQueryInformationTransactionManager</a> routine.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564762">TRANSACTIONMANAGER_INFORMATION_CLASS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567058">ZwQueryInformationTransactionManager</a>
 

 

