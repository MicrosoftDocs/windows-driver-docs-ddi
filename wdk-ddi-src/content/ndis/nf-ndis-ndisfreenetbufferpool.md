---
UID: NF:ndis.NdisFreeNetBufferPool
title: NdisFreeNetBufferPool function
author: windows-driver-content
description: Call the NdisFreeNetBufferPool function to free NET_BUFFER structure pools that are created with the NdisAllocateNetBufferPool function.
old-location: netvista\ndisfreenetbufferpool.htm
old-project: netvista
ms.assetid: e1ea63d1-9322-44c7-8196-2fe1a7b6a220
ms.author: windowsdriverdev
ms.date: 4/25/2018
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
req.typenames: 
---

# NdisFreeNetBufferPool function


## -description


Call the 
  <b>NdisFreeNetBufferPool</b> function to free 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structure pools that are created with
  the 
  <a href="https://msdn.microsoft.com/bc27758a-a793-48a1-a6ab-bd193aa9c61a">
  NdisAllocateNetBufferPool</a> function.


## -parameters




### -param PoolHandle [in]

The pool handle for the NET_BUFFER structure pool to be freed.


## -returns



None




## -remarks



You should free all the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structures in a pool before freeing
    the NET_BUFFER structure pool. Call the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff562582">NdisFreeNetBuffer</a> function to free each
    NET_BUFFER structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561613">NdisAllocateNetBufferPool</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562582">NdisFreeNetBuffer</a>
 

 

