---
UID: NF:ntifs.RtlCreateHeap
title: RtlCreateHeap function (ntifs.h)
description: The RtlCreateHeap routine creates a heap object that can be used by the calling process. This routine reserves space in the virtual address space of the process and allocates physical storage for a specified initial portion of this block.
old-location: ifsk\rtlcreateheap.htm
tech.root: ifsk
ms.assetid: 77ba5ba3-11d3-4c28-86e6-91f3189b5403
ms.date: 04/16/2018
ms.keywords: RtlCreateHeap, RtlCreateHeap routine [Installable File System Drivers], ifsk.rtlcreateheap, ntifs/RtlCreateHeap, rtlref_e57e4a89-3686-4ab4-85e2-af223cdb3b18.xml
ms.topic: function
f1_keywords:
 - "ntifs/RtlCreateHeap"
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
req.lib: Ntoskrnl.lib
req.dll: NtosKrnl.exe (kernel mode); Ntdll.dll (user mode)
req.irql: < DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
- Ntdll.dll
api_name:
- RtlCreateHeap
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlCreateHeap function


## -description


The <b>RtlCreateHeap</b> routine creates a heap object that can be used by the calling process. This routine reserves space in the virtual address space of the process and allocates physical storage for a specified initial portion of this block. 


## -parameters




### -param Flags [in]

Flags specifying optional attributes of the heap. These options affect subsequent access to the new heap through calls to the heap functions (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlallocateheap">RtlAllocateHeap</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlfreeheap">RtlFreeHeap</a>). 

Callers should set this parameter to zero if no optional attributes are requested. 

This parameter can be one or more of the following values. 





#### HEAP_GENERATE_EXCEPTIONS

Specifies that the system will indicate a heap failure by raising an exception, such as STATUS_NO_MEMORY, instead of returning <b>NULL</b>. 



#### HEAP_GROWABLE

Specifies that the heap is growable. Must be specified if <i>HeapBase</i> is <b>NULL</b>. 



#### HEAP_NO_SERIALIZE

Specifies that mutual exclusion will not be used when the heap functions allocate and free memory from this heap. The default, when HEAP_NO_SERIALIZE is not specified, is to serialize access to the heap. Serialization of heap access allows two or more threads to simultaneously allocate and free memory from the same heap. 


### -param HeapBase [in, optional]

Specifies one of two actions:

If <i>HeapBase</i> is a non-<b>NULL</b> value, it specifies the base address for a block of caller-allocated memory to use for the heap. 

If <i>HeapBase</i> is <b>NULL</b>, <b>RtlCreateHeap</b> allocates system memory for the heap from the process's virtual address space. 


### -param ReserveSize [in, optional]

If <i>ReserveSize</i> is a nonzero value, it specifies the initial amount of memory, in bytes, to reserve for the heap. <b>RtlCreateHeap</b> rounds <i>ReserveSize</i> up to the next page boundary, and then reserves a block of that size for the heap. 

This parameter is optional and can be zero. The following table summarizes the interaction of the <i>ReserveSize</i> and <i>CommitSize</i> parameters. 

<table>
<tr>
<th>Values</th>
<th>Result</th>
</tr>
<tr>
<td>
<i>ReserveSize</i> zero, <i>CommitSize</i> zero

</td>
<td>
64 pages are initially reserved for the heap. One page is initially committed. 

</td>
</tr>
<tr>
<td>
<i>ReserveSize</i> zero, <i>CommitSize</i> nonzero

</td>
<td>
<b>RtlCreateHeap</b> sets <i>ReserveSize</i> to be equal to <i>CommitSize</i>, and then rounds <i>ReserveSize</i> up to the nearest multiple of (PAGE_SIZE * 16). 

</td>
</tr>
<tr>
<td>
<i>ReserveSize</i> nonzero, <i>CommitSize</i> zero

</td>
<td>
One page is initially committed for the heap. 

</td>
</tr>
<tr>
<td>
<i>ReserveSize</i> nonzero, <i>CommitSize</i> nonzero

</td>
<td>
If <i>CommitSize</i> is greater than <i>ReserveSize</i>, <b>RtlCreateHeap</b> reduces <i>CommitSize</i> to <i>ReserveSize</i>. 

</td>
</tr>
</table>
 


### -param CommitSize [in, optional]

