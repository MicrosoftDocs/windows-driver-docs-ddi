---
UID: NF:ndis.NdisMFlushLog
title: NdisMFlushLog function
author: windows-driver-content
description: NdisMFlushLog clears the log file.
old-location: netvista\ndismflushlog.htm
old-project: netvista
ms.assetid: a681b704-80cc-406a-b60f-31ef5f953164
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NdisMFlushLog, NdisMFlushLog function [Network Drivers Starting with Windows Vista], miniport_logging_ref_9de3f5b8-80d8-4f98-82ac-c4b490a3c8a4.xml, ndis/NdisMFlushLog, netvista.ndismflushlog
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisMFlushLog (NDIS 5.1)) in Windows   Vista. Supported for NDIS 5.1 drivers (see    NdisMFlushLog (NDIS 5.1)) in Windows   XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Miniport_Driver_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisMFlushLog
product:
- Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisMFlushLog function


## -description


<b>NdisMFlushLog</b> clears the log file.


## -parameters




### -param LogHandle [in]

Specifies the handle returned by 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff563572">NdisMCreateLog</a>.


## -returns



None




## -remarks



<b>NdisMFlushLog</b> resets the position pointers within the log file to the start of the file.

The driver must release any spin lock it is holding before calling 
    <b>NdisMFlushLog</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562790">NdisMCloseLog</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563572">NdisMCreateLog</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563695">NdisMWriteLogData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564524">NdisReleaseSpinLock</a>
 

 

