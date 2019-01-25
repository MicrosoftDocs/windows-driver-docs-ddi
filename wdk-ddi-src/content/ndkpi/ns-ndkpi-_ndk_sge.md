---
UID: NS:ndkpi._NDK_SGE
title: "_NDK_SGE" (ndkpi.h)
description: The NDK_SGE structure specifies the local buffers for NDK work requests.
old-location: netvista\ndk_sge.htm
tech.root: netvista
ms.assetid: D64DD5F0-2BCA-4A6B-A7BA-04A2B8E3B9FE
ms.date: 05/02/2018
ms.keywords: NDK_SGE, NDK_SGE structure [Network Drivers Starting with Windows Vista], _NDK_SGE, ndkpi/NDK_SGE, netvista.ndk_sge
ms.topic: struct
req.header: ndkpi.h
req.include-header: Ndkpi.h
req.target-type: Windows
req.target-min-winverclnt: None supported,Supported in NDIS 6.30 and later.
req.target-min-winversvr: Windows Server 2012
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndkpi.h
api_name:
-	NDK_SGE
product:
- Windows
targetos: Windows
req.typenames: NDK_SGE
---

# _NDK_SGE structure


## -description


The  <b>NDK_SGE</b> structure specifies the local buffers for NDK work requests.


## -struct-fields




### -field VirtualAddress

A virtual address.


### -field LogicalAddress

A logical address.


### -field Length

The length, in bytes, of the buffer.


### -field MemoryRegionToken

A memory region token. When <b>MemoryRegionToken</b> is set to the token returned by <i>NdkGetPrivilegedMemoryRegionToken</i> (<a href="https://msdn.microsoft.com/library/windows/hardware/hh439896">NDK_FN_GET_PRIVILEGED_MEMORY_REGION_TOKEN</a>), the <b>NDK_SGE</b> must contain a <b>LogicalAddress</b>. When <b>MemoryRegionToken</b> is not equal to the token returned by <i>NdkGetPrivilegedMemoryRegionToken</i>, the <b>NDK_SGE</b> structure must contain a <b>VirtualAddress</b>. When an <b>NDK_SGE</b> structure is used in a work request with the <b>NDK_OP_FLAG_INLINE</b> flag, <b>MemoryRegionToken</b> might be invalid. See the remarks section for more information about the <b>MemoryRegionToken</b>. 


## -remarks



The <b>NDK_SGE</b> structure specifies the local buffers for send, receive, read, and write work requests. 

When the <b>MemoryRegionToken</b> member is set to the token returned by <i>NdkGetPrivilegedMemoryRegionToken</i> (<a href="https://msdn.microsoft.com/library/windows/hardware/hh439896">NDK_FN_GET_PRIVILEGED_MEMORY_REGION_TOKEN</a>), the <b>NDK_SGE</b> must contain a logical address returned by the <i>NdkBuildLam</i> (<a href="https://msdn.microsoft.com/library/windows/hardware/hh439860">NDK_FN_BUILD_LAM</a>) function with the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439920">NDK_LOGICAL_ADDRESS_MAPPING</a> structure. Note that consecutive entries in the <b>AdapterPageArray</b> member of an <b>NDK_LOGICAL_ADDRESS_MAPPING</b> are not necessarily contiguous pages in the adapter's logical address space. Therefore, an NDK consumer might use multiple SGEs to cover all of the pages in an adapter page array.

When the token in the <b>MemoryRegionToken</b> member is not equal to the token that is returned by <i>NdkGetPrivilegedMemoryRegionToken</i>, the <b>NDK_SGE</b> structure must contain a virtual address that falls within the virtual address span of a previously registered memory region.

When an <b>NDK_SGE</b> structure is used in a work request with the <b>NDK_OP_FLAG_INLINE</b> flag,  the token in <b>MemoryRegionToken</b> might  be invalid, so it must be ignored by the NDK provider. When the <b>NDK_OP_FLAG_INLINE</b> flag is specified, the <b>VirtualAddress</b> member  of any <b>NDK_SGE</b> structure that is  passed to the work request function must point to a buffer that can be accessed by the NDK provider at an  IRQL less than or equal to  <b>DISPATCH_LEVEL</b>, That is, the buffer must be guaranteed to be resident in physical memory until the work request function returns. The total size of inline data that is passed to the provider in a single call must not exceed the  value in the  <i>InlineDataSize</i> parameter  that was  specified when the queue pair (QP) was  created.




## -see-also




<a href="https://msdn.microsoft.com/94993523-D0D7-441E-B95C-417800840BAC">NDKPI Object Lifetime Requirements</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439860">NDK_FN_BUILD_LAM</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439896">NDK_FN_GET_PRIVILEGED_MEMORY_REGION_TOKEN</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439906">NDK_FN_READ</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439907">NDK_FN_RECEIVE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439914">NDK_FN_SEND</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439916">NDK_FN_SRQ_RECEIVE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439917">NDK_FN_WRITE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439920">NDK_LOGICAL_ADDRESS_MAPPING</a>
 

 

