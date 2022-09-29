---
UID: NF:ntifs.RtlCreateHeap
title: RtlCreateHeap function (ntifs.h)
description: The RtlCreateHeap routine creates a heap object that can be used by the calling process. This routine reserves space in the virtual address space of the process and allocates physical storage for a specified initial portion of this block.
old-location: ifsk\rtlcreateheap.htm
tech.root: ifsk
ms.date: 07/26/2022
keywords: ["RtlCreateHeap function"]
ms.keywords: RtlCreateHeap, RtlCreateHeap routine [Installable File System Drivers], ifsk.rtlcreateheap, ntifs/RtlCreateHeap, rtlref_e57e4a89-3686-4ab4-85e2-af223cdb3b18.xml
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Windows XP
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
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlCreateHeap
 - ntifs/RtlCreateHeap
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
---

# RtlCreateHeap function

## -description

The **RtlCreateHeap** routine creates a heap object that can be used by the calling process. This routine reserves space in the virtual address space of the process and allocates physical storage for a specified initial portion of this block.

## -parameters

### -param Flags [in]

Flags specifying optional attributes of the heap. These options affect subsequent access to the new heap through calls to the heap functions ([**RtlAllocateHeap**](nf-ntifs-rtlallocateheap.md) and [**RtlFreeHeap**](nf-ntifs-rtlfreeheap.md)).

Callers should set this parameter to zero if no optional attributes are requested.

This parameter can be one or more of the following values.

| Value | Meaning |
| ----- | ------- |
| HEAP_GENERATE_EXCEPTIONS | Specifies that the system will indicate a heap failure by raising an exception, such as STATUS_NO_MEMORY, instead of returning NULL. |
| HEAP_GROWABLE            | Specifies that the heap is growable. Must be specified if **HeapBase** is NULL. |
| HEAP_NO_SERIALIZE        | Specifies that mutual exclusion will not be used when the heap functions allocate and free memory from this heap. The default, when HEAP_NO_SERIALIZE is not specified, is to serialize access to the heap. Serialization of heap access allows two or more threads to simultaneously allocate and free memory from the same heap. |

### -param HeapBase [in, optional]

Specifies one of two actions:

If **HeapBase** is a non-NULL value, it specifies the base address for a block of caller-allocated memory to use for the heap.

If **HeapBase** is NULL, **RtlCreateHeap** allocates system memory for the heap from the process's virtual address space.

### -param ReserveSize [in, optional]

If **ReserveSize** is a nonzero value, it specifies the initial amount of memory, in bytes, to reserve for the heap. **RtlCreateHeap** rounds **ReserveSize** up to the next page boundary, and then reserves a block of that size for the heap.

This parameter is optional and can be zero. The following table summarizes the interaction of the **ReserveSize** and **CommitSize** parameters.

| Values | Result |
| ------ | ------ |
| **ReserveSize** zero, **CommitSize** zero    | 64 pages are initially reserved for the heap. One page is initially committed. |
| **ReserveSize** zero, **CommitSize** nonzero | **RtlCreateHeap** sets **ReserveSize** to be equal to **CommitSize**, and then rounds **ReserveSize** up to the nearest multiple of (PAGE_SIZE * 16). |
| **ReserveSize** nonzero, **CommitSize** zero | One page is initially committed for the heap. |
| **ReserveSize** nonzero, **CommitSize** nonzero | If **CommitSize** is greater than **ReserveSize**, **RtlCreateHeap** reduces **CommitSize** to **ReserveSize**. |

### -param CommitSize [in, optional]

If **CommitSize** is a nonzero value, it specifies the initial amount of memory, in bytes, to commit for the heap. **RtlCreateHeap** rounds **CommitSize** up to the next page boundary, and then commits a block of that size in the process's virtual address space for the heap.

This parameter is optional and can be zero.

### -param Lock [in, optional]

Pointer to an opaque ERESOURCE structure to be used as a resource lock. This parameter is optional and can be NULL. When provided by the caller, the structure must be allocated from nonpaged pool and initialized by calling [**ExInitializeResourceLite**](../wdm/nf-wdm-exinitializeresourcelite.md) or [**ExReinitializeResourceLite**](../wdm/nf-wdm-exreinitializeresourcelite.md). If the HEAP_NO_SERIALIZE flag is set, this parameter must be NULL.

