<<<<<<< HEAD:wdk-ddi-src/content/nblapi/nf-nblapi-ndisgetpoolfromnetbuffer.md
---
UID: NF:nblapi.NdisGetPoolFromNetBuffer
title: NdisGetPoolFromNetBuffer
ms.date: 11/30/2020
ms.topic: language-reference
targetos: Windows
description: Call the NdisGetPoolFromNetBuffer function to get the NET_BUFFER structure pool handle that is associated with a specified NET_BUFFER structure.
tech.root: netvista
req.assembly: 
req.construct-type: function
req.ddi-compliance: Irql_NetBuffer_Function
req.dll: 
req.header: ndis/nblapi.h
req.idl: 
req.include-header: ndis.h
req.irql: <= DISPATCH_LEVEL
req.kmdf-ver: 
req.lib: Ndis.lib
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.target-type: Universal
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - nblapi.h
api_name:
 - NdisGetPoolFromNetBuffer
f1_keywords:
 - NdisGetPoolFromNetBuffer
 - nblapi/NdisGetPoolFromNetBuffer
dev_langs:
 - c++
---

# NdisGetPoolFromNetBuffer function


## -description

Call the 
  <b>NdisGetPoolFromNetBuffer</b> function to get the 
  <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structure pool handle that is associated
  with a specified NET_BUFFER structure.

## -parameters

### -param NetBuffer 

[in]
A pointer to a previously allocated 
     <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structure.

## -returns

<b>NdisGetPoolFromNetBuffer</b> returns a handle to the NET_BUFFER structure pool that is associated with
     the specified NET_BUFFER structure.

## -remarks

The handle that 
    <b>NdisGetPoolFromNetBuffer</b> returns is a required parameter in calls to NDIS functions that manipulate    
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structures that are from the
    associated NET_BUFFER structure pool.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>
=======
---
UID: NF:ndis.NdisGetPoolFromNetBuffer
title: NdisGetPoolFromNetBuffer function (ndis.h)
description: Call the NdisGetPoolFromNetBuffer function to get the NET_BUFFER structure pool handle that is associated with a specified NET_BUFFER structure.
old-location: netvista\ndisgetpoolfromnetbuffer.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NdisGetPoolFromNetBuffer function"]
ms.keywords: NdisGetPoolFromNetBuffer, NdisGetPoolFromNetBuffer function [Network Drivers Starting with Windows Vista], ndis/NdisGetPoolFromNetBuffer, ndis_netbuf_functions_ref_ae9f36c7-ab1c-4ea4-9721-2fd15aabc667.xml, netvista.ndisgetpoolfromnetbuffer
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
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisGetPoolFromNetBuffer
 - ndis/NdisGetPoolFromNetBuffer
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
---

# NdisGetPoolFromNetBuffer function


## -description

Call the 
  <b>NdisGetPoolFromNetBuffer</b> function to get the 
  <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structure pool handle that is associated
  with a specified NET_BUFFER structure.

## -parameters

### -param NetBuffer 

[in]
A pointer to a previously allocated 
     <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structure.

## -returns

<b>NdisGetPoolFromNetBuffer</b> returns a handle to the NET_BUFFER structure pool that is associated with
     the specified NET_BUFFER structure.

## -remarks

The handle that 
    <b>NdisGetPoolFromNetBuffer</b> returns is a required parameter in calls to NDIS functions that manipulate    
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structures that are from the
    associated NET_BUFFER structure pool.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>
>>>>>>> release-iron:wdk-ddi-src/content/ndis/nf-ndis-ndisgetpoolfromnetbuffer.md
