---
UID: NF:ndis.NdisAdvanceNetBufferDataStart
title: NdisAdvanceNetBufferDataStart function
author: windows-driver-content
description: Call the NdisAdvanceNetBufferDataStart function to release the used data space that was added with the NdisRetreatNetBufferDataStart function.
old-location: netvista\ndisadvancenetbufferdatastart.htm
old-project: netvista
ms.assetid: 49b69282-137d-4bb5-92f5-4d27cedbb6d4
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: NdisAdvanceNetBufferDataStart, NdisAdvanceNetBufferDataStart function [Network Drivers Starting with Windows Vista], ndis/NdisAdvanceNetBufferDataStart, ndis_netbuf_functions_ref_b03aee2c-859d-425f-9b07-91b324505ff4.xml, netvista.ndisadvancenetbufferdatastart
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
-	NdisAdvanceNetBufferDataStart
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisAdvanceNetBufferDataStart function


## -description


Call the 
  <b>NdisAdvanceNetBufferDataStart</b> function to release the 
  <i>used data space</i> that was added with the 
  <a href="..\ndis\nf-ndis-ndisretreatnetbufferdatastart.md">
  NdisRetreatNetBufferDataStart</a> function.


## -syntax


````
VOID NdisAdvanceNetBufferDataStart(
  _In_     PNET_BUFFER                 NetBuffer,
  _In_     ULONG                       DataOffsetDelta,
  _In_     BOOLEAN                     FreeMdl,
  _In_opt_ NET_BUFFER_FREE_MDL_HANDLER FreeMdlHandler
);
````


## -parameters




### -param NetBuffer [in]

A pointer to a previously allocated 
     <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> structure.


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
     <a href="..\ndis\nc-ndis-net_buffer_free_mdl_handler.md">NetFreeMdl</a> function. If the caller
     specifies an entry point for the 
     <i>NetFreeMdl</i> function, NDIS calls 
     <i>NetFreeMdl</i> to free an MDL and memory.


## -returns



None




## -remarks



If NDIS allocated memory to satisfy a corresponding call to the 
    <a href="..\ndis\nf-ndis-ndisretreatnetbufferdatastart.md">
    NdisRetreatNetBufferDataStart</a> function, then 
    <b>NdisAdvanceNetBufferDataStart</b> frees the memory that 
    <b>NdisRetreatNetBufferDataStart</b> allocated. Otherwise, the memory remains in the MDL and only the
    value of the 
    <b>DataOffset</b> member of the 
    <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> structure is modified.

NDIS calls the 
    <a href="..\ndis\nc-ndis-net_buffer_free_mdl_handler.md">NetFreeMdl</a> function specified at 
    <i>FreeMdl</i> if 
    <b>NdisAdvanceNetBufferDataStart</b> must free memory. NDIS calls 
    <i>NetFreeMdl</i> only to free the MDLs and memory that the driver allocated in the 
    <a href="..\ndis\nc-ndis-net_buffer_allocate_mdl_handler.md">NetAllocateMdl</a> function.

When protocol drivers call 
    <b>NdisAdvanceNetBufferDataStart</b> on the receive path to access the various transport headers, the MDL
    chain should not be modified and 
    <i>FreeMdl</i> is <b>FALSE</b>.




## -see-also

<a href="..\ndis\nc-ndis-net_buffer_free_mdl_handler.md">NetFreeMdl</a>



<a href="..\ndis\nc-ndis-net_buffer_allocate_mdl_handler.md">NetAllocateMdl</a>



<a href="..\ndis\nf-ndis-ndisretreatnetbufferdatastart.md">
   NdisRetreatNetBufferDataStart</a>



<a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisAdvanceNetBufferDataStart function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

