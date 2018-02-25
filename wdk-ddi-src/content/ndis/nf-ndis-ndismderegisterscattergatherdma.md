---
UID: NF:ndis.NdisMDeregisterScatterGatherDma
title: NdisMDeregisterScatterGatherDma function
author: windows-driver-content
description: Bus-master miniport drivers call NdisMDeregisterScatterGatherDma to release DMA resources that were allocated with the NdisMRegisterScatterGatherDma function.
old-location: netvista\ndismderegisterscattergatherdma.htm
old-project: netvista
ms.assetid: 44792a1f-c6d5-4491-a06d-e00e41e40059
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , D, G, M, N, NdisMDeregisterScatterGatherDma, NdisMDeregisterScatterGatherDma function [Network Drivers Starting with Windows Vista], S, a, c, d, e, g, h, i, m, ndis/NdisMDeregisterScatterGatherDma, ndis_sgdma_ref_93a42580-1486-4ec8-90e6-ca6219c54884.xml, netvista.ndismderegisterscattergatherdma, r, s, t"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisMDeregisterScatterGatherDma
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisMDeregisterScatterGatherDma function


## -description


Bus-master miniport drivers call 
  <b>NdisMDeregisterScatterGatherDma</b> to release DMA resources that were allocated with the 
  <a href="..\ndis\nf-ndis-ndismregisterscattergatherdma.md">
  NdisMRegisterScatterGatherDma</a> function.


## -syntax


````
VOID NdisMDeregisterScatterGatherDma(
  _In_ NDIS_HANDLE NdisMiniportDmaHandle
);
````


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
    <a href="..\ndis\nc-ndis-miniport_halt.md">MiniportHaltEx</a> function to release the
    DMA resources it allocated and initialized in a previous call to 
    <b>NdisMRegisterScatterGatherDma</b>.




## -see-also

<a href="https://msdn.microsoft.com/70b8321b-7b21-4d11-a9c2-46b0caa26ce6">NDIS Scatter/Gather DMA</a>



<a href="https://msdn.microsoft.com/b24e0a56-1864-4f70-a646-c35e8eccd9e3">Registering and Deregistering DMA Channels</a>



<a href="https://msdn.microsoft.com/95463617-65df-4c02-82f4-e3aba44d42fb">Allocating and Freeing Scatter/Gather Lists</a>



<a href="..\ndis\nf-ndis-ndismregisterscattergatherdma.md">
   NdisMRegisterScatterGatherDma</a>



<a href="..\ndis\nc-ndis-miniport_halt.md">MiniportHaltEx</a>



<a href="https://msdn.microsoft.com/c7e702aa-494f-4b27-a7c3-d42ef8f42a6e">Miniport Driver Scatter/Gather DMA</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMDeregisterScatterGatherDma function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

