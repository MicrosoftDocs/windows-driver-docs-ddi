---
UID: NF:ndis.NdisMDeregisterDmaChannel
title: NdisMDeregisterDmaChannel function (ndis.h)
description: The NdisMDeregisterDmaChannel function releases a miniport driver's claim on a DMA channel for a NIC.
old-location: netvista\ndismderegisterdmachannel.htm
tech.root: netvista
ms.assetid: 1581cbfd-bdab-40ed-9978-f60ec220c17a
ms.date: 05/02/2018
keywords: ["NdisMDeregisterDmaChannel function"]
ms.keywords: NdisMDeregisterDmaChannel, NdisMDeregisterDmaChannel function [Network Drivers Starting with Windows Vista], dma_ref_8babcd45-1946-4928-a0a2-2fc0871b9f90.xml, ndis/NdisMDeregisterDmaChannel, netvista.ndismderegisterdmachannel
f1_keywords:
 - "ndis/NdisMDeregisterDmaChannel"
 - "NdisMDeregisterDmaChannel"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisMDeregisterDmaChannel (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisMDeregisterDmaChannel (NDIS   5.1)) in Windows XP.
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
- NdisMDeregisterDmaChannel
targetos: Windows
req.typenames: 
---

# NdisMDeregisterDmaChannel function


## -description


The 
  <b>NdisMDeregisterDmaChannel</b> function releases a miniport driver's claim on a DMA channel for a
  NIC.


## -parameters




### -param MiniportDmaHandle 
[in]
The DMA handle returned by the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterdmachannel">
     NdisMRegisterDmaChannel</a> function.


## -remarks



The caller should consider 
    <i>MiniportDmaHandle</i> invalid as soon as it is passed to 
    <b>NdisMDeregisterDmaChannel</b>. This function releases the NIC's claim on the DMA channel in the
    registry.

<b>NdisMDeregisterDmaChannel</b> can be called only from a miniport driver's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a> and 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_halt">MiniportHaltEx</a> functions.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_halt">MiniportHaltEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterdmachannel">NdisMRegisterDmaChannel</a>
 

 

