---
UID: NF:ndis.NdisRetreatNetBufferDataStart
title: NdisRetreatNetBufferDataStart function (ndis.h)
description: Call the NdisRetreatNetBufferDataStart function to access more used data space in the MDL chain of a NET_BUFFER structure.
old-location: netvista\ndisretreatnetbufferdatastart.htm
tech.root: netvista
ms.assetid: 4b58a1dc-8a5a-464b-a2a2-deb952febe25
ms.date: 05/02/2018
ms.keywords: NdisRetreatNetBufferDataStart, NdisRetreatNetBufferDataStart function [Network Drivers Starting with Windows Vista], ndis/NdisRetreatNetBufferDataStart, ndis_netbuf_functions_ref_1075cc2e-490a-4b90-93d9-269e226e8dde.xml, netvista.ndisretreatnetbufferdatastart
f1_keywords:
 - "ndis/NdisRetreatNetBufferDataStart"
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
- NdisRetreatNetBufferDataStart
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisRetreatNetBufferDataStart function


## -description


Call the 
  <b>NdisRetreatNetBufferDataStart</b> function to access more 
  <i>used data space</i> in the MDL chain of a 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structure.


## -parameters




### -param NetBuffer [in]

A pointer to a previously allocated NET_BUFFER structure.


### -param DataOffsetDelta [in]

The amount of 
     <i>used data space</i> to add. NDIS adjusts the 
     <b>DataOffset</b> member of the NET_BUFFER structure accordingly. If there is not enough 
     <i>unused data space</i> to satisfy the request, NDIS allocates additional memory.


### -param DataBackFill [in]

If NDIS must allocate memory, this parameter specifies the amount of data space, in addition to
     the value of the 
     <i>DataOffsetDelta</i> parameter, to allocate.


### -param AllocateMdlHandler [in, optional]

An optional entry point for an 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-net_buffer_allocate_mdl_handler">NetAllocateMdl</a> function. If the caller
     specifies an entry point for the 
     <i>NetAllocateMdl</i> function, NDIS calls 
     <i>NetAllocateMdl</i> to allocate an MDL and memory.


## -returns



<b>NdisRetreatNetBufferDataStart</b> returns one of the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
<b>NdisRetreatNetBufferDataStart</b> successfully allocated 
       <i>used data space</i> either by using the 
       <i>unused data space</i> or by allocating new storage.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
<b>NdisRetreatNetBufferDataStart</b> failed due to insufficient resources.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>
</td>
<td width="60%">
<b>NdisRetreatNetBufferDataStart</b> failed for reasons other than insufficient resources.

</td>
</tr>
</table>
 




## -remarks



<b>NdisRetreatNetBufferDataStart</b> attempts to satisfy the request by reducing the value of the 
    <b>DataOffset</b> member of the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> structure.

If there isn't enough 
    <i>unused data space</i>, this function allocates a new buffer and an MDL to describe the new buffer and
    chains the new MDL to the beginning of the MDL chain. NDIS calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-net_buffer_allocate_mdl_handler">NetAllocateMdl</a> function specified at 
    <i>AllocateMdl</i> to allocate the MDL and memory. The 
    <i>NetAllocateMdl</i> function can use any allocation method that meets the
    driver's design requirements.

Call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisadvancenetbufferdatastart">
    NdisAdvanceNetBufferDataStart</a> function to release the 
    <i>used data space</i> that was added with 
    <b>NdisRetreatNetBufferDataStart</b>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisadvancenetbufferdatastart">
   NdisAdvanceNetBufferDataStart</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-net_buffer_allocate_mdl_handler">NetAllocateMdl</a>
 

 

