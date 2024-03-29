---
UID: NF:ndis.NdisFreeMemoryWithTagPriority
title: NdisFreeMemoryWithTagPriority function (ndis.h)
description: The NdisFreeMemoryWithTagPriority function releases memory that was allocated with the NdisAllocateMemoryWithTagPriority function.
old-location: netvista\ndisfreememorywithtagpriority.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NdisFreeMemoryWithTagPriority function"]
ms.keywords: NdisFreeMemoryWithTagPriority, NdisFreeMemoryWithTagPriority function [Network Drivers Starting with Windows Vista], ndis/NdisFreeMemoryWithTagPriority, ndis_shared_memory_ref_60846563-cc80-4e5e-b9da-37bcfd5239b2.xml, netvista.ndisfreememorywithtagpriority
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
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisFreeMemoryWithTagPriority
 - ndis/NdisFreeMemoryWithTagPriority
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisFreeMemoryWithTagPriority
---

# NdisFreeMemoryWithTagPriority function


## -description

The 
  <b>NdisFreeMemoryWithTagPriority</b> function releases memory that was allocated with the 
  <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatememorywithtagpriority">
  NdisAllocateMemoryWithTagPriority</a> function.

## -parameters

### -param NdisHandle [in]


An NDIS driver or instance handle that was obtained during caller initialization. This should be
     the same handle that the driver passed to the 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatememorywithtagpriority">
     NdisAllocateMemoryWithTagPriority</a> function. For example, a miniport driver can use the NDIS handle
     that it obtained from the 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterminiportdriver">
     NdisMRegisterMiniportDriver</a> or 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a> function.
     Other NDIS drivers can use the handles from the following functions:
     


<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisregisterprotocoldriver">NdisRegisterProtocolDriver</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfregisterfilterdriver">NdisFRegisterFilterDriver</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_attach">FilterAttach</a>

### -param VirtualAddress [in]


A pointer to the base virtual address of the allocated memory. This address was returned by the 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatememorywithtagpriority">
     NdisAllocateMemoryWithTagPriority</a> function.

### -param Tag [in]


A string, delimited by single quotation marks, with up to four characters, usually specified in
     reversed order. The NDIS-supplied default tag for this call is 'maDN', but the caller can override this
     default by supplying an explicit value.

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
      <b>NdisFreeMemoryWithTagPriority</b> releases noncached memory, it must be running at IRQL <
      DISPATCH_LEVEL.

</li>
<li>
When a caller of 
      <b>NdisFreeMemoryWithTagPriority</b> releases memory that is neither contiguous nor noncached, it must
      be running at IRQL <= DISPATCH_LEVEL.

</li>
</ul>

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_attach">FilterAttach</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatememorywithtagpriority">
   NdisAllocateMemoryWithTagPriority</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfregisterfilterdriver">NdisFRegisterFilterDriver</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterminiportdriver">NdisMRegisterMiniportDriver</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisregisterprotocoldriver">NdisRegisterProtocolDriver</a>
