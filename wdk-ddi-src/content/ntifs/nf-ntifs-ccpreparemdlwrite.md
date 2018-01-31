---
UID: NF:ntifs.CcPrepareMdlWrite
title: CcPrepareMdlWrite function
author: windows-driver-content
description: The CcPrepareMdlWrite routine provides direct access to cached file memory so that the caller can write data to the file.
old-location: ifsk\ccpreparemdlwrite.htm
old-project: ifsk
ms.assetid: 84e231ad-50a1-471e-b514-6b769f2a7e1e
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: CcPrepareMdlWrite routine [Installable File System Drivers], ifsk.ccpreparemdlwrite, ntifs/CcPrepareMdlWrite, CcPrepareMdlWrite, ccref_2523ff15-d200-4f45-bc05-aab30afadc15.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "< DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	CcPrepareMdlWrite
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# CcPrepareMdlWrite function


## -description


The <b>CcPrepareMdlWrite</b> routine provides direct access to cached file memory so that the caller can write data to the file.


## -syntax


````
VOID CcPrepareMdlWrite(
  _In_  PFILE_OBJECT     FileObject,
  _In_  PLARGE_INTEGER   FileOffset,
  _In_  ULONG            Length,
  _Out_ PMDL             *MdlChain,
  _Out_ PIO_STATUS_BLOCK IoStatus
);
````


## -parameters




#### - FileObject [in]

Pointer to a file object for the cached file. 


#### - FileOffset [in]

Pointer to a variable that specifies the starting byte offset within the cached file where the data is to be written.


#### - Length [in]

Length in bytes of the data to be written to the system cache.


#### - MdlChain [out]

A chain of one or more memory descriptor lists (MDL) describing the pages to which the data is to be written.


#### - IoStatus [out]

Pointer to an IO_STATUS_BLOCK structure. If the call to <b>CcPrepareMdlWrite</b> succeeds, <i>IoStatus.Status</i> is set to STATUS_SUCCESS. Otherwise, it is set to an appropriate NTSTATUS error code. <i>IoStatus.Information</i> is set to the actual number of bytes that were successfully locked down in the MDL chain.


## -returns


None



## -remarks


<b>CcPrepareMdlWrite</b> is similar to <a href="..\ntifs\nf-ntifs-cccopywrite.md">CcCopyWrite</a>, except that the data is not copied to the cached file. Instead, the physical pages to be overwritten in the system cache are locked in memory, and <b>CcPrepareMdlWrite</b> returns one or more memory descriptor lists (MDL) describing the specified byte range. These pages remain locked in memory until <a href="..\ntifs\nf-ntifs-ccmdlwritecomplete.md">CcMdlWriteComplete</a> or <a href="..\ntifs\nf-ntifs-ccmdlwriteabort.md">CcMdlWriteAbort</a> is called. Thus each call to <b>CcPrepareMdlWrite</b> must be followed by a call to <b>CcMdlWriteComplete</b> or <b>CcMdlWriteAbort</b>.

Note that the pages described by the MDL are locked in memory, but not mapped in system space. The caller can perform this mapping by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff554559">MmGetSystemAddressForMdlSafe</a>.

Note that even if the call to <b>CcPrepareMdlWrite</b> fails, one or more MDLs may have been allocated. The caller can examine the value of <i>IoStatus.Information</i> to determine whether this has occurred. If it has, the caller must call <a href="..\ntifs\nf-ntifs-ccmdlwritecomplete.md">CcMdlWriteComplete</a> to free the allocated MDLs.

If any failure occurs, <b>CcPrepareMdlWrite</b> raises a status exception for that particular failure. For example, if a pool allocation failure occurs, <b>CcPrepareMdlWrite</b> raises a STATUS_INSUFFICIENT_RESOURCES exception; if an I/O error occurs, <b>CcPrepareMdlWrite</b> raises the status exception of the I/O error. Therefore, to gain control if a failure occurs, the driver should wrap the call to <b>CcPrepareMdlWrite</b> in a <b>try-except</b> or <b>try-finally</b> statement.

To cache a file, use <a href="..\ntifs\nf-ntifs-ccinitializecachemap.md">CcInitializeCacheMap</a>.



## -see-also

<a href="..\wdm\nf-wdm-iobuildpartialmdl.md">IoBuildPartialMdl</a>

<a href="..\ntifs\nf-ntifs-ccmdlwriteabort.md">CcMdlWriteAbort</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554537">MmGetMdlPfnArray</a>

<a href="..\wdm\nf-wdm-mmgetmdlbytecount.md">MmGetMdlByteCount</a>

<a href="..\wdm\nf-wdm-mmunmaplockedpages.md">MmUnmapLockedPages</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554539">MmGetMdlVirtualAddress</a>

<a href="..\wdm\nf-wdm-mmunlockpages.md">MmUnlockPages</a>

<a href="..\ntifs\nf-ntifs-ccinitializecachemap.md">CcInitializeCacheMap</a>

<a href="..\wdm\nf-wdm-ioallocatemdl.md">IoAllocateMdl</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554660">MmPrepareMdlForReuse</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554568">MmInitializeMdl</a>

<a href="..\wdm\nf-wdm-mmmaplockedpages.md">MmMapLockedPages</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554559">MmGetSystemAddressForMdlSafe</a>

<a href="..\wdm\nf-wdm-mmgetsystemaddressformdl.md">MmGetSystemAddressForMdl</a>

<a href="..\ntifs\nf-ntifs-cccopywrite.md">CcCopyWrite</a>

<a href="..\wdm\nf-wdm-mmprobeandlockpages.md">MmProbeAndLockPages</a>

<a href="..\ntifs\nf-ntifs-ccmdlwritecomplete.md">CcMdlWriteComplete</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554533">MmGetMdlByteOffset</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20CcPrepareMdlWrite routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

