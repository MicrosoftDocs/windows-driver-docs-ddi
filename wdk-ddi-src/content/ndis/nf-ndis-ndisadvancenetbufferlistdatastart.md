---
UID: NF:ndis.NdisAdvanceNetBufferListDataStart
title: NdisAdvanceNetBufferListDataStart function
author: windows-driver-content
description: Call the NdisAdvanceNetBufferListDataStart function to release data space that was claimed in previous calls to the NdisRetreatNetBufferListDataStart function.
old-location: netvista\ndisadvancenetbufferlistdatastart.htm
old-project: netvista
ms.assetid: 819ac05b-15c2-4a24-ae6b-8a47991a4e7a
ms.author: windowsdriverdev
ms.date: 2/27/2018
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
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisAdvanceNetBufferListDataStart function


## -description


Call the 
  <b>NdisAdvanceNetBufferListDataStart</b> function to release data space that was claimed in previous calls
  to the 
  <a href="..\ndis\nf-ndis-ndisretreatnetbufferlistdatastart.md">
  NdisRetreatNetBufferListDataStart</a> function.


## -syntax


````
VOID NdisAdvanceNetBufferListDataStart(
  _In_     PNET_BUFFER_LIST            NetBufferList,
  _In_     ULONG                       DataOffsetDelta,
  _In_     BOOLEAN                     FreeMdl,
  _In_opt_ NET_BUFFER_FREE_MDL_HANDLER FreeMdlHandler
);
````


## -parameters




### -param NetBufferList [in]

A pointer to a previously allocated 
     <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure.


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
     <a href="..\ndis\nc-ndis-net_buffer_free_mdl_handler.md">NetFreeMdl</a> function. If the caller
     specifies an entry point for the 
     <i>NetFreeMdl</i> function, NDIS calls 
     <i>NetFreeMdl</i> to free an MDL and memory.


## -returns



None




## -remarks



<b>NdisAdvanceNetBufferListDataStart</b> releases 
    <i>used data space</i> for all the 
    <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> structures in a 
    <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure. If 
    <i>FreeMdl</i> is <b>TRUE</b> and 
    <a href="..\ndis\nf-ndis-ndisretreatnetbufferlistdatastart.md">
    NdisRetreatNetBufferListDataStart</a> allocated memory to satisfy the corresponding allocation request,
    
    <b>NdisAdvanceNetBufferListDataStart</b> frees the allocated memory. Calling this function is equivalent
    to calling 
    <a href="..\ndis\nf-ndis-ndisadvancenetbufferdatastart.md">
    NdisAdvanceNetBufferDataStart</a> for every NET_BUFFER structure on the NET_BUFFER_LIST structure.
    However, calling 
    <b>NdisAdvanceNetBufferListDataStart</b> is more efficient.

When protocol drivers call 
    <b>NdisAdvanceNetBufferListDataStart</b> on the receive path to access the various transport headers, the
    MDL chain should not be modified and 
    <i>FreeMdl</i> is <b>FALSE</b>.




## -see-also

<a href="..\ndis\nc-ndis-net_buffer_allocate_mdl_handler.md">NetAllocateMdl</a>



<a href="..\ndis\nf-ndis-ndisadvancenetbufferdatastart.md">
   NdisAdvanceNetBufferDataStart</a>



<a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a>



<a href="..\ndis\nf-ndis-ndisretreatnetbufferlistdatastart.md">
   NdisRetreatNetBufferListDataStart</a>



<a href="..\ndis\nc-ndis-net_buffer_free_mdl_handler.md">NetFreeMdl</a>



<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisAdvanceNetBufferListDataStart function%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

