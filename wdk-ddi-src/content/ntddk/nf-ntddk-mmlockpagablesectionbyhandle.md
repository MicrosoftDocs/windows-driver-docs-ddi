---
UID: NF:ntddk.MmLockPagableSectionByHandle
title: MmLockPagableSectionByHandle function
author: windows-driver-content
description: The MmLockPagableSectionByHandle routine locks a pageable code or data section into system memory by incrementing the reference count on the handle to the section.
old-location: kernel\mmlockpagablesectionbyhandle.htm
old-project: kernel
ms.assetid: d2e50d98-1c25-4ed6-98eb-0fb7e71fda55
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: kernel.mmlockpagablesectionbyhandle, MmLockPagableSectionByHandle routine [Kernel-Mode Driver Architecture], k106_9c5e1e9c-8382-4082-a3ac-5985224c8b2a.xml, MmLockPagableSectionByHandle, ntddk/MmLockPagableSectionByHandle
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	MmLockPagableSectionByHandle
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# MmLockPagableSectionByHandle function


## -description


The <b>MmLockPagableSectionByHandle</b> routine locks a pageable code or data section into system memory by incrementing the reference count on the handle to the section.


## -syntax


````
VOID MmLockPagableSectionByHandle(
  _In_ PVOID ImageSectionHandle
);
````


## -parameters




### -param ImageSectionHandle [in]

The handle to a pageable code or data section. The caller obtained this handle from a previous call to the <a href="..\wdm\nf-wdm-mmlockpagablecodesection.md">MmLockPagableCodeSection</a> or <a href="..\wdm\nf-wdm-mmlockpagabledatasection.md">MmLockPagableDataSection</a> routine.


## -returns



None




## -remarks



A driver initially calls <b>MmLockPagableCodeSection</b> or <b>MmLockPagableDataSection</b> to obtain a handle to a pageable code or data section. Thereafter, the driver can call <b>MmLockPagableSectionByHandle</b> and <a href="..\wdm\nf-wdm-mmunlockpagableimagesection.md">MmUnlockPagableImageSection</a> to increment and decrement the reference count on the handle.

The <b>MmLockPagableCodeSection</b> or <b>MmLockPagableDataSection</b> call locks the pageable section into system memory, returns a handle to the section, and initializes the reference count on the handle to one. <b>MmLockPagableSectionByHandle</b> increments the reference count by one, and <b>MmUnlockPagableImageSection</b> decrements the reference count by one.

If the reference count on the handle is nonzero, the pageable section is locked. If the reference count is zero, the section is unlocked.

The handle to the pageable section remains valid as long as the driver stays loaded in memory. The driver can use the same handle to repeatedly lock and unlock the section. That is, the driver can reuse a handle whose reference count is zero. <b>MmLockPagableSectionByHandle</b> checks to see if the referenced section is resident in the caller's address space and, if it is, simply increments the reference count on the section. If the section is not resident, <b>MmLockPagableSectionByHandle</b> pages in the section, locks it in system space, and sets the reference count to one.

To avoid leaking system memory, the reference count on the handle must be zero when the driver is unloaded from memory. Otherwise, the pageable section will stay locked into system memory after the driver unloads.

If the driver is preparing to unload, and the reference count on the handle is nonzero, the driver should call <b>MmUnlockPagableImageSection</b> to decrement the count to zero before the unload occurs.

A driver cannot call <b>MmLockPagableSectionByHandle</b> to lock down user buffers passed in IRPs. Use <b>MmProbeAndLockPages</b> instead.

For more information about paging code and data, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554346">Making Drivers Pageable</a>.




## -see-also

<a href="..\wdm\nf-wdm-mmprobeandlockpages.md">MmProbeAndLockPages</a>



<a href="..\wdm\nf-wdm-mmunlockpagableimagesection.md">MmUnlockPagableImageSection</a>



<a href="..\wdm\nf-wdm-mmresetdriverpaging.md">MmResetDriverPaging</a>



<a href="..\wdm\nf-wdm-mmlockpagablecodesection.md">MmLockPagableCodeSection</a>



<a href="..\wdm\nf-wdm-mmlockpagabledatasection.md">MmLockPagableDataSection</a>



<a href="..\wdm\nf-wdm-mmpageentiredriver.md">MmPageEntireDriver</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20MmLockPagableSectionByHandle routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

