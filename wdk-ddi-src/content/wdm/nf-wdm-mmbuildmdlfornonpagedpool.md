---
UID: NF:wdm.MmBuildMdlForNonPagedPool
title: MmBuildMdlForNonPagedPool function (wdm.h)
description: The MmBuildMdlForNonPagedPool routine receives an MDL that specifies a nonpaged virtual memory buffer, and updates it to describe the underlying physical pages.
old-location: kernel\mmbuildmdlfornonpagedpool.htm
tech.root: kernel
ms.assetid: f83a9a57-be44-4aa0-bb2e-740f48d82e06
ms.date: 04/30/2018
ms.keywords: MmBuildMdlForNonPagedPool, MmBuildMdlForNonPagedPool routine [Kernel-Mode Driver Architecture], k106_58d8437c-b6da-4b88-85a4-300392fb58f9.xml, kernel.mmbuildmdlfornonpagedpool, wdm/MmBuildMdlForNonPagedPool
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<=DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- MmBuildMdlForNonPagedPool
product:
- Windows
targetos: Windows
req.typenames: 
---

# MmBuildMdlForNonPagedPool function


## -description


The <b>MmBuildMdlForNonPagedPool</b> routine receives an MDL that specifies a nonpaged virtual memory buffer, and updates it to describe the underlying physical pages. 


## -parameters




### -param MemoryDescriptorList [in, out]

A pointer to an MDL that specifies a virtual memory buffer in nonpaged memory. The caller used the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548263">IoAllocateMdl</a> routine to create the MDL for this buffer. 


## -returns



None




## -remarks



At entry, the specified MDL must describe a buffer in nonpaged system memory or in memory that is locked down (the physical pages cannot be traded), such as memory that is allocated by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544520">ExAllocatePoolWithTag</a> routine with <i>PoolType</i> = <b>NonPagedPool</b> or by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554464">MmAllocateContiguousMemorySpecifyCache</a> routine. <b>MmBuildMdlForNonPagedPool</b> updates the MDL to describe the underlying physical pages.


<b>MmBuildMdlForNonPagedPool</b> may not be used with MDLs describing buffers allocated on a kernel stack. To build an MDL describing a kernel stack buffer, drivers must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff554664">MmProbeAndLockPages</a>. This is because kernel stack pages can be traded unless they are probe-and-locked. This rule applies even if the driver guarantees that the kernel stack cannot be paged out.

Because the pages described by the MDL are already nonpageable and are already mapped to the system address space, drivers must not try to lock them by using the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554664">MmProbeAndLockPages</a> routine, or to create additional system-address-space mappings by using the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554629">MmMapLockedPagesSpecifyCache</a> routine. Similarly, drivers must not try to unlock the pages by using the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556381">MmUnlockPages</a> routine, or to release the existing system-address-space mapping by using the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556391">MmUnmapLockedPages</a> routine. If a driver performs any of these illegal operations on an MDL that is built by <b>MmBuildMdlForNonPagedPool,</b> the resulting behavior is undefined.

Passing an MDL built by <b>MmBuildMdlForNonPagedPool</b> to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554559">MmGetSystemAddressForMdlSafe</a> routine is allowed. The <b>MmGetSystemAddressForMdlSafe</b> call, in this case, simply returns the starting virtual address of the buffer that is described by the MDL.

A driver can use the <b>MmMapLockedPagesSpecifyCache</b> routine to map an MDL that is built by <b>MmBuildMdlForNonPagedPool</b> into user virtual address space. However, the driver must perform this operation in a way that avoids certain security issues. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554629">MmMapLockedPagesSpecifyCache</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544520">ExAllocatePoolWithTag</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554464">MmAllocateContiguousMemorySpecifyCache</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554559">MmGetSystemAddressForMdlSafe</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554629">MmMapLockedPagesSpecifyCache</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554664">MmProbeAndLockPages</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556381">MmUnlockPages</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556391">MmUnmapLockedPages</a>
 

 

