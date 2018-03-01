---
UID: NF:ndis.NdisFreeMemoryWithTagPriority
title: NdisFreeMemoryWithTagPriority function
author: windows-driver-content
description: The NdisFreeMemoryWithTagPriority function releases memory that was allocated with the NdisAllocateMemoryWithTagPriority function.
old-location: netvista\ndisfreememorywithtagpriority.htm
old-project: netvista
ms.assetid: 3870e2c8-22cf-4f96-8c2b-4c3cac26d50f
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: NdisFreeMemoryWithTagPriority, NdisFreeMemoryWithTagPriority function [Network Drivers Starting with Windows Vista], ndis/NdisFreeMemoryWithTagPriority, ndis_shared_memory_ref_60846563-cc80-4e5e-b9da-37bcfd5239b2.xml, netvista.ndisfreememorywithtagpriority
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
-	NdisFreeMemoryWithTagPriority
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisFreeMemoryWithTagPriority function


## -description


The 
  <b>NdisFreeMemoryWithTagPriority</b> function releases memory that was allocated with the 
  <a href="..\ndis\nf-ndis-ndisallocatememorywithtagpriority.md">
  NdisAllocateMemoryWithTagPriority</a> function.


## -syntax


````
VOID NdisFreeMemoryWithTagPriority(
  _In_ NDIS_HANDLE NdisHandle,
  _In_ PVOID       VirtualAddress,
  _In_ ULONG       Tag
);
````


## -parameters




### -param NdisHandle [in]

An NDIS driver or instance handle that was obtained during caller initialization. This should be
     the same handle that the driver passed to the 
     <a href="..\ndis\nf-ndis-ndisallocatememorywithtagpriority.md">
     NdisAllocateMemoryWithTagPriority</a> function. For example, a miniport driver can use the NDIS handle
     that it obtained from the 
     <a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">
     NdisMRegisterMiniportDriver</a> or 
     <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> function.
     Other NDIS drivers can use the handles from the following functions:
     


<a href="..\ndis\nf-ndis-ndisregisterprotocoldriver.md">NdisRegisterProtocolDriver</a>



<a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a>



<a href="..\ndis\nf-ndis-ndisfregisterfilterdriver.md">NdisFRegisterFilterDriver</a>



<a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a>



### -param VirtualAddress [in]

A pointer to the base virtual address of the allocated memory. This address was returned by the 
     <a href="..\ndis\nf-ndis-ndisallocatememorywithtagpriority.md">
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

<a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a>



<a href="..\ndis\nf-ndis-ndisregisterprotocoldriver.md">NdisRegisterProtocolDriver</a>



<a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">NdisMRegisterMiniportDriver</a>



<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>



<a href="..\ndis\nf-ndis-ndisallocatememorywithtagpriority.md">
   NdisAllocateMemoryWithTagPriority</a>



<a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a>



<a href="..\ndis\nf-ndis-ndisfregisterfilterdriver.md">NdisFRegisterFilterDriver</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisFreeMemoryWithTagPriority function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

