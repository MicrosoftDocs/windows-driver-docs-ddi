---
UID: NF:fltkernel.FltCbdqInitialize
title: FltCbdqInitialize function
author: windows-driver-content
description: FltCbdqInitialize initializes a minifilter driver's callback data queue dispatch table.
old-location: ifsk\fltcbdqinitialize.htm
old-project: ifsk
ms.assetid: a3e089bf-6037-4d85-92ce-db9c865bdc02
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltApiRef_a_to_d_e365fdac-7834-4388-b8ba-65593b045d19.xml, FltCbdqInitialize, FltCbdqInitialize function [Installable File System Drivers], fltkernel/FltCbdqInitialize, ifsk.fltcbdqinitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
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
req.lib: 
req.dll: 
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	fltkernel.h
api_name:
-	FltCbdqInitialize
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltCbdqInitialize function


## -description


FltCbdqInitialize initializes a minifilter driver's callback data queue dispatch table. 


## -parameters




### -param Instance [in]

Opaque instance pointer for the instance whose callback data queue is to be initialized. 


### -param Cbdq [in, out]

Pointer to a callback data queue allocated by the minifilter driver. 


### -param CbdqInsertIo [in]

Pointer to a caller-supplied insert callback routine. The Filter Manager calls this routine to insert the specified callback data structure into the queue. This routine is declared as follows: 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef NTSTATUS
(*PFLT_CALLBACK_DATA_QUEUE_INSERT_IO)(
      _Inout_ PFLT_CALLBACK_DATA_QUEUE Cbdq,
      _In_ PFLT_CALLBACK_DATA Cbd,
      _In_opt_ PVOID InsertContext
      );</pre>
</td>
</tr>
</table></span></div>




#### Cbdq

Pointer to the minifilter driver's cancel-safe callback data queue. This queue must have been initialized by calling <i>FltCbdqInitialize</i>. 



#### Cbd

Pointer to the callback data structure to be inserted into the queue. 



#### InsertContext

Context information pointer that was passed as the <i>InsertContext</i> parameter to <a href="https://msdn.microsoft.com/library/windows/hardware/ff541815">FltCbdqInsertIo</a>. 


### -param CbdqRemoveIo [in]

Pointer to a caller-supplied remove callback routine. The Filter Manager calls this routine to remove the specified callback data structure from the queue. This routine is declared as follows: 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef VOID
(*PFLT_CALLBACK_DATA_QUEUE_REMOVE_IO)(
      _Inout_ PFLT_CALLBACK_DATA_QUEUE Cbdq,
      _In_ PFLT_CALLBACK_DATA Cbd
      );</pre>
</td>
</tr>
</table></span></div>




#### Cbdq

Pointer to the minifilter driver's cancel-safe callback data queue. This queue must have been initialized by calling <i>FltCbdqInitialize</i>. 



#### Cbd

Pointer to the callback data structure to be removed from the queue. 


### -param CbdqPeekNextIo [in]

Pointer to a caller-supplied peek callback routine. The Filter Manager calls this function to get a pointer to the next I/O operation matching <i>PeekContext</i> in the queue; or, if <i>Cbd</i> is <b>NULL</b>, to get a pointer to the first matching I/O operation in the queue. The minifilter driver entirely defines the meaning of <i>PeekContext</i> and defines when an I/O operation matches a given <i>PeekContext</i>. This routine is declared as follows: 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef PFLT_CALLBACK_DATA
(*PFLT_CALLBACK_DATA_QUEUE_PEEK_NEXT_IO)(
      _In_ PFLT_CALLBACK_DATA_QUEUE Cbdq,
      _In_opt_ PFLT_CALLBACK_DATA Cbd,
      _In_opt_ PVOID PeekContext
      );</pre>
</td>
</tr>
</table></span></div>




#### Cbdq

Pointer to the minifilter driver's cancel-safe callback data queue. This queue must have been initialized by calling <i>FltCbdqInitialize</i>. 



#### Cbd

Pointer to the callback data structure marking the position in the queue to begin searching for a match to <i>PeekContext</i>. If <i>Cbd</i> is <b>NULL</b>, the search begins at the head of the queue. 



#### PeekContext

