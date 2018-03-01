---
UID: NF:ndis.NdisRetreatNetBufferListDataStart
title: NdisRetreatNetBufferListDataStart function
author: windows-driver-content
description: Call the NdisRetreatNetBufferListDataStart function to increase the used data space in all the NET_BUFFER structures in a NET_BUFFER_LIST structure.
old-location: netvista\ndisretreatnetbufferlistdatastart.htm
old-project: netvista
ms.assetid: 76a1294f-d098-4751-9b59-923993379c6e
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: NdisRetreatNetBufferListDataStart, NdisRetreatNetBufferListDataStart function [Network Drivers Starting with Windows Vista], ndis/NdisRetreatNetBufferListDataStart, ndis_netbuf_functions_ref_9a59d1c8-f5b1-490b-b091-84c709b82605.xml, netvista.ndisretreatnetbufferlistdatastart
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
-	NdisRetreatNetBufferListDataStart
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisRetreatNetBufferListDataStart function


## -description


Call the 
  <b>NdisRetreatNetBufferListDataStart</b> function to increase the 
  <i>used data space</i> in all the 
  <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> structures in a 
  <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure.


## -syntax


````
NDIS_STATUS NdisRetreatNetBufferListDataStart(
  _In_     PNET_BUFFER_LIST                NetBufferList,
  _In_     ULONG                           DataOffsetDelta,
  _In_     ULONG                           DataBackFill,
  _In_opt_ NET_BUFFER_ALLOCATE_MDL_HANDLER AllocateMdlHandler,
  _In_opt_ NET_BUFFER_FREE_MDL_HANDLER     FreeMdlHandler
);
````


## -parameters




### -param NetBufferList [in]

A pointer to a previously allocated NET_BUFFER_LIST structure.


### -param DataOffsetDelta [in]

The amount of additional 
     <i>used data space</i> in each NET_BUFFER structure. If there is not enough 
     <i>unused data space</i> to satisfy the request, NDIS allocates more memory.


### -param DataBackFill [in]

If NDIS must allocate memory, this parameter specifies the amount of data space in addition to the
     value of the 
     <i>DataOffsetDelta</i> parameter to allocate.


### -param AllocateMdlHandler [in, optional]

An optional entry point for an 
     <a href="..\ndis\nc-ndis-net_buffer_allocate_mdl_handler.md">NetAllocateMdl</a> function. If the caller
     specifies an entry point for the 
     <i>NetAllocateMdl</i> function, NDIS calls 
     <i>NetAllocateMdl</i> to allocate an MDL and memory.


### -param FreeMdlHandler [in, optional]

An optional entry point for an 
     <a href="..\ndis\nc-ndis-net_buffer_free_mdl_handler.md">NetFreeMdl</a> function. If the caller
     specifies an entry point for the 
     <i>NetFreeMdl</i> function, NDIS calls 
     <i>NetFreeMdl</i> to free an MDL and memory.


## -returns



<b>NdisRetreatNetBufferListDataStart</b> returns one of the following:

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
<b>NdisRetreatNetBufferListDataStart</b> successfully allocated the data space on all the NET_BUFFER
       structures either by reducing the value of the 
       <b>DataOffset</b> member or by allocating new storage.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
<b>NdisRetreatNetBufferListDataStart</b> failed due to insufficient resources.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>
</td>
<td width="60%">
<b>NdisRetreatNetBufferListDataStart</b> failed for reasons other than insufficient resources.

</td>
</tr>
</table>
 




## -remarks



Calling 
    <b>NdisRetreatNetBufferListDataStart</b> is the equivalent of calling the 
    <a href="..\ndis\nf-ndis-ndisretreatnetbufferdatastart.md">
    NdisRetreatNetBufferDataStart</a> function for every 
    <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> structure on the 
    <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure. 
    <b>NdisRetreatNetBufferListDataStart</b> attempts to satisfy the request by reducing the value of the 
    <b>DataOffset</b> member in every NET_BUFFER structure. If there is not enough 
    <i>unused data space</i> available, this function allocates a new buffer and MDL, and then chains the new
    MDL to the beginning of the MDL chain on the NET_BUFFER structure.

Call the 
    <a href="..\ndis\nf-ndis-ndisadvancenetbufferlistdatastart.md">
    NdisAdvanceNetBufferListDataStart</a> function to release data space that was claimed in a previous 
    <b>NdisRetreatNetBufferListDataStart</b> call. Alternatively, the driver can call the 
    <a href="..\ndis\nf-ndis-ndisadvancenetbufferdatastart.md">
    NdisAdvanceNetBufferDataStart</a> function for each NET_BUFFER structure on the NET_BUFFER_LIST
    structure. Calling 
    <b>NdisAdvanceNetBufferListDataStart</b> is more efficient.




## -see-also

<a href="..\ndis\nf-ndis-ndisadvancenetbufferlistdatastart.md">
   NdisAdvanceNetBufferListDataStart</a>



<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>



<a href="..\ndis\nc-ndis-net_buffer_free_mdl_handler.md">NetFreeMdl</a>



<a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a>



<a href="..\ndis\nc-ndis-net_buffer_allocate_mdl_handler.md">NetAllocateMdl</a>



<a href="..\ndis\nf-ndis-ndisretreatnetbufferdatastart.md">
   NdisRetreatNetBufferDataStart</a>



<a href="..\ndis\nf-ndis-ndisadvancenetbufferdatastart.md">
   NdisAdvanceNetBufferDataStart</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisRetreatNetBufferListDataStart function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

