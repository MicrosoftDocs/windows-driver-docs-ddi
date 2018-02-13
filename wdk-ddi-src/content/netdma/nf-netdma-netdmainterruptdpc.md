---
UID: NF:netdma.NetDmaInterruptDpc
title: NetDmaInterruptDpc function
author: windows-driver-content
description: The NetDmaInterruptDpc function notifies the NetDMA interface that a DMA transfer deferred procedure call (DPC) has completed on a DMA channel.
old-location: netvista\netdmainterruptdpc.htm
old-project: netvista
ms.assetid: 93d7e4dd-70ee-4490-bffd-9b07511ee9fe
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: NetDmaInterruptDpc, NetDmaInterruptDpc function [Network Drivers Starting with Windows Vista], netdma/NetDmaInterruptDpc, netdma_ref_112a0d48-213e-4b5c-a776-11d5dcb83e1b.xml, netvista.netdmainterruptdpc
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: DISPATCH_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	netdma.h
apiname:
-	NetDmaInterruptDpc
product: Windows
targetos: Windows
req.typenames: NET_DMA_PNP_NOTIFICATION_CODE, *PNET_DMA_PNP_NOTIFICATION_CODE
---

# NetDmaInterruptDpc function


## -description


<div class="alert"><b>Note</b>  The NetDMA interface is not supported 

in Windows 8 and later.</div><div> </div>The 
  <b>NetDmaInterruptDpc</b> function notifies the NetDMA interface that a DMA transfer deferred procedure call
  (DPC) has completed on a DMA channel.


## -syntax


````
VOID NetDmaInterruptDpc(
  _In_     PVOID            NetDmaChannelHandle,
  _In_opt_ PHYSICAL_ADDRESS DmaDescriptor
);
````


## -parameters




### -param NetDmaChannelHandle [in]

A handle that identifies the DMA channel. The DMA provider driver received this handle from NetDMA
     in a call to the 
     <a href="..\netdma\nc-netdma-dma_channel_allocate_handler.md">
     ProviderAllocateDmaChannel</a> function.


### -param DmaDescriptor [in, optional]

A pointer to the last DMA descriptor that was processed.


## -returns



None.




## -remarks



DMA providers call the 
    <b>NetDmaInterruptDpc</b> function in their DPC handler.




## -see-also

<a href="..\netdma\nc-netdma-dma_channel_allocate_handler.md">ProviderAllocateDmaChannel</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NetDmaInterruptDpc function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

