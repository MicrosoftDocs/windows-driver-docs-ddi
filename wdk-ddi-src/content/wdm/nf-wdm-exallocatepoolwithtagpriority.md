---
UID: NF:wdm.ExAllocatePoolWithTagPriority
title: ExAllocatePoolWithTagPriority function (wdm.h)
description: The ExAllocatePoolWithTagPriority routine allocates pool memory of the specified type.
old-location: kernel\exallocatepoolwithtagpriority.htm
tech.root: kernel
ms.assetid: 33087a37-e6fc-4b21-aa9e-e4617eeccd29
ms.date: 04/30/2018
ms.keywords: ExAllocatePoolWithTagPriority, ExAllocatePoolWithTagPriority routine [Kernel-Mode Driver Architecture], k102_cca6adc7-0f37-4565-858d-a191062f4fbd.xml, kernel.exallocatepoolwithtagpriority, wdm/ExAllocatePoolWithTagPriority
ms.topic: function
f1_keywords:
 - "wdm/ExAllocatePoolWithTagPriority"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.irql: "<= DISPATCH_LEVEL (see Remarks section)"
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- ExAllocatePoolWithTagPriority
product:
- Windows
targetos: Windows
req.typenames: 
---

# ExAllocatePoolWithTagPriority function


## -description


The <b>ExAllocatePoolWithTagPriority</b> routine allocates pool memory of the specified type.


## -parameters




### -param PoolType [in]

The type of pool memory to allocate. For a description of the available pool memory types, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ne-wdm-_pool_type">POOL_TYPE</a>.

You can modify the <i>PoolType</i> value by bitwise-ORing this value with the POOL_RAISE_IF_ALLOCATION_FAILURE flag. This flag causes an exception to be raised if the request cannot be satisfied.

Similarly, you can modify the <i>PoolType</i> value by bitwise-ORing this value with the POOL_COLD_ALLOCATION flag as a hint to the kernel to allocate the memory from pages that are likely to be paged out  quickly. To reduce the amount of resident pool memory as much as possible, you should not reference these allocations frequently. The POOL_COLD_ALLOCATION flag is only advisory and is available starting with Windows XP.


### -param NumberOfBytes [in]

The number of bytes to allocate.


### -param Tag [in]

The pool tag to use for the allocated memory. For more information, see the <i>Tag</i> parameter of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-exallocatepoolwithtag">ExAllocatePoolWithTag</a>.


### -param Priority [in]

The priority of this request. Set this parameter to one of the following <b>EX_POOL_PRIORITY</b> enumeration values.

<table>
<tr>
<th>Priority value</th>
<th>Description</th>
</tr>
<tr>
<td>
<b>LowPoolPriority</b>

</td>
<td>
Specifies that the system may fail the request when it runs low on resources. Driver allocations that can recover from an allocation failure use this priority.

</td>
</tr>
<tr>
<td>
<b>NormalPoolPriority</b>

</td>
<td>
Specifies that the system may fail the request when it runs very low on resources. Most drivers should use this value.

</td>
</tr>
<tr>
<td>
<b>HighPoolPriority</b>

</td>
<td>
Specifies that the system must not fail the request, unless it is completely out of resources. Drivers only use this value when it is critically important for the request to succeed.

</td>
</tr>
</table>
 

The <b>EX_POOL_PRIORITY</b> enumeration defines <b><i>Xxx</i>SpecialPoolOverrun</b> and <b><i>Xxx</i>SpecialPoolUnderrun</b> variants to specify how memory should be allocated when <a href="https://docs.microsoft.com/windows-hardware/drivers/what-s-new-in-driver-development">Driver Verifier</a> (or special pool) is enabled. If the driver specifies <b><i>Xxx</i>SpecialPoolUnderrun</b>, when the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/windows-kernel-mode-memory-manager">memory manager</a> allocates memory from <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/special-pool">special pool</a>, it allocates it at the start of a physical page. If the driver specifies <b><i>Xxx</i>SpecialPoolOverrun</b>, the memory manager allocates it at the end of a physical page.


## -returns



<b>ExAllocatePoolWithTagPriority</b> returns <b>NULL</b> if there is insufficient memory in the free pool to satisfy the request unless POOL_RAISE_IF_ALLOCATION_FAILURE is specified. Otherwise, the routine returns a pointer to the allocated memory. 




## -remarks



Callers of <b>ExAllocatePoolWithTagPriority</b> must be executing at IRQL <= DISPATCH_LEVEL. A caller executing at DISPATCH_LEVEL must specify a <b>NonPaged</b><i>Xxx</i> value for <i>PoolType</i>. A caller executing at IRQL <= APC_LEVEL can specify any <b>POOL_TYPE</b> value, but the IRQL and environment must also be considered for determining the page type.

If <i>NumberOfBytes</i> is PAGE_SIZE or greater, a page-aligned buffer is allocated. Memory allocations of PAGE_SIZE or less are allocated within a page and do not cross page boundaries. Memory allocations of less than PAGE_SIZE are not necessarily page-aligned but are aligned to 8-byte boundaries in 32-bit systems and to 16-byte boundaries in 64-bit systems.

<div class="alert"><b>Note</b>  Do not set <i>NumberOfBytes</i> = 0. Avoid zero-length allocations because they waste pool header space and, in many cases, indicate a potential validation issue in the calling code. For this reason, <a href="https://docs.microsoft.com/windows-hardware/drivers/what-s-new-in-driver-development">Driver Verifier</a> flags such allocations as possible errors.</div>
<div> </div>
The system automatically sets certain standard event objects when the amount of pool (paged or nonpaged) is high or low. Drivers can wait for these events to tune their pool usage. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/standard-event-objects">Standard Event Objects</a>.

In a non-uniform memory access (NUMA) multiprocessor architecture, <b>ExAllocatePoolWithTagPriority</b> tries to allocate memory that is local to the processor that is calling <b>ExAllocatePoolWithTagPriority</b>. If no local memory is available, <b>ExAllocatePoolWithTagPriority</b> allocates the closest available memory.

<div class="alert"><b>Note</b>  Memory that <b>ExAllocatePoolWithTagPriority</b> allocates is uninitialized. A kernel-mode driver must first zero this memory if it is going to make it visible to user-mode software (to avoid leaking potentially privileged contents).</div>
<div> </div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-exallocatepoolwithtag">ExAllocatePoolWithTag</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-exfreepool">ExFreePool</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ne-wdm-_pool_type">POOL_TYPE</a>
 

 

