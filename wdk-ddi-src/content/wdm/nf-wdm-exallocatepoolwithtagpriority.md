---
UID: NF:wdm.ExAllocatePoolWithTagPriority
title: ExAllocatePoolWithTagPriority function (wdm.h)
description: The ExAllocatePoolWithTagPriority routine allocates pool memory of the specified type.
tech.root: kernel
ms.date: 12/12/2022
keywords: ["ExAllocatePoolWithTagPriority function"]
ms.keywords: ExAllocatePoolWithTagPriority, ExAllocatePoolWithTagPriority routine [Kernel-Mode Driver Architecture], k102_cca6adc7-0f37-4565-858d-a191062f4fbd.xml, kernel.exallocatepoolwithtagpriority, wdm/ExAllocatePoolWithTagPriority
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlExAllocatePool, IrqlExFree2, HwStorPortProhibitedDDIs, SpNoWait, StorPortStartIo
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
 - ExAllocatePoolWithTagPriority
 - wdm/ExAllocatePoolWithTagPriority
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ExAllocatePoolWithTagPriority
---

## -description

The **ExAllocatePoolWithTagPriority** routine allocates pool memory of the specified type.

>[!WARNING]
> ExAllocatePoolWithTagPriority has been deprecated in Windows 10, version 2004 and has been replaced by [ExAllocatePool3](nf-wdm-exallocatepool3.md). For more information, see [Updating deprecated ExAllocatePool calls to ExAllocatePool2 and ExAllocatePool3](/windows-hardware/drivers/kernel/updating-deprecated-exallocatepool-calls).

## -parameters

### -param PoolType [in]

The type of pool memory to allocate. For a description of the available pool memory types, see [POOL_TYPE](/windows-hardware/drivers/ddi/wdm/ne-wdm-_pool_type).

You can modify the *PoolType* value by bitwise-ORing this value with the POOL_RAISE_IF_ALLOCATION_FAILURE flag. This flag causes an exception to be raised if the request cannot be satisfied.

Similarly, you can modify the *PoolType* value by bitwise-ORing this value with the POOL_COLD_ALLOCATION flag as a hint to the kernel to allocate the memory from pages that are likely to be paged out  quickly. To reduce the amount of resident pool memory as much as possible, you should not reference these allocations frequently. The POOL_COLD_ALLOCATION flag is only advisory and is available starting with Windows XP.

### -param NumberOfBytes [in]

The number of bytes to allocate.

### -param Tag [in]

The pool tag to use for the allocated memory. For more information, see the *Tag* parameter of [ExAllocatePoolWithTag](/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatepoolwithtag).

### -param Priority [in]

The priority of this request. Set this parameter to one of the following **EX_POOL_PRIORITY** enumeration values.

| Priority value | Description |
|---|---|
| **LowPoolPriority** | Specifies that the system may fail the request when it runs low on resources. Driver allocations that can recover from an allocation failure use this priority. |
| **NormalPoolPriority** | Specifies that the system may fail the request when it runs very low on resources. Most drivers should use this value. |
| **HighPoolPriority** | Specifies that the system must not fail the request, unless it is completely out of resources. Drivers only use this value when it is critically important for the request to succeed. |

The **EX_POOL_PRIORITY** enumeration defines ***Xxx*SpecialPoolOverrun** and ***Xxx*SpecialPoolUnderrun** variants to specify how memory should be allocated when [Driver Verifier](/windows-hardware/drivers/what-s-new-in-driver-development) (or special pool) is enabled. If the driver specifies ***Xxx*SpecialPoolUnderrun**, when the [memory manager](/windows-hardware/drivers/kernel/windows-kernel-mode-memory-manager) allocates memory from [special pool](/windows-hardware/drivers/devtest/special-pool), it allocates it at the start of a physical page. If the driver specifies ***Xxx*SpecialPoolOverrun**, the memory manager allocates it at the end of a physical page.

## -returns

**ExAllocatePoolWithTagPriority** returns **NULL** if there is insufficient memory in the free pool to satisfy the request unless POOL_RAISE_IF_ALLOCATION_FAILURE is specified. Otherwise, the routine returns a pointer to the allocated memory.

## -remarks

Callers of **ExAllocatePoolWithTagPriority** must be executing at IRQL <= DISPATCH_LEVEL. A caller executing at DISPATCH_LEVEL must specify a **NonPaged***Xxx* value for *PoolType*. A caller executing at IRQL <= APC_LEVEL can specify any **POOL_TYPE** value, but the IRQL and environment must also be considered for determining the page type.

If *NumberOfBytes* is PAGE_SIZE or greater, a page-aligned buffer is allocated. Memory allocations of PAGE_SIZE or less are allocated within a page and do not cross page boundaries. Memory allocations of less than PAGE_SIZE are not necessarily page-aligned but are aligned to 8-byte boundaries in 32-bit systems and to 16-byte boundaries in 64-bit systems.

Do not set *NumberOfBytes* = 0. Avoid zero-length allocations because they waste pool header space and, in many cases, indicate a potential validation issue in the calling code. For this reason, [Driver Verifier](/windows-hardware/drivers/what-s-new-in-driver-development) flags such allocations as possible errors.

The system automatically sets certain standard event objects when the amount of pool (paged or nonpaged) is high or low. Drivers can wait for these events to tune their pool usage. For more information, see [Standard Event Objects](/windows-hardware/drivers/kernel/standard-event-objects).

In a non-uniform memory access (NUMA) multiprocessor architecture, **ExAllocatePoolWithTagPriority** tries to allocate memory that is local to the processor that is calling **ExAllocatePoolWithTagPriority**. If no local memory is available, **ExAllocatePoolWithTagPriority** allocates the closest available memory.

Memory that **ExAllocatePoolWithTagPriority** allocates is uninitialized. A kernel-mode driver must first zero this memory if it is going to make it visible to user-mode software (to avoid leaking potentially privileged contents).

## -see-also

[ExAllocatePoolWithTag](/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatepoolwithtag)

[ExFreePool](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-exfreepool)

[POOL_TYPE](/windows-hardware/drivers/ddi/wdm/ne-wdm-_pool_type)
