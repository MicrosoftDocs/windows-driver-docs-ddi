---
UID: NF:ndis.NdisAllocateMemoryWithTagPriority
title: NdisAllocateMemoryWithTagPriority function
author: windows-driver-content
description: NDIS drivers call the NdisAllocateMemoryWithTagPriority function to allocate a pool of memory from the non-paged pool.
old-location: netvista\ndisallocatememorywithtagpriority.htm
old-project: netvista
ms.assetid: aac4049c-a876-4bbb-ba3b-fa36c299e1c7
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ndis/NdisAllocateMemoryWithTagPriority, NdisAllocateMemoryWithTagPriority function [Network Drivers Starting with Windows Vista], ndis_memory_ref_1b725109-fc0d-4f5f-8c88-d7a21a1f4c01.xml, netvista.ndisallocatememorywithtagpriority, NdisAllocateMemoryWithTagPriority
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
req.ddi-compliance: Irql_Miscellaneous_Function, NdisAllocateMemoryWithTagPriority
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisAllocateMemoryWithTagPriority
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisAllocateMemoryWithTagPriority function


## -description


NDIS drivers call the 
  <b>NdisAllocateMemoryWithTagPriority</b> function to allocate a pool of memory from the non-paged
  pool.


## -syntax


````
PVOID NdisAllocateMemoryWithTagPriority(
  _In_ NDIS_HANDLE      NdisHandle,
  _In_ UINT             Length,
  _In_ ULONG            Tag,
  _In_ EX_POOL_PRIORITY Priority
);
````


## -parameters




### -param NdisHandle [in]

An NDIS handle that the caller obtained during initialization. For example, a miniport driver can
     use the NDIS handle that it obtained from the 
     <a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">
     NdisMRegisterMiniportDriver</a> or 
     <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> function.
     Other NDIS drivers can use the handles from the following functions:
     


<a href="..\ndis\nf-ndis-ndisregisterprotocoldriver.md">NdisRegisterProtocolDriver</a>



<a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a>



<a href="..\ndis\nf-ndis-ndisfregisterfilterdriver.md">NdisFRegisterFilterDriver</a>



<a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a>



### -param Length [in]

The size to be allocated, in bytes.


### -param Tag [in]

A string, delimited by single quotation marks, with up to four characters, usually specified in
     reversed order. The NDIS-supplied default tag for this call is 'maDN', but the caller can override this
     default by supplying an explicit value.


### -param Priority [in]

The importance of this request. For more information, see 
     <a href="..\wdm\nf-wdm-exallocatepoolwithtagpriority.md">
     ExAllocatePoolWithTagPriority</a>.


## -returns


<b>NdisAllocateMemoryWithTagPriority</b> returns a pointer to a base virtual address of the allocated
     memory, or <b>NULL</b> if sufficient nonpaged memory is currently unavailable.



## -remarks


To free memory that was allocated with 
    <b>NdisAllocateMemoryWithTagPriority</b>, call the 
    <a href="..\ndis\nf-ndis-ndisfreememorywithtagpriority.md">NdisFreeMemoryWithTagPriority</a> or <a href="..\ndis\nf-ndis-ndisfreememory.md">NdisFreeMemory</a> function.



## -see-also

<a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a>

<a href="..\ndis\nf-ndis-ndisfreememorywithtagpriority.md">NdisFreeMemoryWithTagPriority</a>

<a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a>

<a href="..\ndis\nf-ndis-ndisfregisterfilterdriver.md">NdisFRegisterFilterDriver</a>

<a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">NdisMRegisterMiniportDriver</a>

<a href="..\ndis\nf-ndis-ndisregisterprotocoldriver.md">NdisRegisterProtocolDriver</a>

<a href="..\wdm\nf-wdm-exallocatepoolwithtagpriority.md">ExAllocatePoolWithTagPriority</a>

<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>

<a href="..\ndis\nf-ndis-ndisfreememory.md">NdisFreeMemory</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550767">NdisAllocateMemoryWithTag</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisAllocateMemoryWithTagPriority function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

