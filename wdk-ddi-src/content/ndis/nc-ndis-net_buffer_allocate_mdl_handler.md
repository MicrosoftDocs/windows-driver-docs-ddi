---
UID: NC:ndis.NET_BUFFER_ALLOCATE_MDL_HANDLER
title: NET_BUFFER_ALLOCATE_MDL_HANDLER
author: windows-driver-content
description: The NetAllocateMdl function allocates an MDL with an associated memory block of a specified size.
old-location: netvista\netallocatemdl.htm
tech.root: netvista
ms.assetid: 14247f48-7ef8-481c-aa1e-e657475812fa
ms.date: 05/02/2018
ms.keywords: NET_BUFFER_ALLOCATE_MDL_HANDLER, NET_BUFFER_ALLOCATE_MDL_HANDLER callback, NetAllocateMdl, NetAllocateMdl callback function [Network Drivers Starting with Windows Vista], ndis/NetAllocateMdl, ndis_netbuf_functions_ref_d6801343-5c75-4328-b2d9-4b252afdfe15.xml, netvista.netallocatemdl
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
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
req.lib: 
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ndis.h
api_name:
-	NetAllocateMdl
product:
- Windows
targetos: Windows
req.typenames: 
---

# NET_BUFFER_ALLOCATE_MDL_HANDLER callback function


## -description


The 
  <i>NetAllocateMdl</i> function allocates an MDL with an associated memory block of a specified size.


## -parameters




### -param BufferSize [in]

The size of the memory block, in bytes. When calling 
     <i>NetAllocateMdl</i>, NDIS passes in the requested size.


## -returns



<i>NetAllocateMdl</i> returns a pointer to the allocated MDL. If the allocation fails, the return value
     is <b>NULL</b>.




## -remarks



If the NDIS driver specifies an entry point for the 
    <i>NetAllocateMdl</i> function at the 
    <i>AllocateMdl</i> parameter of the 
    <a href="https://msdn.microsoft.com/4b58a1dc-8a5a-464b-a2a2-deb952febe25">
    NdisRetreatNetBufferDataStart</a> function, NDIS calls 
    <i>NetAllocateMdl</i> to allocate an MDL and memory.

NDIS specifies the size of the associated memory block at 
    <i>BufferSize</i> .

<i>NetAllocateMdl</i> can use any allocation method that meets the driver's design requirements. When NDIS
    calls the 
    <a href="https://msdn.microsoft.com/a92b2de9-231d-4dcc-8220-857063a35eb1">NetFreeMdl</a> function to free the memory, the
    NDIS driver should free the memory by using the same memory management mechanism that it used to allocate
    the memory.

NDIS calls 
    <i>NetAllocateMdl</i> at IRQL &lt;= DISPATCH_LEVEL.




## -see-also




<a href="https://msdn.microsoft.com/4b58a1dc-8a5a-464b-a2a2-deb952febe25">
   NdisRetreatNetBufferDataStart</a>



<a href="https://msdn.microsoft.com/a92b2de9-231d-4dcc-8220-857063a35eb1">NetFreeMdl</a>
 

 

