---
UID: NF:ndis.NdisMReadDmaCounter
title: NdisMReadDmaCounter function
author: windows-driver-content
description: The NdisMReadDmaCounter function returns the current value of the system DMA controller's counter.
old-location: netvista\ndismreaddmacounter.htm
old-project: netvista
ms.assetid: bfce0f28-4cca-48a2-8836-2f77f4b6370a
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NdisMReadDmaCounter, NdisMReadDmaCounter function [Network Drivers Starting with Windows Vista], dma_ref_12d2675f-d576-4a5d-9af0-42dfd63fd1da.xml, ndis/NdisMReadDmaCounter, netvista.ndismreaddmacounter
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisMReadDmaCounter (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisMReadDmaCounter (NDIS   5.1)) in Windows XP.
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
-	NdisMReadDmaCounter
product:
- Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisMReadDmaCounter function


## -description


The 
  <b>NdisMReadDmaCounter</b> function returns the current value of the system DMA controller's counter.


## -parameters




### -param MiniportDmaHandle [in]

The handle returned when the miniport driver called the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff563646">NdisMRegisterDmaChannel</a> function
     during initialization.


## -returns



<b>NdisMReadDmaCounter</b> returns the number of bytes remaining in the current DMA transfer on the
     channel used by the NIC.




## -remarks



Miniport drivers of devices that use the system DMA controller's auto-initialize mode can call 
    <b>NdisMReadDmaCounter</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563646">NdisMRegisterDmaChannel</a>
 

 

