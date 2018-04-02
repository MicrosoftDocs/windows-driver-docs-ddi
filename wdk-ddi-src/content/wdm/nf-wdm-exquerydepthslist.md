---
UID: NF:wdm.ExQueryDepthSList
title: ExQueryDepthSList function
author: windows-driver-content
description: The ExQueryDepthSList routine returns the number of entries currently in a given sequenced singly linked list.
old-location: kernel\exquerydepthslist.htm
old-project: kernel
ms.assetid: fdf40535-4e0d-4db9-9e95-744029eb2bd5
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: ExQueryDepthSList, ExQueryDepthSList routine [Kernel-Mode Driver Architecture], k102_14e2b5cb-bc6a-43f7-a0b2-1fcd8fd414a7.xml, kernel.exquerydepthslist, wdm/ExQueryDepthSList
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	ExQueryDepthSList
product:
- Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ExQueryDepthSList function


## -description


The <b>ExQueryDepthSList</b> routine returns the number of entries currently in a given sequenced singly linked list.


## -parameters




### -param SListHead [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563810">SLIST_HEADER</a> structure that serves as the header for the sequenced singly linked list. <i>SListHead</i> must have been initialized by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff545321">ExInitializeSListHead</a>.


## -returns



<b>ExQueryDepthSList</b> returns the current number of entries in the list.




## -remarks



For more information about using this routine to implement a sequenced singly linked list, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563802">Singly and Doubly Linked Lists</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545321">ExInitializeSListHead</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545414">ExInterlockedPopEntrySList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545422">ExInterlockedPushEntrySList</a>
 

 

