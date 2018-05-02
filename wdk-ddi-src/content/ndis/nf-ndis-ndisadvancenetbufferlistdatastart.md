---
UID: NF:ndis.NdisAdvanceNetBufferListDataStart
title: NdisAdvanceNetBufferListDataStart function
author: windows-driver-content
description: Call the NdisAdvanceNetBufferListDataStart function to release data space that was claimed in previous calls to the NdisRetreatNetBufferListDataStart function.
old-location: netvista\ndisadvancenetbufferlistdatastart.htm
old-project: netvista
ms.assetid: 819ac05b-15c2-4a24-ae6b-8a47991a4e7a
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: NdisAdvanceNetBufferListDataStart, NdisAdvanceNetBufferListDataStart function [Network Drivers Starting with Windows Vista], ndis/NdisAdvanceNetBufferListDataStart, ndis_netbuf_functions_ref_6d98353d-427f-49ce-9b28-e1c178a8af24.xml, netvista.ndisadvancenetbufferlistdatastart
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
-	NdisAdvanceNetBufferListDataStart
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisAdvanceNetBufferListDataStart function


## -description


Call the 
  <b>NdisAdvanceNetBufferListDataStart</b> function to release data space that was claimed in previous calls
  to the 
  <a href="https://msdn.microsoft.com/76a1294f-d098-4751-9b59-923993379c6e">
  NdisRetreatNetBufferListDataStart</a> function.


## -parameters




### -param NetBufferList [in]

A pointer to a previously allocated 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure.


### -param DataOffsetDelta [in]

The amount of 
     <i>used data space</i> to release.


### -param FreeMdl [in]

If <b>TRUE</b> and NDIS allocated memory to satisfy the corresponding 
     <b>NdisRetreatNetBufferListDataStart</b> call, this function frees the memory that was allocated and the
     associated MDL.


### -param FreeMdlMdlHandler

TBD




#### - FreeMdlHandler [in, optional]

An optional entry point for an 
     <a href="https://msdn.microsoft.com/a92b2de9-231d-4dcc-8220-857063a35eb1">NetFreeMdl</a> function. If the caller
     specifies an entry point for the 
     <i>NetFreeMdl</i> function, NDIS calls 
     <i>NetFreeMdl</i> to free an MDL and memory.


## -returns



None




## -remarks



<b>NdisAdvanceNetBufferListDataStart</b> releases 
    <i>used data space</i> for all the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structures in a 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure. If 
    <i>FreeMdl</i> is <b>TRUE</b> and 
    <a href="https://msdn.microsoft.com/76a1294f-d098-4751-9b59-923993379c6e">
    NdisRetreatNetBufferListDataStart</a> allocated memory to satisfy the corresponding allocation request,
    
    <b>NdisAdvanceNetBufferListDataStart</b> frees the allocated memory. Calling this function is equivalent
    to calling 
    <a href="https://msdn.microsoft.com/49b69282-137d-4bb5-92f5-4d27cedbb6d4">
    NdisAdvanceNetBufferDataStart</a> for every NET_BUFFER structure on the NET_BUFFER_LIST structure.
    However, calling 
    <b>NdisAdvanceNetBufferListDataStart</b> is more efficient.

When protocol drivers call 
    <b>NdisAdvanceNetBufferListDataStart</b> on the receive path to access the various transport headers, the
    MDL chain should not be modified and 
    <i>FreeMdl</i> is <b>FALSE</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>



<a href="https://msdn.microsoft.com/49b69282-137d-4bb5-92f5-4d27cedbb6d4">
   NdisAdvanceNetBufferDataStart</a>



<a href="https://msdn.microsoft.com/76a1294f-d098-4751-9b59-923993379c6e">
   NdisRetreatNetBufferListDataStart</a>



<a href="https://msdn.microsoft.com/14247f48-7ef8-481c-aa1e-e657475812fa">NetAllocateMdl</a>



<a href="https://msdn.microsoft.com/a92b2de9-231d-4dcc-8220-857063a35eb1">NetFreeMdl</a>
 

 