### -param Parameters [in, optional]

Pointer to a [**RTL_HEAP_PARAMETERS**](ns-ntifs-rtl_heap_parameters.md) structure that contains parameters to be applied when creating the heap. This parameter is optional and can be NULL.

## -returns

**RtlCreateHeap** returns a handle to be used in accessing the created heap.

## -remarks

**RtlCreateHeap** creates a private heap object from which the calling process can allocate memory blocks by calling [**RtlAllocateHeap**](nf-ntifs-rtlallocateheap.md). The initial commit size determines the number of pages that are initially allocated for the heap. The initial reserve size determines the number of pages that are initially reserved for the heap. Pages that are reserved but uncommitted create a block in the process's virtual address space into which the heap can expand.

If allocation requests made by [**RtlAllocateHeap**](nf-ntifs-rtlallocateheap.md) exceed the heap's initial commit size, the system commits additional pages of physical storage for the heap, up to the heap's maximum size. If the heap is nongrowable, its maximum size is limited to its initial reserve size.

If the heap is growable, its size is limited only by available memory. If requests by [**RtlAllocateHeap**](nf-ntifs-rtlallocateheap.md) exceed the current size of committed pages, the system calls [**ZwAllocateVirtualMemory**](nf-ntifs-zwallocatevirtualmemory.md) to obtain the memory needed, assuming that the physical storage is available.

In addition, if the heap is nongrowable, an absolute limitation arises: the maximum size of a memory block in the heap is 0x7F000 bytes. The virtual memory threshold of the heap is equal to the maximum heap block size or the value of the **VirtualMemoryThreshold** member of the **Parameters** structure, whichever is less. The heap also may need to pad the request size for metadata and alignment purposes so requests to allocate blocks within 4096 Bytes (1 Page) of the **VirtualMemoryThreshold** may fail even if the maximum size of the heap is large enough to contain the block. (For more information about **VirtualMemoryThreshold**, see the members of the **Parameters** parameter to **RtlCreateHeap**.)  

If the heap is growable, requests to allocate blocks larger than the heap's virtual memory threshold do not automatically fail; the system calls [**ZwAllocateVirtualMemory**](nf-ntifs-zwallocatevirtualmemory.md) to obtain the memory needed for such large blocks.

The memory of a private heap object is accessible only to the process that created it.

The system uses memory from the private heap to store heap support structures, so not all of the specified heap size is available to the process. For example, if [**RtlAllocateHeap**](nf-ntifs-rtlallocateheap.md) requests 64 kilobytes (K) from a heap with a maximum size of 64K, the request may fail because of system overhead.

If HEAP_NO_SERIALIZE is not specified (the simple default), the heap will serialize access within the calling process. Serialization ensures mutual exclusion when two or more threads attempt to simultaneously allocate or free blocks from the same heap. There is a small performance cost to serialization, but it must be used whenever multiple threads allocate and free memory from the same heap.

Setting HEAP_NO_SERIALIZE eliminates mutual exclusion on the heap. Without serialization, two or more threads that use the same heap handle might attempt to allocate or free memory simultaneously, likely causing corruption in the heap. Therefore, HEAP_NO_SERIALIZE can safely be used only in the following situations:

* The process has only one thread.

* The process has multiple threads, but only one thread calls the heap functions for a specific heap.

* The process has multiple threads, and the application provides its own mechanism for mutual exclusion to a specific heap.

> [!NOTE]
> To guard against an access violation, use structured exception handling to protect any code that writes to or reads from a heap. For more information about structured exception handling with memory accesses, see [Handling Exceptions**](/windows-hardware/drivers/kernel/handling-exceptions).

## -see-also

[**RtlAllocateHeap**](nf-ntifs-rtlallocateheap.md)

[**RtlDestroyHeap**](nf-ntifs-rtldestroyheap.md)

[**RtlFreeHeap**](nf-ntifs-rtlfreeheap.md)
