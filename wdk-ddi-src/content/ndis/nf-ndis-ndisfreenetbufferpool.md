---
UID: NF:ndis.NdisFreeNetBufferPool
title: NdisFreeNetBufferPool function
author: windows-driver-content
description: Call the NdisFreeNetBufferPool function to free NET_BUFFER structure pools that are created with the NdisAllocateNetBufferPool function.
old-location: netvista\ndisfreenetbufferpool.htm
old-project: netvista
ms.assetid: e1ea63d1-9322-44c7-8196-2fe1a7b6a220
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisFreeNetBufferPool, NdisFreeNetBufferPool function [Network Drivers Starting with Windows Vista], ndis/NdisFreeNetBufferPool, ndis_netbuf_functions_ref_8fcb5f46-efc3-4059-9774-cbdf14c5500a.xml, netvista.ndisfreenetbufferpool
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisFreeNetBufferPool
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisFreeNetBufferPool function


## -description


Call the 
  <b>NdisFreeNetBufferPool</b> function to free 
  <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> structure pools that are created with
  the 
  <a href="..\ndis\nf-ndis-ndisallocatenetbufferpool.md">
  NdisAllocateNetBufferPool</a> function.


## -syntax


````
VOID NdisFreeNetBufferPool(
  _In_ NDIS_HANDLE PoolHandle
);
````


## -parameters




### -param PoolHandle [in]

The pool handle for the NET_BUFFER structure pool to be freed.


## -returns



None




## -remarks



You should free all the 
    <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> structures in a pool before freeing
    the NET_BUFFER structure pool. Call the 
    <a href="..\ndis\nf-ndis-ndisfreenetbuffer.md">NdisFreeNetBuffer</a> function to free each
    NET_BUFFER structure.




## -see-also

<a href="..\ndis\nf-ndis-ndisallocatenetbufferpool.md">NdisAllocateNetBufferPool</a>



<a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a>



<a href="..\ndis\nf-ndis-ndisfreenetbuffer.md">NdisFreeNetBuffer</a>



 

 


