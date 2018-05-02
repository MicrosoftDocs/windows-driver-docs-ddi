---
UID: NF:wdm.FirstEntrySList
title: FirstEntrySList function
author: windows-driver-content
description: The FirstEntrySList routine returns the first entry in a sequenced singly linked list.
old-location: kernel\firstentryslist.htm
old-project: kernel
ms.assetid: 80444a10-91f3-44b5-ad20-3d3d8f49ca60
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: FirstEntrySList, FirstEntrySList routine [Kernel-Mode Driver Architecture], k109_0a6c7f88-35fa-4cc9-ac3d-03bf1e873cf3.xml, kernel.firstentryslist, wdm/FirstEntrySList
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntifs.h, Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: 
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
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	FirstEntrySList
product: Windows
targetos: Windows
req.typenames: 
---

# FirstEntrySList function


## -description


The <b>FirstEntrySList</b> routine returns the first entry in a sequenced singly linked list.


## -parameters




### -param SListHead [in]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563810">SLIST_HEADER</a> structure that serves as the header for the sequenced singly linked list.


## -returns



<b>FirstEntrySList</b> returns a pointer to the first <a href="https://msdn.microsoft.com/library/windows/hardware/ff563805">SLIST_ENTRY</a> structure on the list. If the list is empty, the routine returns <b>NULL</b>.




## -remarks



Unlike other sequenced singly linked list routines, the <b>FirstEntrySList</b> routine is not atomic. For more information about sequenced singly linked lists, see <a href="https://msdn.microsoft.com/3a305f54-7866-4163-a3e4-e078d1927adc">Sequenced Singly Linked Lists</a>. Callers of this routine can run at any level. If called at IRQL &gt;= DISPATCH_LEVEL, the storage for <b>ListHead</b> must be resident.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563805">SLIST_ENTRY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563810">SLIST_HEADER</a>
 

 

