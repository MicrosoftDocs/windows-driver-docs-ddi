---
UID: NF:ndis.NdisMCloseLog
title: NdisMCloseLog function
author: windows-driver-content
description: NdisMCloseLog releases resources that were used for logging.
old-location: netvista\ndismcloselog.htm
old-project: netvista
ms.assetid: a4b2bf1a-f15d-409f-bd5f-84dbf8dadc09
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisMCloseLog, NdisMCloseLog function [Network Drivers Starting with Windows Vista], miniport_logging_ref_ad3e4ea9-60c4-46b7-ac68-84517df279e0.xml, ndis/NdisMCloseLog, netvista.ndismcloselog
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisMCloseLog (NDIS 5.1)) in Windows   Vista. Supported for NDIS 5.1 drivers (see    NdisMCloseLog (NDIS 5.1)) in Windows   XP.
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
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisMCloseLog
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisMCloseLog function


## -description


<b>NdisMCloseLog</b> releases resources that were used for logging.


## -syntax


````
VOID NdisMCloseLog(
  _In_ NDIS_HANDLE LogHandle
);
````


## -parameters




### -param LogHandle [in]

Specifies the handle returned by 
     <a href="..\ndis\nf-ndis-ndismcreatelog.md">NdisMCreateLog</a>.


## -returns



None




## -remarks



<b>NdisMCloseLog</b> closes the temporary log file allocated by 
    <b>NdisMCreateLog</b> and releases all resources associated with the driver's logging operations when a
    miniport driver is unloading.




## -see-also

<a href="..\ndis\nf-ndis-ndismwritelogdata.md">NdisMWriteLogData</a>



<a href="..\ndis\nf-ndis-ndismflushlog.md">NdisMFlushLog</a>



<a href="..\ndis\nf-ndis-ndismcreatelog.md">NdisMCreateLog</a>



<a href="..\ndis\nc-ndis-miniport_halt.md">MiniportHaltEx</a>



 

 


