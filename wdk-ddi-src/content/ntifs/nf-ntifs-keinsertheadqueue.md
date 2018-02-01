---
UID: NF:ntifs.KeInsertHeadQueue
title: KeInsertHeadQueue function
author: windows-driver-content
description: The KeInsertHeadQueue routine inserts an entry at the head of the given queue if it cannot immediately use the entry to satisfy a thread wait.
old-location: ifsk\keinsertheadqueue.htm
old-project: ifsk
ms.assetid: 82e0bf14-b751-4919-b8d0-26fc7c5598a8
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: keref_a3279265-434b-42d6-95d9-5a8a12f54c9b.xml, ifsk.keinsertheadqueue, ntifs/KeInsertHeadQueue, KeInsertHeadQueue, KeInsertHeadQueue routine [Installable File System Drivers]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	KeInsertHeadQueue
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# KeInsertHeadQueue function


## -description


The <b>KeInsertHeadQueue</b> routine inserts an entry at the head of the given queue if it cannot immediately use the entry to satisfy a thread wait. 


## -syntax


````
LONG KeInsertHeadQueue(
  _Inout_ PRKQUEUE    Queue,
  _Inout_ PLIST_ENTRY Entry
);
````


## -parameters




### -param Queue [in, out]

Pointer to an initialized queue object for which the caller provides resident storage in nonpaged pool. This structure is defined as follows:
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
</table></span></div><table>
<tr>
<th>Member</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<b>Header</b>

</td>
<td>
Queue header

</td>
</tr>
<tr>
<td>
<b>EntryListHead</b>

</td>
<td>
Pointer to the first entry in the queue

</td>
</tr>
<tr>
<td>
<b>CurrentCount</b>

</td>
<td>
Number of entries in the queue

</td>
</tr>
<tr>
<td>
<b>MaximumCount</b>

</td>
<td>
Maximum number of entries the queue can contain

</td>
</tr>
<tr>
<td>
<b>ThreadListHead</b>

</td>
<td>
Pointer to the first entry in the thread list

</td>
</tr>
</table> 


### -param Entry [in, out]

Pointer to the queue entry that is to be inserted. This pointer must be a resident system-space address. 


## -returns


<b>KeInsertHeadQueue</b> returns the previous signal state of the given queue. If it was set to zero (not signaled) before <b>KeInsertHeadQueue</b> was called, <b>KeInsertHeadQueue</b> returns zero, meaning that no entries were queued. If it was nonzero (signaled), <b>KeInsertHeadQueue</b> returns the number of entries that were queued before <b>KeInsertHeadQueue</b> was called. 



## -remarks


Entries to be queued by <b>KeInsertHeadQueue</b> must be allocated from nonpaged pool. For example, memory for caller-defined entries can be allocated with <a href="..\wdm\nf-wdm-exallocatepoolwithtag.md">ExAllocatePoolWithTag</a>. If the caller allocates entries of a fixed size, creating a lookaside list with <a href="..\wdm\nf-wdm-exinitializenpagedlookasidelist.md">ExInitializeNPagedLookasideList</a> and allocating from it with <a href="..\wdm\nf-wdm-exallocatefromnpagedlookasidelist.md">ExAllocateFromNPagedLookasideList</a> is more efficient than making frequent calls to <b>ExAllocatePoolWithTag</b>, particularly for entries whose size is not a multiple of PAGE_SIZE. 

If any threads are waiting on the queue object when <b>KeInsertHeadQueue</b> is called, a single thread's wait is satisfied by this call. The thread is dispatched for execution with the given <i>Entry</i> pointer. 

If no threads are currently waiting on the queue object when <b>KeInsertHeadQueue</b> is called, the given entry is inserted in the queue and the queue object's signal state is incremented. 

For more information about using driver-managed internal queues, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff544165">Driver-Managed Queues</a>. 



## -see-also

<a href="..\wdm\nf-wdm-exallocatefromnpagedlookasidelist.md">ExAllocateFromNPagedLookasideList</a>

<a href="..\wdm\nf-wdm-exinitializenpagedlookasidelist.md">ExInitializeNPagedLookasideList</a>

<a href="..\ntifs\nf-ntifs-keinsertqueue.md">KeInsertQueue</a>

<a href="..\wdm\nf-wdm-exallocatepoolwithtag.md">ExAllocatePoolWithTag</a>

<a href="..\ntifs\nf-ntifs-keinitializequeue.md">KeInitializeQueue</a>

<a href="..\ntifs\nf-ntifs-keremovequeue.md">KeRemoveQueue</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20KeInsertHeadQueue routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

