---
UID: NF:ndis.NdisMCloseLog
title: NdisMCloseLog function (ndis.h)
description: NdisMCloseLog releases resources that were used for logging.
old-location: netvista\ndismcloselog.htm
tech.root: netvista
ms.assetid: a4b2bf1a-f15d-409f-bd5f-84dbf8dadc09
ms.date: 05/02/2018
ms.keywords: NdisMCloseLog, NdisMCloseLog function [Network Drivers Starting with Windows Vista], miniport_logging_ref_ad3e4ea9-60c4-46b7-ac68-84517df279e0.xml, ndis/NdisMCloseLog, netvista.ndismcloselog
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
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisMCloseLog
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisMCloseLog function


## -description


<b>NdisMCloseLog</b> releases resources that were used for logging.


## -parameters




### -param LogHandle [in]

Specifies the handle returned by 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismcreatelog">NdisMCreateLog</a>.


## -returns



None




## -remarks



<b>NdisMCloseLog</b> closes the temporary log file allocated by 
    <b>NdisMCreateLog</b> and releases all resources associated with the driver's logging operations when a
    miniport driver is unloading.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_halt">MiniportHaltEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismcreatelog">NdisMCreateLog</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismflushlog">NdisMFlushLog</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismwritelogdata">NdisMWriteLogData</a>
 

 

