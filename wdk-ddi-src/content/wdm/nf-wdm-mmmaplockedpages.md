---
UID: NF:wdm.MmMapLockedPages
title: MmMapLockedPages function (wdm.h)
description: The MmMapLockedPages routine is obsolete for Windows 2000 and later versions of Windows, and for Windows Me.
old-location: kernel\mmmaplockedpages.htm
tech.root: kernel
ms.assetid: f27b7622-614b-4c9e-8253-51f4638e5eb0
ms.date: 04/30/2018
keywords: ["MmMapLockedPages function"]
ms.keywords: MmMapLockedPages, MmMapLockedPages routine [Kernel-Mode Driver Architecture], k106_009bdc6a-6bbc-4a7f-927e-ea5c6de8fa95.xml, kernel.mmmaplockedpages, wdm/MmMapLockedPages
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Obsolete for Windows 2000 and later versions of Windows, and for Windows Me. This routine is supported only for WDM drivers that must run on Windows 98. Otherwise, use MmMapLockedPagesSpecifyCache.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: See Remarks section.
targetos: Windows
req.typenames: 
f1_keywords:
 - MmMapLockedPages
 - wdm/MmMapLockedPages
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - MmMapLockedPages
---

# MmMapLockedPages function


## -description

The <b>MmMapLockedPages</b> routine is <u>obsolete</u> for Windows 2000 and later versions of Windows, and for Windows Me. It is supported only for WDM drivers that must run on Windows 98. Otherwise, use <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-mmmaplockedpagesspecifycache">MmMapLockedPagesSpecifyCache</a>.

The <b>MmMapLockedPages</b> routine maps the physical pages that are described by a given MDL.

## -parameters

### -param MemoryDescriptorList 

[in]
Pointer to an MDL that was updated by <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-mmprobeandlockpages">MmProbeAndLockPages</a>.

### -param AccessMode 

[in]
Specifies the access mode in which to map the MDL, either <b>KernelMode</b> or <b>UserMode</b>. Almost all drivers should use <b>KernelMode</b>.

## -returns

<b>MmMapLockedPages</b> returns the starting address of the mapped pages. (For NT-based operating systems prior to Windows NT 4.0 Service Pack 4 (SP4), <b>MmMapLockedPages</b> returns the beginning address of the first page of the mapped pages.)

## -remarks

Use <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-mmunmaplockedpages">MmUnmapLockedPages</a> to unmap the physical pages that were mapped by <b>MmMapLockedPages</b>.

If <i>AccessMode</i> is KernelMode and <b>MmMapLockedPages</b> cannot map the specified pages, the system issues a bug check. (For this reason, drivers should use <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-mmmaplockedpagesspecifycache">MmMapLockedPagesSpecifyCache</a> when available; that routine returns <b>NULL</b> on failure, rather than causing a bug check.) If <i>AccessMode</i> is <b>UserMode</b> and the specified pages cannot be mapped, the routine raises an exception. Callers that specify <b>UserMode</b> must wrap the call to <b>MmMapLockedPages</b> in a <b>try/except</b> block. For more information, see <a href="/windows-hardware/drivers/kernel/handling-exceptions">Handling Exceptions</a>.

Callers of <b>MmMapLockedPages</b> must be running at IRQL <= DISPATCH_LEVEL if <i>AccessMode</i> is <b>KernelMode</b>. Otherwise, the caller must be running at IRQL <= APC_LEVEL.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-mmgetsystemaddressformdl">MmGetSystemAddressForMdl</a>



<a href="/windows-hardware/drivers/kernel/mm-bad-pointer">MmGetSystemAddressForMdlSafe</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-mmmaplockedpagesspecifycache">MmMapLockedPagesSpecifyCache</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-mmprobeandlockpages">MmProbeAndLockPages</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-mmunmaplockedpages">MmUnmapLockedPages</a>