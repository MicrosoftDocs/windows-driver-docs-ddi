---
UID: NF:ndis.NdisFreeNetBuffer
title: NdisFreeNetBuffer function (ndis.h)
description: Call the NdisFreeNetBuffer function to free a NET_BUFFER structure that was previously allocated from a NET_BUFFER structure pool with the NdisAllocateNetBuffer function.
old-location: netvista\ndisfreenetbuffer.htm
tech.root: netvista
ms.assetid: 9b5fe91b-29ae-4c83-b405-4a90e4375b4a
ms.date: 05/02/2018
keywords: ["NdisFreeNetBuffer function"]
ms.keywords: NdisFreeNetBuffer, NdisFreeNetBuffer function [Network Drivers Starting with Windows Vista], ndis/NdisFreeNetBuffer, ndis_netbuf_functions_ref_623498b1-25e0-48ae-831e-8c1240106bd4.xml, netvista.ndisfreenetbuffer
f1_keywords:
 - "ndis/NdisFreeNetBuffer"
 - "NdisFreeNetBuffer"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_NetBuffer_Function, NdisAllocateNetBuffer
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
- NdisFreeNetBuffer
targetos: Windows
req.typenames: 
---

# NdisFreeNetBuffer function


## -description


Call the 
  <b>NdisFreeNetBuffer</b> function to free a 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structure that was previously allocated
  from a NET_BUFFER structure pool with the 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbuffer">NdisAllocateNetBuffer</a> function.


## -parameters




### -param NetBuffer 
[in]
A pointer to a NET_BUFFER structure that was allocated by calling 
     <b>NdisAllocateNetBuffer</b>.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbuffer">NdisAllocateNetBuffer</a>
 

 

