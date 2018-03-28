---
UID: NF:ndis.NdisAllocateNetBuffer
title: NdisAllocateNetBuffer function
author: windows-driver-content
description: Call the NdisAllocateNetBuffer function to allocate and initialize a NET_BUFFER structure from a NET_BUFFER structure pool.
old-location: netvista\ndisallocatenetbuffer.htm
old-project: netvista
ms.assetid: b10c5a4b-fb43-4880-9641-ff2dcf0e5cb3
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NdisAllocateNetBuffer, NdisAllocateNetBuffer function [Network Drivers Starting with Windows Vista], ndis/NdisAllocateNetBuffer, ndis_netbuf_functions_ref_2c90427d-c174-48fa-b588-d48e5c099331.xml, netvista.ndisallocatenetbuffer
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
req.ddi-compliance: Irql_NetBuffer_Function, NdisAllocateNetBuffer
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
-	NdisAllocateNetBuffer
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisAllocateNetBuffer function


## -description


Call the 
  <b>NdisAllocateNetBuffer</b> function to allocate and initialize a 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structure from a <b>NET_BUFFER</b> structure
  pool.


## -parameters




### -param PoolHandle [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structure pool handle that was previously returned from a call to 
     <a href="https://msdn.microsoft.com/bc27758a-a793-48a1-a6ab-bd193aa9c61a">
     NdisAllocateNetBufferPool</a>.


### -param MdlChain [in, optional]

A pointer to an MDL chain that NDIS uses to initialize the new <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structure. 
     <i>MdlChain</i> can be <b>NULL</b>.


### -param DataOffset [in]

The initial offset, in bytes, from the start of the buffer to the start of the 
     <i>used data space</i> in the MDL chain. Data space ahead of this offset is 
     <i>unused data space</i>. Therefore, this value also represents the initial amount of available backfill
     space in the MDL chain. If 
     <i>MdlChain</i> is <b>NULL</b>, 
     <i>DataOffset</i> must be 0.


### -param DataLength [in]

The length of the 
     <i>used data space</i>, in bytes, in the MDL chain. If 
     <i>MdlChain</i> is <b>NULL</b>, 
     <i>DataLength</i> must be 0.


## -returns



<b>NdisAllocateNetBuffer</b> returns a pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structure that NDIS allocated. If the
     allocation was unsuccessful, this pointer is <b>NULL</b>.




## -remarks



Call 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff562582">NdisFreeNetBuffer</a> to free a 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structure that was allocated from a
    <b>NET_BUFFER</b> structure pool.

<div class="alert"><b>Note</b>  <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> and 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures must be allocated
    from an NDIS buffer pool. A driver must not allocate and initialize a <b>NET_BUFFER</b> or <b>NET_BUFFER_LIST</b>
    structure from its private memory pool or the stack.</div>
<div> </div>
The preallocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> can be reused by reinitializing it with another MDL chain when it owns
    <b>NET_BUFFER</b>, but the 
    <i>DataOffset</i>, 
    <i>DataLength</i>, 
    <i>CurrentMdl</i>, and 
    <i>CurrentMdlOffset</i> fields in <b>NET_BUFFER</b> must be consistent with the new MDL chain.

For example, if the original MDL chain contains <i>X</i>
<i>DataLength</i> and <i>Y</i>
<i>DataOffset</i>, and 
    <i>CurrentMdl</i> starts with the second MDL (<i>M</i>) in the original MDL chain, 
    <i>CurrentMdlOffset</i> is <i>Z</i>. The 
    <i>MdlChain</i> field in <a href="https://msdn.microsoft.com/library/windows/hardware/ff568381">NET_BUFFER_DATA</a> then needs to point to a new MDL chain that contains <i>X'</i>
<i>DataLength</i> and <i>Y'</i>
<i>DataOffset</i>. If 
    <i>CurrentMdl</i> starts with the third MDL (<i>M'</i>) in the new MDL chain, 
    <i>CurrentMdlOffset</i> is <i>Z'</i>, and the following macros need to be used to set fields in <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a>:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NET_BUFFER_FIRST_MDL(_NB) = New MDL chain;
NET_BUFFER_DATA_LENGTH(_NB) = X';
NET_BUFFER_DATA_OFFSET(_NB) = Y';
NET_BUFFER_CURRENT_MDL(_NB) = M';
NET_BUFFER_CURRENT_MDL_OFFSET(_NB) = Z';</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561613">NdisAllocateNetBufferPool</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562582">NdisFreeNetBuffer</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisAllocateNetBuffer function%20 RELEASE:%20(3/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

