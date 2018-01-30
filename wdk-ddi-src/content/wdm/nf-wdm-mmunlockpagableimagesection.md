---
UID: NF:wdm.MmUnlockPagableImageSection
title: MmUnlockPagableImageSection function
author: windows-driver-content
description: The MmUnlockPagableImageSection routine releases a section of driver code or driver data, previously locked into system space with MmLockPagableCodeSection, MmLockPagableDataSection or MmLockPagableSectionByHandle, so the section can be paged out again.
old-location: kernel\mmunlockpagableimagesection.htm
old-project: kernel
ms.assetid: 3a6e3029-d378-4e42-8556-e3640cfdb392
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: MmUnlockPagableImageSection, k106_1420e152-a858-4256-87ed-8fa78ee76379.xml, MmUnlockPagableImageSection routine [Kernel-Mode Driver Architecture], kernel.mmunlockpagableimagesection, wdm/MmUnlockPagableImageSection
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
req.ddi-compliance: IrqlMmApcLte, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<=APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	MmUnlockPagableImageSection
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# MmUnlockPagableImageSection function


## -description


The <b>MmUnlockPagableImageSection</b> routine releases a section of driver code or driver data, previously locked into system space with <b>MmLockPagableCodeSection</b>, <b>MmLockPagableDataSection</b> or <b>MmLockPagableSectionByHandle</b>, so the section can be paged out again. 


## -syntax


````
VOID MmUnlockPagableImageSection(
  _In_ PVOID ImageSectionHandle
);
````


## -parameters




### -param ImageSectionHandle [in]

Specifies the handle returned by a call to <a href="..\wdm\nf-wdm-mmlockpagablecodesection.md">MmLockPagableCodeSection</a> or <a href="..\wdm\nf-wdm-mmlockpagabledatasection.md">MmLockPagableDataSection</a>. 


## -returns


None



## -remarks


The handle for a driver's pageable section must not be released if the driver has any outstanding IRPs in its device queue(s) or internal queue(s). A call to <b>MmUnlockPagableImageSection</b> restores the pageability of that entire section when there are no more references to the handle for that section. 

The memory manager maintains the reference count on the handle to a section. A pageable section is only available to be paged out when the reference count is zero. Every lock request increments the count; every unlock request decrements the count. A driver must unlock a section as many times as it locks a section to make the section available to be paged out.

A handle is always valid, no matter what the count. If the count on a handle is zero and a call is made to <b>MmLockPagableSectionByHandle</b>, the count is set to one, and if the section has been paged out, it will be paged in.

In most cases, <b>MmUnlockPagableImageSection</b> is called before a driver's <i>Unload</i> routine. That is, a driver with a pageable section is likely to have its <i>DispatchClose</i> and/or <i>DispatchShutdown</i> routine call <b>MmUnlockPagableImageSection</b> before its <i>Unload</i> routine is called. However, care should be taken in unloadable drivers to release any pageable section before the driver itself is unloaded from the system.

For more information about paging code and data, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554346">Making Drivers Pageable</a>. 



## -see-also

<a href="..\wdm\nf-wdm-mmlockpagabledatasection.md">MmLockPagableDataSection</a>

<a href="..\ntddk\nf-ntddk-mmlockpagablesectionbyhandle.md">MmLockPagableSectionByHandle</a>

<a href="..\wdm\nf-wdm-mmlockpagablecodesection.md">MmLockPagableCodeSection</a>

<a href="..\wdm\nf-wdm-mmpageentiredriver.md">MmPageEntireDriver</a>

<a href="..\wdm\nf-wdm-mmresetdriverpaging.md">MmResetDriverPaging</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20MmUnlockPagableImageSection routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

