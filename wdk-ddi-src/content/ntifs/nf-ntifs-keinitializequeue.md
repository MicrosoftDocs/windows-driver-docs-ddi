---
UID: NF:ntifs.KeInitializeQueue
title: KeInitializeQueue function
author: windows-driver-content
description: The KeInitializeQueue routine initializes a queue object on which threads can wait for entries.
old-location: ifsk\keinitializequeue.htm
old-project: ifsk
ms.assetid: 8dd47333-679a-482b-bd45-1e73505b3fea
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: KeInitializeQueue, KeInitializeQueue routine [Installable File System Drivers], ifsk.keinitializequeue, keref_85ea0829-c42c-4411-8ad9-a32d8eb0a40f.xml, ntifs/KeInitializeQueue
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	KeInitializeQueue
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# KeInitializeQueue function


## -description


The <b>KeInitializeQueue</b> routine initializes a queue object on which threads can wait for entries. 


## -parameters




### -param Queue [out]

Pointer to a KQUEUE structure for which the caller must provide resident storage in nonpaged pool. This structure is defined as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _KQUEUE {
    DISPATCHER_HEADER Header;
    LIST_ENTRY EntryListHead;
    ULONG CurrentCount;
    ULONG MaximumCount;
    LIST_ENTRY ThreadListHead;
} KQUEUE, *PKQUEUE, *RESTRICTED_POINTER PRKQUEUE;</pre>
</td>
</tr>
</table></span></div>
<table>
<tr>
<th>Member</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<b>Header</b>

</td>
<td>
Queue header.

</td>
</tr>
<tr>
<td>
<b>EntryListHead</b>

</td>
<td>
Pointer to the first entry in the queue.

</td>
</tr>
<tr>
<td>
<b>CurrentCount</b>

</td>
<td>
Current number of threads waiting on the queue.

</td>
</tr>
<tr>
<td>
<b>MaximumCount</b>

</td>
<td>
Maximum number of concurrent threads the queue can satisfy waits for.

</td>
</tr>
<tr>
<td>
<b>ThreadListHead</b>

</td>
<td>
Pointer to the first entry in the thread list.

</td>
</tr>
</table>
 


### -param Count [in]

The maximum number of threads for which the waits on the queue object can be satisfied concurrently. If this parameter is not supplied, the number of processors in the machine is used.


## -returns



None




## -remarks



Usually the caller of <b>KeInitializeQueue</b> also creates a set of dedicated threads to queue and dequeue its entries. Such a caller can specify an explicit <i>Count</i> to prevent too many of its dedicated threads from waiting concurrently on its queue object. 

<b>KeInitializeQueue</b> sets the queue object's initial signal state to Not Signaled.

For more information about using driver-managed internal queues, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff544165">Driver-Managed Queues</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544520">ExAllocatePoolWithTag</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548276">IoAllocateWorkItem</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549466">IoQueueWorkItem</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549570">KeInsertQueue</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549605">KeRemoveQueue</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549638">KeRundownQueue</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559932">PsCreateSystemThread</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20KeInitializeQueue routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

