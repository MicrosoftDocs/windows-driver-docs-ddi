---
UID: NF:ntifs.KeInsertHeadQueue
title: KeInsertHeadQueue function (ntifs.h)
description: The KeInsertHeadQueue routine inserts an entry at the head of the given queue if it cannot immediately use the entry to satisfy a thread wait.
old-location: ifsk\keinsertheadqueue.htm
tech.root: ifsk
ms.assetid: 82e0bf14-b751-4919-b8d0-26fc7c5598a8
ms.date: 04/16/2018
ms.keywords: KeInsertHeadQueue, KeInsertHeadQueue routine [Installable File System Drivers], ifsk.keinsertheadqueue, keref_a3279265-434b-42d6-95d9-5a8a12f54c9b.xml, ntifs/KeInsertHeadQueue
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- KeInsertHeadQueue
product:
- Windows
targetos: Windows
req.typenames: 
---

# KeInsertHeadQueue function


## -description


The <b>KeInsertHeadQueue</b> routine inserts an entry at the head of the given queue if it cannot immediately use the entry to satisfy a thread wait. 


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



Entries to be queued by <b>KeInsertHeadQueue</b> must be allocated from nonpaged pool. For example, memory for caller-defined entries can be allocated with <a href="https://msdn.microsoft.com/library/windows/hardware/ff544520">ExAllocatePoolWithTag</a>. If the caller allocates entries of a fixed size, creating a lookaside list with <a href="https://msdn.microsoft.com/library/windows/hardware/ff545301">ExInitializeNPagedLookasideList</a> and allocating from it with <a href="https://msdn.microsoft.com/library/windows/hardware/ff544388">ExAllocateFromNPagedLookasideList</a> is more efficient than making frequent calls to <b>ExAllocatePoolWithTag</b>, particularly for entries whose size is not a multiple of PAGE_SIZE. 

If any threads are waiting on the queue object when <b>KeInsertHeadQueue</b> is called, a single thread's wait is satisfied by this call. The thread is dispatched for execution with the given <i>Entry</i> pointer. 

If no threads are currently waiting on the queue object when <b>KeInsertHeadQueue</b> is called, the given entry is inserted in the queue and the queue object's signal state is incremented. 

For more information about using driver-managed internal queues, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff544165">Driver-Managed Queues</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544388">ExAllocateFromNPagedLookasideList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544520">ExAllocatePoolWithTag</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545301">ExInitializeNPagedLookasideList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549547">KeInitializeQueue</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549570">KeInsertQueue</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549605">KeRemoveQueue</a>
 

 