Context information pointer that was passed as the <i>PeekContext</i> parameter to <a href="https://msdn.microsoft.com/library/windows/hardware/ff541825">FltCbdqRemoveNextIo</a>. 


### -param CbdqAcquire [in]

Pointer to a caller-supplied acquire queue lock callback routine. The Filter Manager calls this routine to acquire the lock on the queue before attempting to insert or remove an item from the queue. This routine is declared as follows: 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef VOID
(*PFLT_CALLBACK_DATA_QUEUE_ACQUIRE)(
      _Inout_ PFLT_CALLBACK_DATA_QUEUE Cbdq,
      _Out_opt_ PKIRQL Irql
      );</pre>
</td>
</tr>
</table></span></div>




#### Cbdq

Pointer to the minifilter driver's cancel-safe callback data queue. This queue must have been initialized by calling <i>FltCbdqInitialize</i>. 



#### Irql

Pointer to a system-supplied variable that receives the current IRQL. The same variable is passed to the corresponding <i>CbdqRelease</i> routine. 


### -param CbdqRelease [in]

Pointer to a caller-supplied release queue lock callback routine. The Filter Manager calls this routine to release the lock that it obtained by calling the corresponding <i>CbdqAcquire</i> routine. This routine is declared as follows: 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef VOID
(*PFLT_CALLBACK_DATA_QUEUE_RELEASE)(
      _Inout_ PFLT_CALLBACK_DATA_QUEUE Cbdq,
      _In_opt_ KIRQL Irql
      );</pre>
</td>
</tr>
</table></span></div>




#### Cbdq

Pointer to the minifilter driver's cancel-safe callback data queue. This queue must have been initialized by calling <i>FltCbdqInitialize</i>. 



#### Irql

The same system-supplied variable that received the current IRQL as the <i>Irql</i> parameter to the corresponding <i>CbdqAcquire</i> routine. 


### -param CbdqCompleteCanceledIo [in]

Pointer to a caller-supplied cancel routine. The Filter Manager calls this routine to signal to the minifilter driver to complete a canceled I/O operation. This routine is declared as follows: 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef VOID
(*PFLT_CALLBACK_DATA_QUEUE_COMPLETE_CANCELED_IO)(
      _Inout_ PFLT_CALLBACK_DATA_QUEUE Cbdq,
      _Inout_ PFLT_CALLBACK_DATA Cbd
      );</pre>
</td>
</tr>
</table></span></div>




#### Cbdq

Pointer to the minifilter driver's cancel-safe callback data queue. This queue must have been initialized by calling <i>FltCbdqInitialize</i>. 



#### Cbd

Pointer to the callback data structure for the canceled I/O operation. 


## -returns



<i>FltCbdqInitialize</i> returns STATUS_SUCCESS or an appropriate NTSTATUS value. 




## -remarks



The newly initialized callback data queue is in the enabled state, which  means that callback data structure items can be inserted into the queue. The queue can be disabled by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff541796">FltCbdqDisable</a> and reenabled by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff541799">FltCbdqEnable</a>. 

Minifilter drivers can use the <b>FltCbdq</b><i>Xxx</i> routines to implement a callback data queue for IRP-based I/O operations. By using these routines, minifilter drivers can make their queues cancel-safe; the system transparently handles I/O cancellation for the minifilter drivers. 

The <b>FltCbdq</b><i>Xxx</i> routines can only be used for IRP-based I/O operations. To determine whether a given callback data structure represents an IRP-based I/O operation, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544654">FLT_IS_IRP_OPERATION</a> macro. 

Minifilter drivers can use any internal implementation for the queue. The Filter Manager interacts with the minifilter driver's queue implementation solely through the set of dispatch routines provided by <i>FltCbdqInitialize</i>. 

The system automatically locks and unlocks the queue as necessary. Minifilter drivers do not implement any locking inside their <i>CbdqInsertIo</i>, <i>CbdqRemoveIo</i>, and <i>CbdqPeekNextIo</i> routines. 

