---
UID: NF:wdm.IsListEmpty
title: IsListEmpty function
author: windows-driver-content
description: The IsListEmpty routine indicates whether a doubly linked list of LIST_ENTRY structures is empty.
old-location: kernel\islistempty.htm
old-project: kernel
ms.assetid: 6e494112-a808-4914-8194-e68a2799c38e
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: wdm/IsListEmpty, k109_26969818-30d0-4e01-965d-e0ee6891fdd5.xml, IsListEmpty routine [Kernel-Mode Driver Architecture], kernel.islistempty, IsListEmpty
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: Any level (see Remarks section)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wdm.h
apiname:
-	IsListEmpty
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IsListEmpty function


## -description


The <b>IsListEmpty</b> routine indicates whether a doubly linked list of <a href="https://msdn.microsoft.com/library/windows/hardware/ff554296">LIST_ENTRY</a> structures is empty.


## -syntax


````
BOOLEAN IsListEmpty(
  _In_ const LIST_ENTRY *ListHead
);
````


## -parameters




### -param ListHead [in]

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff554296">LIST_ENTRY</a> structure that represents the head of the list. 


## -returns


<b>IsListEmpty</b> returns <b>TRUE</b> if there are currently no entries in the list and <b>FALSE</b> otherwise.



## -remarks


<b>IsListEmpty</b> returns <b>TRUE</b> if <i>ListHead</i>-&gt;<b>Flink</b> refers back to <i>ListHead</i>.

For information about using this routine when implementing a doubly linked list, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563802">Singly and Doubly Linked Lists</a>.

Callers of <b>IsListEmpty</b> can be running at any IRQL. If <b>IsListEmpty</b> is called at IRQL &gt;= DISPATCH_LEVEL, the storage for <i>ListHead</i> must be resident. 



## -see-also

<a href="..\wdm\nf-wdm-initializelisthead.md">InitializeListHead</a>

<a href="..\wdm\nf-wdm-removeheadlist.md">RemoveHeadList</a>

<a href="..\wdm\nf-wdm-removeentrylist.md">RemoveEntryList</a>

<a href="..\wdm\nf-wdm-removetaillist.md">RemoveTailList</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IsListEmpty routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

