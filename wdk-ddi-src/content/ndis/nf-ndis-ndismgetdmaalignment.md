---
UID: NF:ndis.NdisMGetDmaAlignment
title: NdisMGetDmaAlignment function (ndis.h)
description: The NdisMGetDmaAlignment function returns the alignment requirements of the DMA system for a NIC.
old-location: netvista\ndismgetdmaalignment.htm
tech.root: netvista
ms.assetid: b683518c-b4f4-4ae4-945d-8a2d064a5390
ms.date: 05/02/2018
ms.keywords: NdisMGetDmaAlignment, NdisMGetDmaAlignment function [Network Drivers Starting with Windows Vista], dma_ref_75f5af9e-a351-428c-a465-ccd747fcdd37.xml, ndis/NdisMGetDmaAlignment, netvista.ndismgetdmaalignment
f1_keywords:
 - "ndis/NdisMGetDmaAlignment"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
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
req.irql: = PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisMGetDmaAlignment
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisMGetDmaAlignment function


## -description


The 
  <b>NdisMGetDmaAlignment</b> function returns the alignment requirements of the DMA system for a NIC.


## -parameters




### -param MiniportAdapterHandle [in]

An NDIS handle that identifies the miniport adapter for the NIC. This handle was originally passed
     to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">
     MiniportInitializeEx</a> function.


## -returns



Returns a value that specifies the alignment requirements of the DMA system. The miniport driver
     uses this value to round up the size of a receive buffer to a cache-line size or a multiple of that size
     when it allocates such a buffer.




## -remarks



<div class="alert"><b>Note</b>  A miniport driver must have already called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterscattergatherdma">NdisMRegisterScatterGatherDma</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterdmachannel">NdisMRegisterDmaChannel</a> to initialize a
  scatter/gather DMA channel before calling <b>NdisMGetDmaAlignment</b>.</div>
<div> </div>
A miniport driver can call the 
    <b>NdisMGetDmaAlignment</b> function to determine alignment requirements for DMA buffers that it
    allocates. A miniport driver might require increasing the returned value because of additional hardware
    device restrictions.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterscattergatherdma">
   NdisMRegisterScatterGatherDma</a>
 

 