Minifilter drivers can use any of the operating system's synchronization primitives as the locking mechanism in their <i>CbdqAcquire</i> and <i>CbdqRelease</i> routines, such as a <a href="https://msdn.microsoft.com/0585fc2a-0d0b-434d-92b3-da07a9385444">spin lock</a>, <a href="https://msdn.microsoft.com/e2142b6d-f460-4f80-be0f-e00b5d43731c">mutex object</a>, or <a href="https://msdn.microsoft.com/be18a6e6-863d-4a0c-9bcd-a36ace0b54fe">resource variable</a>. Note that if a minifilter driver uses a spin lock  rather than a mutex or resource to protect the queue, it can call the <b>FltCbdq</b><i>Xxx</i> routines at IRQL &lt;= DISPATCH_LEVEL. If a mutex or resource is used, the minifilter driver must be running at IRQL &lt;= APC_LEVEL when it calls  any of these routines except <i>FltCbdqInitialize</i>. 

The minifilter driver does not manipulate the queue directly. Instead, it calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff541815">FltCbdqInsertIo</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff541821">FltCbdqRemoveIo</a>, and <a href="https://msdn.microsoft.com/library/windows/hardware/ff541825">FltCbdqRemoveNextIo</a> to add or remove a callback data structure. These routines in turn call the callback functions that the minifilter driver provided to <i>FltCbdqInitialize</i>. 

Minifilter drivers should implement the queue routines as follows. 

<table>
<tr>
<th>Cbdq Routine</th>
<th>Implementation</th>
</tr>
<tr>
<td>
<i>CbdqInsertIo</i>

</td>
<td>
Insert the specified callback data structure into the queue.

</td>
</tr>
<tr>
<td>
<i>CbdqRemoveIo</i>

</td>
<td>
Remove the specified callback data structure from the queue.

</td>
</tr>
<tr>
<td>
<i>CbdqPeekNextIo</i>

</td>
<td>
This routine should allow the system to loop through the callback data structures with matching <i>PeekContext</i> in the queue. <i>Cbd</i> = <i>CbdqPeekNextIo</i>(<i>Cbdq</i>, <b>NULL</b>, <i>PeekContext</i>) should return the first matching entry in the queue, and <i>CbdqPeekNextIo</i>(<i>Cbdq</i>, <i>Cbd</i>, <i>PeekContext</i>) should return the next matching entry after the given callback data structure in the queue. The minifilter driver entirely defines the meaning of <i>PeekContext</i> and defines when a callback data structure matches a <i>PeekContext</i> value.

</td>
</tr>
<tr>
<td>
<i>CbdqAcquire</i>

</td>
<td>
This routine should lock the queue so that no other thread can access it. Minifilter drivers can use any locking mechanism to lock the queue. If the minifilter driver uses the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551917">KeAcquireSpinLock</a> routine, the minifilter driver can use the memory location pointed to by the routine's <i>Irql</i> parameter to store the IRQL. Otherwise, minifilter drivers can ignore that parameter.

</td>
</tr>
<tr>
<td>
<i>CbdqRelease</i>

</td>
<td>
This routine should unlock the queue created by <i>CbdqAcquire</i>. If the minifilter driver used a spin lock and returned the IRQL value in the <i>Irql</i> parameter of <i>CbdqAcquire</i>, the system passes that value in the <i>Irql</i> parameter of <i>CbdqRelease</i>. The minifilter driver can use the IRQL to unlock the spin lock by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff553145">KeReleaseSpinLock</a>. Otherwise, minifilter drivers can ignore the <i>Irql</i> parameter.

</td>
</tr>
<tr>
<td>
<i>CbdqCompleteCanceledIo</i>

</td>
<td>
This routine should complete a canceled I/O operation. Normally, minifilter drivers can just call <a href="https://msdn.microsoft.com/library/windows/hardware/ff541913">FltCompletePendedPreOperation</a>(Data, FLT_PREOP_COMPLETE, <b>NULL</b>). Minifilter drivers do not need to dequeue the callback data structure -- the Filter Manager automatically calls the queue's <i>CbdqRemoveIo</i> before calling <i>CbdqCompleteCanceledIo</i>.

</td>
</tr>
</table>
 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544624">FLT_CALLBACK_DATA_QUEUE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544654">FLT_IS_IRP_OPERATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541796">FltCbdqDisable</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541799">FltCbdqEnable</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541815">FltCbdqInsertIo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541821">FltCbdqRemoveIo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541825">FltCbdqRemoveNextIo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541913">FltCompletePendedPreOperation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551917">KeAcquireSpinLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553145">KeReleaseSpinLock</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltCbdqInitialize function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

