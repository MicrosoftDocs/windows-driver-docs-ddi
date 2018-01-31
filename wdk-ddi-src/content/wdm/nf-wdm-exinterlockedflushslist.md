---
UID: NF:wdm.ExInterlockedFlushSList
title: ExInterlockedFlushSList function
author: windows-driver-content
description: The ExInterlockedFlushSList routine atomically removes all entries from a sequenced singly linked list.
old-location: kernel\exinterlockedflushslist.htm
old-project: kernel
ms.assetid: 98fcada7-5160-4eb2-ac7c-0ab1192340a9
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: k102_493935e2-44c7-471b-807f-ca6f110d8155.xml, ExInterlockedFlushSList routine [Kernel-Mode Driver Architecture], wdm/ExInterlockedFlushSList, ExInterlockedFlushSList, kernel.exinterlockedflushslist
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
req.irql: Any level (see Remarks section)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	ExInterlockedFlushSList
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ExInterlockedFlushSList function


## -description


The <b>ExInterlockedFlushSList</b> routine atomically removes all entries from a sequenced singly linked list.


## -syntax


````
PSLIST_ENTRY ExInterlockedFlushSList(
  _Inout_ PSLIST_HEADER ListHead
);
````


## -parameters




#### - ListHead [in, out]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563810">SLIST_HEADER</a> structure that serves as the header for the sequenced singly linked list.


## -returns


If there were entries on the specified list, <b>ExInterlockedFlushSList</b> returns a pointer to the first <a href="..\wdm\ns-wdm-_slist_entry.md">SLIST_ENTRY</a> structure that was entry on the list; otherwise, it returns <b>NULL</b>.



## -remarks


<b>ExInterlockedFlushSList</b> does not delete the <a href="..\wdm\ns-wdm-_slist_entry.md">SLIST_ENTRY</a> structures that made up the list; it only sets the internal pointer of <i>ListHead</i> to the beginning of the list to <b>NULL</b>. The driver must free the entries explicitly.

The routine returns a pointer to the first <b>SLIST_ENTRY</b> structure that was on the list. The driver can use this pointer to iterate through the entries.

For more information about using this routine to implement a sequenced singly linked list, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563802">Singly and Doubly Linked Lists</a>.

Callers of <b>ExInterlockedFlushSList</b> can be running at any IRQL. The storage for the <i>ListHead</i> parameter and the list entries must be resident at all IRQLs.



## -see-also

<a href="..\wdm\nf-wdm-initializeslisthead.md">ExInitializeSListHead</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExInterlockedFlushSList routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

