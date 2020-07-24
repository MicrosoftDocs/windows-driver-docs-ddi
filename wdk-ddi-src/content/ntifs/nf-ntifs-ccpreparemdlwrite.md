---
UID: NF:ntifs.CcPrepareMdlWrite
title: CcPrepareMdlWrite function (ntifs.h)
description: The CcPrepareMdlWrite routine provides direct access to cached file memory so that the caller can write data to the file.
old-location: ifsk\ccpreparemdlwrite.htm
tech.root: ifsk
ms.assetid: 84e231ad-50a1-471e-b514-6b769f2a7e1e
ms.date: 04/16/2018
keywords: ["CcPrepareMdlWrite function"]
ms.keywords: CcPrepareMdlWrite, CcPrepareMdlWrite routine [Installable File System Drivers], ccref_2523ff15-d200-4f45-bc05-aab30afadc15.xml, ifsk.ccpreparemdlwrite, ntifs/CcPrepareMdlWrite
f1_keywords:
 - "ntifs/CcPrepareMdlWrite"
 - "CcPrepareMdlWrite"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: 
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
req.irql: < DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- CcPrepareMdlWrite
targetos: Windows
req.typenames: 
---

# CcPrepareMdlWrite function


## -description


The <b>CcPrepareMdlWrite</b> routine provides direct access to cached file memory so that the caller can write data to the file.


## -parameters




### -param FileObject [in]

Pointer to a file object for the cached file. 


### -param FileOffset [in]

Pointer to a variable that specifies the starting byte offset within the cached file where the data is to be written.


### -param Length [in]

Length in bytes of the data to be written to the system cache.


### -param MdlChain [out]

A chain of one or more memory descriptor lists (MDL) describing the pages to which the data is to be written.


### -param IoStatus [out]

Pointer to an IO_STATUS_BLOCK structure. If the call to <b>CcPrepareMdlWrite</b> succeeds, <i>IoStatus.Status</i> is set to STATUS_SUCCESS. Otherwise, it is set to an appropriate NTSTATUS error code. <i>IoStatus.Information</i> is set to the actual number of bytes that were successfully locked down in the MDL chain.


## -remarks



<b>CcPrepareMdlWrite</b> is similar to <a href="https://msdn.microsoft.com/library/windows/hardware/ff539045">CcCopyWrite</a>, except that the data is not copied to the cached file. Instead, the physical pages to be overwritten in the system cache are locked in memory, and <b>CcPrepareMdlWrite</b> returns one or more memory descriptor lists (MDL) describing the specified byte range. These pages remain locked in memory until <a href="https://msdn.microsoft.com/library/windows/hardware/ff539172">CcMdlWriteComplete</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff539166">CcMdlWriteAbort</a> is called. Thus each call to <b>CcPrepareMdlWrite</b> must be followed by a call to <b>CcMdlWriteComplete</b> or <b>CcMdlWriteAbort</b>.

Note that the pages described by the MDL are locked in memory, but not mapped in system space. The caller can perform this mapping by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/mm-bad-pointer">MmGetSystemAddressForMdlSafe</a>.

Note that even if the call to <b>CcPrepareMdlWrite</b> fails, one or more MDLs may have been allocated. The caller can examine the value of <i>IoStatus.Information</i> to determine whether this has occurred. If it has, the caller must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff539172">CcMdlWriteComplete</a> to free the allocated MDLs.

If any failure occurs, <b>CcPrepareMdlWrite</b> raises a status exception for that particular failure. For example, if a pool allocation failure occurs, <b>CcPrepareMdlWrite</b> raises a STATUS_INSUFFICIENT_RESOURCES exception; if an I/O error occurs, <b>CcPrepareMdlWrite</b> raises the status exception of the I/O error. Therefore, to gain control if a failure occurs, the driver should wrap the call to <b>CcPrepareMdlWrite</b> in a <b>try-except</b> or <b>try-finally</b> statement.

To cache a file, use <a href="https://msdn.microsoft.com/library/windows/hardware/ff539135">CcInitializeCacheMap</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff539045">CcCopyWrite</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539135">CcInitializeCacheMap</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539166">CcMdlWriteAbort</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539172">CcMdlWriteComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioallocatemdl">IoAllocateMdl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iobuildpartialmdl">IoBuildPartialMdl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmgetmdlbytecount">MmGetMdlByteCount</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/mm-bad-pointer">MmGetMdlByteOffset</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/mm-bad-pointer">MmGetMdlPfnArray</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/mm-bad-pointer">MmGetMdlVirtualAddress</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmgetsystemaddressformdl">MmGetSystemAddressForMdl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/mm-bad-pointer">MmGetSystemAddressForMdlSafe</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/mm-bad-pointer">MmInitializeMdl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmmaplockedpages">MmMapLockedPages</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/mm-bad-pointer">MmPrepareMdlForReuse</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmprobeandlockpages">MmProbeAndLockPages</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmunlockpages">MmUnlockPages</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmunmaplockedpages">MmUnmapLockedPages</a>
 

 

