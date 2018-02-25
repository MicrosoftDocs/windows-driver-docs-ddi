---
UID: NF:ndis.NdisAllocateNetBufferMdlAndData
title: NdisAllocateNetBufferMdlAndData function
author: windows-driver-content
description: NDIS drivers call the NdisAllocateNetBufferMdlAndData function to allocate a NET_BUFFER structure along with the associated MDL and data.
old-location: netvista\ndisallocatenetbuffermdlanddata.htm
old-project: netvista
ms.assetid: cfac9061-a685-4e67-aaa2-ca43b7e36cfa
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , A, B, D, M, N, NdisAllocateNetBufferMdlAndData, NdisAllocateNetBufferMdlAndData function [Network Drivers Starting with Windows Vista], a, c, d, e, f, i, l, n, ndis/NdisAllocateNetBufferMdlAndData, ndis_netbuf_functions_ref_4f5d872d-11c1-4d75-889c-0c2157ce5f2e.xml, netvista.ndisallocatenetbuffermdlanddata, o, r, s, t, u"
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
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisAllocateNetBufferMdlAndData
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisAllocateNetBufferMdlAndData function


## -description


NDIS drivers call the 
  <b>NdisAllocateNetBufferMdlAndData</b> function to allocate a NET_BUFFER structure along with the associated
  MDL and data.


## -syntax


````
PNET_BUFFER NdisAllocateNetBufferMdlAndData(
  _In_ NDIS_HANDLE PoolHandle
);
````


## -parameters




### -param PoolHandle [in]

A NET_BUFFER structure pool handle that was previously returned from a call to the 
     <b>NdisAllocateNetBufferPool</b> function.


## -returns



<b>NdisAllocateNetBufferMdlAndData</b> returns a pointer to the NET_BUFFER structure that NDIS allocated.
     If the allocation was unsuccessful, this pointer is <b>NULL</b>.




## -remarks



The caller must call the 
    <b>NdisAllocateNetBufferPool</b> function and specify the maximum size of the data buffers. Given this
    value, NDIS can preallocate buffers for the caller.

This function allocates a 
    <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> structure, MDL and data in a single
    memory buffer. This is useful to achieve high performance when NET_BUFFER structures are frequently
    allocated and freed. The caller should not call 
    <a href="..\ndis\nf-ndis-ndisallocatenetbuffer.md">NdisAllocateNetBuffer</a> to allocate
    NET_BUFFERs out of NET_BUFFER pools which contain data.

NDIS uses the 
    <i>PoolHandle</i> parameter to get a block of memory, and then creates the NET_BUFFER, MDL, and data
    buffer.

To free the NET_BUFFER and associated information, call the 
    <a href="..\ndis\nf-ndis-ndisfreenetbuffer.md">NdisFreeNetBuffer</a> function.




## -see-also

<a href="..\ndis\nf-ndis-ndisfreenetbuffer.md">NdisFreeNetBuffer</a>



<a href="..\ndis\nf-ndis-ndisallocatenetbuffer.md">NdisAllocateNetBuffer</a>



<a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisAllocateNetBufferMdlAndData function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

