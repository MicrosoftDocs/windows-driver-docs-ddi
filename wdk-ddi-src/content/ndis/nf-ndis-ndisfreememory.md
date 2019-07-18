---
UID: NF:ndis.NdisFreeMemory
title: NdisFreeMemory function (ndis.h)
description: The NdisFreeMemory function releases a block of memory that was previously allocated with the NdisAllocateMemoryWithTagPriority function.
old-location: netvista\ndisfreememory.htm
tech.root: netvista
ms.assetid: 0096fef7-2a5a-45cd-8e54-dc1ec0e84237
ms.date: 05/02/2018
ms.keywords: NdisFreeMemory, NdisFreeMemory function [Network Drivers Starting with Windows Vista], ndis/NdisFreeMemory, ndis_memory_ref_a178b0d7-8966-4356-8f63-3293605a6655.xml, netvista.ndisfreememory
ms.topic: function
f1_keywords:
 - "ndis/NdisFreeMemory"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisFreeMemory (NDIS 5.1)) in   Windows Vista. Supported for NDIS 5.1 drivers (see    NdisFreeMemory (NDIS 5.1)) in   Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Miscellaneous_Function, NdisQueryBindInstanceName
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: See Remarks section
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisFreeMemory
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisFreeMemory function


## -description


The
  <b>NdisFreeMemory</b> function releases a block of memory that was previously allocated with the 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisallocatememorywithtagpriority">NdisAllocateMemoryWithTagPriority</a> function.


## -parameters




### -param VirtualAddress [in]

A pointer to the base virtual address of the allocated memory. This address was returned by the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisallocatememorywithtagpriority">NdisAllocateMemoryWithTagPriority</a> function.


### -param Length [in]

The size, in bytes, of the memory block to be released. If the memory was allocated with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisallocatememorywithtagpriority">NdisAllocateMemoryWithTagPriority</a> or the <i>MemoryFlags</i> parameter is zero, this parameter is ignored. 


### -param MemoryFlags [in]

A set of flags that specify the type of memory to free. This value must be zero if the memory was
      allocated with 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisallocatememorywithtagpriority">NdisAllocateMemoryWithTagPriority</a>. With NDIS 6.0 and later versions, the 
      <b>NdisAllocateMemoryWithTagPriority</b> is always used to allocate memory.


## -returns



None




## -remarks



Because noncached memory and contiguous memory are seldom released until the allocating miniport
    driver is unloading, a caller of 
    <b>NdisFreeMemory</b> usually is running at IRQL = PASSIVE_LEVEL for these types of deallocations. In any
    case:

<ul>
<li>
When releasing contiguous memory, a caller of 
      <b>NdisFreeMemory</b> must be running at IRQL = PASSIVE_LEVEL.

</li>
<li>
When releasing noncached memory, a caller of 
      <b>NdisFreeMemory</b> must be running at IRQL < DISPATCH_LEVEL.

</li>
<li>
When releasing memory that is neither contiguous nor noncached, a caller of 
      <b>NdisFreeMemory</b> must be running at IRQL <= DISPATCH_LEVEL.

</li>
</ul>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_halt">MiniportHaltEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisallocatememorywithtagpriority">
   NdisAllocateMemoryWithTagPriority</a>
 

 

