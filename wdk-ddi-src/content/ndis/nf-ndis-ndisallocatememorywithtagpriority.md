---
UID: NF:ndis.NdisAllocateMemoryWithTagPriority
title: NdisAllocateMemoryWithTagPriority function (ndis.h)
description: NDIS drivers call the NdisAllocateMemoryWithTagPriority function to allocate a pool of memory from the non-paged pool.
old-location: netvista\ndisallocatememorywithtagpriority.htm
tech.root: netvista
ms.assetid: aac4049c-a876-4bbb-ba3b-fa36c299e1c7
ms.date: 05/02/2018
keywords: ["NdisAllocateMemoryWithTagPriority function"]
ms.keywords: NdisAllocateMemoryWithTagPriority, NdisAllocateMemoryWithTagPriority function [Network Drivers Starting with Windows Vista], ndis/NdisAllocateMemoryWithTagPriority, ndis_memory_ref_1b725109-fc0d-4f5f-8c88-d7a21a1f4c01.xml, netvista.ndisallocatememorywithtagpriority
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Miscellaneous_Function, NdisAllocateMemoryWithTagPriority
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisAllocateMemoryWithTagPriority
 - ndis/NdisAllocateMemoryWithTagPriority
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisAllocateMemoryWithTagPriority
---

# NdisAllocateMemoryWithTagPriority function


## -description

NDIS drivers call the 
  <b>NdisAllocateMemoryWithTagPriority</b> function to allocate a pool of memory from the non-paged
  pool.

## -parameters

### -param NdisHandle 

[in]
An NDIS handle that the caller obtained during initialization. For example, a miniport driver can
     use the NDIS handle that it obtained from the 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterminiportdriver">
     NdisMRegisterMiniportDriver</a> or 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a> function.
     Other NDIS drivers can use the handles from the following functions:
     


<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisregisterprotocoldriver">NdisRegisterProtocolDriver</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfregisterfilterdriver">NdisFRegisterFilterDriver</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_attach">FilterAttach</a>

### -param Length 

[in]
The size to be allocated, in bytes.

### -param Tag 

[in]
A string, delimited by single quotation marks, with up to four characters, usually specified in
     reversed order. The NDIS-supplied default tag for this call is 'maDN', but the caller can override this
     default by supplying an explicit value.

### -param Priority 

[in]
The importance of this request. For more information, see 
     <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatepoolwithtagpriority">
     ExAllocatePoolWithTagPriority</a>.

## -returns

<b>NdisAllocateMemoryWithTagPriority</b> returns a pointer to a base virtual address of the allocated
     memory, or <b>NULL</b> if sufficient nonpaged memory is currently unavailable.

## -remarks

To free memory that was allocated with 
    <b>NdisAllocateMemoryWithTagPriority</b>, call the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreememorywithtagpriority">NdisFreeMemoryWithTagPriority</a> or <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreememory">NdisFreeMemory</a> function.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatepoolwithtagpriority">ExAllocatePoolWithTagPriority</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_attach">FilterAttach</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="/previous-versions/windows/hardware/network/ff550767(v=vs.85)">NdisAllocateMemoryWithTag</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfregisterfilterdriver">NdisFRegisterFilterDriver</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreememory">NdisFreeMemory</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreememorywithtagpriority">NdisFreeMemoryWithTagPriority</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterminiportdriver">NdisMRegisterMiniportDriver</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisregisterprotocoldriver">NdisRegisterProtocolDriver</a>