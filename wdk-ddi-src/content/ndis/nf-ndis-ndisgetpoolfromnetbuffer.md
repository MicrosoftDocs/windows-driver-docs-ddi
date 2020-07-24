---
UID: NF:ndis.NdisGetPoolFromNetBuffer
title: NdisGetPoolFromNetBuffer function (ndis.h)
description: Call the NdisGetPoolFromNetBuffer function to get the NET_BUFFER structure pool handle that is associated with a specified NET_BUFFER structure.
old-location: netvista\ndisgetpoolfromnetbuffer.htm
tech.root: netvista
ms.assetid: 64bb049a-6b8a-470f-8269-8a168761e388
ms.date: 05/02/2018
keywords: ["NdisGetPoolFromNetBuffer function"]
ms.keywords: NdisGetPoolFromNetBuffer, NdisGetPoolFromNetBuffer function [Network Drivers Starting with Windows Vista], ndis/NdisGetPoolFromNetBuffer, ndis_netbuf_functions_ref_ae9f36c7-ab1c-4ea4-9721-2fd15aabc667.xml, netvista.ndisgetpoolfromnetbuffer
f1_keywords:
 - "ndis/NdisGetPoolFromNetBuffer"
 - "NdisGetPoolFromNetBuffer"
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
- NdisGetPoolFromNetBuffer
targetos: Windows
req.typenames: 
---

# NdisGetPoolFromNetBuffer function


## -description


Call the 
  <b>NdisGetPoolFromNetBuffer</b> function to get the 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structure pool handle that is associated
  with a specified NET_BUFFER structure.


## -parameters




### -param NetBuffer [in]

A pointer to a previously allocated 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structure.


## -returns



<b>NdisGetPoolFromNetBuffer</b> returns a handle to the NET_BUFFER structure pool that is associated with
     the specified NET_BUFFER structure.




## -remarks



The handle that 
    <b>NdisGetPoolFromNetBuffer</b> returns is a required parameter in calls to NDIS functions that manipulate    
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structures that are from the
    associated NET_BUFFER structure pool.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>
 

 

