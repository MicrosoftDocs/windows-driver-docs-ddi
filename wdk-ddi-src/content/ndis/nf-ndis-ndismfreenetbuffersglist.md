---
UID: NF:ndis.NdisMFreeNetBufferSGList
title: NdisMFreeNetBufferSGList function
author: windows-driver-content
description: Bus-master miniport drivers call the NdisMFreeNetBufferSGList function to free scatter/gather list resources that were allocated by calling the NdisMAllocateNetBufferSGList function.
old-location: netvista\ndismfreenetbuffersglist.htm
old-project: netvista
ms.assetid: 22945e04-9feb-4f4b-9ca6-916dab372a64
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ndis_sgdma_ref_e2f486cf-eba4-410d-ac18-724efb32fd59.xml, netvista.ndismfreenetbuffersglist, NdisMFreeNetBufferSGList function [Network Drivers Starting with Windows Vista], ndis/NdisMFreeNetBufferSGList, NdisMFreeNetBufferSGList
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Gather_DMA_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: DISPATCH_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisMFreeNetBufferSGList
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisMFreeNetBufferSGList function


## -description


Bus-master miniport drivers call the 
  <b>NdisMFreeNetBufferSGList</b> function to free scatter/gather list resources that were allocated by
  calling the 
  <a href="..\ndis\nf-ndis-ndismallocatenetbuffersglist.md">
  NdisMAllocateNetBufferSGList</a> function.


## -syntax


````
VOID NdisMFreeNetBufferSGList(
  _In_ NDIS_HANDLE          NdisMiniportDmaHandle,
  _In_ PSCATTER_GATHER_LIST pSGL,
  _In_ PNET_BUFFER          NetBuffer
);
````


## -parameters




### -param NdisMiniportDmaHandle [in]

A handle to a context area that NDIS uses to manage a DMA resource. The caller obtained this
     handle by calling the 
     <a href="..\ndis\nf-ndis-ndismregisterscattergatherdma.md">
     NdisMRegisterScatterGatherDma</a> function.


### -param pSGL [in]

A pointer to a miniport driver scatter/gather list buffer.


### -param NetBuffer [in]

A pointer to the 
     <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> structure associated with the
     specified scatter/gather list buffer.


## -returns


None



## -remarks


Bus-master miniport drivers must call the 
    <b>NdisMFreeNetBufferSGList</b> function to free a scatter/gather list. A miniport driver typically calls 
    <b>NdisMFreeNetBufferSGList</b> from its 
    <a href="..\ndis\nc-ndis-miniport_interrupt_dpc.md">MiniportInterruptDPC</a> function
    while it is handling a send complete interrupt or at any time that the driver no longer requires the
    scatter/gather list. Do not call 
    <b>NdisMFreeNetBufferSGList</b> while the driver or hardware is still accessing the memory that is
    described by the 
    <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> structure that is associated with the
    scatter/gather list.

Miniport drivers can free the buffer that was specified in the 
    <i>ScatterGatherListBuffer</i> parameter of the 
    <a href="..\ndis\nf-ndis-ndismallocatenetbuffersglist.md">NdisMAllocateNetBufferSGList</a> function after 
    <b>NdisMFreeNetBufferSGList</b> returns.

Before accessing received data, miniport drivers must call <b>NdisMFreeNetBufferSGList</b> to flush the memory cache.



## -see-also

<a href="https://msdn.microsoft.com/b24e0a56-1864-4f70-a646-c35e8eccd9e3">Registering and Deregistering DMA Channels</a>

<a href="..\ndis\nf-ndis-ndismallocatenetbuffersglist.md">NdisMAllocateNetBufferSGList</a>

<a href="https://msdn.microsoft.com/c7e702aa-494f-4b27-a7c3-d42ef8f42a6e">Miniport Driver Scatter/Gather DMA</a>

<a href="..\ndis\nf-ndis-ndismregisterscattergatherdma.md">
   NdisMRegisterScatterGatherDma</a>

<a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a>

<a href="..\ndis\nc-ndis-miniport_interrupt_dpc.md">MiniportInterruptDPC</a>

<a href="https://msdn.microsoft.com/95463617-65df-4c02-82f4-e3aba44d42fb">Allocating and Freeing Scatter/Gather Lists</a>

<a href="https://msdn.microsoft.com/70b8321b-7b21-4d11-a9c2-46b0caa26ce6">NDIS Scatter/Gather DMA</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMFreeNetBufferSGList function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

