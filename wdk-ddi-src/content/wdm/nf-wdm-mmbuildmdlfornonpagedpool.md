---
UID: NF:wdm.MmBuildMdlForNonPagedPool
title: MmBuildMdlForNonPagedPool function
author: windows-driver-content
description: The MmBuildMdlForNonPagedPool routine receives an MDL that specifies a nonpaged virtual memory buffer, and updates it to describe the underlying physical pages.
old-location: kernel\mmbuildmdlfornonpagedpool.htm
old-project: kernel
ms.assetid: f83a9a57-be44-4aa0-bb2e-740f48d82e06
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: wdm/MmBuildMdlForNonPagedPool, MmBuildMdlForNonPagedPool, MmBuildMdlForNonPagedPool routine [Kernel-Mode Driver Architecture], k106_58d8437c-b6da-4b88-85a4-300392fb58f9.xml, kernel.mmbuildmdlfornonpagedpool
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	MmBuildMdlForNonPagedPool
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# MmBuildMdlForNonPagedPool function


## -description


The <b>MmBuildMdlForNonPagedPool</b> routine receives an MDL that specifies a nonpaged virtual memory buffer, and updates it to describe the underlying physical pages. 


## -syntax


````
VOID MmBuildMdlForNonPagedPool(
  _Inout_ PMDLX MemoryDescriptorList
);
````


## -parameters




### -param MemoryDescriptorList [in, out]

A pointer to an MDL that specifies a virtual memory buffer in nonpaged memory. The caller used the <a href="..\wdm\nf-wdm-ioallocatemdl.md">IoAllocateMdl</a> routine to create the MDL for this buffer. 


## -returns



None




## -remarks



At entry, the specified MDL must describe a buffer in nonpaged system memory, such as memory that is allocated by the <a href="..\wdm\nf-wdm-exallocatepoolwithtag.md">ExAllocatePoolWithTag</a> routine with <i>PoolType</i> = <b>NonPagedPool</b> or by the <a href="..\wdm\nf-wdm-mmallocatecontiguousmemoryspecifycache.md">MmAllocateContiguousMemorySpecifyCache</a> routine. <b>MmBuildMdlForNonPagedPool</b> updates the MDL to describe the underlying physical pages.

<b>MmBuildMdlForNonPagedPool</b> may not be used with MDLs describing buffers allocated on a kernel stack. To build an MDL describing a kernel stack buffer, drivers must call <a href="..\wdm\nf-wdm-mmprobeandlockpages.md">MmProbeAndLockPages</a>. This rule applies even if the driver guarantees that the kernel stack cannot be paged out.

Because the pages described by the MDL are already nonpageable and are already mapped to the system address space, drivers must not try to lock them by using the <a href="..\wdm\nf-wdm-mmprobeandlockpages.md">MmProbeAndLockPages</a> routine, or to create additional system-address-space mappings by using the <a href="..\wdm\nf-wdm-mmmaplockedpagesspecifycache.md">MmMapLockedPagesSpecifyCache</a> routine. Similarly, drivers must not try to unlock the pages by using the <a href="..\wdm\nf-wdm-mmunlockpages.md">MmUnlockPages</a> routine, or to release the existing system-address-space mapping by using the <a href="..\wdm\nf-wdm-mmunmaplockedpages.md">MmUnmapLockedPages</a> routine. If a driver performs any of these illegal operations on an MDL that is built by <b>MmBuildMdlForNonPagedPool,</b> the resulting behavior is undefined.

Passing an MDL built by <b>MmBuildMdlForNonPagedPool</b> to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554559">MmGetSystemAddressForMdlSafe</a> routine is allowed. The <b>MmGetSystemAddressForMdlSafe</b> call, in this case, simply returns the starting virtual address of the buffer that is described by the MDL.

A driver can use the <b>MmMapLockedPagesSpecifyCache</b> routine to map an MDL that is built by <b>MmBuildMdlForNonPagedPool</b> into user virtual address space. However, the driver must perform this operation in a way that avoids certain security issues. For more information, see <a href="..\wdm\nf-wdm-mmmaplockedpagesspecifycache.md">MmMapLockedPagesSpecifyCache</a>. 




## -see-also

<a href="..\wdm\nf-wdm-mmunmaplockedpages.md">MmUnmapLockedPages</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554559">MmGetSystemAddressForMdlSafe</a>



<a href="..\wdm\nf-wdm-mmprobeandlockpages.md">MmProbeAndLockPages</a>



<a href="..\wdm\nf-wdm-mmunlockpages.md">MmUnlockPages</a>



<a href="..\wdm\nf-wdm-mmmaplockedpagesspecifycache.md">MmMapLockedPagesSpecifyCache</a>



<a href="..\wdm\nf-wdm-exallocatepoolwithtag.md">ExAllocatePoolWithTag</a>



<a href="..\wdm\nf-wdm-mmallocatecontiguousmemoryspecifycache.md">MmAllocateContiguousMemorySpecifyCache</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20MmBuildMdlForNonPagedPool routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

