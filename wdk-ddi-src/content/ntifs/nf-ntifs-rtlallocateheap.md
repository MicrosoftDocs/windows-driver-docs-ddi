---
UID: NF:ntifs.RtlAllocateHeap
title: RtlAllocateHeap function (ntifs.h)
description: The RtlAllocateHeap routine allocates a block of memory from a heap.
old-location: ifsk\rtlallocateheap.htm
tech.root: ifsk
ms.assetid: 38f4c2b7-f9cd-42f2-b75e-725976b6b9dd
ms.date: 04/16/2018
ms.keywords: RtlAllocateHeap, RtlAllocateHeap routine [Installable File System Drivers], ifsk.rtlallocateheap, ntifs/RtlAllocateHeap, rtlref_fa360ead-62c7-46c3-8d66-a73ee9e1a0bb.xml
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Microsoft Windows XP and later.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "< DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
-	ntdll.dll
api_name:
-	RtlAllocateHeap
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlAllocateHeap function


## -description


The <b>RtlAllocateHeap</b> routine allocates a block of memory from a heap. 


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

Number of bytes to be allocated. If the heap, specified by the <i>HeapHandle</i> parameter, is a nongrowable heap, <i>Size</i> must be less than or equal to the heap's virtual memory threshold. (For more information, see the <b>VirtualMemoryThreshold</b> member of the <i>Parameters</i> parameter to <a href="https://msdn.microsoft.com/library/windows/hardware/ff552159">RtlCreateHeap</a>.) 


## -returns



If the call to <b>RtlAllocateHeap</b> succeeds, the return value is a pointer to the newly-allocated block. 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_VIOLATION</b></dt>
</dl>
</td>
<td width="60%">
The allocation attempt failed because of heap corruption or improper function parameters.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The allocation attempt failed because the heap is nongrowable and the requested <i>Size</i> was greater than the heap's virtual memory threshold. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>
</td>
<td width="60%">
The allocation attempt failed because of a lack of available memory or heap corruption. 

</td>
</tr>
</table>
 




## -remarks



<b>RtlAllocateHeap</b> allocates a block of memory of the specified size from the specified heap. 

To free a block of memory allocated by <b>RtlAllocateHeap</b>, call <b>RtlFreeHeap</b>. 

Memory allocated by <b>RtlAllocateHeap</b> is not movable. Since the memory is not movable, it is possible for the heap to become fragmented. 

Serialization ensures mutual exclusion when two or more threads attempt to simultaneously allocate or free blocks from the same heap. There is a small performance cost to serialization, but it must be used whenever multiple threads allocate and free memory from the same heap. Setting the HEAP_NO_SERIALIZE value eliminates mutual exclusion on the heap. Without serialization, two or more threads that use the same heap handle might attempt to allocate or free memory simultaneously, likely causing corruption in the heap. The HEAP_NO_SERIALIZE value can, therefore, be safely used only in the following situations: 

<ul>
<li>
The process has only one thread. 

</li>
<li>
The process has multiple threads, but only one thread calls the heap functions for a specific heap. 

</li>
<li>
The process has multiple threads, and the application provides its own mechanism for mutual exclusion to a specific heap. 

</li>
</ul>
<div class="alert"><b>Note</b>    To guard against an access violation, use structured exception handling to protect any code that writes to or reads from a heap. For more information about structured exception handling with memory accesses, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff546823">Handling Exceptions</a>. </div>
<div> </div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552159">RtlCreateHeap</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552233">RtlDestroyHeap</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552276">RtlFreeHeap</a>
 

 

