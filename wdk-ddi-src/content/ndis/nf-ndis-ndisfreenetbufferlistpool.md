---
UID: NF:ndis.NdisFreeNetBufferListPool
title: NdisFreeNetBufferListPool function
author: windows-driver-content
description: Call the NdisFreeNetBufferListPool function to free a NET_BUFFER_LIST structure pool.
old-location: netvista\ndisfreenetbufferlistpool.htm
tech.root: netvista
ms.assetid: 811df5ea-f5e6-4986-adc0-c5fa95e5f072
ms.author: windowsdriverdev
ms.date: 5/2/2018
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	ndis.sys
api_name:
-	NdisFreeNetBufferListPool
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisFreeNetBufferListPool function


## -description


Call the 
  <b>NdisFreeNetBufferListPool</b> function to free a 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure pool.


## -parameters




### -param PoolHandle [in]

A handle that was obtained from a call to the 
     <a href="https://msdn.microsoft.com/b117b472-0c26-41a9-b364-3d0cfbd26cc9">
     NdisAllocateNetBufferListPool</a> function.


## -returns



None




## -remarks



Before freeing a 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure pool, you must
    free all the NET_BUFFER_LIST structures in the pool. To free a NET_BUFFER_LIST structure, call the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff562583">NdisFreeNetBufferList</a> function.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>



<a href="https://msdn.microsoft.com/b117b472-0c26-41a9-b364-3d0cfbd26cc9">
   NdisAllocateNetBufferListPool</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562583">NdisFreeNetBufferList</a>
 

 

