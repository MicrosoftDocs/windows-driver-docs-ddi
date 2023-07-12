---
UID: NF:fwpsk.FwpsAllocateDeepCloneNetBufferList0
tech.root: netvista
title: FwpsAllocateDeepCloneNetBufferList0
ms.date: 07/10/2023
targetos: Windows
description: The FwpsAllocateDeepCloneNetBufferList0 function allocates a NET_BUFFER_LIST structure that is a deep clone of an existing NET_BUFFER_LIST structure.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: fwpsk.h
req.idl: 
req.include-header: Fwpsk.h
req.irql: <= DISPATCH_LEVEL
req.kmdf-ver: 
req.lib: Fwpkclnt.lib
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: WIP build 25324
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
 - fwpsk.h
api_name:
 - FwpsAllocateDeepCloneNetBufferList0
f1_keywords:
 - FwpsAllocateDeepCloneNetBufferList0
 - fwpsk/FwpsAllocateDeepCloneNetBufferList0
dev_langs:
 - c++
helpviewer_keywords:
 - FwpsAllocateDeepCloneNetBufferList0
---

## -description

The **FwpsAllocateDeepCloneNetBufferList0** function allocates a [**NET_BUFFER_LIST**](../nbl/ns-nbl-net_buffer_list.md) structure that is a deep clone of an existing **NET_BUFFER_LIST** structure.

## -parameters

### -param originalNetBufferList [in, out]

A pointer to the original [**NET_BUFFER_LIST**](../nbl/ns-nbl-net_buffer_list.md) structure that is being cloned.

### -param netBufferListPoolHandle [in, optional]

A [**NET_BUFFER_LIST**](../nbl/ns-nbl-net_buffer_list.md) pool handle that was obtained from a previous call to the [**NdisAllocateNetBufferListPool**](../nblapi/nf-nblapi-ndisallocatenetbufferlistpool.md) function. This parameter is optional and can be **NULL**.

### -param netBufferPoolHandle [in, optional]

A [**NET_BUFFER_LIST**](../nbl/ns-nbl-net_buffer_list.md) pool handle that was obtained from a previous call to the [**NdisAllocateNetBufferPool**](../ndis/nf-ndis-ndisallocatenetbufferpool.md) function. This parameter is optional and can be **NULL**.

### -param netBufferList [out]

A pointer to a variable that receives a pointer to the deep clone [**NET_BUFFER_LIST**](../nbl/ns-nbl-net_buffer_list.md) structure.

## -returns

The **FwpsAllocateDeepCloneNetBufferList0** function returns one of the following NTSTATUS codes.

|Return code|Description|
|--- |--- |
|**STATUS_SUCCESS**|The deep clone [**NET_BUFFER_LIST**](../nbl/ns-nbl-net_buffer_list.md) structure was successfully allocated.|
|**Other status codes**|An error occurred.|

## -remarks

A callout driver calls the **FwpsAllocateDeepCloneNetBufferList0** function to allocate a deep clone [**NET_BUFFER_LIST**](../nbl/ns-nbl-net_buffer_list.md) structure of an existing **NET_BUFFER_LIST** structure.

This function is a wrapper around the [**NdisAllocateCloneNetBufferList**](../ndis/nf-ndis-ndisallocateclonenetbufferlist.md) function, but it is specialized for use by WFP [packet injection functions](/windows-hardware/drivers/network/packet-injection-functions).

If the deep clone **NET_BUFFER_LIST** structure should have attributes that are associated with a specific pool, the callout driver must specify the pool handle in the _NetBufferListPoolHandle_ or _NetBufferPoolHandle_ parameter. If these parameters are **NULL**, the default pool preallocated by NDIS is used.

The deep clone **NET_BUFFER_LIST** structure describes the same data that is described by the original **NET_BUFFER_LIST** structure. The **FwpsAllocateDeepCloneNetBufferList0** function copies the data that is described by the original MDLs to new data buffers. The clone **NET_BUFFER_LIST** structure includes an initial [**NET_BUFFER_LIST_CONTEXT**](../nbl/ns-nbl-net_buffer_list_context.md) structure.

This function sets the **ParentNetBufferList** member of the newly created clone **NET_BUFFER_LIST** structure to point to the parent **NET_BUFFER_LIST** structure. The parent structure's **ChildRefCount** member is incremented by **1**.

A callout driver can modify the clone **NET_BUFFER_LIST** structure and inject it into the network stack in place of the original **NET_BUFFER_LIST** structure by calling the [packet injection functions](/windows-hardware/drivers/network/packet-injection-functions). After the data described by the clone **NET_BUFFER_LIST** structure has been successfully injected into the network stack, the callout driver frees the clone **NET_BUFFER_LIST** structure by calling the [**FwpsFreeCloneNetBufferList0**](nf-fwpsk-fwpsfreeclonenetbufferlist0.md) function.

A callout driver can insert or replace individual net buffers ([**NET_BUFFER**](../nbl/ns-nbl-net_buffer.md)) or MDLs inside the deep clone **NET_BUFFER_LIST**. The driver must undo these modifications before it calls the [**FwpsFreeCloneNetBufferList0**](nf-fwpsk-fwpsfreeclonenetbufferlist0.md) function.

### Guidelines for managing cloned packets
A callout driver must not hold cloned packets indefinitely. A cloned packet can interfere with power management operations on an idle computer.

The intended use for deep cloned packets in WFP is to get clarification from a user-mode application or other relatively fast operation that needs a packet independent of the original. The callout driver must not hold cloned packets while waiting for user input, web service clearance, or any other operation that might take an arbitrary amount of time.

Callout drivers should always return held packets as quickly as possible.

## -see-also

[**FwpsFreeCloneNetBufferList0**](nf-fwpsk-fwpsfreeclonenetbufferlist0.md)

[**NET_BUFFER**](../nbl/ns-nbl-net_buffer.md)

[**NET_BUFFER_LIST**](../nbl/ns-nbl-net_buffer_list.md)

[**NET_BUFFER_LIST_CONTEXT**](../nbl/ns-nbl-net_buffer_list_context.md)

[**NdisAllocateNetBufferListPool**](../nblapi/nf-nblapi-ndisallocatenetbufferlistpool.md)

[**NdisAllocateNetBufferPool**](../ndis/nf-ndis-ndisallocatenetbufferpool.md)

[Packet injection functions](/windows-hardware/drivers/network/packet-injection-functions)
