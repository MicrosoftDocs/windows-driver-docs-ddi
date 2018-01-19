---
UID: NF:ndis.NdisMGetDmaAlignment
title: NdisMGetDmaAlignment function
author: windows-driver-content
description: The NdisMGetDmaAlignment function returns the alignment requirements of the DMA system for a NIC.
old-location: netvista\ndismgetdmaalignment.htm
old-project: netvista
ms.assetid: b683518c-b4f4-4ae4-945d-8a2d064a5390
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: NdisMGetDmaAlignment
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
req.alt-api: NdisMGetDmaAlignment
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: Irql_Miniport_Driver_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: = PASSIVE_LEVEL
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisMGetDmaAlignment function



## -description
The 
  <b>NdisMGetDmaAlignment</b> function returns the alignment requirements of the DMA system for a NIC.



## -syntax

````
ULONG NdisMGetDmaAlignment(
  _In_ NDIS_HANDLE MiniportAdapterHandle
);
````


## -parameters

### -param MiniportAdapterHandle [in]

An NDIS handle that identifies the miniport adapter for the NIC. This handle was originally passed
     to the 
     <a href="..\ndis\nc-ndis-miniport_initialize.md">
     MiniportInitializeEx</a> function.


## -returns
Returns a value that specifies the alignment requirements of the DMA system. The miniport driver
     uses this value to round up the size of a receive buffer to a cache-line size or a multiple of that size
     when it allocates such a buffer.


## -remarks
A miniport driver can call the 
    <b>NdisMGetDmaAlignment</b> function to determine alignment requirements for DMA buffers that it
    allocates. A miniport driver might require increasing the returned value because of additional hardware
    device restrictions.


## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismregisterscattergatherdma.md">
   NdisMRegisterScatterGatherDma</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMGetDmaAlignment function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