If <i>CommitSize</i> is a nonzero value, it specifies the initial amount of memory, in bytes, to commit for the heap. <b>RtlCreateHeap</b> rounds <i>CommitSize</i> up to the next page boundary, and then commits a block of that size in the process's virtual address space for the heap. 

This parameter is optional and can be zero. 


### -param Lock [in, optional]

Pointer to an opaque ERESOURCE structure to be used as a resource lock. This parameter is optional and can be <b>NULL</b>. When provided by the caller, the structure must be allocated from nonpaged pool and initialized by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exinitializeresourcelite">ExInitializeResourceLite</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exreinitializeresourcelite">ExReinitializeResourceLite</a>. If the HEAP_NO_SERIALIZE flag is set, this parameter must be <b>NULL</b>.


### -param Parameters [in, optional]

Pointer to a RTL_HEAP_PARAMETERS structure that contains parameters to be applied when creating the heap. This parameter is optional and can be <b>NULL</b>. 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _RTL_HEAP_PARAMETERS {
    ULONG Length;
    SIZE_T SegmentReserve;
    SIZE_T SegmentCommit;
    SIZE_T DeCommitFreeBlockThreshold;
    SIZE_T DeCommitTotalFreeThreshold;
    SIZE_T MaximumAllocationSize;
    SIZE_T VirtualMemoryThreshold;
    SIZE_T InitialCommit;
    SIZE_T InitialReserve;
    PRTL_HEAP_COMMIT_ROUTINE CommitRoutine;
    SIZE_T Reserved[ 2 ];
} RTL_HEAP_PARAMETERS, *PRTL_HEAP_PARAMETERS;</pre>
</td>
</tr>
</table></span></div>
<table>
<tr>
<th>Member</th>
<th>Value</th>
</tr>
<tr>
<td>
<b>Length</b>

</td>
<td>
Size, in bytes, of the RTL_HEAP_PARAMETERS structure. 

</td>
</tr>
<tr>
<td>
<b>SegmentReserve</b>

</td>
<td>
Segment reserve size, in bytes. If this value is not specified, 1 MB is used. 

</td>
</tr>
<tr>
<td>
<b>SegmentCommit</b>

</td>
<td>
Segment commit size, in bytes. If this value is not specified, PAGE_SIZE * 2 is used. 

</td>
</tr>
<tr>
<td>
<b>DeCommitFreeBlockThreshold</b>

</td>
<td>
Decommit free block threshold, in bytes. If this value is not specified, PAGE_SIZE is used. 

</td>
</tr>
<tr>
<td>
<b>DeCommitTotalFreeThreshold</b>

</td>
<td>
Decommit total free threshold, in bytes. If this value is not specified, 65536 is used. 

</td>
</tr>
<tr>
<td>
<b>MaximumAllocationSize</b>

</td>
<td>
Size, in bytes, of the largest block of memory that can be allocated from the heap. If this value is not specified, the difference between the highest and lowest addresses, less one page, is used. 

</td>
</tr>
<tr>
<td>
<b>VirtualMemoryThreshold</b>

</td>
<td>
Virtual memory threshold, in bytes. If this value is not specified, or if it is greater than the maximum heap block size, the maximum heap block size of 0x7F000 is used. 

</td>
</tr>
<tr>
<td>
<b>InitialCommit</b>

</td>
<td>
Initial amount of memory, in bytes, to commit for the heap. 

Must be less than or equal to <b>InitialReserve</b>. 

If <i>HeapBase</i> and <b>CommitRoutine</b> are non-<b>NULL</b>, this parameter, which overrides the value of <i>CommitSize</i>, must be a nonzero value; otherwise it is ignored. 

</td>
</tr>
<tr>
<td>
<b>InitialReserve</b>

</td>
<td>
Initial amount of memory, in bytes, to reserve for the heap. 

If <i>HeapBase</i> and <b>CommitRoutine</b> are non-<b>NULL</b>, this parameter, which overrides the value of <i>ReserveSize</i>, must be a nonzero value; otherwise it is ignored. 

</td>
</tr>
<tr>
<td>
<b>CommitRoutine</b>

</td>
<td>
Callback routine to commit pages from the heap. If this parameter is non-<b>NULL</b>, the heap must be nongrowable. 

If <i>HeapBase</i> is <b>NULL</b>, <b>CommitRoutine</b> must also be <b>NULL</b>. 

