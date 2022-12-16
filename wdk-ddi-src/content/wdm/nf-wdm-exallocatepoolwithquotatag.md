---
UID: NF:wdm.ExAllocatePoolWithQuotaTag
title: ExAllocatePoolWithQuotaTag function (wdm.h)
description: The ExAllocatePoolWithQuotaTag routine allocates pool memory, charging the quota against the current process.
tech.root: kernel
ms.date: 12/12/2022
keywords: ["ExAllocatePoolWithQuotaTag function"]
ms.keywords: ExAllocatePoolWithQuotaTag, ExAllocatePoolWithQuotaTag routine [Kernel-Mode Driver Architecture], k102_70106c3b-0d33-4fa7-be6a-2ac42cf3cbfe.xml, kernel.exallocatepoolwithquotatag, wdm/ExAllocatePoolWithQuotaTag
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: HwStorPortProhibitedDDIs, SpNoWait, StorPortStartIo
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= DISPATCH_LEVEL (see Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - ExAllocatePoolWithQuotaTag
 - wdm/ExAllocatePoolWithQuotaTag
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ExAllocatePoolWithQuotaTag
---


## -description

The **ExAllocatePoolWithQuotaTag** routine allocates pool memory, charging the quota against the current process.

>[!WARNING]
> ExAllocatePoolWithQuotaTag has been deprecated in Windows 10, version 2004 and has been replaced by [ExAllocatePool2](nf-wdm-exallocatepool2.md). For more information, see [Updating deprecated ExAllocatePool calls to ExAllocatePool2 and ExAllocatePool3](/windows-hardware/drivers/kernel/updating-deprecated-exallocatepool-calls).

## -parameters

### -param PoolType [in]

Specifies the type of pool memory to allocate. For a description of the available pool memory types, see [POOL_TYPE](/windows-hardware/drivers/ddi/wdm/ne-wdm-_pool_type).

You can modify the *PoolType* value by bitwise-ORing this value with the POOL_QUOTA_FAIL_INSTEAD_OF_RAISE flag. This flag causes the routine to return a **NULL** value if the request cannot be satisfied.

Similarly, you can modify the *PoolType* value by bitwise-ORing this value with the POOL_COLD_ALLOCATION flag as a hint to the kernel to allocate the memory from pages that are likely to be paged out quickly. To reduce the amount of resident pool memory as much as possible, you should not reference these allocations frequently. The POOL_COLD_ALLOCATION flag is only advisory and is supported in Windows XP and later versions of the Windows operating system.

### -param NumberOfBytes [in]

Specifies the number of bytes to allocate.

### -param Tag [in]

Specifies the pool tag for the allocated memory. For more information, see the *Tag* parameter of [ExAllocatePoolWithTag](/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatepoolwithtag).

## -returns

**ExAllocatePoolWithQuotaTag** returns a pointer to the allocated pool.

If the request cannot be satisfied, **ExAllocatePoolWithQuotaTag** raises an exception unless POOL_QUOTA_FAIL_INSTEAD_OF_RAISE is specified. Using POOL_QUOTA_FAIL_INSTEAD_OF_RAISE is preferred for performance reasons.

## -remarks

This routine is called by highest-level drivers that allocate memory to satisfy a request in the context of the process that originally made the I/O request. Lower-level drivers call [ExAllocatePoolWithTag](/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatepoolwithtag) instead.

If *NumberOfBytes* is PAGE_SIZE or greater, a page-aligned buffer is allocated. Memory allocations of PAGE_SIZE or less are allocated within a page and do not cross page boundaries. Memory allocations of less than PAGE_SIZE are not necessarily page-aligned but are aligned to 8-byte boundaries in 32-bit systems and to 16-byte boundaries in 64-bit systems.

The system associates the pool tag with the allocated memory. Programming tools, such as WinDbg, can display the pool tag associated with each allocated buffer. The value of *Tag* is normally displayed in reversed order. For example, if a caller passes 'Fred' as a *Tag*, it would appear as 'derF' if the pool is dumped or when tracking pool usage in the debugger.

The allocated buffer can be freed with either [ExFreePool](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-exfreepool) or [ExFreePoolWithTag](/windows-hardware/drivers/ddi/wdm/nf-wdm-exfreepoolwithtag).

Do not set *NumberOfBytes* = 0. Avoid zero-length allocations because they waste pool header space and, in many cases, indicate a potential validation issue in the calling code. For this reason, [Driver Verifier](/windows-hardware/drivers/what-s-new-in-driver-development) flags such allocations as possible errors.

The system automatically sets certain standard event objects when the amount of pool (paged or nonpaged) is high or low. Drivers can wait for these events to tune their pool usage. For more information, see [Standard Event Objects](/windows-hardware/drivers/kernel/standard-event-objects).

In a non-uniform memory access (NUMA) multiprocessor architecture, **ExAllocatePoolWithQuotaTag** tries to allocate memory that is local to the processor that is calling **ExAllocatePoolWithQuotaTag**. If no local memory is available, **ExAllocatePoolWithQuotaTag** allocates the closest available memory.

Memory that **ExAllocatePoolWithQuotaTag** allocates is uninitialized. A kernel-mode driver must first zero this memory if it is going to make it visible to user-mode software (to avoid leaking potentially privileged contents).

Callers of **ExAllocatePoolWithQuotaTag** must be executing at IRQL <= DISPATCH_LEVEL. A caller executing at DISPATCH_LEVEL must specify a **NonPaged***Xxx* value for *PoolType*. A caller executing at IRQL <= APC_LEVEL can specify any **POOL_TYPE** value, but the IRQL and environment must also be considered for determining the pool type.

## -see-also

[ExAllocatePoolWithTag](/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatepoolwithtag)

[ExFreePool](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-exfreepool)

[ExFreePoolWithTag](/windows-hardware/drivers/ddi/wdm/nf-wdm-exfreepoolwithtag)

[POOL_TYPE](/windows-hardware/drivers/ddi/wdm/ne-wdm-_pool_type)
