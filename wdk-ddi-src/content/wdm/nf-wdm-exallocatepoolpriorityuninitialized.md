---
UID: NF:wdm.ExAllocatePoolPriorityUninitialized
title: ExAllocatePoolPriorityUninitialized
tech.root: kernel
ms.date: 03/01/2020
ms.topic: language-reference
targetos: Windows
description: 
req.assembly: 
req.construct-type: function
req.ddi-compliance: IrqlExAllocatePool, IrqlExFree2, HwStorPortProhibitedDDIs, SpNoWait, StorPortStartIo 
req.dll: NtosKrnl.exe
req.header: wdm.h
req.idl: 
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.irql: <= DISPATCH_LEVEL (see Remarks section)
req.kmdf-ver: 
req.lib: NtosKrnl.lib
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Requires WDK for Windows 10, version 2004. Targets Windows 7 and later versions of the Windows operating system.
req.target-min-winversvr: 
req.target-type: Universal
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
- DllExport
api_location:
 - wdm.h
api_name:
 - ExAllocatePoolPriorityUninitialized
f1_keywords:
 - wdm/ExAllocatePoolPriorityUninitialized
dev_langs:
 - c++
---

## -description

This routine is a wrapper and replacement option for [**ExAllocatePoolWithTagPriority**](nf-wdm-exallocatepoolwithtagpriority.md).

**ExAllocatePoolPriorityUninitialized** allocates pool memory of the specified type. 

## -parameters

### -param PoolType

The type of pool memory to allocate. For a description of the available pool memory types, see [**POOL_TYPE**](ne-wdm-_pool_type.md). 

You can modify the enumeration value by performing a bitwise-OR with the **POOL_RAISE_IF_ALLOCATION_FAILURE** flag defined in `wdm.h`. This flag causes an exception to be raised if the request cannot be satisfied. Use of this flag is not recommended because it is costly. 

Similarly, you can modify the *PoolType* value by bitwise-ORing this value with the **POOL_COLD_ALLOCATION** flag (also defined in `wdm.h`) as a hint to the kernel to allocate the memory from pages that are likely to be paged out quickly. To reduce the amount of resident pool memory as much as possible, you should not reference these allocations frequently. The **POOL_COLD_ALLOCATION** flag is only advisory. 


### -param NumberOfBytes

The number of bytes to allocate. 

### -param Tag

The pool tag to use for the allocated memory. For more information, see the Tag parameter of [**ExAllocatePoolWithTag**](nf-wdm-exallocatepoolwithtag.md). 

### -param Priority

An [**EX_POOL_PRIORITY**](ne-wdm-ex_pool_priority.md) enumeration value specifying the priority of this request.


## -returns

**ExAllocatePoolPriorityUninitialized** returns NULL if there is insufficient memory in the free pool to satisfy the request unless POOL_RAISE_IF_ALLOCATION_FAILURE is specified. Otherwise, the routine returns a pointer to the allocated memory. 

## -remarks

> [!NOTE]
> Memory that **ExAllocatePoolPriorityUninitialized** allocates is uninitialized. A kernel-mode driver must first zero this memory if it is going to make it visible to user-mode software (to avoid leaking potentially privileged contents)

See the Remarks section of [**ExAllocatePoolWithTagPriority**](nf-wdm-exallocatepoolwithtagpriority.md) for additional guidance.

## -see-also

[**ExAllocatePoolWithTagPriority**](nf-wdm-exallocatepoolwithtagpriority.md)

[**ExAllocatePoolPriorityZero**](nf-wdm-exallocatepoolpriorityzero.md)