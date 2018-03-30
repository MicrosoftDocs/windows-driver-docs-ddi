---
UID: NF:ndis.NdisRetreatNetBufferDataStart
title: NdisRetreatNetBufferDataStart function
author: windows-driver-content
description: Call the NdisRetreatNetBufferDataStart function to access more used data space in the MDL chain of a NET_BUFFER structure.
old-location: netvista\ndisretreatnetbufferdatastart.htm
old-project: netvista
ms.assetid: 4b58a1dc-8a5a-464b-a2a2-deb952febe25
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisRetreatNetBufferDataStart, NdisRetreatNetBufferDataStart function [Network Drivers Starting with Windows Vista], ndis/NdisRetreatNetBufferDataStart, ndis_netbuf_functions_ref_1075cc2e-490a-4b90-93d9-269e226e8dde.xml, netvista.ndisretreatnetbufferdatastart
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
-	NdisRetreatNetBufferDataStart
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisRetreatNetBufferDataStart function


## -description


Call the 
  <b>NdisRetreatNetBufferDataStart</b> function to access more 
  <i>used data space</i> in the MDL chain of a 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structure.


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
     <a href="https://msdn.microsoft.com/14247f48-7ef8-481c-aa1e-e657475812fa">NetAllocateMdl</a> function. If the caller
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
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structure.

If there isn't enough 
    <i>unused data space</i>, this function allocates a new buffer and an MDL to describe the new buffer and
    chains the new MDL to the beginning of the MDL chain. NDIS calls the 
    <a href="https://msdn.microsoft.com/14247f48-7ef8-481c-aa1e-e657475812fa">NetAllocateMdl</a> function specified at 
    <i>AllocateMdl</i> to allocate the MDL and memory. The 
    <i>NetAllocateMdl</i> function can use any allocation method that meets the
    driver's design requirements.

Call the 
    <a href="https://msdn.microsoft.com/49b69282-137d-4bb5-92f5-4d27cedbb6d4">
    NdisAdvanceNetBufferDataStart</a> function to release the 
    <i>used data space</i> that was added with 
    <b>NdisRetreatNetBufferDataStart</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a>



<a href="https://msdn.microsoft.com/49b69282-137d-4bb5-92f5-4d27cedbb6d4">
   NdisAdvanceNetBufferDataStart</a>



<a href="https://msdn.microsoft.com/14247f48-7ef8-481c-aa1e-e657475812fa">NetAllocateMdl</a>
 

 

<<<<<<< HEAD
=======
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisRetreatNetBufferDataStart function%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

>>>>>>> parent of 2d896a8e266... Added changes
