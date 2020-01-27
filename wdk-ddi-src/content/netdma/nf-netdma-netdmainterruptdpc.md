---
UID: NF:netdma.NetDmaInterruptDpc
title: NetDmaInterruptDpc function (netdma.h)
description: The NetDmaInterruptDpc function notifies the NetDMA interface that a DMA transfer deferred procedure call (DPC) has completed on a DMA channel.
old-location: netvista\netdmainterruptdpc.htm
tech.root: netvista
ms.assetid: 93d7e4dd-70ee-4490-bffd-9b07511ee9fe
ms.date: 05/02/2018
ms.keywords: NetDmaInterruptDpc, NetDmaInterruptDpc function [Network Drivers Starting with Windows Vista], netdma/NetDmaInterruptDpc, netdma_ref_112a0d48-213e-4b5c-a776-11d5dcb83e1b.xml, netvista.netdmainterruptdpc
f1_keywords:
 - "netdma/NetDmaInterruptDpc"
req.header: netdma.h
req.include-header: Netdma.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NetDMA 1.0 drivers in Windows Vista.
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
req.irql: DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- netdma.h
api_name:
- NetDmaInterruptDpc
product:
- Windows
targetos: Windows
req.typenames: 
---

# NetDmaInterruptDpc function


## -description


<div class="alert"><b>Note</b>  The NetDMA interface is not supported 

in Windows 8 and later.</div><div> </div>The 
  <b>NetDmaInterruptDpc</b> function notifies the NetDMA interface that a DMA transfer deferred procedure call
  (DPC) has completed on a DMA channel.


## -parameters




### -param NetDmaChannelHandle [in]

A handle that identifies the DMA channel. The DMA provider driver received this handle from NetDMA
     in a call to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/nc-netdma-dma_channel_allocate_handler">
     ProviderAllocateDmaChannel</a> function.


### -param DmaDescriptor [in, optional]

A pointer to the last DMA descriptor that was processed.


## -returns



None.




## -remarks



DMA providers call the 
    <b>NetDmaInterruptDpc</b> function in their DPC handler.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/nc-netdma-dma_channel_allocate_handler">ProviderAllocateDmaChannel</a>
 

 

