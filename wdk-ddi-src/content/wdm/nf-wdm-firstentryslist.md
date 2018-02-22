---
UID: NF:wdm.FirstEntrySList
title: FirstEntrySList function
author: windows-driver-content
description: The FirstEntrySList routine returns the first entry in a sequenced singly linked list.
old-location: kernel\firstentryslist.htm
old-project: kernel
ms.assetid: 80444a10-91f3-44b5-ad20-3d3d8f49ca60
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FirstEntrySList, k109_0a6c7f88-35fa-4cc9-ac3d-03bf1e873cf3.xml, kernel.firstentryslist, wdm/FirstEntrySList, FirstEntrySList routine [Kernel-Mode Driver Architecture]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	FirstEntrySList
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# FirstEntrySList function


## -description


The <b>FirstEntrySList</b> routine returns the first entry in a sequenced singly linked list.


## -syntax


````
PSLIST_ENTRY FirstEntrySList(
  _In_ PSLIST_HEADER SListHead
);
````


## -parameters




### -param SListHead [in]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563810">SLIST_HEADER</a> structure that serves as the header for the sequenced singly linked list.


## -returns



<b>FirstEntrySList</b> returns a pointer to the first <a href="..\wdm\ns-wdm-_slist_entry.md">SLIST_ENTRY</a> structure on the list. If the list is empty, the routine returns <b>NULL</b>.




## -remarks



Unlike other sequenced singly linked list routines, the <b>FirstEntrySList</b> routine is not atomic. For more information about sequenced singly linked lists, see <a href="https://msdn.microsoft.com/3a305f54-7866-4163-a3e4-e078d1927adc">Sequenced Singly Linked Lists</a>. Callers of this routine can run at any level. If called at IRQL &gt;= DISPATCH_LEVEL, the storage for <b>ListHead</b> must be resident.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff563810">SLIST_HEADER</a>



<a href="..\wdm\ns-wdm-_slist_entry.md">SLIST_ENTRY</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20FirstEntrySList routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

