---
UID: NF:ndis.NdisMCloseLog
title: NdisMCloseLog function (ndis.h)
description: NdisMCloseLog releases resources that were used for logging.
old-location: netvista\ndismcloselog.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NdisMCloseLog function"]
ms.keywords: NdisMCloseLog, NdisMCloseLog function [Network Drivers Starting with Windows Vista], miniport_logging_ref_ad3e4ea9-60c4-46b7-ac68-84517df279e0.xml, ndis/NdisMCloseLog, netvista.ndismcloselog
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
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisMCloseLog
 - ndis/NdisMCloseLog
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisMCloseLog
---

# NdisMCloseLog function


## -description

<b>NdisMCloseLog</b> releases resources that were used for logging.

## -parameters

### -param LogHandle [in]


Specifies the handle returned by 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcreatelog">NdisMCreateLog</a>.

## -remarks

<b>NdisMCloseLog</b> closes the temporary log file allocated by 
    <b>NdisMCreateLog</b> and releases all resources associated with the driver's logging operations when a
    miniport driver is unloading.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_halt">MiniportHaltEx</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismcreatelog">NdisMCreateLog</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismflushlog">NdisMFlushLog</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismwritelogdata">NdisMWriteLogData</a>
