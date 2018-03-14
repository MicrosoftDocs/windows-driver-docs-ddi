---
UID: NC:ndis.NET_BUFFER_ALLOCATE_MDL_HANDLER
title: NET_BUFFER_ALLOCATE_MDL_HANDLER
author: windows-driver-content
description: The NetAllocateMdl function allocates an MDL with an associated memory block of a specified size.
old-location: netvista\netallocatemdl.htm
old-project: netvista
ms.assetid: 14247f48-7ef8-481c-aa1e-e657475812fa
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NET_BUFFER_ALLOCATE_MDL_HANDLER, NetAllocateMdl, NetAllocateMdl callback function [Network Drivers Starting with Windows Vista], ndis/NetAllocateMdl, ndis_netbuf_functions_ref_d6801343-5c75-4328-b2d9-4b252afdfe15.xml, netvista.netallocatemdl
ms.prod: windows-hardware
ms.technology: windows-devices
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
product: Windows
targetos: Windows
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# NET_BUFFER_ALLOCATE_MDL_HANDLER callback


## -description


The 
  <i>NetAllocateMdl</i> function allocates an MDL with an associated memory block of a specified size.


## -prototype


````
NET_BUFFER_ALLOCATE_MDL_HANDLER NetAllocateMdl;

PMDL NetAllocateMdl(
  _In_ PULONG BufferSize
)
{ ... }
````


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
    <a href="..\ndis\nf-ndis-ndisretreatnetbufferdatastart.md">
    NdisRetreatNetBufferDataStart</a> function, NDIS calls 
    <i>NetAllocateMdl</i> to allocate an MDL and memory.

NDIS specifies the size of the associated memory block at 
    <i>BufferSize</i> .

<i>NetAllocateMdl</i> can use any allocation method that meets the driver's design requirements. When NDIS
    calls the 
    <a href="..\ndis\nc-ndis-net_buffer_free_mdl_handler.md">NetFreeMdl</a> function to free the memory, the
    NDIS driver should free the memory by using the same memory management mechanism that it used to allocate
    the memory.

NDIS calls 
    <i>NetAllocateMdl</i> at IRQL &lt;= DISPATCH_LEVEL.




## -see-also

<a href="..\ndis\nc-ndis-net_buffer_free_mdl_handler.md">NetFreeMdl</a>



<a href="..\ndis\nf-ndis-ndisretreatnetbufferdatastart.md">
   NdisRetreatNetBufferDataStart</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NET_BUFFER_ALLOCATE_MDL_HANDLER callback function%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

