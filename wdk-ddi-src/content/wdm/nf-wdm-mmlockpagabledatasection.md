---
UID: NF:wdm.MmLockPagableDataSection
title: MmLockPagableDataSection function
author: windows-driver-content
description: The MmLockPagableDataSection routine locks an entire section of driver data into system space.
old-location: kernel\mmlockpagabledatasection.htm
old-project: kernel
ms.assetid: 9bf21128-acf3-4d7d-83c5-a32ac54e78ca
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: kernel.mmlockpagabledatasection, MmLockPagableDataSection, MmLockPagableDataSection routine [Kernel-Mode Driver Architecture], wdm/MmLockPagableDataSection, k106_05a47a6d-54f2-48d3-abba-ba3864aaa94b.xml
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
-	MmLockPagableDataSection
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# MmLockPagableDataSection function


## -description


The <b>MmLockPagableDataSection</b> routine locks an entire section of driver data into system space.


## -syntax


````
PVOID MmLockPagableDataSection(
  _In_ PVOID AddressWithinSection
);
````


## -parameters




### -param AddressWithinSection [in]

Specifies the symbolic address of one item of data within the pageable section.


## -returns



<b>MmLockPagableDataSection</b> returns an opaque value that identifies the section. This value must be passed subsequently to <b>MmLockPagableSectionByHandle</b> or to <b>MmUnlockPagableImageSection</b>.




## -remarks



Drivers can use this routine, <b>MmLockPagableSectionByHandle</b>, and <b>MmUnlockPagableImageSection</b> to make their private data that is typically pageable locked into memory.

Data can be locked down if:

<ul>
<li>
The data is typically accessed at &lt;= APC_LEVEL, but it might need to be accessed at higher IRQL levels for short periods. 

</li>
<li>
The driver uses the data infrequently and predictably. 

</li>
</ul>
For example, drivers for mixer devices use pageable-data sections. Because the driver uses sufficient data to make creating a pageable-data section worthwhile and the driver knows when the data is needed, such a driver uses <b>MmLockPagableDataSection</b>,  <b>MmLockPagableSectionByHandle</b> and <b>MmUnlockPagableImageSection</b> to bring a data section into system space when needed and make it available to be paged out when not needed.

A single call to <b>MmLockPagableDataSection</b> causes the entire section, containing the referenced data, to be locked into system space.

It is an expensive operation to lock down a section. If a pageable-data section is locked down in more than one place by a driver, use <b>MmLockPagableDataSection</b> for the first request. Make subsequent lock requests by calling <b>MmLockPagableSectionByHandle</b>, passing the handle returned by <b>MmLockPagableDataSection</b>. Locking by handle significantly improves driver performance. A locked down section is unlocked by calling <b>MmUnlockPagableImageSection</b>.

The memory manager maintains a reference count on the section. A pageable-data section is only available to be paged out when the reference count is zero. Every lock request increments the count; every unlock request decrements the count. A driver must unlock a section as many times as it locks a section to ensure that such a section will be available to be paged out when the section is not needed. A handle is always valid, no matter what the count. If the count on a handle is zero and a call is made to <b>MmLockPagableSectionByHandle</b>, the count is set to one, and if the section has been paged out, it will be paged in.

Data in a pageable-data section is marked by a compiler directive. To create a pageable data section, use <b>#pragma data_seg ("PAGE")</b>, at the beginning of the data module, and <b>#pragma data_seg ()</b> at the end of the module. The keyword <b>PAGE</b> is case-sensitive, that is, <b>PAGE</b> must be capitalized.

Note that there is also a <b>#pragma data_seg("INIT")</b> that is used to make data discardable after system initialization. Except for the use of <b>INIT</b> rather than <b>PAGE</b>, the syntax is the same. However the result is not; use of the <b>PAGE</b> directive makes the data section pageable. When the <b>INIT</b> directive is used, the data in the section is discarded as soon as the driver returns from its driver entry routine or its reinitialization routine if the driver has one.

For more information about paging data, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554346">Making Drivers Pageable</a>. 




## -see-also

<a href="..\wdm\nf-wdm-mmunlockpagableimagesection.md">MmUnlockPagableImageSection</a>



<a href="..\wdm\nf-wdm-mmresetdriverpaging.md">MmResetDriverPaging</a>



<a href="..\wdm\nf-wdm-mmlockpagablecodesection.md">MmLockPagableCodeSection</a>



<a href="..\ntddk\nf-ntddk-mmlockpagablesectionbyhandle.md">MmLockPagableSectionByHandle</a>



<a href="..\wdm\nf-wdm-mmpageentiredriver.md">MmPageEntireDriver</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20MmLockPagableDataSection routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

