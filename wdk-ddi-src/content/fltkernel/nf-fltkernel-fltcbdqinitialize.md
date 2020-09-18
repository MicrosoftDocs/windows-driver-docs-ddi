---
UID: NF:fltkernel.FltCbdqInitialize
title: FltCbdqInitialize function (fltkernel.h)
description: FltCbdqInitialize initializes a minifilter driver's callback data queue dispatch table.
old-location: ifsk\fltcbdqinitialize.htm
tech.root: ifsk
ms.assetid: a3e089bf-6037-4d85-92ce-db9c865bdc02
ms.date: 04/16/2018
keywords: ["FltCbdqInitialize function"]
ms.keywords: FltApiRef_a_to_d_e365fdac-7834-4388-b8ba-65593b045d19.xml, FltCbdqInitialize, FltCbdqInitialize function [Installable File System Drivers], fltkernel/FltCbdqInitialize, ifsk.fltcbdqinitialize
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
targetos: Windows
req.typenames: 
f1_keywords:
 - FltCbdqInitialize
 - fltkernel/FltCbdqInitialize
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - fltkernel.h
api_name:
 - FltCbdqInitialize
---

# FltCbdqInitialize function


## -description

FltCbdqInitialize initializes a minifilter driver's callback data queue dispatch table.

## -parameters

### -param Instance 

[in]
Opaque instance pointer for the instance whose callback data queue is to be initialized.

### -param Cbdq 

[in, out]
Pointer to a callback data queue allocated by the minifilter driver.

### -param CbdqInsertIo 

[in]
Pointer to a caller-supplied insert callback routine. The Filter Manager calls this routine to insert the specified callback data structure into the queue. This routine is declared as follows: 


```
typedef NTSTATUS
(*PFLT_CALLBACK_DATA_QUEUE_INSERT_IO)(
      _Inout_ PFLT_CALLBACK_DATA_QUEUE Cbdq,
      _In_ PFLT_CALLBACK_DATA Cbd,
      _In_opt_ PVOID InsertContext
      );
```





#### Cbdq

Pointer to the minifilter driver's cancel-safe callback data queue. This queue must have been initialized by calling <i>FltCbdqInitialize</i>. 



#### Cbd

Pointer to the callback data structure to be inserted into the queue. 



#### InsertContext

Context information pointer that was passed as the <i>InsertContext</i> parameter to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcbdqinsertio">FltCbdqInsertIo</a>.

### -param CbdqRemoveIo 

[in]
Pointer to a caller-supplied remove callback routine. The Filter Manager calls this routine to remove the specified callback data structure from the queue. This routine is declared as follows: 


```
typedef VOID
(*PFLT_CALLBACK_DATA_QUEUE_REMOVE_IO)(
      _Inout_ PFLT_CALLBACK_DATA_QUEUE Cbdq,
      _In_ PFLT_CALLBACK_DATA Cbd
      );
```





#### Cbdq

Pointer to the minifilter driver's cancel-safe callback data queue. This queue must have been initialized by calling <i>FltCbdqInitialize</i>. 



#### Cbd

Pointer to the callback data structure to be removed from the queue.

### -param CbdqPeekNextIo 

[in]
Pointer to a caller-supplied peek callback routine. The Filter Manager calls this function to get a pointer to the next I/O operation matching <i>PeekContext</i> in the queue; or, if <i>Cbd</i> is <b>NULL</b>, to get a pointer to the first matching I/O operation in the queue. The minifilter driver entirely defines the meaning of <i>PeekContext</i> and defines when an I/O operation matches a given <i>PeekContext</i>. This routine is declared as follows: 


```
typedef PFLT_CALLBACK_DATA
(*PFLT_CALLBACK_DATA_QUEUE_PEEK_NEXT_IO)(
      _In_ PFLT_CALLBACK_DATA_QUEUE Cbdq,
      _In_opt_ PFLT_CALLBACK_DATA Cbd,
      _In_opt_ PVOID PeekContext
      );
```





#### Cbdq

Pointer to the minifilter driver's cancel-safe callback data queue. This queue must have been initialized by calling <i>FltCbdqInitialize</i>. 



#### Cbd

Pointer to the callback data structure marking the position in the queue to begin searching for a match to <i>PeekContext</i>. If <i>Cbd</i> is <b>NULL</b>, the search begins at the head of the queue. 



#### PeekContext

Context information pointer that was passed as the <i>PeekContext</i> parameter to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcbdqremovenextio">FltCbdqRemoveNextIo</a>.

### -param CbdqAcquire 

[in]
Pointer to a caller-supplied acquire queue lock callback routine. The Filter Manager calls this routine to acquire the lock on the queue before attempting to insert or remove an item from the queue. This routine is declared as follows: 


```
typedef VOID
(*PFLT_CALLBACK_DATA_QUEUE_ACQUIRE)(
      _Inout_ PFLT_CALLBACK_DATA_QUEUE Cbdq,
      _Out_opt_ PKIRQL Irql
      );
```





#### Cbdq

Pointer to the minifilter driver's cancel-safe callback data queue. This queue must have been initialized by calling <i>FltCbdqInitialize</i>. 



#### Irql

Pointer to a system-supplied variable that receives the current IRQL. The same variable is passed to the corresponding <i>CbdqRelease</i> routine.

### -param CbdqRelease 

[in]
Pointer to a caller-supplied release queue lock callback routine. The Filter Manager calls this routine to release the lock that it obtained by calling the corresponding <i>CbdqAcquire</i> routine. This routine is declared as follows: 


```
typedef VOID
(*PFLT_CALLBACK_DATA_QUEUE_RELEASE)(
      _Inout_ PFLT_CALLBACK_DATA_QUEUE Cbdq,
      _In_opt_ KIRQL Irql
      );
```





