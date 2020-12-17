---
UID: NF:wdm.ExAllocatePoolPriorityZero
title: ExAllocatePoolPriorityZero
tech.root: kernel
ms.date: 12/17/2020
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
 - ExAllocatePoolPriorityZero
f1_keywords:
 - ExAllocatePoolPriorityZero
 - wdm/ExAllocatePoolPriorityZero
dev_langs:
 - c++
---

## -description

> [!IMPORTANT]
> Microsoft is aware of an issue with **ExAllocatePoolPriorityZero** that can lead to an allocation not getting zeroed on Windows 10, version 1909. This issue has been fixed in version 10.0.19041.685 of the WDK. For information on downloading the latest WDK, see [Download the Windows Driver Kit (WDK)](/windows-hardware/drivers/download-the-wdk).

This routine is a wrapper for and a recommended replacement option for [**ExAllocatePoolWithTagPriority**](nf-wdm-exallocatepoolwithtagpriority.md).

**ExAllocatePoolPriorityZero** allocates pool memory of the specified type. 

It is identical to [**ExAllocatePoolWithTagPriority**](nf-wdm-exallocatepoolwithtagpriority.md) except it zero initializes the allocated memory. If this is not desired, use [**ExAllocatePoolPriorityUninitialized**](nf-wdm-exAllocatepoolpriorityuninitialized.md) instead.

## -parameters

### -param PoolType

The type of pool memory to allocate. For a description of the available pool memory types, see [**POOL_TYPE**](ne-wdm-_pool_type.md). 

You can modify the enumeration value by performing a bitwise-OR with the **POOL_RAISE_IF_ALLOCATION_FAILURE** flag defined in `wdm.h`. This flag causes an exception to be raised if the request cannot be satisfied. Use of this flag is not recommended because it is costly. 

Similarly, you can modify the *PoolType* value by bitwise-ORing this value with the **POOL_COLD_ALLOCATION** flag (also defined in `wdm.h`) as a hint to the kernel to allocate the memory from pages that are likely to be paged out quickly. To reduce the amount of resident pool memory as much as possible, you should not reference these allocations frequently. The **POOL_COLD_ALLOCATION** flag is only advisory.

### -param NumberOfBytes

The number of bytes to allocate.

### -param Tag

The pool tag to use for the allocated memory. Specify the pool tag as a non-zero character literal of one to four characters delimited by single quotation marks (for example, `Tag1`). The string is usually specified in reverse order (for example, `1gaT`). Each ASCII character in the tag must be a value in the range 0x20 (space) to 0x7E (tilde). Each allocation code path should use a unique pool tag to help debuggers and verifiers identify the code path.

### -param Priority

An [**EX_POOL_PRIORITY**](ne-wdm-ex_pool_priority.md) enumeration value specifying the priority of this request.

## -returns

**ExAllocatePoolPriorityZero** returns NULL if there is insufficient memory in the free pool to satisfy the request unless POOL_RAISE_IF_ALLOCATION_FAILURE is specified. Otherwise, the routine returns a pointer to the allocated memory.

## -remarks

To run on versions of Windows prior to Windows 10 version 2004, the driver must define **POOL_ZERO_DOWN_LEVEL_SUPPORT** and call [**ExInitializeDriverRuntime**](nf-wdm-exinitializedriverruntime.md) before calling this function.

See the Remarks section of [**ExAllocatePoolWithTagPriority**](nf-wdm-exallocatepoolwithtagpriority.md) for additional guidance.

## -see-also

[**ExAllocatePoolWithTagPriority**](nf-wdm-exallocatepoolwithtagpriority.md)

[**ExAllocatePoolPriorityUninitialized**](nf-wdm-exallocatepoolpriorityuninitialized.md)

