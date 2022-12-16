---
UID: NF:wdm.ExAllocatePoolWithTag
title: ExAllocatePoolWithTag function (wdm.h)
description: Obsolete. Use ExAllocatePool2 instead. The ExAllocatePoolWithTag routine allocates pool memory of the specified type and returns a pointer to the allocated block.
tech.root: kernel
ms.date: 12/12/2022
keywords: ["ExAllocatePoolWithTag function"]
ms.keywords: ExAllocatePoolWithTag, ExAllocatePoolWithTag routine [Kernel-Mode Driver Architecture], k102_13ab2d7e-dd96-4474-bf27-59ee9b7d84d6.xml, kernel.exallocatepoolwithtag, wdm/ExAllocatePoolWithTag
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: CheckDeviceObjectFlags, IrqlExAllocatePool, IrqlExFree1, PowerDownAllocate, PowerUpFail, HwStorPortProhibitedDDIs, SpNoWait, StorPortStartIo
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: IRQL <= DISPATCH_LEVEL (see Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - ExAllocatePoolWithTag
 - wdm/ExAllocatePoolWithTag
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ExAllocatePoolWithTag
---

## -description

The **ExAllocatePoolWithTag** routine allocates pool memory of the specified type and returns a pointer to the allocated block.

>[!WARNING]
> ExAllocatePoolWithTag has been deprecated in Windows 10, version 2004 and has been replaced by [ExAllocatePool2](nf-wdm-exallocatepool2.md). For more information, see [Updating deprecated ExAllocatePool calls to ExAllocatePool2 and ExAllocatePool3](/windows-hardware/drivers/kernel/updating-deprecated-exallocatepool-calls).

## -parameters

### -param PoolType [in]

The type of pool memory to allocate. For a description of the available pool memory types, see [POOL_TYPE](/windows-hardware/drivers/ddi/wdm/ne-wdm-_pool_type).

You can modify the *PoolType* value by bitwise-ORing this value with the POOL_RAISE_IF_ALLOCATION_FAILURE flag. This flag causes an exception to be raised if the request cannot be satisfied. Use of the POOL_RAISE_IF_ALLOCATION_FAILURE flag is not recommended because it is costly.

Similarly, you can modify the *PoolType* value by bitwise-ORing this value with the POOL_COLD_ALLOCATION flag as a hint to the kernel to allocate the memory from pages that are likely to be paged out quickly. To reduce the amount of resident pool memory as much as possible, you should not reference these allocations frequently. The POOL_COLD_ALLOCATION flag is only advisory.

### -param NumberOfBytes [in]

The number of bytes to allocate.

### -param Tag [in]

The pool tag to use for the allocated memory. Specify the pool tag as a non-zero character literal of one to to four characters delimited by single quotation marks (for example, 'Tag1'). The string is usually specified in reverse order (for example, '1gaT'). Each ASCII character in the tag must be a value in the range 0x20 (space) to 0x7E (tilde). Each allocation code path should use a unique pool tag to help debuggers and verifiers identify the code path.

## -returns

**ExAllocatePoolWithTag** returns **NULL** if there is insufficient memory in the free pool to satisfy the request. Otherwise, the routine returns a pointer to the allocated memory.

## -remarks

This routine is used for the general pool allocation of memory.

If *NumberOfBytes* is PAGE_SIZE or greater, a page-aligned buffer is allocated. Memory allocations of PAGE_SIZE or less are allocated within a page and do not cross page boundaries. Memory allocations of less than PAGE_SIZE are not necessarily page-aligned but are aligned to 8-byte boundaries in 32-bit systems and to 16-byte boundaries in 64-bit systems.

A successful allocation requesting *NumberOfBytes* < PAGE_SIZE of nonpaged pool gives the caller exactly the number of requested bytes of memory. If an allocation request for *NumberOfBytes* > PAGE_SIZE succeeds and *NumberOfBytes* is not an exact multiple of PAGE_SIZE, the last page in the allocation contains bytes that are not part of the caller's allocation. If possible, the pool allocator uses these bytes. To avoid corrupting data that belongs to other kernel-mode components, drivers must access only storage addresses that they have explicitly allocated.

The system associates the pool tag with the allocated memory. Programming tools, such as WinDbg, can display the pool tag associated with each allocated buffer. Gflags, a tool included in [Debugging Tools for Windows](/windows-hardware/drivers/debugger/index), turns on a system feature that requests allocation from [special pool](/windows-hardware/drivers/devtest/special-pool) for a particular pool tag. [Poolmon](/windows-hardware/drivers/devtest/poolmon), which is included in the WDK, tracks memory by pool tag.

The value of *Tag* is stored, and sometimes displayed, in reverse (little-endian) order. For example, if a caller passes 'Fred' as a *Tag*, it appears as "derF" in a pool dump and in pool usage tracking in the debugger, and as 0x64657246 in the registry and in tool displays.

The allocated buffer can be freed with either [ExFreePool](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-exfreepool) or [ExFreePoolWithTag](/windows-hardware/drivers/ddi/wdm/nf-wdm-exfreepoolwithtag).

The system automatically sets certain standard event objects when the amount of pool (paged or nonpaged) is high or low. Drivers can wait for these events to tune their pool usage. For more information, see [Standard Event Objects](/windows-hardware/drivers/kernel/standard-event-objects).

Callers of **ExAllocatePoolWithTag** must be executing at IRQL <= DISPATCH_LEVEL. A caller executing at DISPATCH_LEVEL must specify a **NonPaged***Xxx* value for *PoolType*. A caller executing at IRQL <= APC_LEVEL can specify any **POOL_TYPE** value, but the IRQL and environment must also be considered for determining the page type.

Do not set *NumberOfBytes* = 0. Avoid zero-length allocations because they waste pool header space and, in many cases, indicate a potential validation issue in the calling code. For this reason, [Driver Verifier](/windows-hardware/drivers/what-s-new-in-driver-development) flags such allocations as possible errors.

In a non-uniform memory access (NUMA) multiprocessor architecture, **ExAllocatePoolWithTag** tries to allocate memory that is local to the processor that is calling **ExAllocatePoolWithTag**. If no local memory is available, **ExAllocatePoolWithTag** allocates the closest available memory.

Memory that **ExAllocatePoolWithTag** allocates is uninitialized. A kernel-mode driver must first zero this memory if it is going to make it visible to user-mode software (to avoid leaking potentially privileged contents).

## -see-also

[ExAllocatePoolWithQuotaTag](/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatepoolwithquotatag)

[ExAllocatePoolWithTagPriority](/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatepoolwithtagpriority)

[ExFreePool](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-exfreepool)

[ExFreePoolWithTag](/windows-hardware/drivers/ddi/wdm/nf-wdm-exfreepoolwithtag)

[POOL_TYPE](/windows-hardware/drivers/ddi/wdm/ne-wdm-_pool_type)
