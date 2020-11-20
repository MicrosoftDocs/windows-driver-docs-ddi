---
UID: NF:fwpsk.FwpsAllocateCloneNetBufferList0
title: FwpsAllocateCloneNetBufferList0 function (fwpsk.h)
description: The FwpsAllocateCloneNetBufferList0 function allocates a NET_BUFFER_LIST structure that is a clone of an existing NET_BUFFER_LIST structure.Note  FwpsAllocateCloneNetBufferList0 is a specific version of FwpsAllocateCloneNetBufferList.
old-location: netvista\fwpsallocateclonenetbufferlist0.htm
tech.root: netvista
ms.assetid: 72759748-fac6-45b9-9a81-ab71e6e7c3ef
ms.date: 05/02/2018
keywords: ["FwpsAllocateCloneNetBufferList0 function"]
ms.keywords: FwpsAllocateCloneNetBufferList0, FwpsAllocateCloneNetBufferList0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsAllocateCloneNetBufferList0, netvista.fwpsallocateclonenetbufferlist0, wfp_ref_2_funct_3_fwps_A-B_1b361080-1a63-485a-89fc-05ef6b0cb1df.xml
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Fwpkclnt.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FwpsAllocateCloneNetBufferList0
 - fwpsk/FwpsAllocateCloneNetBufferList0
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - fwpkclnt.lib
 - fwpkclnt.dll
api_name:
 - FwpsAllocateCloneNetBufferList0
---

# FwpsAllocateCloneNetBufferList0 function


## -description

The 
  <b>FwpsAllocateCloneNetBufferList0</b> function allocates a 
  <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structure that is a clone of an existing
  <b>NET_BUFFER_LIST</b> structure.
<div class="alert"><b>Note</b>  <b>FwpsAllocateCloneNetBufferList0</b> is a specific version of <b>FwpsAllocateCloneNetBufferList</b>. See <a href="/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -parameters

### -param originalNetBufferList 

[in, out]
A pointer to the original 
     <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structure that is being
     cloned.

### -param netBufferListPoolHandle 

[in, optional]
A 
     <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> pool handle that was
     obtained from a previous call to the 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferlistpool">
     NdisAllocateNetBufferListPool</a> function. This parameter is optional and can be <b>NULL</b>.

### -param netBufferPoolHandle 

[in, optional]
A 
     <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> pool handle that was obtained from a
     previous call to the 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferpool">NdisAllocateNetBufferPool</a> function. This parameter is optional and can be <b>NULL</b>.

### -param allocateCloneFlags 

[in]
There are currently no flags defined for this function. Callout drivers should set this parameter
     to zero.

### -param netBufferList 

[out]
A pointer to a variable that receives a pointer to the clone 
     <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structure.

## -returns

The 
     <b>FwpsAllocateCloneNetBufferList0</b> function returns one of the following NTSTATUS codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The clone 
       <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structure was
       successfully allocated.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Other status codes</b></dt>
</dl>
</td>
<td width="60%">
An error occurred.

</td>
</tr>
</table>

## -remarks

A callout driver calls the 
    <b>FwpsAllocateCloneNetBufferList0</b> function to allocate a clone 
    <a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a> structure of an existing
    NET_BUFFER_LIST structure.

This function is a wrapper around the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocateclonenetbufferlist">
    NdisAllocateCloneNetBufferList</a> function, but it is specialized for use by WFP 
    <a href="/windows-hardware/drivers/network/packet-injection-functions">packet injection functions</a>.

If the clone NET_BUFFER_LIST structure should have attributes that are associated with a specific pool,
    the callout driver must specify the pool handle in the 
    <i>NetBufferListPoolHandle</i> or 
    <i>NetBufferPoolHandle</i> parameter. If these parameters are <b>NULL</b>, the default pool preallocated by NDIS
    is used.

The clone NET_BUFFER_LIST structure describes the same data that is described by the original
    NET_BUFFER_LIST structure. The 
    <b>FwpsAllocateCloneNetBufferList0</b> function does not copy the data that is described by the original
    MDLs to new data buffers. Instead, the clone NET_BUFFER_LIST structure references the original data
    buffers. The clone NET_BUFFER_LIST structure does not include an initial 
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list_context">
    NET_BUFFER_LIST_CONTEXT</a> structure.

This function sets the 
    <b>ParentNetBufferList</b> member of the newly created clone NET_BUFFER_LIST structure to point to the
    parent NET_BUFFER_LIST structure. The parent structure's 
    <b>ChildRefCount</b> member is incremented by 1.

A callout driver can modify the clone NET_BUFFER_LIST structure and inject it into the network stack
    in place of the original NET_BUFFER_LIST structure by calling the 
    <a href="/windows-hardware/drivers/network/packet-injection-functions">packet injection functions</a>. After
    the data described by the clone NET_BUFFER_LIST structure has been successfully injected into the network
    stack, the callout driver frees the clone NET_BUFFER_LIST structure by calling the 
    <a href="/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsfreeclonenetbufferlist0">FwpsFreeCloneNetBufferList0</a> function.

A callout driver can insert or replace individual net buffers (<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>) or MDLs inside the clone net buffer
    list. Such a driver must also undo the modifications before it calls the 
    <a href="/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsfreeclonenetbufferlist0">
    FwpsFreeCloneNetBufferList0</a> function.

<h3><a id="Guidelines_for_Managing_Cloned_Packets"></a><a id="guidelines_for_managing_cloned_packets"></a><a id="GUIDELINES_FOR_MANAGING_CLONED_PACKETS"></a>Guidelines for Managing Cloned Packets</h3>
A callout driver must not hold cloned packets indefinitely. A cloned packet can interfere with power
     management operations on an idle computer.

The intended use for cloned packets in WFP is to get clarification from a user-mode application or
     other relatively fast operation. The callout driver must not hold cloned packets while, for example,
     waiting for user input, or waiting for web service clearance, or waiting for any other operation that
     might take an arbitrary amount of time.

If the callout driver needs to wait for a potentially lengthy operation, it makes a deep copy of
     the packet using 
     <a href="/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsallocatenetbufferandnetbufferlist0">
     FwpsAllocateNetBufferAndNetBufferList0</a>, and it blocks and absorbs the original packet.

Callout drivers should always return held packets as quickly as possible.

## -see-also

<a href="/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsfreeclonenetbufferlist0">FwpsFreeCloneNetBufferList0</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="/windows-hardware/drivers/ddi/nbl/ns-nbl-net_buffer_list">NET_BUFFER_LIST</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list_context">NET_BUFFER_LIST_CONTEXT</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferlistpool">
   NdisAllocateNetBufferListPool</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferpool">NdisAllocateNetBufferPool</a>



<a href="/windows-hardware/drivers/network/packet-injection-functions">Packet Injection Functions</a>