#### Cbdq

Pointer to the minifilter driver's cancel-safe callback data queue. This queue must have been initialized by calling <i>FltCbdqInitialize</i>. 



#### Irql

The same system-supplied variable that received the current IRQL as the <i>Irql</i> parameter to the corresponding <i>CbdqAcquire</i> routine.

### -param CbdqCompleteCanceledIo 

[in]
Pointer to a caller-supplied cancel routine. The Filter Manager calls this routine to signal to the minifilter driver to complete a canceled I/O operation. This routine is declared as follows: 


```
typedef VOID
(*PFLT_CALLBACK_DATA_QUEUE_COMPLETE_CANCELED_IO)(
      _Inout_ PFLT_CALLBACK_DATA_QUEUE Cbdq,
      _Inout_ PFLT_CALLBACK_DATA Cbd
      );
```





#### Cbdq

Pointer to the minifilter driver's cancel-safe callback data queue. This queue must have been initialized by calling <i>FltCbdqInitialize</i>. 



#### Cbd

Pointer to the callback data structure for the canceled I/O operation.

## -returns

<i>FltCbdqInitialize</i> returns STATUS_SUCCESS or an appropriate NTSTATUS value.

## -remarks

The newly initialized callback data queue is in the enabled state, which  means that callback data structure items can be inserted into the queue. The queue can be disabled by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcbdqdisable">FltCbdqDisable</a> and reenabled by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcbdqenable">FltCbdqEnable</a>. 

Minifilter drivers can use the <b>FltCbdq</b><i>Xxx</i> routines to implement a callback data queue for IRP-based I/O operations. By using these routines, minifilter drivers can make their queues cancel-safe; the system transparently handles I/O cancellation for the minifilter drivers. 

The <b>FltCbdq</b><i>Xxx</i> routines can only be used for IRP-based I/O operations. To determine whether a given callback data structure represents an IRP-based I/O operation, use the <a href="https://docs.microsoft.com/previous-versions/ff544654(v=vs.85)">FLT_IS_IRP_OPERATION</a> macro. 

Minifilter drivers can use any internal implementation for the queue. The Filter Manager interacts with the minifilter driver's queue implementation solely through the set of dispatch routines provided by <i>FltCbdqInitialize</i>. 

The system automatically locks and unlocks the queue as necessary. Minifilter drivers do not implement any locking inside their <i>CbdqInsertIo</i>, <i>CbdqRemoveIo</i>, and <i>CbdqPeekNextIo</i> routines. 

Minifilter drivers can use any of the operating system's synchronization primitives as the locking mechanism in their <i>CbdqAcquire</i> and <i>CbdqRelease</i> routines, such as a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/spin-locks">spin lock</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/mutex-objects">mutex object</a>, or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exinitializeresourcelite">resource variable</a>. Note that if a minifilter driver uses a spin lock  rather than a mutex or resource to protect the queue, it can call the <b>FltCbdq</b><i>Xxx</i> routines at IRQL <= DISPATCH_LEVEL. If a mutex or resource is used, the minifilter driver must be running at IRQL <= APC_LEVEL when it calls  any of these routines except <i>FltCbdqInitialize</i>. 

The minifilter driver does not manipulate the queue directly. Instead, it calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcbdqinsertio">FltCbdqInsertIo</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcbdqremoveio">FltCbdqRemoveIo</a>, and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcbdqremovenextio">FltCbdqRemoveNextIo</a> to add or remove a callback data structure. These routines in turn call the callback functions that the minifilter driver provided to <i>FltCbdqInitialize</i>. 

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
This routine should lock the queue so that no other thread can access it. Minifilter drivers can use any locking mechanism to lock the queue. If the minifilter driver uses the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keacquirespinlock">KeAcquireSpinLock</a> routine, the minifilter driver can use the memory location pointed to by the routine's <i>Irql</i> parameter to store the IRQL. Otherwise, minifilter drivers can ignore that parameter.

</td>
</tr>
<tr>
<td>
<i>CbdqRelease</i>

</td>
<td>
This routine should unlock the queue created by <i>CbdqAcquire</i>. If the minifilter driver used a spin lock and returned the IRQL value in the <i>Irql</i> parameter of <i>CbdqAcquire</i>, the system passes that value in the <i>Irql</i> parameter of <i>CbdqRelease</i>. The minifilter driver can use the IRQL to unlock the spin lock by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kereleasespinlock">KeReleaseSpinLock</a>. Otherwise, minifilter drivers can ignore the <i>Irql</i> parameter.

</td>
</tr>
<tr>
<td>
<i>CbdqCompleteCanceledIo</i>

</td>
<td>
This routine should complete a canceled I/O operation. Normally, minifilter drivers can just call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcompletependedpreoperation">FltCompletePendedPreOperation</a>(Data, FLT_PREOP_COMPLETE, <b>NULL</b>). Minifilter drivers do not need to dequeue the callback data structure -- the Filter Manager automatically calls the queue's <i>CbdqRemoveIo</i> before calling <i>CbdqCompleteCanceledIo</i>.

</td>
</tr>
</table>

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data_queue">FLT_CALLBACK_DATA_QUEUE</a>



<a href="https://docs.microsoft.com/previous-versions/ff544654(v=vs.85)">FLT_IS_IRP_OPERATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcbdqdisable">FltCbdqDisable</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcbdqenable">FltCbdqEnable</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcbdqinsertio">FltCbdqInsertIo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcbdqremoveio">FltCbdqRemoveIo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcbdqremovenextio">FltCbdqRemoveNextIo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcompletependedpreoperation">FltCompletePendedPreOperation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keacquirespinlock">KeAcquireSpinLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kereleasespinlock">KeReleaseSpinLock</a>

