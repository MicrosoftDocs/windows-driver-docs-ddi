---
UID: NF:wdm.IoBuildPartialMdl
title: IoBuildPartialMdl function (wdm.h)
description: The IoBuildPartialMdl routine builds a new memory descriptor list (MDL) that represents part of a buffer that is described by an existing MDL.
old-location: kernel\iobuildpartialmdl.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["IoBuildPartialMdl function"]
ms.keywords: IoBuildPartialMdl, IoBuildPartialMdl routine [Kernel-Mode Driver Architecture], k104_8c9451f6-614c-45a2-b95a-4f0935588d7f.xml, kernel.iobuildpartialmdl, wdm/IoBuildPartialMdl
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
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IoBuildPartialMdl
 - wdm/IoBuildPartialMdl
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoBuildPartialMdl
---

# IoBuildPartialMdl function


## -description

The <b>IoBuildPartialMdl</b> routine builds a new memory descriptor list (MDL) that represents part of a buffer that is described by an existing MDL.

## -parameters

### -param SourceMdl [in]


A pointer to an MDL that describes the original buffer, of which a subrange is to be mapped.

### -param TargetMdl [in, out]


A pointer to a caller-allocated MDL. This MDL must be large enough to describe the pages in the subrange that are specified by <i>VirtualAddress</i> and <i>Length</i>.

### -param VirtualAddress [in]


A pointer to the base virtual address for the subrange to be described by the <i>TargetMdl</i>.

### -param Length [in]


Specifies the length, in bytes, to be mapped by the <i>TargetMdl</i>. This value, in combination with <i>VirtualAddress</i>, must specify a buffer that is a proper subrange of the buffer that is described by <i>SourceMdl</i>. If <i>Length</i> is zero, the subrange to be mapped starts at <i>VirtualAddress</i> and includes the remaining range described by the <i>SourceMdl</i>.

## -remarks

This routine builds a target MDL that describes a subrange of the buffer that is described by the source MDL. This subrange is specified by the <i>VirtualAddress</i> and <i>Length</i> parameters. The <i>SourceMdl</i> and <i>TargetMdl</i> parameters point to the source MDL and target MDL.

A driver can use <b>IoBuildPartialMdl</b> to split a large transfer request into smaller transfer requests. The physical pages that the source MDL describes must be locked before the driver calls <b>IoBuildPartialMdl</b>. Typically, the source MDL describes a buffer in user address space, and the driver calls the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-mmprobeandlockpages">MmProbeAndLockPages</a> routine to lock the pages in this buffer. However, the driver can build the source MDL from nonpaged memory by calling the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-mmbuildmdlfornonpagedpool">MmBuildMdlForNonPagedPool</a>, <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-mmallocatepagesformdlex">MmAllocatePagesForMdlEx</a>, or <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-mmallocatepagesformdl">MmAllocatePagesForMdl</a> routine.

When creating a partial MDL:

* If the original MDL was already mapped in system space, the partial MDL shares that mapping and there is no need to map it again.
* If the original MDL was not mapped in system space, the partial MDL is not either.  If you need a system mode address, call [**MmGetSystemAddressForMdlSafe**](/windows-hardware/drivers/kernel/mm-bad-pointer) on the partial MDL.
* If you do not know which of the above applies, it is safe to call [**MmGetSystemAddressForMdlSafe**](/windows-hardware/drivers/kernel/mm-bad-pointer) regardless.  If a partial MDL is built from a source MDL that is already mapped into the system address space, <b>MmGetSystemAddressForMdlSafe</b> uses the existing source mapping. Otherwise, <b>MmGetSystemAddressForMdlSafe</b> creates a new mapping.

To prevent this new mapping from being leaked, drivers must call [MmPrepareMdlForReuse](./nf-wdm-mmpreparemdlforreuse.md) before reusing a partial MDL. In addition, the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iofreemdl">IoFreeMdl</a> routine releases the system-address-space mapping for a partial MDL, if such a mapping exists.

For more information about MDLs, see <a href="/windows-hardware/drivers/kernel/using-mdls">Using MDLs</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iofreemdl">IoFreeMdl</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-mmallocatepagesformdl">MmAllocatePagesForMdl</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-mmallocatepagesformdlex">MmAllocatePagesForMdlEx</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-mmbuildmdlfornonpagedpool">MmBuildMdlForNonPagedPool</a>



[MmGetSystemAddressForMdlSafe](../wdm/nf-wdm-mmgetsystemaddressformdlsafe.md)



[MmPrepareMdlForReuse](./nf-wdm-mmpreparemdlforreuse.md)



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-mmprobeandlockpages">MmProbeAndLockPages</a>