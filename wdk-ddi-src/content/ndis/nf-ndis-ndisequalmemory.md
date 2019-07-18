---
UID: NF:ndis.NdisEqualMemory
title: NdisEqualMemory macro (ndis.h)
description: The NdisEqualMemory function compares a specified number of characters in one block of memory with the same number of characters in a second block of memory.
old-location: netvista\ndisequalmemory.htm
tech.root: netvista
ms.assetid: 5417b821-b51d-4789-8380-f93d113f42d3
ms.date: 05/02/2018
ms.keywords: NdisEqualMemory, NdisEqualMemory macro [Network Drivers Starting with Windows Vista], ndis/NdisEqualMemory, ndis_memory_ref_67be2fe2-f491-4b7d-9524-a4e324630f74.xml, netvista.ndisequalmemory
ms.topic: macro
f1_keywords:
 - "ndis/NdisEqualMemory"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for existing drivers in  NDIS 6.0 and later, but new drivers should use RtlEqualMemory instead.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Miscellaneous_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: See Remarks section
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ndis.h
api_name:
- NdisEqualMemory
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisEqualMemory macro


## -description


The 
  <b>NdisEqualMemory</b> function compares a specified number of characters in one block of memory with the
  same number of characters in a second block of memory.


## -parameters




### -param Source1

A pointer to the first block of memory to be compared.


### -param Source2

A pointer to the second block of memory to be compared.


### -param Length

The number of bytes to be compared.


## -remarks



<b>NdisEqualMemory</b> compares two blocks of memory and uses the value that is specified in the 
    <i>Length</i> parameter for both blocks. The data type of anything in the compared memory blocks is
    irrelevant.

Callers of 
    <b>NdisEqualMemory</b> can be running at IRQL <= DISPATCH_LEVEL if both memory blocks are resident. If
    either block is pageable, callers must be running at IRQL < DISPATCH_LEVEL.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisallocatememorywithtagpriority">
   NdisAllocateMemoryWithTagPriority</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisfreememory">NdisFreeMemory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-rtlcopymemory">RtlCopyMemory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-rtlfillmemory">RtlFillMemory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-rtlzeromemory">RtlZeroMemory</a>
 

 

