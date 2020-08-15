---
UID: NF:ndis.NdisZeroMappedMemory
title: NdisZeroMappedMemory macro (ndis.h)
description: NdisZeroMappedMemory fills a block of memory that was mapped with a preceding call to NdisMMapIoSpace with zeros.
old-location: netvista\ndiszeromappedmemory.htm
tech.root: netvista
ms.assetid: 210e20a5-c101-4005-97fb-e549ff97e7ce
ms.date: 05/02/2018
keywords: ["NdisZeroMappedMemory macro"]
ms.keywords: NdisZeroMappedMemory, NdisZeroMappedMemory function [Network Drivers Starting with Windows Vista], miniport_memory_mapped_ref_41b91ff3-a113-4a69-bb38-ec3ba89cc0d7.xml, ndis/NdisZeroMappedMemory, netvista.ndiszeromappedmemory
f1_keywords:
 - "ndis/NdisZeroMappedMemory"
 - "NdisZeroMappedMemory"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ndis.h
api_name:
- NdisZeroMappedMemory
targetos: Windows
req.typenames: 
---

# NdisZeroMappedMemory macro


## -description


<b>NdisZeroMappedMemory</b> fills a block of memory that was mapped with a preceding call to 
  <b>NdisMMapIoSpace</b> with zeros.


## -parameters




### -param Destination 
[in]
Specifies the base virtual address of a block of mapped memory.


### -param Length 
[in]
Specifies the number of bytes to be filled with zeros.


## -remarks



A miniport driver can call 
    <b>NdisZeroMappedMemory</b> to zero-initialize mapped device memory. The given 
    <i>Destination</i> and 
    <i>Length</i> must be a proper subrange of the range specified when the driver called 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/ndis-ndismmapiospace">NdisMMapIoSpace</a>.

<b>NdisZeroMappedMemory</b> is optimized, and a miniport driver can call this function any time that it
    needs to clear a mapped memory range.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/ndis-ndismmapiospace">NdisMMapIoSpace</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiszeromemory">NdisZeroMemory</a>
 

 

