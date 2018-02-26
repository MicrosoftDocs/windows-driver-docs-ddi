---
UID: NF:classpnp.ExAllocatePoolWithQuota
title: ExAllocatePoolWithQuota macro
author: windows-driver-content
description: The ExAllocatePoolWithQuota routine is obsolete, and is exported only for existing driver binaries. Use ExAllocatePoolWithQuotaTag instead.ExAllocatePoolWithQuota allocates pool memory, charging quota against the current process.
old-location: kernel\exallocatepoolwithquota.htm
old-project: kernel
ms.assetid: cfdfae5e-4669-4e88-82d2-35fb2bca3012
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , A, E, ExAllocatePoolWithQuota, ExAllocatePoolWithQuota routine [Kernel-Mode Driver Architecture], P, Q, W, a, c, e, h, i, k102_6f0151af-8673-4fde-a4ab-744cb25d660f.xml, kernel.exallocatepoolwithquota, l, o, t, u, wdm/ExAllocatePoolWithQuota, x"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: classpnp.h
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
req.irql: "<= DISPATCH_LEVEL (see Remarks section)"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	ExAllocatePoolWithQuota
product: Windows
targetos: Windows
req.typenames: POWERSOURCEUPDATEEX, *PPOWERSOURCEUPDATEEX
---

# ExAllocatePoolWithQuota macro


## -description


The <b>ExAllocatePoolWithQuota</b> routine is <u>obsolete</u>, and is exported only for existing driver binaries. Use <a href="..\wdm\nf-wdm-exallocatepoolwithquotatag.md">ExAllocatePoolWithQuotaTag</a> instead.

<b>ExAllocatePoolWithQuota</b> allocates pool memory, charging quota against the current process.


## -syntax


````
PVOID ExAllocatePoolWithQuota(
  _In_ POOL_TYPE PoolType,
  _In_ SIZE_T    NumberOfBytes
);
````


## -parameters




### -param a

TBD


### -param b

TBD






#### - PoolType [in]

Specifies the type of pool memory to allocate. For a description of the available pool memory types, see <a href="..\wdm\ne-wdm-_pool_type.md">POOL_TYPE</a>.

You can modify <i>PoolType</i> by using a bitwise OR with the POOL_COLD_ALLOCATION flag as a hint to the kernel to allocate the memory from pages that are likely to be paged out quickly. To reduce the amount of resident pool memory as much as possible, you should not reference these allocations frequently. The POOL_COLD_ALLOCATION flag is only advisory and is available for Windows XP and later versions of the Windows operating system.


#### - NumberOfBytes [in]

Specifies the number of bytes to allocate.


## -remarks



This routine is called by highest-level drivers that allocate memory to satisfy a request in the context of the process that originally made the I/O request. Lower-level drivers call <a href="..\wdm\nf-wdm-exallocatepoolwithtag.md">ExAllocatePoolWithTag</a> instead.

If <i>NumberOfBytes</i> is PAGE_SIZE or greater, a page-aligned buffer is allocated. Quota is <u>not</u> charged to the process for allocations of PAGE_SIZE or greater.

Memory allocations of less than PAGE_SIZE are allocated within a page and do not cross page boundaries. Memory allocations of PAGE_SIZE or less are not necessarily page-aligned but are aligned to 8-byte boundaries in 32-bit systems and to 16-byte boundaries in 64-bit systems.

<div class="alert"><b>Note</b>  Do not set <i>NumberOfBytes</i> = 0. Avoid zero-length allocations because they waste pool header space and, in many cases, indicate a potential validation issue in the calling code. For this reason, <a href="https://msdn.microsoft.com/library/windows/hardware/ff557262">Driver Verifier</a> flags such allocations as possible errors.</div>
<div> </div>
The system automatically sets certain standard event objects when the amount of pool (paged or nonpaged) is high or low. Drivers can wait for these events to tune their pool usage. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563847">Standard Event Objects</a>.

<div class="alert"><b>Note</b>  Memory that <b>ExAllocatePoolWithQuota</b> allocates is uninitialized. A kernel-mode driver must first zero this memory if it is going to make it visible to user-mode software (to avoid leaking potentially privileged contents).</div>
<div> </div>
Callers of <b>ExAllocatePoolWithQuota</b> must be executing at IRQL &lt;= DISPATCH_LEVEL. A caller executing at DISPATCH_LEVEL must specify a <b>NonPaged</b><i>Xxx</i> value for <i>PoolType</i>. A caller executing at IRQL &lt;= APC_LEVEL can specify any <b>POOL_TYPE</b> value, but the IRQL and environment must also be considered for determining the pool type.




## -see-also

<a href="..\wdm\nf-wdm-exfreepool.md">ExFreePool</a>



<a href="..\wdm\ne-wdm-_pool_type.md">POOL_TYPE</a>



<a href="..\wdm\nf-wdm-exallocatepoolwithtag.md">ExAllocatePoolWithTag</a>



<a href="..\wdm\nf-wdm-exallocatepoolwithquotatag.md">ExAllocatePoolWithQuotaTag</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExAllocatePoolWithQuota routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

