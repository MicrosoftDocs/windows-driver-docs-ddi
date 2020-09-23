---
UID: NF:ntifs.RtlAllocateHeap
title: RtlAllocateHeap function (ntifs.h)
description: The RtlAllocateHeap routine allocates a block of memory from a heap.
old-location: ifsk\rtlallocateheap.htm
tech.root: ifsk
ms.assetid: 38f4c2b7-f9cd-42f2-b75e-725976b6b9dd
ms.date: 11/26/2019
keywords: ["RtlAllocateHeap function"]
ms.keywords: RtlAllocateHeap, RtlAllocateHeap routine [Installable File System Drivers], ifsk.rtlallocateheap, ntifs/RtlAllocateHeap, rtlref_fa360ead-62c7-46c3-8d66-a73ee9e1a0bb.xml
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
req.irql: < DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlAllocateHeap
 - ntifs/RtlAllocateHeap
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
 - ntdll.dll
api_name:
 - RtlAllocateHeap
---

# RtlAllocateHeap function


## -description

The **RtlAllocateHeap** routine allocates a block of memory from a heap.

## -parameters

### -param HeapHandle 

[in]
Handle for a private heap from which the memory will be allocated. This parameter is a handle returned from a successful call to [**RtlCreateHeap**](./nf-ntifs-rtlcreateheap.md)    .

### -param Flags 

[in, optional]
Controllable aspects of heap allocation. Specifying any of these values will override the corresponding value specified when the heap was created with **RtlCreateHeap**. This parameter can be one or more of the following values.

| Flag | Meaning |
| ---- | ------- |
| HEAP_GENERATE_EXCEPTIONS | The system will raise an exception to indicate a function failure, such as an out-of-memory condition, instead of returning **NULL**. |
| HEAP_NO_SERIALIZE | Mutual exclusion will not be used while **RtlAllocateHeap** is accessing the heap. |
| HEAP_ZERO_MEMORY | The allocated memory will be initialized to zero. Otherwise, the memory is not initialized to zero. |

### -param Size 

[in]
Number of bytes to be allocated. If the heap, specified by the *HeapHandle* parameter, is a nongrowable heap, *Size* must be less than or equal to the heap's virtual memory threshold. (For more information, see the **VirtualMemoryThreshold** member of the *Parameters* parameter to [**RtlCreateHeap**](./nf-ntifs-rtlcreateheap.md).)

## -returns

If the call to **RtlAllocateHeap** succeeds, the return value is a pointer to the newly-allocated block. The return value is NULL if the allocation failed.

## -remarks

**RtlAllocateHeap** allocates a block of memory of the specified size from the specified heap.

To free a block of memory allocated by **RtlAllocateHeap**, call **RtlFreeHeap**.

Memory allocated by **RtlAllocateHeap** is not movable. Since the memory is not movable, it is possible for the heap to become fragmented.

Serialization ensures mutual exclusion when two or more threads attempt to simultaneously allocate or free blocks from the same heap. There is a small performance cost to serialization, but it must be used whenever multiple threads allocate and free memory from the same heap. Setting the HEAP_NO_SERIALIZE value eliminates mutual exclusion on the heap. Without serialization, two or more threads that use the same heap handle might attempt to allocate or free memory simultaneously, likely causing corruption in the heap. The HEAP_NO_SERIALIZE value can, therefore, be safely used only in the following situations:

- The process has only one thread.

- The process has multiple threads, but only one thread calls the heap functions for a specific heap.

- The process has multiple threads, and the application provides its own mechanism for mutual exclusion to a specific heap.

> [!NOTE]
> To guard against an access violation, use structured exception handling to protect any code that writes to or reads from a heap. For more information about structured exception handling with memory accesses, see [Handling Exceptions](/windows-hardware/drivers/kernel/handling-exceptions).

## -see-also

[**RtlCreateHeap**](./nf-ntifs-rtlcreateheap.md)

[**RtlDestroyHeap**](./nf-ntifs-rtldestroyheap.md)

[**RtlFreeHeap**](./nf-ntifs-rtlfreeheap.md)