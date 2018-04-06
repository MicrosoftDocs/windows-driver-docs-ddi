---
UID: NF:ndis.NdisFreeMemoryWithTag
title: NdisFreeMemoryWithTag function
author: windows-driver-content
description: The NdisFreeMemoryWithTag function is deprecated for all NDIS versions. Use NdisAllocateMemoryWithTagPriority instead.
old-location: netvista\ndisfreememorywithtag.htm
old-project: netvista
ms.assetid: c9010a08-3c62-481a-8545-253d7b24b1ac
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NdisFreeMemoryWithTag, NdisFreeMemoryWithTag function [Network Drivers Starting with Windows Vista], ndis/NdisFreeMemoryWithTag, ndis_shared_memory_ref_2a68decc-2cef-4606-9679-c29c0e5362a2.xml, netvista.ndisfreememorywithtag
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.20 and later.
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
req.lib: Ndis.lib
req.dll: 
req.irql: See Remarks section.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisFreeMemoryWithTag
product:
- Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisFreeMemoryWithTag function


## -description


The 
  <b>NdisFreeMemoryWithTag</b> function is deprecated for all NDIS versions.  Use <a href="https://msdn.microsoft.com/library/windows/hardware/ff561606">NdisAllocateMemoryWithTagPriority</a> instead.


## -parameters




### -param VirtualAddress [in]

A pointer to the base virtual address of the allocated memory. This address was returned by the 
     <a href="https://msdn.microsoft.com/0dae26f7-0c00-4a5c-a447-825290ab6570">
     NdisAllocateMemoryWithTag</a> function.


### -param Tag [in]

A string, delimited by single quotation marks, with up to four characters, usually specified in
     reversed order. The NDIS-supplied default tag for this call is 'maDN', but the caller can override this
     default by supplying an explicit value.


## -returns



None




## -remarks



Because noncached memory and contiguous memory are seldom released until the allocating miniport
    driver is unloading, a caller of 
    <b>NdisFreeMemoryWithTag</b> usually is running at IRQL = PASSIVE_LEVEL for these types of de-allocations.
    In any case:

<ul>
<li>
When a caller of 
      <b>NdisFreeMemoryWithTag</b> releases contiguous memory, it must be running at IRQL = PASSIVE_LEVEL.

</li>
<li>
When a caller of 
      <b>NdisFreeMemoryWithTag</b> releases noncached memory, it must be running at IRQL &lt;
      DISPATCH_LEVEL.

</li>
<li>
When a caller of 
      <b>NdisFreeMemoryWithTag</b> releases memory that is neither contiguous nor noncached, it must be
      running at IRQL &lt;= DISPATCH_LEVEL.

</li>
</ul>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550767">NdisAllocateMemoryWithTag</a>
 

 

