---
UID: NF:wdm.MmUnlockPagableImageSection
title: MmUnlockPagableImageSection function (wdm.h)
description: The MmUnlockPagableImageSection routine releases a section of driver code or driver data, previously locked into system space with MmLockPagableCodeSection, MmLockPagableDataSection or MmLockPagableSectionByHandle, so the section can be paged out again.
old-location: kernel\mmunlockpagableimagesection.htm
tech.root: kernel
ms.assetid: 3a6e3029-d378-4e42-8556-e3640cfdb392
ms.date: 04/30/2018
keywords: ["MmUnlockPagableImageSection function"]
ms.keywords: MmUnlockPagableImageSection, MmUnlockPagableImageSection routine [Kernel-Mode Driver Architecture], k106_1420e152-a858-4256-87ed-8fa78ee76379.xml, kernel.mmunlockpagableimagesection, wdm/MmUnlockPagableImageSection
f1_keywords:
 - "wdm/MmUnlockPagableImageSection"
 - "MmUnlockPagableImageSection"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
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
req.irql: <=APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- MmUnlockPagableImageSection
product:
- Windows
targetos: Windows
req.typenames: 
---

# MmUnlockPagableImageSection function


## -description


The <b>MmUnlockPagableImageSection</b> routine releases a section of driver code or driver data, previously locked into system space with <b>MmLockPagableCodeSection</b>, <b>MmLockPagableDataSection</b> or <b>MmLockPagableSectionByHandle</b>, so the section can be paged out again. 


## -parameters




### -param ImageSectionHandle [in]

Specifies the handle returned by a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmlockpagablecodesection">MmLockPagableCodeSection</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmlockpagabledatasection">MmLockPagableDataSection</a>. 


## -remarks



The handle for a driver's pageable section must not be released if the driver has any outstanding IRPs in its device queue(s) or internal queue(s). A call to <b>MmUnlockPagableImageSection</b> restores the pageability of that entire section when there are no more references to the handle for that section. 

The memory manager maintains the reference count on the handle to a section. A pageable section is only available to be paged out when the reference count is zero. Every lock request increments the count; every unlock request decrements the count. A driver must unlock a section as many times as it locks a section to make the section available to be paged out.

A handle is always valid, no matter what the count. If the count on a handle is zero and a call is made to <b>MmLockPagableSectionByHandle</b>, the count is set to one, and if the section has been paged out, it will be paged in.

In most cases, <b>MmUnlockPagableImageSection</b> is called before a driver's <i>Unload</i> routine. That is, a driver with a pageable section is likely to have its <i>DispatchClose</i> and/or <i>DispatchShutdown</i> routine call <b>MmUnlockPagableImageSection</b> before its <i>Unload</i> routine is called. However, care should be taken in unloadable drivers to release any pageable section before the driver itself is unloaded from the system.

For more information about paging code and data, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/making-drivers-pageable">Making Drivers Pageable</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmlockpagablecodesection">MmLockPagableCodeSection</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmlockpagabledatasection">MmLockPagableDataSection</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-mmlockpagablesectionbyhandle">MmLockPagableSectionByHandle</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmpageentiredriver">MmPageEntireDriver</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmresetdriverpaging">MmResetDriverPaging</a>
 

 

