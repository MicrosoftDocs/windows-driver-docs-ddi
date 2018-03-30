---
UID: NF:ndis.NdisAllocateMemoryWithTagPriority
title: NdisAllocateMemoryWithTagPriority function
author: windows-driver-content
description: NDIS drivers call the NdisAllocateMemoryWithTagPriority function to allocate a pool of memory from the non-paged pool.
old-location: netvista\ndisallocatememorywithtagpriority.htm
old-project: netvista
ms.assetid: aac4049c-a876-4bbb-ba3b-fa36c299e1c7
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisAllocateMemoryWithTagPriority, NdisAllocateMemoryWithTagPriority function [Network Drivers Starting with Windows Vista], ndis/NdisAllocateMemoryWithTagPriority, ndis_memory_ref_1b725109-fc0d-4f5f-8c88-d7a21a1f4c01.xml, netvista.ndisallocatememorywithtagpriority
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
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


## -parameters




### -param NdisHandle [in]

An NDIS handle that the caller obtained during initialization. For example, a miniport driver can
     use the NDIS handle that it obtained from the 
     <a href="https://msdn.microsoft.com/bed68aa8-499d-41fd-997b-a46316913cc8">
     NdisMRegisterMiniportDriver</a> or 
     <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a> function.
     Other NDIS drivers can use the handles from the following functions:
     


<a href="https://msdn.microsoft.com/library/windows/hardware/ff564520">NdisRegisterProtocolDriver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563715">NdisOpenAdapterEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562608">NdisFRegisterFilterDriver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540442">FilterAttach</a>



### -param Length [in]

The size to be allocated, in bytes.


### -param Tag [in]

A string, delimited by single quotation marks, with up to four characters, usually specified in
     reversed order. The NDIS-supplied default tag for this call is 'maDN', but the caller can override this
     default by supplying an explicit value.


### -param Priority [in]

The importance of this request. For more information, see 
     <a href="https://msdn.microsoft.com/33087a37-e6fc-4b21-aa9e-e4617eeccd29">
     ExAllocatePoolWithTagPriority</a>.


## -returns



<b>NdisAllocateMemoryWithTagPriority</b> returns a pointer to a base virtual address of the allocated
     memory, or <b>NULL</b> if sufficient nonpaged memory is currently unavailable.




## -remarks



To free memory that was allocated with 
    <b>NdisAllocateMemoryWithTagPriority</b>, call the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff562581">NdisFreeMemoryWithTagPriority</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff562577">NdisFreeMemory</a> function.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544523">ExAllocatePoolWithTagPriority</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540442">FilterAttach</a>



<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550767">NdisAllocateMemoryWithTag</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562608">NdisFRegisterFilterDriver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562577">NdisFreeMemory</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562581">NdisFreeMemoryWithTagPriority</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563654">NdisMRegisterMiniportDriver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563715">NdisOpenAdapterEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564520">NdisRegisterProtocolDriver</a>
 

 

<<<<<<< HEAD
=======
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisAllocateMemoryWithTagPriority function%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

>>>>>>> parent of 2d896a8e266... Added changes
