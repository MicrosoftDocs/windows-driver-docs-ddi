---
UID: NF:netdma.NetDmaProviderStop
title: NetDmaProviderStop function (netdma.h)
description: The NetDmaProviderStop function notifies the NetDMA interface that all of the DMA channels that are associated with a DMA provider are no longer available for DMA transfers.
old-location: netvista\netdmaproviderstop.htm
tech.root: netvista
ms.assetid: 992fcdbd-200f-465d-b4be-922132d51d97
ms.date: 05/02/2018
keywords: ["NetDmaProviderStop function"]
ms.keywords: NetDmaProviderStop, NetDmaProviderStop function [Network Drivers Starting with Windows Vista], netdma/NetDmaProviderStop, netdma_ref_3d99732a-b6db-4d07-a5f0-0e79f82dac32.xml, netvista.netdmaproviderstop
f1_keywords:
 - "netdma/NetDmaProviderStop"
 - "NetDmaProviderStop"
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- netdma.h
api_name:
- NetDmaProviderStop
targetos: Windows
req.typenames: 
---

# NetDmaProviderStop function


## -description


<div class="alert"><b>Note</b>  The NetDMA interface is not supported 

in Windows 8 and later.</div><div> </div>The 
  <b>NetDmaProviderStop</b> function notifies the NetDMA interface that all of the DMA channels that are
  associated with a DMA provider are no longer available for DMA transfers.


## -parameters




### -param NetDmaProviderHandle 
[in]
A handle that identifies a DMA provider. The DMA provider driver received this handle from the
     NetDMA interface in a call to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/nf-netdma-netdmaregisterprovider">
     NetDmaRegisterProvider</a> function.


## -returns



None




## -remarks



A DMA provider driver calls the 
    <b>NetDmaProviderStop</b> function to notify the NetDMA interface that a DMA engine, which was started by
    calling the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/nf-netdma-netdmaproviderstart">NetDmaProviderStart</a> function, is no
    longer available.

The DMA provider driver must call 
    <b>NetDmaProviderStop</b> before it calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/nf-netdma-netdmaderegisterprovider">NetDmaDeregisterProvider</a> function
    to deregister a DMA provider.

DMA provider drivers typically call 
    <b>NetDmaProviderStop</b> while handling the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-remove-device">IRP_MN_REMOVE_DEVICE</a> or 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-stop-device">IRP_MN_STOP_DEVICE</a> IRP.

A DMA provider driver can call 
    <b>NetDmaProviderStop</b> and 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/nf-netdma-netdmaproviderstart">NetDmaProviderStart</a> as many times as
    the application requires after registering the DMA provider and before deregistering the DMA provider. If
    a DMA engine is being restarted after it called 
    <b>NetDmaProviderStop</b>, the DMA provider driver can specify new attributes in the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/ns-netdma-_net_dma_provider_attributes">
    NET_DMA_PROVIDER_ATTRIBUTES</a> structure at the 
    <i>ProviderAttributes</i> parameter of 
    <b>NetDmaProviderStart</b>.

The NetDMA interface waits for outstanding DMA operations to complete and frees all of the allocated
    DMA channels before it returns from the 
    <b>NetDmaProviderStop</b> function.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-remove-device">IRP_MN_REMOVE_DEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-stop-device">IRP_MN_STOP_DEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/ns-netdma-_net_dma_provider_attributes">NET_DMA_PROVIDER_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/nf-netdma-netdmaderegisterprovider">NetDmaDeregisterProvider</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/nf-netdma-netdmaproviderstart">NetDmaProviderStart</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/nf-netdma-netdmaregisterprovider">NetDmaRegisterProvider</a>
 

 

