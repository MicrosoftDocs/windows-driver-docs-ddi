---
UID: NF:wdm.IoBuildPartialMdl
title: IoBuildPartialMdl function
author: windows-driver-content
description: The IoBuildPartialMdl routine builds a new memory descriptor list (MDL) that represents part of a buffer that is described by an existing MDL.
old-location: kernel\iobuildpartialmdl.htm
old-project: kernel
ms.assetid: 26d88928-798f-46ee-9805-3b7da2056e2e
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: k104_8c9451f6-614c-45a2-b95a-4f0935588d7f.xml, IoBuildPartialMdl routine [Kernel-Mode Driver Architecture], IoBuildPartialMdl, kernel.iobuildpartialmdl, wdm/IoBuildPartialMdl
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
req.ddi-compliance: MdlAfterReqCompletedIntIoctlA, MdlAfterReqCompletedIoctlA, MdlAfterReqCompletedReadA, MdlAfterReqCompletedWriteA
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
-	IoBuildPartialMdl
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoBuildPartialMdl function


## -description


The <b>IoBuildPartialMdl</b> routine builds a new memory descriptor list (MDL) that represents part of a buffer that is described by an existing MDL. 


## -syntax


````
VOID IoBuildPartialMdl(
  _In_    PMDL  SourceMdl,
  _Inout_ PMDL  TargetMdl,
  _In_    PVOID VirtualAddress,
  _In_    ULONG Length
);
````


## -parameters




### -param SourceMdl [in]

A pointer to an MDL that describes the original buffer, of which a subrange is to be mapped. 


### -param TargetMdl [in, out]

A pointer to a caller-allocated MDL. This MDL must be large enough to describe the pages in the subrange that are specified by <i>VirtualAddress</i> and <i>Length</i>. 


### -param VirtualAddress [in]

A pointer to the base virtual address for the subrange to be described by the <i>TargetMdl</i>.


### -param Length [in]

Specifies the length, in bytes, to be mapped by the <i>TargetMdl</i>. This value, in combination with <i>VirtualAddress</i>, must specify a buffer that is a proper subrange of the buffer that is described by <i>SourceMdl</i>. If <i>Length</i> is zero, the subrange to be mapped starts at <i>VirtualAddress</i> and includes the remaining range described by the <i>SourceMdl</i>. 


## -returns



None




## -remarks



This routine builds a target MDL that describes a subrange of the buffer that is described by the source MDL. This subrange is specified by the <i>VirtualAddress</i> and <i>Length</i> parameters. The <i>SourceMdl</i> and <i>TargetMdl</i> parameters point to the source MDL and target MDL.

A driver can use <b>IoBuildPartialMdl</b> to split a large transfer request into smaller transfer requests. The physical pages that the source MDL describes must be locked before the driver calls <b>IoBuildPartialMdl</b>. Typically, the source MDL describes a buffer in user address space, and the driver calls the <a href="..\wdm\nf-wdm-mmprobeandlockpages.md">MmProbeAndLockPages</a> routine to lock the pages in this buffer. However, the driver can build the source MDL from nonpaged memory by calling the <a href="..\wdm\nf-wdm-mmbuildmdlfornonpagedpool.md">MmBuildMdlForNonPagedPool</a>, <a href="..\wdm\nf-wdm-mmallocatepagesformdlex.md">MmAllocatePagesForMdlEx</a>, or <a href="..\wdm\nf-wdm-mmallocatepagesformdl.md">MmAllocatePagesForMdl</a> routine.

A driver can map a partial MDL into the system address space by using the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554559">MmGetSystemAddressForMdlSafe</a> macro. If a partial MDL is built from a source MDL that is already mapped into the system address space, <b>MmGetSystemAddressForMdlSafe</b> uses the existing source mapping. Otherwise, <b>MmGetSystemAddressForMdlSafe</b> creates a new mapping. To prevent this new mapping from being leaked, drivers must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff554660">MmPrepareMdlForReuse</a> before reusing a partial MDL. In addition, the <a href="..\wdm\nf-wdm-iofreemdl.md">IoFreeMdl</a> routine releases the system-address-space mapping for a partial MDL, if such a mapping exists.

For more information about MDLs, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565421">Using MDLs</a>. 




## -see-also

<a href="..\wdm\nf-wdm-iofreemdl.md">IoFreeMdl</a>



<a href="..\wdm\nf-wdm-mmallocatepagesformdl.md">MmAllocatePagesForMdl</a>



<a href="..\wdm\nf-wdm-mmbuildmdlfornonpagedpool.md">MmBuildMdlForNonPagedPool</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554660">MmPrepareMdlForReuse</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554559">MmGetSystemAddressForMdlSafe</a>



<a href="..\wdm\nf-wdm-mmprobeandlockpages.md">MmProbeAndLockPages</a>



<a href="..\wdm\nf-wdm-mmallocatepagesformdlex.md">MmAllocatePagesForMdlEx</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoBuildPartialMdl routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

