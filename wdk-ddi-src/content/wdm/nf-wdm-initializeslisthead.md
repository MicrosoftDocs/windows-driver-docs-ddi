---
UID: NF:wdm.InitializeSListHead
title: InitializeSListHead function
author: windows-driver-content
description: The InitializeSListHead routine (or ExInitializeSListHead) initializes an SLIST_HEADER structure that represents the head of a sequenced singly linked list.
old-location: kernel\exinitializeslisthead.htm
old-project: kernel
ms.assetid: 258addec-7231-494c-aa70-5966e9a57132
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: wdm/InitializeSListHead, InitializeSListHead, k102_6d3b712b-2dd5-4962-ad16-a296bdc4de2b.xml, kernel.exinitializeslisthead, ExInitializeSListHead, InitializeSListHead routine [Kernel-Mode Driver Architecture]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.irql: Any level (see Remarks section)
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	DllExport
apilocation: 
-	NtosKrnl.exe
apiname: 
-	InitializeSListHead
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# InitializeSListHead function


## -description


The <b>InitializeSListHead</b> routine (or ExInitializeSListHead) initializes an <a href="https://msdn.microsoft.com/library/windows/hardware/ff563810">SLIST_HEADER</a> structure that represents the head of a sequenced singly linked list.


## -syntax


````
VOID InitializeSListHead(
  _In_ PSLIST_HEADER SListHead
);
````


## -parameters




### -param SListHead [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563810">SLIST_HEADER</a> structure to initialize. The structure must be 16-byte aligned on 64-bit platforms. 


## -returns


None



## -remarks


For more information about using this routine to implement a sequenced singly linked list, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563802">Singly and Doubly Linked Lists</a>.

Callers of <b>InitializeSListHead or ExInitializeSListHead</b> can be running at any IRQL. If <b>ExInitializeSListHead</b> is called at IRQL &gt;= DISPATCH_LEVEL the storage for <i>SListHead</i> must be resident.



## -see-also

<a href="..\wdm\nf-wdm-exinterlockedinserttaillist.md">ExInterlockedInsertTailList</a>

<a href="..\wdm\nf-wdm-exinterlockedpopentryslist.md">ExInterlockedPopEntrySList</a>

<a href="..\wdm\nf-wdm-exinitializenpagedlookasidelist.md">ExInitializeNPagedLookasideList</a>

<a href="..\wdm\nf-wdm-exinterlockedpushentryslist.md">ExInterlockedPushEntrySList</a>

<a href="..\wdm\nf-wdm-keinitializespinlock.md">KeInitializeSpinLock</a>

<a href="..\wdm\nf-wdm-exquerydepthslist.md">ExQueryDepthSList</a>

<a href="..\wdm\nf-wdm-exinitializepagedlookasidelist.md">ExInitializePagedLookasideList</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20InitializeSListHead routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

