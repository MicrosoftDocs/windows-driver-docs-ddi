---
UID: NF:netdma.NetDmaProviderStop
title: NetDmaProviderStop function
author: windows-driver-content
description: The NetDmaProviderStop function notifies the NetDMA interface that all of the DMA channels that are associated with a DMA provider are no longer available for DMA transfers.
old-location: netvista\netdmaproviderstop.htm
old-project: netvista
ms.assetid: 992fcdbd-200f-465d-b4be-922132d51d97
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: NetDmaProviderStop
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: netdma.h
req.include-header: Netdma.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NetDMA 1.0 drivers in Windows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NetDmaProviderStop
req.alt-loc: netdma.h
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
req.typenames: NET_DMA_PNP_NOTIFICATION_CODE, *PNET_DMA_PNP_NOTIFICATION_CODE
---

# NetDmaProviderStop function



## -description

## -syntax

````
VOID NetDmaProviderStop(
  _In_ PVOID NetDmaProviderHandle
);
````


## -parameters

### -param NetDmaProviderHandle [in]

A handle that identifies a DMA provider. The DMA provider driver received this handle from the
     NetDMA interface in a call to the 
     <a href="..\netdma\nf-netdma-netdmaregisterprovider.md">
     NetDmaRegisterProvider</a> function.


## -returns
None


## -remarks
A DMA provider driver calls the 
    <b>NetDmaProviderStop</b> function to notify the NetDMA interface that a DMA engine, which was started by
    calling the 
    <a href="..\netdma\nf-netdma-netdmaproviderstart.md">NetDmaProviderStart</a> function, is no
    longer available.

The DMA provider driver must call 
    <b>NetDmaProviderStop</b> before it calls the 
    <a href="..\netdma\nf-netdma-netdmaderegisterprovider.md">NetDmaDeregisterProvider</a> function
    to deregister a DMA provider.

DMA provider drivers typically call 
    <b>NetDmaProviderStop</b> while handling the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff551738">IRP_MN_REMOVE_DEVICE</a> or 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff551755">IRP_MN_STOP_DEVICE</a> IRP.

A DMA provider driver can call 
    <b>NetDmaProviderStop</b> and 
    <a href="..\netdma\nf-netdma-netdmaproviderstart.md">NetDmaProviderStart</a> as many times as
    the application requires after registering the DMA provider and before deregistering the DMA provider. If
    a DMA engine is being restarted after it called 
    <b>NetDmaProviderStop</b>, the DMA provider driver can specify new attributes in the 
    <a href="..\netdma\ns-netdma-_net_dma_provider_attributes.md">
    NET_DMA_PROVIDER_ATTRIBUTES</a> structure at the 
    <i>ProviderAttributes</i> parameter of 
    <b>NetDmaProviderStart</b>.

The NetDMA interface waits for outstanding DMA operations to complete and frees all of the allocated
    DMA channels before it returns from the 
    <b>NetDmaProviderStop</b> function.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551738">IRP_MN_REMOVE_DEVICE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551755">IRP_MN_STOP_DEVICE</a>
</dt>
<dt>
<a href="..\netdma\ns-netdma-_net_dma_provider_attributes.md">NET_DMA_PROVIDER_ATTRIBUTES</a>
</dt>
<dt>
<a href="..\netdma\nf-netdma-netdmaderegisterprovider.md">NetDmaDeregisterProvider</a>
</dt>
<dt>
<a href="..\netdma\nf-netdma-netdmaproviderstart.md">NetDmaProviderStart</a>
</dt>
<dt>
<a href="..\netdma\nf-netdma-netdmaregisterprovider.md">NetDmaRegisterProvider</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NetDmaProviderStop function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

