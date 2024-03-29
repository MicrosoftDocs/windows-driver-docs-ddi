---
UID: NF:ndis.NdisMFlushLog
title: NdisMFlushLog function (ndis.h)
description: NdisMFlushLog clears the log file.
old-location: netvista\ndismflushlog.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NdisMFlushLog function"]
ms.keywords: NdisMFlushLog, NdisMFlushLog function [Network Drivers Starting with Windows Vista], miniport_logging_ref_9de3f5b8-80d8-4f98-82ac-c4b490a3c8a4.xml, ndis/NdisMFlushLog, netvista.ndismflushlog
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
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisMFlushLog
 - ndis/NdisMFlushLog
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisMFlushLog
---

# NdisMFlushLog function


## -description

<b>NdisMFlushLog</b> clears the log file.

## -parameters

### -param LogHandle [in]


Specifies the handle returned by 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcreatelog">NdisMCreateLog</a>.

## -remarks

<b>NdisMFlushLog</b> resets the position pointers within the log file to the start of the file.

The driver must release any spin lock it is holding before calling 
    <b>NdisMFlushLog</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcloselog">NdisMCloseLog</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcreatelog">NdisMCreateLog</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismwritelogdata">NdisMWriteLogData</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisreleasespinlock">NdisReleaseSpinLock</a>
