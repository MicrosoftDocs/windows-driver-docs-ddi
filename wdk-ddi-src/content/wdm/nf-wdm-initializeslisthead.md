---
UID: NF:wdm.InitializeSListHead
title: InitializeSListHead function
author: windows-driver-content
description: The InitializeSListHead routine (or ExInitializeSListHead) initializes an SLIST_HEADER structure that represents the head of a sequenced singly linked list.
old-location: kernel\exinitializeslisthead.htm
tech.root: kernel
ms.assetid: 258addec-7231-494c-aa70-5966e9a57132
ms.date: 04/30/2018
ms.keywords: ExInitializeSListHead, InitializeSListHead, InitializeSListHead routine [Kernel-Mode Driver Architecture], k102_6d3b712b-2dd5-4962-ad16-a296bdc4de2b.xml, kernel.exinitializeslisthead, wdm/InitializeSListHead
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	InitializeSListHead
product:
- Windows
targetos: Windows
req.typenames: 
---

# InitializeSListHead function


## -description


The <b>InitializeSListHead</b> routine (or ExInitializeSListHead) initializes an <a href="https://msdn.microsoft.com/library/windows/hardware/ff563810">SLIST_HEADER</a> structure that represents the head of a sequenced singly linked list.


## -parameters




### -param SListHead [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563810">SLIST_HEADER</a> structure to initialize. The structure must be 16-byte aligned on 64-bit platforms. 


## -returns



None




## -remarks



For more information about using this routine to implement a sequenced singly linked list, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563802">Singly and Doubly Linked Lists</a>.

Callers of <b>InitializeSListHead or ExInitializeSListHead</b> can be running at any IRQL. If <b>ExInitializeSListHead</b> is called at IRQL &gt;= DISPATCH_LEVEL the storage for <i>SListHead</i> must be resident.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545301">ExInitializeNPagedLookasideList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545309">ExInitializePagedLookasideList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545402">ExInterlockedInsertTailList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545414">ExInterlockedPopEntrySList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545422">ExInterlockedPushEntrySList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545502">ExQueryDepthSList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552160">KeInitializeSpinLock</a>
 

 

