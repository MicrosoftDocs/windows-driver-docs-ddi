---
UID: NF:ndis.NdisRetreatNetBufferListDataStart
title: NdisRetreatNetBufferListDataStart function
author: windows-driver-content
description: Call the NdisRetreatNetBufferListDataStart function to increase the used data space in all the NET_BUFFER structures in a NET_BUFFER_LIST structure.
old-location: netvista\ndisretreatnetbufferlistdatastart.htm
tech.root: netvista
ms.assetid: 76a1294f-d098-4751-9b59-923993379c6e
ms.date: 5/2/2018
ms.keywords: NdisRetreatNetBufferListDataStart, NdisRetreatNetBufferListDataStart function [Network Drivers Starting with Windows Vista], ndis/NdisRetreatNetBufferListDataStart, ndis_netbuf_functions_ref_9a59d1c8-f5b1-490b-b091-84c709b82605.xml, netvista.ndisretreatnetbufferlistdatastart
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
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisRetreatNetBufferListDataStart function


## -description


Call the 
  <b>NdisRetreatNetBufferListDataStart</b> function to increase the 
  <i>used data space</i> in all the 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structures in a 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure.


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
     <a href="https://msdn.microsoft.com/14247f48-7ef8-481c-aa1e-e657475812fa">NetAllocateMdl</a> function. If the caller
     specifies an entry point for the 
     <i>NetAllocateMdl</i> function, NDIS calls 
     <i>NetAllocateMdl</i> to allocate an MDL and memory.


### -param FreeMdlHandler [in, optional]

An optional entry point for an 
     <a href="https://msdn.microsoft.com/a92b2de9-231d-4dcc-8220-857063a35eb1">NetFreeMdl</a> function. If the caller
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
    <a href="https://msdn.microsoft.com/4b58a1dc-8a5a-464b-a2a2-deb952febe25">
    NdisRetreatNetBufferDataStart</a> function for every 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structure on the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure. 
    <b>NdisRetreatNetBufferListDataStart</b> attempts to satisfy the request by reducing the value of the 
    <b>DataOffset</b> member in every NET_BUFFER structure. If there is not enough 
    <i>unused data space</i> available, this function allocates a new buffer and MDL, and then chains the new
    MDL to the beginning of the MDL chain on the NET_BUFFER structure.

Call the 
    <a href="https://msdn.microsoft.com/819ac05b-15c2-4a24-ae6b-8a47991a4e7a">
    NdisAdvanceNetBufferListDataStart</a> function to release data space that was claimed in a previous 
    <b>NdisRetreatNetBufferListDataStart</b> call. Alternatively, the driver can call the 
    <a href="https://msdn.microsoft.com/49b69282-137d-4bb5-92f5-4d27cedbb6d4">
    NdisAdvanceNetBufferDataStart</a> function for each NET_BUFFER structure on the NET_BUFFER_LIST
    structure. Calling 
    <b>NdisAdvanceNetBufferListDataStart</b> is more efficient.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>



<a href="https://msdn.microsoft.com/49b69282-137d-4bb5-92f5-4d27cedbb6d4">
   NdisAdvanceNetBufferDataStart</a>



<a href="https://msdn.microsoft.com/819ac05b-15c2-4a24-ae6b-8a47991a4e7a">
   NdisAdvanceNetBufferListDataStart</a>



<a href="https://msdn.microsoft.com/4b58a1dc-8a5a-464b-a2a2-deb952febe25">
   NdisRetreatNetBufferDataStart</a>



<a href="https://msdn.microsoft.com/14247f48-7ef8-481c-aa1e-e657475812fa">NetAllocateMdl</a>



<a href="https://msdn.microsoft.com/a92b2de9-231d-4dcc-8220-857063a35eb1">NetFreeMdl</a>
 

 

