---
UID: NF:wdm.MmUnmapLockedPages
title: MmUnmapLockedPages function
author: windows-driver-content
description: The MmUnmapLockedPages routine releases a mapping that was set up by a preceding call to the MmMapLockedPages or MmMapLockedPagesSpecifyCache routine.
old-location: kernel\mmunmaplockedpages.htm
old-project: kernel
ms.assetid: ab5f33b9-5261-4d30-bceb-8e91a24ae0a8
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: k106_1ed6ae95-665b-4a6e-802a-4f80294c4f6e.xml, wdm/MmUnmapLockedPages, MmUnmapLockedPages routine [Kernel-Mode Driver Architecture], kernel.mmunmaplockedpages, MmUnmapLockedPages
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	MmUnmapLockedPages
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# MmUnmapLockedPages function


## -description


The <b>MmUnmapLockedPages</b> routine releases a mapping that was set up by a preceding call to the <a href="..\wdm\nf-wdm-mmmaplockedpages.md">MmMapLockedPages</a> or <a href="..\wdm\nf-wdm-mmmaplockedpagesspecifycache.md">MmMapLockedPagesSpecifyCache</a> routine.


## -syntax


````
VOID MmUnmapLockedPages(
  _In_ PVOID BaseAddress,
  _In_ PMDL  MemoryDescriptorList
);
````


## -parameters




### -param BaseAddress [in]

Pointer to the base virtual address to which the physical pages were mapped.


### -param MemoryDescriptorList [in]

Pointer to an MDL.


## -returns



None




## -remarks



Callers of <b>MmUnmapLockedPages</b> must be running at IRQL &lt;= DISPATCH_LEVEL if the pages were mapped to system space. Otherwise, the caller must be running at IRQL &lt;= APC_LEVEL.

Note that if the call to <b>MmMapLockedPages</b> or <b>MmMapLockedPagesSpecifyCache</b> specified user mode, the caller must be in the context of the original process before calling <b>MmUnmapLockedPages</b>. This is because the unmapping operation occurs in the context of the calling process, and, if the context is incorrect, the unmapping operation could delete the address range of a random process.




## -see-also

<a href="..\wdm\nf-wdm-mmmaplockedpages.md">MmMapLockedPages</a>



<a href="..\wdm\nf-wdm-mmmaplockedpagesspecifycache.md">MmMapLockedPagesSpecifyCache</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20MmUnmapLockedPages routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

