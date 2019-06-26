---
UID: NF:wdm.ExAllocatePoolWithQuotaTag
title: ExAllocatePoolWithQuotaTag function (wdm.h)
description: The ExAllocatePoolWithQuotaTag routine allocates pool memory, charging the quota against the current process.
old-location: kernel\exallocatepoolwithquotatag.htm
tech.root: kernel
ms.assetid: 1d2e4c8c-c76c-4936-80bf-005d8a393aa9
ms.date: 04/30/2018
ms.keywords: ExAllocatePoolWithQuotaTag, ExAllocatePoolWithQuotaTag routine [Kernel-Mode Driver Architecture], k102_70106c3b-0d33-4fa7-be6a-2ac42cf3cbfe.xml, kernel.exallocatepoolwithquotatag, wdm/ExAllocatePoolWithQuotaTag
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.irql: "<= DISPATCH_LEVEL (see Remarks section)"
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- ExAllocatePoolWithQuotaTag
product:
- Windows
targetos: Windows
req.typenames: 
---

# ExAllocatePoolWithQuotaTag function


## -description


The <b>ExAllocatePoolWithQuotaTag</b> routine allocates pool memory, charging the quota against the current process.


## -parameters




### -param PoolType [in]

Specifies the type of pool memory to allocate. For a description of the available pool memory types, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ne-wdm-_pool_type">POOL_TYPE</a>.

You can modify the <i>PoolType</i> value by bitwise-ORing this value with the POOL_QUOTA_FAIL_INSTEAD_OF_RAISE flag. This flag causes the routine to return a <b>NULL</b> value if the request cannot be satisfied.

Similarly, you can modify the <i>PoolType</i> value by bitwise-ORing this value with the POOL_COLD_ALLOCATION flag as a hint to the kernel to allocate the memory from pages that are likely to be paged out quickly. To reduce the amount of resident pool memory as much as possible, you should not reference these allocations frequently. The POOL_COLD_ALLOCATION flag is only advisory and is supported in Windows XP and later versions of the Windows operating system.


### -param NumberOfBytes [in]

Specifies the number of bytes to allocate.


### -param Tag [in]

Specifies the pool tag for the allocated memory. For more information, see the <i>Tag</i> parameter of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-exallocatepoolwithtag">ExAllocatePoolWithTag</a>.


## -returns



<b>ExAllocatePoolWithQuotaTag</b> returns a pointer to the allocated pool.

If the request cannot be satisfied, <b>ExAllocatePoolWithQuotaTag</b> raises an exception unless POOL_QUOTA_FAIL_INSTEAD_OF_RAISE is specified. Using POOL_QUOTA_FAIL_INSTEAD_OF_RAISE is preferred for performance reasons.




## -remarks



This routine is called by highest-level drivers that allocate memory to satisfy a request in the context of the process that originally made the I/O request. Lower-level drivers call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-exallocatepoolwithtag">ExAllocatePoolWithTag</a> instead.

If <i>NumberOfBytes</i> is PAGE_SIZE or greater, a page-aligned buffer is allocated. Memory allocations of PAGE_SIZE or less are allocated within a page and do not cross page boundaries. Memory allocations of less than PAGE_SIZE are not necessarily page-aligned but are aligned to 8-byte boundaries in 32-bit systems and to 16-byte boundaries in 64-bit systems.

The system associates the pool tag with the allocated memory. Programming tools, such as WinDbg, can display the pool tag associated with each allocated buffer. The value of <i>Tag</i> is normally displayed in reversed order. For example, if a caller passes 'Fred' as a <i>Tag</i>, it would appear as 'derF' if the pool is dumped or when tracking pool usage in the debugger.

The allocated buffer can be freed with either <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-exfreepool">ExFreePool</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-exfreepoolwithtag">ExFreePoolWithTag</a>.

<div class="alert"><b>Note</b>  Do not set <i>NumberOfBytes</i> = 0. Avoid zero-length allocations because they waste pool header space and, in many cases, indicate a potential validation issue in the calling code. For this reason, <a href="https://docs.microsoft.com/windows-hardware/drivers/what-s-new-in-driver-development">Driver Verifier</a> flags such allocations as possible errors.</div>
<div> </div>
The system automatically sets certain standard event objects when the amount of pool (paged or nonpaged) is high or low. Drivers can wait for these events to tune their pool usage. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/standard-event-objects">Standard Event Objects</a>.

In a non-uniform memory access (NUMA) multiprocessor architecture, <b>ExAllocatePoolWithQuotaTag</b> tries to allocate memory that is local to the processor that is calling <b>ExAllocatePoolWithQuotaTag</b>. If no local memory is available, <b>ExAllocatePoolWithQuotaTag</b> allocates the closest available memory.

<div class="alert"><b>Note</b>  Memory that <b>ExAllocatePoolWithQuotaTag</b> allocates is uninitialized. A kernel-mode driver must first zero this memory if it is going to make it visible to user-mode software (to avoid leaking potentially privileged contents).</div>
<div> </div>
Callers of <b>ExAllocatePoolWithQuotaTag</b> must be executing at IRQL <= DISPATCH_LEVEL. A caller executing at DISPATCH_LEVEL must specify a <b>NonPaged</b><i>Xxx</i> value for <i>PoolType</i>. A caller executing at IRQL <= APC_LEVEL can specify any <b>POOL_TYPE</b> value, but the IRQL and environment must also be considered for determining the pool type.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-exallocatepoolwithtag">ExAllocatePoolWithTag</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-exfreepool">ExFreePool</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-exfreepoolwithtag">ExFreePoolWithTag</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ne-wdm-_pool_type">POOL_TYPE</a>
 

 

