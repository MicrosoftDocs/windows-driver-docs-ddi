---
UID: NF:ntifs.RtlAllocateHeap
title: RtlAllocateHeap function
author: windows-driver-content
description: The RtlAllocateHeap routine allocates a block of memory from a heap.
old-location: ifsk\rtlallocateheap.htm
old-project: ifsk
ms.assetid: 38f4c2b7-f9cd-42f2-b75e-725976b6b9dd
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: RtlAllocateHeap
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Microsoft Windows XP and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RtlAllocateHeap
req.alt-loc: NtosKrnl.exe,ntdll.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: < DISPATCH_LEVEL
req.typenames: TOKEN_TYPE
---

# RtlAllocateHeap function



## -description
The <b>RtlAllocateHeap</b> routine allocates a block of memory from a heap. 



## -syntax

````
PVOID RtlAllocateHeap(
  _In_     PVOID  HeapHandle,
  _In_opt_ ULONG  Flags,
  _In_     SIZE_T Size
);
````


## -parameters

### -param HeapHandle [in]

Handle for a private heap from which the memory will be allocated. This parameter is a handle returned from a successful call to <b>RtlCreateHeap</b>. 


### -param Flags [in, optional]

Specifies several controllable aspects of heap allocation. Specifying any of these values will override the corresponding value specified when the heap was created with <b>RtlCreateHeap</b>. This parameter can be one or more of the following values. 

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
HEAP_GENERATE_EXCEPTIONS

</td>
<td>
Specifies that the system will raise an exception to indicate a function failure, such as an out-of-memory condition, instead of returning <b>NULL</b>. 

</td>
</tr>
<tr>
<td>
HEAP_NO_SERIALIZE

</td>
<td>
Specifies that mutual exclusion will not be used while <b>RtlAllocateHeap</b> is accessing the heap. 

</td>
</tr>
<tr>
<td>
HEAP_ZERO_MEMORY

</td>
<td>
Specifies that the allocated memory will be initialized to zero. Otherwise, the memory is not initialized to zero. 

</td>
</tr>
</table>
 


### -param Size [in]

Number of bytes to be allocated. If the heap, specified by the <i>HeapHandle</i> parameter, is a nongrowable heap, <i>Size</i> must be less than or equal to the heap's virtual memory threshold. (For more information, see the <b>VirtualMemoryThreshold</b> member of the <i>Parameters</i> parameter to <a href="..\ntifs\nf-ntifs-rtlcreateheap.md">RtlCreateHeap</a>.) 


## -returns
If the call to <b>RtlAllocateHeap</b> succeeds, the return value is a pointer to the newly-allocated block. 
<dl>
<dt><b>STATUS_ACCESS_VIOLATION</b></dt>
</dl>The allocation attempt failed because of heap corruption or improper function parameters.
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>The allocation attempt failed because the heap is nongrowable and the requested <i>Size</i> was greater than the heap's virtual memory threshold. 
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>The allocation attempt failed because of a lack of available memory or heap corruption. 

 


## -remarks
<b>RtlAllocateHeap</b> allocates a block of memory of the specified size from the specified heap. 

To free a block of memory allocated by <b>RtlAllocateHeap</b>, call <b>RtlFreeHeap</b>. 

Memory allocated by <b>RtlAllocateHeap</b> is not movable. Since the memory is not movable, it is possible for the heap to become fragmented. 

Serialization ensures mutual exclusion when two or more threads attempt to simultaneously allocate or free blocks from the same heap. There is a small performance cost to serialization, but it must be used whenever multiple threads allocate and free memory from the same heap. Setting the HEAP_NO_SERIALIZE value eliminates mutual exclusion on the heap. Without serialization, two or more threads that use the same heap handle might attempt to allocate or free memory simultaneously, likely causing corruption in the heap. The HEAP_NO_SERIALIZE value can, therefore, be safely used only in the following situations: 

The process has only one thread. 

The process has multiple threads, but only one thread calls the heap functions for a specific heap. 

The process has multiple threads, and the application provides its own mechanism for mutual exclusion to a specific heap. 


## -see-also
<dl>
<dt>
<a href="..\ntifs\nf-ntifs-rtlcreateheap.md">RtlCreateHeap</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-rtldestroyheap.md">RtlDestroyHeap</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-rtlfreeheap.md">RtlFreeHeap</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlAllocateHeap routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

