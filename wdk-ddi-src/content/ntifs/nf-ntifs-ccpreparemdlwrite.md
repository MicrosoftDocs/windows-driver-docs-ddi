---
UID: NF:ntifs.CcPrepareMdlWrite
title: CcPrepareMdlWrite function (ntifs.h)
description: The CcPrepareMdlWrite routine provides direct access to cached file memory so that the caller can write data to the file.
old-location: ifsk\ccpreparemdlwrite.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["CcPrepareMdlWrite function"]
ms.keywords: CcPrepareMdlWrite, CcPrepareMdlWrite routine [Installable File System Drivers], ccref_2523ff15-d200-4f45-bc05-aab30afadc15.xml, ifsk.ccpreparemdlwrite, ntifs/CcPrepareMdlWrite
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
targetos: Windows
req.typenames: 
f1_keywords:
 - CcPrepareMdlWrite
 - ntifs/CcPrepareMdlWrite
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - CcPrepareMdlWrite
---

# CcPrepareMdlWrite function


## -description

The <b>CcPrepareMdlWrite</b> routine provides direct access to cached file memory so that the caller can write data to the file.

## -parameters

### -param FileObject 

[in]
Pointer to a file object for the cached file.

### -param FileOffset 

[in]
Pointer to a variable that specifies the starting byte offset within the cached file where the data is to be written.

### -param Length 

[in]
Length in bytes of the data to be written to the system cache.

### -param MdlChain 

[out]
A chain of one or more memory descriptor lists (MDL) describing the pages to which the data is to be written.

### -param IoStatus 

[out]
Pointer to an IO_STATUS_BLOCK structure. If the call to <b>CcPrepareMdlWrite</b> succeeds, <i>IoStatus.Status</i> is set to STATUS_SUCCESS. Otherwise, it is set to an appropriate NTSTATUS error code. <i>IoStatus.Information</i> is set to the actual number of bytes that were successfully locked down in the MDL chain.

## -remarks

<b>CcPrepareMdlWrite</b> is similar to <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-cccopywrite">CcCopyWrite</a>, except that the data is not copied to the cached file. Instead, the physical pages to be overwritten in the system cache are locked in memory, and <b>CcPrepareMdlWrite</b> returns one or more memory descriptor lists (MDL) describing the specified byte range. These pages remain locked in memory until <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccmdlwritecomplete">CcMdlWriteComplete</a> or <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccmdlwriteabort">CcMdlWriteAbort</a> is called. Thus each call to <b>CcPrepareMdlWrite</b> must be followed by a call to <b>CcMdlWriteComplete</b> or <b>CcMdlWriteAbort</b>.

Note that the pages described by the MDL are locked in memory, but not mapped in system space. The caller can perform this mapping by calling [MmGetSystemAddressForMdlSafe](../wdm/nf-wdm-mmgetsystemaddressformdlsafe.md).

Note that even if the call to <b>CcPrepareMdlWrite</b> fails, one or more MDLs may have been allocated. The caller can examine the value of <i>IoStatus.Information</i> to determine whether this has occurred. If it has, the caller must call <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccmdlwritecomplete">CcMdlWriteComplete</a> to free the allocated MDLs.

If any failure occurs, <b>CcPrepareMdlWrite</b> raises a status exception for that particular failure. For example, if a pool allocation failure occurs, <b>CcPrepareMdlWrite</b> raises a STATUS_INSUFFICIENT_RESOURCES exception; if an I/O error occurs, <b>CcPrepareMdlWrite</b> raises the status exception of the I/O error. Therefore, to gain control if a failure occurs, the driver should wrap the call to <b>CcPrepareMdlWrite</b> in a <b>try-except</b> or <b>try-finally</b> statement.

To cache a file, use <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccinitializecachemap">CcInitializeCacheMap</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-cccopywrite">CcCopyWrite</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccinitializecachemap">CcInitializeCacheMap</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccmdlwriteabort">CcMdlWriteAbort</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccmdlwritecomplete">CcMdlWriteComplete</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ioallocatemdl">IoAllocateMdl</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iobuildpartialmdl">IoBuildPartialMdl</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-mmgetmdlbytecount">MmGetMdlByteCount</a>



[MmGetMdlByteOffset](../wdm/nf-wdm-mmgetmdlbyteoffset.md)



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-mmgetmdlpfnarray">MmGetMdlPfnArray</a>



[MmGetMdlVirtualAddress](../wdm/nf-wdm-mmgetmdlvirtualaddress.md)



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-mmgetsystemaddressformdl">MmGetSystemAddressForMdl</a>



[MmGetSystemAddressForMdlSafe](../wdm/nf-wdm-mmgetsystemaddressformdlsafe.md)



[MmInitializeMdl](../wdm/nf-wdm-mminitializemdl.md)



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-mmmaplockedpages">MmMapLockedPages</a>



[MmPrepareMdlForReuse](../wdm/nf-wdm-mmpreparemdlforreuse.md)



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-mmprobeandlockpages">MmProbeAndLockPages</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-mmunlockpages">MmUnlockPages</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-mmunmaplockedpages">MmUnmapLockedPages</a>