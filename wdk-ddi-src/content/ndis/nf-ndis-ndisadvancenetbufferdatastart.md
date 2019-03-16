---
UID: NF:ndis.NdisAdvanceNetBufferDataStart
title: NdisAdvanceNetBufferDataStart function (ndis.h)
description: Call the NdisAdvanceNetBufferDataStart function to release the used data space that was added with the NdisRetreatNetBufferDataStart function.
old-location: netvista\ndisadvancenetbufferdatastart.htm
tech.root: netvista
ms.assetid: 49b69282-137d-4bb5-92f5-4d27cedbb6d4
ms.date: 05/02/2018
ms.keywords: NdisAdvanceNetBufferDataStart, NdisAdvanceNetBufferDataStart function [Network Drivers Starting with Windows Vista], ndis/NdisAdvanceNetBufferDataStart, ndis_netbuf_functions_ref_b03aee2c-859d-425f-9b07-91b324505ff4.xml, netvista.ndisadvancenetbufferdatastart
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
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisAdvanceNetBufferDataStart
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisAdvanceNetBufferDataStart function


## -description


Call the 
  <b>NdisAdvanceNetBufferDataStart</b> function to release the 
  <i>used data space</i> that was added with the 
  <a href="https://msdn.microsoft.com/4b58a1dc-8a5a-464b-a2a2-deb952febe25">
  NdisRetreatNetBufferDataStart</a> function.


## -parameters




### -param NetBuffer [in]

A pointer to a previously allocated 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structure.


### -param DataOffsetDelta [in]

The amount of 
     <i>used data space</i> to release. NDIS adjusts the value of the 
     <b>DataOffset</b> member of the NET_BUFFER structure accordingly.


### -param FreeMdl [in]

A BOOLEAN value that, if <b>TRUE</b>, requests NDIS to free any MDLs that become unused in the advance
     operation. If 
     <i>FreeMdl</i> is <b>FALSE</b>, NDIS retains unused MDLs for use in subsequent retreat operations.


### -param FreeMdlHandler [in, optional]

An optional entry point for an 
     <a href="https://msdn.microsoft.com/a92b2de9-231d-4dcc-8220-857063a35eb1">NetFreeMdl</a> function. If the caller
     specifies an entry point for the 
     <i>NetFreeMdl</i> function, NDIS calls 
     <i>NetFreeMdl</i> to free an MDL and memory.


## -returns



None




## -remarks



If NDIS allocated memory to satisfy a corresponding call to the 
    <a href="https://msdn.microsoft.com/4b58a1dc-8a5a-464b-a2a2-deb952febe25">
    NdisRetreatNetBufferDataStart</a> function, then 
    <b>NdisAdvanceNetBufferDataStart</b> frees the memory that 
    <b>NdisRetreatNetBufferDataStart</b> allocated. Otherwise, the memory remains in the MDL and only the
    value of the 
    <b>DataOffset</b> member of the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structure is modified.

NDIS calls the 
    <a href="https://msdn.microsoft.com/a92b2de9-231d-4dcc-8220-857063a35eb1">NetFreeMdl</a> function specified at 
    <i>FreeMdl</i> if 
    <b>NdisAdvanceNetBufferDataStart</b> must free memory. NDIS calls 
    <i>NetFreeMdl</i> only to free the MDLs and memory that the driver allocated in the 
    <a href="https://msdn.microsoft.com/14247f48-7ef8-481c-aa1e-e657475812fa">NetAllocateMdl</a> function.

When protocol drivers call 
    <b>NdisAdvanceNetBufferDataStart</b> on the receive path to access the various transport headers, the MDL
    chain should not be modified and 
    <i>FreeMdl</i> is <b>FALSE</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a>



<a href="https://msdn.microsoft.com/4b58a1dc-8a5a-464b-a2a2-deb952febe25">
   NdisRetreatNetBufferDataStart</a>



<a href="https://msdn.microsoft.com/14247f48-7ef8-481c-aa1e-e657475812fa">NetAllocateMdl</a>



<a href="https://msdn.microsoft.com/a92b2de9-231d-4dcc-8220-857063a35eb1">NetFreeMdl</a>
 

 

