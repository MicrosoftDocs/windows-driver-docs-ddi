---
UID: NF:ndis.NdisGetDataBuffer
title: NdisGetDataBuffer function
author: windows-driver-content
description: Call the NdisGetDataBuffer function to gain access to a contiguous block of data from a NET_BUFFER structure.
old-location: netvista\ndisgetdatabuffer.htm
old-project: netvista
ms.assetid: 784d4c32-a517-4219-8e22-a998e0e66d69
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NdisGetDataBuffer, NdisGetDataBuffer function [Network Drivers Starting with Windows Vista], ndis/NdisGetDataBuffer, ndis_netbuf_functions_ref_b4ffded6-13c9-417d-bb03-a6421f718deb.xml, netvista.ndisgetdatabuffer
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
-	NdisGetDataBuffer
product:
- Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisGetDataBuffer function


## -description


Call the 
  <b>NdisGetDataBuffer</b> function to gain access to a contiguous block of data from a 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structure.


## -parameters




### -param NetBuffer [in]

A pointer to a NET_BUFFER structure.


### -param BytesNeeded [in]

The number of contiguous bytes of data requested.


### -param Storage [in, optional]

A pointer to a buffer, or <b>NULL</b> if no buffer is provided by the caller. The buffer must be greater
     than or equal in size to the number of bytes specified in 
     <i>BytesNeeded</i> . If this value is non-<b>NULL</b>, and the data requested is not contiguous, NDIS copies the
     requested data to the area indicated by 
     <i>Storage</i> .


### -param AlignMultiple [in]

The alignment multiple expressed in power of two. For example, 2, 4, 8, 16, and so forth. If 
     <i>AlignMultiple</i> is 1, then there is no alignment requirement.


### -param AlignOffset [in]

The offset, in bytes, from the alignment multiple.


## -returns



<b>NdisGetDataBuffer</b> returns a pointer to the start of the contiguous data or it returns <b>NULL</b>.

If the 
      <b>DataLength</b> member of the 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff568381">NET_BUFFER_DATA</a> structure in the 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structure that the <i>NetBuffer</i>
      parameter points to is less than the value in the 
      <i>BytesNeeded</i> parameter, the return value is <b>NULL</b>.

If the requested data in the buffer is contiguous, the return value is a pointer to a location that
      NDIS provides. If the data is not contiguous, NDIS uses the 
      <i>Storage</i> parameter as follows:

<ul>
<li>If the 
       <i>Storage</i> parameter is non-<b>NULL</b>, NDIS copies the data to the buffer at 
       <i>Storage</i>. The return value is the pointer passed to the 
       <i>Storage</i> parameter.</li>
<li>If the 
       <i>Storage</i> parameter is <b>NULL</b>, the return value is <b>NULL</b>.</li>
</ul>
The return value can also be <b>NULL</b> due to a low resource condition where a data buffer cannot be mapped. This may occur even if the data is contiguous or the <i>Storage</i> parameter is non-<b>NULL</b>.




## -remarks



Call this function to get a pointer to a network data header contained in the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structure. You can easily parse the
    header stored in the contiguous data block that this function returns.

The requested alignment requirement is expressed as a power-of-two multiple plus an offset. For
    example, if 
    <i>AlignMultiple</i> is 4 and 
    <i>AlignOffset</i> is 3 then the data address should be a multiple of 4 plus 3. If necessary, NDIS will
    allocate memory to satisfy the alignment requirement.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568381">NET_BUFFER_DATA</a>
 

 

