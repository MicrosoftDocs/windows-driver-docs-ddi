---
UID: NF:wdm.ExAllocatePoolWithQuota
title: ExAllocatePoolWithQuota function (wdm.h)
description: The ExAllocatePoolWithQuota routine is obsolete, and is exported only for existing driver binaries. Use ExAllocatePoolWithQuotaTag instead.ExAllocatePoolWithQuota allocates pool memory, charging quota against the current process.
old-location: kernel\exallocatepoolwithquota.htm
tech.root: kernel
ms.date: 01/08/2021
keywords: ["ExAllocatePoolWithQuota function"]
ms.keywords: ExAllocatePoolWithQuota, ExAllocatePoolWithQuota routine [Kernel-Mode Driver Architecture], k102_6f0151af-8673-4fde-a4ab-744cb25d660f.xml, kernel.exallocatepoolwithquota, wdm/ExAllocatePoolWithQuota
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Classpnp.h
req.target-type: Universal
req.target-min-winverclnt: Obsolete. This routine is exported only for existing driver binaries. Use ExAllocatePoolWithQuotaTag instead.
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
 - ExAllocatePoolWithQuota
 - wdm/ExAllocatePoolWithQuota
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ExAllocatePoolWithQuota
---

# ExAllocatePoolWithQuota function


## -description

The <b>ExAllocatePoolWithQuota</b> routine is <u>obsolete</u>, and is exported only for existing driver binaries. Use <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatepoolwithquotatag">ExAllocatePoolWithQuotaTag</a> instead.

<b>ExAllocatePoolWithQuota</b> allocates pool memory, charging quota against the current process.

>[!IMPORTANT]
> ExAllocatePoolWithQuota has been deprecated in Windows 10, version 2004 and have been replaced by [ExAllocatePool2](/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatepool2). For more information, see [Updating deprecated ExAllocatePool calls to ExAllocatePool2 and ExAllocatePool3](updating-deprecated-exallocatepool-calls.md).

## -parameters

### -param PoolType 

[in]
Specifies the type of pool memory to allocate. For a description of the available pool memory types, see <a href="/windows-hardware/drivers/ddi/wdm/ne-wdm-_pool_type">POOL_TYPE</a>.

You can modify <i>PoolType</i> by using a bitwise OR with the POOL_COLD_ALLOCATION flag as a hint to the kernel to allocate the memory from pages that are likely to be paged out quickly. To reduce the amount of resident pool memory as much as possible, you should not reference these allocations frequently. The POOL_COLD_ALLOCATION flag is only advisory and is available for Windows XP and later versions of the Windows operating system.

### -param NumberOfBytes 

[in]
Specifies the number of bytes to allocate.

## -returns

<b>ExAllocatePoolWithQuota</b> returns a pointer to the allocated pool.

If the request cannot be satisfied, <b>ExAllocatePoolWithQuota</b> raises an exception.

## -remarks

This routine is called by highest-level drivers that allocate memory to satisfy a request in the context of the process that originally made the I/O request. Lower-level drivers call <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatepoolwithtag">ExAllocatePoolWithTag</a> instead.

If <i>NumberOfBytes</i> is PAGE_SIZE or greater, a page-aligned buffer is allocated. Quota is <u>not</u> charged to the process for allocations of PAGE_SIZE or greater.

Memory allocations of less than PAGE_SIZE are allocated within a page and do not cross page boundaries. Memory allocations of PAGE_SIZE or less are not necessarily page-aligned but are aligned to 8-byte boundaries in 32-bit systems and to 16-byte boundaries in 64-bit systems.

<div class="alert"><b>Note</b>  Do not set <i>NumberOfBytes</i> = 0. Avoid zero-length allocations because they waste pool header space and, in many cases, indicate a potential validation issue in the calling code. For this reason, <a href="/windows-hardware/drivers/what-s-new-in-driver-development">Driver Verifier</a> flags such allocations as possible errors.</div>
<div> </div>
The system automatically sets certain standard event objects when the amount of pool (paged or nonpaged) is high or low. Drivers can wait for these events to tune their pool usage. For more information, see <a href="/windows-hardware/drivers/kernel/standard-event-objects">Standard Event Objects</a>.

<div class="alert"><b>Note</b>  Memory that <b>ExAllocatePoolWithQuota</b> allocates is uninitialized. A kernel-mode driver must first zero this memory if it is going to make it visible to user-mode software (to avoid leaking potentially privileged contents).</div>
<div> </div>
Callers of <b>ExAllocatePoolWithQuota</b> must be executing at IRQL <= DISPATCH_LEVEL. A caller executing at DISPATCH_LEVEL must specify a <b>NonPaged</b><i>Xxx</i> value for <i>PoolType</i>. A caller executing at IRQL <= APC_LEVEL can specify any <b>POOL_TYPE</b> value, but the IRQL and environment must also be considered for determining the pool type.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatepoolwithquotatag">ExAllocatePoolWithQuotaTag</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatepoolwithtag">ExAllocatePoolWithTag</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-exfreepool">ExFreePool</a>



<a href="/windows-hardware/drivers/ddi/wdm/ne-wdm-_pool_type">POOL_TYPE</a>
