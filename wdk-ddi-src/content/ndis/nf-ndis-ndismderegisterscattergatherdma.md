---
UID: NF:ndis.NdisMDeregisterScatterGatherDma
title: NdisMDeregisterScatterGatherDma function (ndis.h)
description: Bus-master miniport drivers call NdisMDeregisterScatterGatherDma to release DMA resources that were allocated with the NdisMRegisterScatterGatherDma function.
old-location: netvista\ndismderegisterscattergatherdma.htm
tech.root: netvista
ms.assetid: 44792a1f-c6d5-4491-a06d-e00e41e40059
ms.date: 05/02/2018
ms.keywords: NdisMDeregisterScatterGatherDma, NdisMDeregisterScatterGatherDma function [Network Drivers Starting with Windows Vista], ndis/NdisMDeregisterScatterGatherDma, ndis_sgdma_ref_93a42580-1486-4ec8-90e6-ca6219c54884.xml, netvista.ndismderegisterscattergatherdma
ms.topic: function
f1_keywords:
 - "ndis/NdisMDeregisterScatterGatherDma"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Init_RegisterSG, Irql_Gather_DMA_Function
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
- NdisMDeregisterScatterGatherDma
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisMDeregisterScatterGatherDma function


## -description

> [!CAUTION]
> For ARM and ARM64 processors, we strongly recommend that NDIS driver writers use WDF DMA or WDM DMA instead of NDIS Scatter/Gather DMA. 
>
> For more information about WDF DMA, see [Handling DMA Operations in KMDF Drivers](https://docs.microsoft.com/windows-hardware/drivers/wdf/handling-dma-operations-in-kmdf-drivers).
>
> For more information about WDM DMA, see the DMA-related child topics of [Managing Input/Output for Drivers](https://docs.microsoft.com/windows-hardware/drivers/kernel/managing-input-output-for-drivers).

Bus-master miniport drivers call 
  <b>NdisMDeregisterScatterGatherDma</b> to release DMA resources that were allocated with the 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismregisterscattergatherdma">
  NdisMRegisterScatterGatherDma</a> function.


## -parameters




### -param NdisMiniportDmaHandle [in]

A handle to a context area that NDIS uses to manage a DMA resource. The caller obtained this
     handle by calling the 
     <b>NdisMRegisterScatterGatherDma</b> function.


## -returns



None




## -remarks



An NDIS miniport driver calls 
    <b>NdisMDeregisterScatterGatherDma</b> from its 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_halt">MiniportHaltEx</a> function to release the
    DMA resources it allocated and initialized in a previous call to 
    <b>NdisMRegisterScatterGatherDma</b>.




## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_halt">MiniportHaltEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-scatter-gather-dma">NDIS Scatter/Gather DMA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismregisterscattergatherdma">
   NdisMRegisterScatterGatherDma</a>
