---
UID: NF:netdma.NetDmaProviderStop
title: NetDmaProviderStop function
author: windows-driver-content
description: The NetDmaProviderStop function notifies the NetDMA interface that all of the DMA channels that are associated with a DMA provider are no longer available for DMA transfers.
old-location: netvista\netdmaproviderstop.htm
old-project: netvista
ms.assetid: 992fcdbd-200f-465d-b4be-922132d51d97
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NetDmaProviderStop, NetDmaProviderStop function [Network Drivers Starting with Windows Vista], netdma/NetDmaProviderStop, netdma_ref_3d99732a-b6db-4d07-a5f0-0e79f82dac32.xml, netvista.netdmaproviderstop
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	netdma.h
api_name:
-	NetDmaProviderStop
product: Windows
targetos: Windows
req.typenames: NET_DMA_PNP_NOTIFICATION_CODE, *PNET_DMA_PNP_NOTIFICATION_CODE
---

# NetDmaProviderStop function


## -description


<div class="alert"><b>Note</b>  The NetDMA interface is not supported 

in Windows 8 and later.</div><div> </div>The 
  <b>NetDmaProviderStop</b> function notifies the NetDMA interface that all of the DMA channels that are
  associated with a DMA provider are no longer available for DMA transfers.


## -parameters




### -param NetDmaProviderHandle [in]

A handle that identifies a DMA provider. The DMA provider driver received this handle from the
     NetDMA interface in a call to the 
     <a href="https://msdn.microsoft.com/35d70d0b-c1b9-433f-941d-6cb61ddf0b62">
     NetDmaRegisterProvider</a> function.


## -returns



None




## -remarks



A DMA provider driver calls the 
    <b>NetDmaProviderStop</b> function to notify the NetDMA interface that a DMA engine, which was started by
    calling the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568334">NetDmaProviderStart</a> function, is no
    longer available.

The DMA provider driver must call 
    <b>NetDmaProviderStop</b> before it calls the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568328">NetDmaDeregisterProvider</a> function
    to deregister a DMA provider.

DMA provider drivers typically call 
    <b>NetDmaProviderStop</b> while handling the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff551738">IRP_MN_REMOVE_DEVICE</a> or 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff551755">IRP_MN_STOP_DEVICE</a> IRP.

A DMA provider driver can call 
    <b>NetDmaProviderStop</b> and 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568334">NetDmaProviderStart</a> as many times as
    the application requires after registering the DMA provider and before deregistering the DMA provider. If
    a DMA engine is being restarted after it called 
    <b>NetDmaProviderStop</b>, the DMA provider driver can specify new attributes in the 
    <a href="https://msdn.microsoft.com/7b5a7e9e-b10b-4c94-80b1-172cd9f0c9ca">
    NET_DMA_PROVIDER_ATTRIBUTES</a> structure at the 
    <i>ProviderAttributes</i> parameter of 
    <b>NetDmaProviderStart</b>.

The NetDMA interface waits for outstanding DMA operations to complete and frees all of the allocated
    DMA channels before it returns from the 
    <b>NetDmaProviderStop</b> function.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551738">IRP_MN_REMOVE_DEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551755">IRP_MN_STOP_DEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568737">NET_DMA_PROVIDER_ATTRIBUTES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568328">NetDmaDeregisterProvider</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568334">NetDmaProviderStart</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568336">NetDmaRegisterProvider</a>
 

 

