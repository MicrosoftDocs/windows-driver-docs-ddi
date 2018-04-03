---
UID: NF:ndis.NdisZeroMappedMemory
title: NdisZeroMappedMemory macro
author: windows-driver-content
description: NdisZeroMappedMemory fills a block of memory that was mapped with a preceding call to NdisMMapIoSpace with zeros.
old-location: netvista\ndiszeromappedmemory.htm
old-project: netvista
ms.assetid: 210e20a5-c101-4005-97fb-e549ff97e7ce
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NdisZeroMappedMemory, NdisZeroMappedMemory function [Network Drivers Starting with Windows Vista], miniport_memory_mapped_ref_41b91ff3-a113-4a69-bb38-ec3ba89cc0d7.xml, ndis/NdisZeroMappedMemory, netvista.ndiszeromappedmemory
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisZeroMappedMemory (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisZeroMappedMemory (NDIS   5.1)) in Windows XP.
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
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	NdisZeroMappedMemory
product:
- Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisZeroMappedMemory macro


## -description


<b>NdisZeroMappedMemory</b> fills a block of memory that was mapped with a preceding call to 
  <b>NdisMMapIoSpace</b> with zeros.


## -parameters




### -param Destination [in]

Specifies the base virtual address of a block of mapped memory.


### -param Length [in]

Specifies the number of bytes to be filled with zeros.


## -remarks



A miniport driver can call 
    <b>NdisZeroMappedMemory</b> to zero-initialize mapped device memory. The given 
    <i>Destination</i> and 
    <i>Length</i> must be a proper subrange of the range specified when the driver called 
    <a href="https://msdn.microsoft.com/library/windows/hardware/hh975119">NdisMMapIoSpace</a>.

<b>NdisZeroMappedMemory</b> is optimized, and a miniport driver can call this function any time that it
    needs to clear a mapped memory range.




## -see-also




<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh975119">NdisMMapIoSpace</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564698">NdisZeroMemory</a>
 

 

