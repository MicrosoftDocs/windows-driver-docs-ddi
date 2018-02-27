---
UID: NF:ndis.NdisFreeNetBufferListPool
title: NdisFreeNetBufferListPool function
author: windows-driver-content
description: Call the NdisFreeNetBufferListPool function to free a NET_BUFFER_LIST structure pool.
old-location: netvista\ndisfreenetbufferlistpool.htm
old-project: netvista
ms.assetid: 811df5ea-f5e6-4986-adc0-c5fa95e5f072
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: NdisFreeNetBufferListPool, NdisFreeNetBufferListPool function [Network Drivers Starting with Windows Vista], ndis/NdisFreeNetBufferListPool, ndis_netbuf_functions_ref_c2efb4b4-41de-4493-92a2-42e3fa78628b.xml, netvista.ndisfreenetbufferlistpool
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
req.ddi-compliance: Irql_NetBuffer_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: Ndis.sys
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	ndis.sys
apiname:
-	NdisFreeNetBufferListPool
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisFreeNetBufferListPool function


## -description


Call the 
  <b>NdisFreeNetBufferListPool</b> function to free a 
  <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure pool.


## -syntax


````
VOID NdisFreeNetBufferListPool(
  _In_ NDIS_HANDLE PoolHandle
);
````


## -parameters




### -param PoolHandle [in]

A handle that was obtained from a call to the 
     <a href="..\ndis\nf-ndis-ndisallocatenetbufferlistpool.md">
     NdisAllocateNetBufferListPool</a> function.


## -returns



None




## -remarks



Before freeing a 
    <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure pool, you must
    free all the NET_BUFFER_LIST structures in the pool. To free a NET_BUFFER_LIST structure, call the 
    <a href="..\ndis\nf-ndis-ndisfreenetbufferlist.md">NdisFreeNetBufferList</a> function.




## -see-also

<a href="..\ndis\nf-ndis-ndisallocatenetbufferlistpool.md">
   NdisAllocateNetBufferListPool</a>



<a href="..\ndis\nf-ndis-ndisfreenetbufferlist.md">NdisFreeNetBufferList</a>



<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisFreeNetBufferListPool function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