</td>
</tr>
<tr>
<td>
<b>Reserved</b>

</td>
<td>
Reserved for system use. Drivers must set this parameter to zero. 

</td>
</tr>
</table>
 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef NTSTATUS
(NTAPI * PRTL_HEAP_COMMIT_ROUTINE)(
    IN PVOID Base,
    IN OUT PVOID *CommitAddress,
    IN OUT PSIZE_T CommitSize
    );</pre>
</td>
</tr>
</table></span></div>
<table>
<tr>
<th>Parameter</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<i>Base</i>

</td>
<td>
Base address for the block of caller-allocated memory being used for the heap. 

</td>
</tr>
<tr>
<td>
<i>CommitAddress</i>

</td>
<td>
Pointer to a variable that will receive the base address of the committed region of pages. 

</td>
</tr>
<tr>
<td>
<i>CommitSize</i>

</td>
<td>
Pointer to a variable that will receive the actual size, in bytes, of the allocated region of pages. 

</td>
</tr>
</table>
 


## -returns



<b>RtlCreateHeap</b> returns a handle to be used in accessing the created heap. 




## -remarks



<b>RtlCreateHeap</b> creates a private heap object from which the calling process can allocate memory blocks by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlallocateheap">RtlAllocateHeap</a>. The initial commit size determines the number of pages that are initially allocated for the heap. The initial reserve size determines the number of pages that are initially reserved for the heap. Pages that are reserved but uncommitted create a block in the process's virtual address space into which the heap can expand. 

If allocation requests made by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlallocateheap">RtlAllocateHeap</a> exceed the heap's initial commit size, the system commits additional pages of physical storage for the heap, up to the heap's maximum size. If the heap is nongrowable, its maximum size is limited to its initial reserve size. 

If the heap is growable, its size is limited only by available memory. If requests by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlallocateheap">RtlAllocateHeap</a> exceed the current size of committed pages, the system calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff566416">ZwAllocateVirtualMemory</a> to obtain the memory needed, assuming that the physical storage is available. 

In addition, if the heap is nongrowable, an absolute limitation arises: the maximum size of a memory block in the heap is 0x7F000 bytes. The virtual memory threshold of the heap is equal to the maximum heap block size or the value of the <b>VirtualMemoryThreshold</b> member of the <i>Parameters</i> structure, whichever is less. The heap also may need to pad the request size for metadata and alignment purposes so requests to allocate blocks within 4096 Bytes (1 Page) of the <b>VirtualMemoryThreshold</b> may fail even if the maximum size of the heap is large enough to contain the block. (For more information about <b>VirtualMemoryThreshold</b>, see the members of the <i>Parameters</i> parameter to <b>RtlCreateHeap</b>.)  

If the heap is growable, requests to allocate blocks larger than the heap's virtual memory threshold do not automatically fail; the system calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff566416">ZwAllocateVirtualMemory</a> to obtain the memory needed for such large blocks. 

The memory of a private heap object is accessible only to the process that created it. 

The system uses memory from the private heap to store heap support structures, so not all of the specified heap size is available to the process. For example, if <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlallocateheap">RtlAllocateHeap</a> requests 64 kilobytes (K) from a heap with a maximum size of 64K, the request may fail because of system overhead. 

If HEAP_NO_SERIALIZE is not specified (the simple default), the heap will serialize access within the calling process. Serialization ensures mutual exclusion when two or more threads attempt to simultaneously allocate or free blocks from the same heap. There is a small performance cost to serialization, but it must be used whenever multiple threads allocate and free memory from the same heap. 

Setting HEAP_NO_SERIALIZE eliminates mutual exclusion on the heap. Without serialization, two or more threads that use the same heap handle might attempt to allocate or free memory simultaneously, likely causing corruption in the heap. Therefore, HEAP_NO_SERIALIZE can safely be used only in the following situations: 

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
<div class="alert"><b>Note</b>  <p class="note">
       To guard against an access violation, use structured exception handling to protect any code that writes to or reads from a heap. For more information about structured exception handling with memory accesses, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/handling-exceptions">Handling Exceptions</a>. 

</div>
<div> </div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlallocateheap">RtlAllocateHeap</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtldestroyheap">RtlDestroyHeap</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlfreeheap">RtlFreeHeap</a>
 

 

