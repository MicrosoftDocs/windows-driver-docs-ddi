---
UID: NF:ndis.NdisFreeNetBufferPool
title: NdisFreeNetBufferPool function (ndis.h)
description: Call the NdisFreeNetBufferPool function to free NET_BUFFER structure pools that are created with the NdisAllocateNetBufferPool function.
old-location: netvista\ndisfreenetbufferpool.htm
tech.root: netvista
ms.assetid: e1ea63d1-9322-44c7-8196-2fe1a7b6a220
ms.date: 05/02/2018
ms.keywords: NdisFreeNetBufferPool, NdisFreeNetBufferPool function [Network Drivers Starting with Windows Vista], ndis/NdisFreeNetBufferPool, ndis_netbuf_functions_ref_8fcb5f46-efc3-4059-9774-cbdf14c5500a.xml, netvista.ndisfreenetbufferpool
ms.topic: function
f1_keywords:
 - "ndis/NdisFreeNetBufferPool"
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
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisFreeNetBufferPool
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisFreeNetBufferPool function


## -description


Call the 
  <b>NdisFreeNetBufferPool</b> function to free 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structure pools that are created with
  the 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferpool">
  NdisAllocateNetBufferPool</a> function.


## -parameters




### -param PoolHandle [in]

The pool handle for the NET_BUFFER structure pool to be freed.


## -remarks



You should free all the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structures in a pool before freeing
    the NET_BUFFER structure pool. Call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreenetbuffer">NdisFreeNetBuffer</a> function to free each
    NET_BUFFER structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferpool">NdisAllocateNetBufferPool</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreenetbuffer">NdisFreeNetBuffer</a>
 

 

