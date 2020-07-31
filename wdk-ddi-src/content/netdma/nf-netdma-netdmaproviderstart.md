---
UID: NF:netdma.NetDmaProviderStart
title: NetDmaProviderStart function (netdma.h)
description: The NetDmaProviderStart function notifies the NetDMA interface that all of the DMA channels that are associated with a DMA provider are initialized and ready for DMA transfers.
old-location: netvista\netdmaproviderstart.htm
tech.root: netvista
ms.assetid: e99ebbe8-8605-4bf2-9ec0-d7cde25058f7
ms.date: 05/02/2018
keywords: ["NetDmaProviderStart function"]
ms.keywords: NetDmaProviderStart, NetDmaProviderStart function [Network Drivers Starting with Windows Vista], netdma/NetDmaProviderStart, netdma_ref_bdb7c400-1c73-4dcb-8eb2-4121172302ad.xml, netvista.netdmaproviderstart
f1_keywords:
 - "netdma/NetDmaProviderStart"
 - "NetDmaProviderStart"
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
- NetDmaProviderStart
targetos: Windows
req.typenames: 
---

# NetDmaProviderStart function


## -description


<div class="alert"><b>Note</b>  The NetDMA interface is not supported 

in Windows 8 and later.</div><div> </div>The 
  <b>NetDmaProviderStart</b> function notifies the NetDMA interface that all of the DMA channels that are
  associated with a DMA provider are initialized and ready for DMA transfers.


## -parameters




### -param NetDmaProviderHandle [in]

A handle that identifies a DMA provider. The DMA provider driver received this handle from the
     NetDMA interface in a call to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/nf-netdma-netdmaregisterprovider">
     NetDmaRegisterProvider</a> function.


### -param ProviderAttributes [in]

A pointer to a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/ns-netdma-_net_dma_provider_attributes">
     NET_DMA_PROVIDER_ATTRIBUTES</a> structure that defines the DMA device attributes of the DMA
     provider.


## -returns



None




## -remarks



DMA providers call the 
    <b>NetDmaProviderStart</b> function to notify the NetDMA interface that a DMA provider is started. A DMA
    provider driver initializes a DMA engine and calls the 
    <b>NetDmaProviderStart</b> function while handling the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-start-device">IRP_MN_START_DEVICE</a> IRP.

The DMA provider driver can also call 
    <b>NetDmaProviderStart</b> after the driver called the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/nf-netdma-netdmaproviderstop">NetDmaProviderStop</a> function for
    application-specific reasons. DMA provider drivers call 
    <b>NetDmaProviderStop</b> to notify the NetDMA interface that a previously started DMA provider is no
    longer available.

The DMA provider driver supplies a 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/ns-netdma-_net_dma_provider_attributes">
    NET_DMA_PROVIDER_ATTRIBUTES</a> structure at the 
    <i>ProviderAttributes</i> parameter of 
    <b>NetDmaProviderStart</b>. The NET_DMA_PROVIDER_ATTRIBUTES structure specifies the configuration
    attributes for a NetDMA provider.

Before a DMA provider driver calls 
    <b>NetDmaProviderStart</b>, it should be ready to handle all NetDMA interface requests, such as
    allocating DMA channels and performing DMA transfers.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-start-device">IRP_MN_START_DEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/ns-netdma-_net_dma_provider_attributes">NET_DMA_PROVIDER_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/nf-netdma-netdmaproviderstop">NetDmaProviderStop</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdma/nf-netdma-netdmaregisterprovider">NetDmaRegisterProvider</a>
 

 

