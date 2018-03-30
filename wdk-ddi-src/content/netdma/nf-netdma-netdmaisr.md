---
UID: NF:netdma.NetDmaIsr
title: NetDmaIsr function
author: windows-driver-content
description: The NetDmaIsr function notifies the NetDMA interface that a DMA transfer interrupt has occurred on a DMA channel.
old-location: netvista\netdmaisr.htm
old-project: netvista
ms.assetid: 81aa5707-b614-429b-bd8e-0204eec74e0f
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NetDmaIsr, NetDmaIsr function [Network Drivers Starting with Windows Vista], netdma/NetDmaIsr, netdma_ref_5a9b1659-b106-4eed-931d-f2ad8b2476e9.xml, netvista.netdmaisr
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
req.irql: DEVICE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	netdma.h
api_name:
-	NetDmaIsr
product: Windows
targetos: Windows
req.typenames: NET_DMA_PNP_NOTIFICATION_CODE, *PNET_DMA_PNP_NOTIFICATION_CODE
---

# NetDmaIsr function


## -description


<div class="alert"><b>Note</b>  The NetDMA interface is not supported 

in Windows 8 and later.</div><div> </div>The 
  <b>NetDmaIsr</b> function notifies the NetDMA interface that a DMA transfer interrupt has occurred on a DMA
  channel.


## -parameters




### -param NetDmaChannelHandle [in]

A handle that identifies the DMA channel. The DMA provider driver received this handle from the
     NetDMA interface in a call to the 
     <a href="https://msdn.microsoft.com/42bc0e08-3d85-424f-aaa4-4df788d3706a">
     ProviderAllocateDmaChannel</a> function.


### -param DmaDescriptor [in]

The physical address of the DMA descriptor that is associated with the interrupt.


### -param pCpuNumber [out]

The number of the CPU that is associated with the interrupt DPC. The NetDMA interface writes this
     CPU number at the provided address before 
     <b>NetDmaIsr</b> returns.


## -returns



None




## -remarks



DMA provider drivers call the 
    <b>NetDmaIsr</b> function in their interrupt service routine (ISR).

If the NET_DMA_INTERRUPT_ON_COMPLETION flag in the 
    <b>ControlFlags</b> member of the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568734">NET_DMA_DESCRIPTOR</a> structure is set, the
    DMA engine should generate an interrupt for the DMA channel after it processes the DMA descriptor. When
    this flag is cleared, the DMA engine does not generate an interrupt.

<div class="alert"><b>Note</b>  When the ISR is called, the current DMA descriptor might already be different from
    the descriptor that triggered the interrupt.</div>
<div> </div>
A DMA provider driver should do as little work as possible in its ISR handler. The driver should defer
    I/O operations to the interrupt DPC handler.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff568734">NET_DMA_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/42bc0e08-3d85-424f-aaa4-4df788d3706a">ProviderAllocateDmaChannel</a>
 

 

