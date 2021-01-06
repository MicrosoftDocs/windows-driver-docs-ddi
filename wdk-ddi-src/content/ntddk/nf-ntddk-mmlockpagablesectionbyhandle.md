---
UID: NF:ntddk.MmLockPagableSectionByHandle
title: MmLockPagableSectionByHandle function (ntddk.h)
description: The MmLockPagableSectionByHandle routine locks a pageable code or data section into system memory by incrementing the reference count on the handle to the section.
old-location: kernel\mmlockpagablesectionbyhandle.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["MmLockPagableSectionByHandle function"]
ms.keywords: MmLockPagableSectionByHandle, MmLockPagableSectionByHandle routine [Kernel-Mode Driver Architecture], k106_9c5e1e9c-8382-4082-a3ac-5985224c8b2a.xml, kernel.mmlockpagablesectionbyhandle, ntddk/MmLockPagableSectionByHandle
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlMmApcLte, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - MmLockPagableSectionByHandle
 - ntddk/MmLockPagableSectionByHandle
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - MmLockPagableSectionByHandle
---

# MmLockPagableSectionByHandle function


## -description

The <b>MmLockPagableSectionByHandle</b> routine locks a pageable code or data section into system memory by incrementing the reference count on the handle to the section.

## -parameters

### -param ImageSectionHandle 

[in]
The handle to a pageable code or data section. The caller obtained this handle from a previous call to the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-mmlockpagablecodesection">MmLockPagableCodeSection</a> or <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-mmlockpagabledatasection">MmLockPagableDataSection</a> routine.

## -remarks

A driver initially calls <b>MmLockPagableCodeSection</b> or <b>MmLockPagableDataSection</b> to obtain a handle to a pageable code or data section. Thereafter, the driver can call <b>MmLockPagableSectionByHandle</b> and <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-mmunlockpagableimagesection">MmUnlockPagableImageSection</a> to increment and decrement the reference count on the handle.

The <b>MmLockPagableCodeSection</b> or <b>MmLockPagableDataSection</b> call locks the pageable section into system memory, returns a handle to the section, and initializes the reference count on the handle to one. <b>MmLockPagableSectionByHandle</b> increments the reference count by one, and <b>MmUnlockPagableImageSection</b> decrements the reference count by one.

If the reference count on the handle is nonzero, the pageable section is locked. If the reference count is zero, the section is unlocked.

The handle to the pageable section remains valid as long as the driver stays loaded in memory. The driver can use the same handle to repeatedly lock and unlock the section. That is, the driver can reuse a handle whose reference count is zero. <b>MmLockPagableSectionByHandle</b> checks to see if the referenced section is resident in the caller's address space and, if it is, simply increments the reference count on the section. If the section is not resident, <b>MmLockPagableSectionByHandle</b> pages in the section, locks it in system space, and sets the reference count to one.

To avoid leaking system memory, the reference count on the handle must be zero when the driver is unloaded from memory. Otherwise, the pageable section will stay locked into system memory after the driver unloads.

If the driver is preparing to unload, and the reference count on the handle is nonzero, the driver should call <b>MmUnlockPagableImageSection</b> to decrement the count to zero before the unload occurs.

A driver cannot call <b>MmLockPagableSectionByHandle</b> to lock down user buffers passed in IRPs. Use <b>MmProbeAndLockPages</b> instead.

For more information about paging code and data, see <a href="/windows-hardware/drivers/kernel/making-drivers-pageable">Making Drivers Pageable</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-mmlockpagablecodesection">MmLockPagableCodeSection</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-mmlockpagabledatasection">MmLockPagableDataSection</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-mmpageentiredriver">MmPageEntireDriver</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-mmprobeandlockpages">MmProbeAndLockPages</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-mmresetdriverpaging">MmResetDriverPaging</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-mmunlockpagableimagesection">MmUnlockPagableImageSection</a>
