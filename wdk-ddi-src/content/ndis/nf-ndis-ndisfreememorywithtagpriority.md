---
UID: NF:ndis.NdisFreeMemoryWithTagPriority
title: NdisFreeMemoryWithTagPriority function
author: windows-driver-content
description: The NdisFreeMemoryWithTagPriority function releases memory that was allocated with the NdisAllocateMemoryWithTagPriority function.
old-location: netvista\ndisfreememorywithtagpriority.htm
tech.root: netvista
ms.assetid: 3870e2c8-22cf-4f96-8c2b-4c3cac26d50f
ms.date: 5/2/2018
ms.keywords: NdisFreeMemoryWithTagPriority, NdisFreeMemoryWithTagPriority function [Network Drivers Starting with Windows Vista], ndis/NdisFreeMemoryWithTagPriority, ndis_shared_memory_ref_60846563-cc80-4e5e-b9da-37bcfd5239b2.xml, netvista.ndisfreememorywithtagpriority
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
-	NdisFreeMemoryWithTagPriority
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisFreeMemoryWithTagPriority function


## -description


The 
  <b>NdisFreeMemoryWithTagPriority</b> function releases memory that was allocated with the 
  <a href="https://msdn.microsoft.com/aac4049c-a876-4bbb-ba3b-fa36c299e1c7">
  NdisAllocateMemoryWithTagPriority</a> function.


## -parameters




### -param NdisHandle [in]

An NDIS driver or instance handle that was obtained during caller initialization. This should be
     the same handle that the driver passed to the 
     <a href="https://msdn.microsoft.com/aac4049c-a876-4bbb-ba3b-fa36c299e1c7">
     NdisAllocateMemoryWithTagPriority</a> function. For example, a miniport driver can use the NDIS handle
     that it obtained from the 
     <a href="https://msdn.microsoft.com/bed68aa8-499d-41fd-997b-a46316913cc8">
     NdisMRegisterMiniportDriver</a> or 
     <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a> function.
     Other NDIS drivers can use the handles from the following functions:
     


<a href="https://msdn.microsoft.com/library/windows/hardware/ff564520">NdisRegisterProtocolDriver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563715">NdisOpenAdapterEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562608">NdisFRegisterFilterDriver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540442">FilterAttach</a>



### -param VirtualAddress [in]

A pointer to the base virtual address of the allocated memory. This address was returned by the 
     <a href="https://msdn.microsoft.com/aac4049c-a876-4bbb-ba3b-fa36c299e1c7">
     NdisAllocateMemoryWithTagPriority</a> function.


### -param Tag [in]

A string, delimited by single quotation marks, with up to four characters, usually specified in
     reversed order. The NDIS-supplied default tag for this call is 'maDN', but the caller can override this
     default by supplying an explicit value.


## -returns



None




## -remarks



Because noncached memory and contiguous memory are seldom released until the allocating miniport
    driver is unloading, a caller of 
    <b>NdisFreeMemoryWithTagPriority</b> usually is running at IRQL = PASSIVE_LEVEL for these types of
    de-allocations. In any case:

<ul>
<li>
When a caller of 
      <b>NdisFreeMemoryWithTagPriority</b> releases contiguous memory, it must be running at IRQL =
      PASSIVE_LEVEL.

</li>
<li>
When a caller of 
      <b>NdisFreeMemoryWithTagPriority</b> releases noncached memory, it must be running at IRQL &lt;
      DISPATCH_LEVEL.

</li>
<li>
When a caller of 
      <b>NdisFreeMemoryWithTagPriority</b> releases memory that is neither contiguous nor noncached, it must
      be running at IRQL &lt;= DISPATCH_LEVEL.

</li>
</ul>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540442">FilterAttach</a>



<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/aac4049c-a876-4bbb-ba3b-fa36c299e1c7">
   NdisAllocateMemoryWithTagPriority</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562608">NdisFRegisterFilterDriver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563654">NdisMRegisterMiniportDriver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563715">NdisOpenAdapterEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564520">NdisRegisterProtocolDriver</a>
 

 

