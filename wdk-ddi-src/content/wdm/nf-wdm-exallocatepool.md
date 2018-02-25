---
UID: NF:wdm.ExAllocatePool
title: ExAllocatePool function
author: windows-driver-content
description: The ExAllocatePool routine is obsolete, and is exported only for existing binaries. Use ExAllocatePoolWithTag instead.ExAllocatePool allocates pool memory of the specified type and returns a pointer to the allocated block.
old-location: kernel\exallocatepool.htm
old-project: kernel
ms.assetid: b5b88a14-3d60-45bf-8340-b78175a55e01
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , A, E, ExAllocatePool, ExAllocatePool routine [Kernel-Mode Driver Architecture], P, a, c, e, k102_02ff5510-3d96-4a15-a0da-5da56e14b1b8.xml, kernel.exallocatepool, l, o, t, wdm/ExAllocatePool, x"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Classpnp.h, Smcnt.h
req.target-type: Universal
req.target-min-winverclnt: Obsolete. This routine is exported only for existing binaries. Use ExAllocatePoolWithTag instead.
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
-	ExAllocatePool
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ExAllocatePool function


## -description


The <b>ExAllocatePool</b> routine is <u>obsolete</u>, and is exported only for existing binaries. Use <a href="..\wdm\nf-wdm-exallocatepoolwithtag.md">ExAllocatePoolWithTag</a> instead.

<b>ExAllocatePool</b> allocates pool memory of the specified type and returns a pointer to the allocated block.


## -syntax


````
PVOID ExAllocatePool(
  _In_ POOL_TYPE PoolType,
  _In_ SIZE_T    NumberOfBytes
);
````


## -parameters




#### - PoolType [in]

Specifies the type of pool memory to allocate. For a description of the available pool memory types, see <a href="..\wudfwdm\ne-wudfwdm-_pool_type.md">POOL_TYPE</a>.

You can modify <i>PoolType</i> by using a bitwise OR with the POOL_COLD_ALLOCATION flag as a hint to the kernel to allocate the memory from pages that are likely to be paged out quickly. To reduce the amount of resident pool memory as much as possible, you should not reference these allocations frequently. The POOL_COLD_ALLOCATION flag is only advisory and is available for Windows XP and later versions of the Windows operating system.


#### - NumberOfBytes [in]

Specifies the number of bytes to allocate. 


## -returns



<b>ExAllocatePool</b> returns <b>NULL</b> if there is insufficient memory in the free pool to satisfy the request. Otherwise the routine returns a pointer to the allocated memory.




## -remarks



This routine is used for the general pool allocation of memory.

If <i>NumberOfBytes</i> is PAGE_SIZE or greater, a page-aligned buffer is allocated. Memory allocations of PAGE_SIZE or less do not cross page boundaries. Memory allocations of less than PAGE_SIZE are not necessarily page-aligned but are aligned to 8-byte boundaries in 32-bit systems and to 16-byte boundaries in 64-bit systems.

A successful allocation requesting <i>NumberOfBytes</i> &lt; PAGE_SIZE of nonpaged pool gives the caller exactly the number of requested bytes of memory. If an allocation request for <i>NumberOfBytes</i> &gt; PAGE_SIZE succeeds and <i>NumberOfBytes</i> is not an exact multiple of PAGE_SIZE, the last page in the allocation contains bytes that are not part of the caller's allocation. If possible, the pool allocator uses these bytes. To avoid corrupting data that belongs to other kernel-mode components, drivers must access only storage addresses that they have explicitly allocated.

If <b>ExAllocatePool</b> returns <b>NULL</b>, the caller should return the NTSTATUS value STATUS_INSUFFICIENT_RESOURCES or should delay processing to another point in time.

Callers of <b>ExAllocatePool</b> must be executing at IRQL &lt;= DISPATCH_LEVEL. A caller executing at DISPATCH_LEVEL must specify a <b>NonPaged</b><i>Xxx</i> value for <i>PoolType</i>. A caller executing at IRQL &lt;= APC_LEVEL can specify any <b>POOL_TYPE</b> value, but the IRQL and environment must also be considered for determining the page type.

<div class="alert"><b>Note</b>  Do not set <i>NumberOfBytes</i> = 0. Avoid zero-length allocations because they waste pool header space and, in many cases, indicate a potential validation issue in the calling code. For this reason, <a href="https://msdn.microsoft.com/library/windows/hardware/ff557262">Driver Verifier</a> flags such allocations as possible errors.</div>
<div> </div>
The system automatically sets certain standard event objects when the amount of pool (paged or nonpaged) is high or low. Drivers can wait for these events to tune their pool usage. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563847">Standard Event Objects</a>.

<div class="alert"><b>Note</b>  Memory that <b>ExAllocatePool</b> allocates is uninitialized. A kernel-mode driver must first zero this memory if it is going to make it visible to user-mode software (to avoid leaking potentially privileged contents).</div>
<div> </div>



## -see-also

<a href="..\wudfwdm\ne-wudfwdm-_pool_type.md">POOL_TYPE</a>



<a href="..\ntddk\nf-ntddk-exfreepool.md">ExFreePool</a>



<a href="..\wdm\nf-wdm-exallocatepoolwithtag.md">ExAllocatePoolWithTag</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExAllocatePool routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

