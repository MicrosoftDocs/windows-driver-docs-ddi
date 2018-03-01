---
UID: NF:wdm.KeWaitForMultipleObjects
title: KeWaitForMultipleObjects function
author: windows-driver-content
description: The KeWaitForMultipleObjects routine puts the current thread into an alertable or nonalertable wait state until any or all of a number of dispatcher objects are set to a signaled state or (optionally) until the wait times out.
old-location: kernel\kewaitformultipleobjects.htm
old-project: kernel
ms.assetid: 2e533d7b-be70-4601-b9e1-4fe3ce51817f
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: KeWaitForMultipleObjects, KeWaitForMultipleObjects routine [Kernel-Mode Driver Architecture], k105_03342f87-b6a7-4e26-a7e8-5a8157026c4a.xml, kernel.kewaitformultipleobjects, wdm/KeWaitForMultipleObjects
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
req.ddi-compliance: IrpProcessingComplete, IrqlKeWaitForMultipleObjects, HwStorPortProhibitedDDIs, SpNoWait
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: See Remarks section.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	KeWaitForMultipleObjects
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeWaitForMultipleObjects function


## -description


The <b>KeWaitForMultipleObjects</b> routine puts the current thread into an alertable or nonalertable wait state until any or all of a number of dispatcher objects are set to a signaled state or (optionally) until the wait times out.


## -syntax


````
NTSTATUS  KeWaitForMultipleObjects(
  _In_      ULONG           Count,
  _In_      PVOID           Object[],
  _In_      WAIT_TYPE       WaitType,
  _In_      KWAIT_REASON    WaitReason,
  _In_      KPROCESSOR_MODE WaitMode,
  _In_      BOOLEAN         Alertable,
  _In_opt_  PLARGE_INTEGER  Timeout,
  _Out_opt_ PKWAIT_BLOCK    WaitBlockArray
);
````


## -parameters




### -param Count [in]

The number of objects to be waited on. This parameter specifies the number of elements in the array pointed to by the <i>Object</i> parameter.


### -param Object [in]

A pointer to an array of pointers to dispatcher objects (events, mutexes, semaphores, threads, and timers) for which the caller supplies the storage. Both the pointer array and the dispatcher objects must reside in nonpaged system memory. For more information, see Remarks.


### -param WaitType [in]

The type of wait operation to perform. Specify either <b>WaitAll</b>, indicating that all of the specified objects must attain a signaled state before the wait is satisfied; or <b>WaitAny</b>, indicating that any one of the objects must attain a signaled state before the wait is satisfied.


### -param WaitReason [in]

The reason for the wait. Drivers should set this value to <b>Executive</b> or, if the driver is doing work on behalf of a user and is running in the context of a user thread, to <b>UserRequest</b>.


### -param WaitMode [in]

Whether the caller waits in <b>KernelMode</b> or <b>UserMode</b>. Intermediate and lowest-level drivers should specify <b>KernelMode</b>. If the set of objects waited on includes a mutex, the caller must specify <b>KernelMode</b>.


### -param Alertable [in]

A Boolean value that indicates whether the thread can be alerted while it is in the waiting state.


### -param Timeout [in, optional]

A pointer to a time-out value that specifies the absolute or relative time, in 100-nanosecond units, at which the wait is to be completed.

A positive value specifies an absolute time, relative to January 1, 1601. A negative value specifies an interval relative to the current time. Absolute expiration times track any changes in the system time; relative expiration times are not affected by system time changes.

If *<i>Timeout</i> = 0, the routine returns without waiting. If the caller supplies a <b>NULL</b> pointer, the routine waits indefinitely until any or all of the dispatcher objects are set to the signaled state. For more information, see the following Remarks section.


### -param WaitBlockArray [out, optional]

A pointer to a caller-allocated <b>KWAIT_BLOCK</b> array. If <i>Count</i> &lt;= THREAD_WAIT_OBJECTS, then <i>WaitBlockArray</i> can be <b>NULL</b>. Otherwise, this parameter must point to a memory buffer of <b>sizeof</b>(<b>KWAIT_BLOCK</b>) * <i>Count</i> bytes. The routine uses this buffer for record-keeping while performing the wait operation. The <i>WaitBlockArray</i> buffer must reside in nonpaged system memory. For more information, see Remarks.


## -returns



<b>KeWaitForMultipleObjects</b> can return one of the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The caller specified <b>WaitAll</b> for the <i>WaitType</i> parameter and all dispatcher objects in the <i>Object</i> array have been set to the signaled state.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ALERTED</b></dt>
</dl>
</td>
<td width="60%">
The wait was interrupted to deliver an alert to the calling thread.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_USER_APC</b></dt>
</dl>
</td>
<td width="60%">
The wait was interrupted to deliver a user asynchronous procedure call (APC) to the calling thread.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_TIMEOUT</b></dt>
</dl>
</td>
<td width="60%">
A time-out occurred before the specified set of wait conditions was met. This value can be returned when an explicit time-out value of zero is specified, but the specified set of wait conditions cannot be met immediately.

</td>
</tr>
</table>
 

Note that the NT_SUCCESS macro recognizes all of these status values as "success" values.




## -remarks



Each thread object has a built-in array of wait blocks that can be used to wait for several objects to be set concurrently. Whenever possible, the built-in array of wait blocks should be used in a wait-multiple operation because no additional wait block storage needs to be allocated and later deallocated. However, if the number of objects that must be waited on concurrently is greater than the number of built-in wait blocks, use the <i>WaitBlockArray</i> parameter to specify an alternate set of wait blocks to be used in the wait operation. Drivers only need to allocate a sufficiently large memory buffer for <i>WaitBlockArray</i>. The buffer does not need to be initialized; however, it must be allocated from nonpaged system memory. If the <i>WaitMode</i> parameter is <b>UserMode</b>, the <i>WaitBlockArray</i> buffer must not be allocated on the local stack because the stack might be swapped out of memory. Drivers can treat this buffer as an opaque structure and can free it after the routine returns. If either <i>Count</i> &gt; MAXIMUM_WAIT_OBJECTS or if <i>WaitBlockArray</i> is <b>NULL</b> and <i>Count</i> &gt; THREAD_WAIT_OBJECTS, the system issues <a href="https://msdn.microsoft.com/99d2eb8f-f331-45b8-a96b-68696802c269">Bug Check 0xC (MAXIMUM_WAIT_OBJECTS_EXCEEDED)</a>.

The current state for each of the specified objects is examined to determine whether the wait can be satisfied immediately. If the necessary side effects are performed on the objects, an appropriate value is returned.

If the wait cannot be satisfied immediately and either no time-out value or a nonzero time-out value has been specified, the current thread is put in a waiting state and a new thread is selected for execution on the current processor. If no <i>Timeout</i> is supplied, the calling thread will remain in a wait state until the conditions specified by <i>Object</i> and <i>WaitType</i> are satisfied.

If <i>Timeout</i> is specified, the wait will be automatically satisfied if none of the specified wait conditions is met when the given interval expires.

A time-out value of zero allows the testing of a set of wait conditions, conditionally performing any side effects if the wait can be immediately satisfied, as in the acquisition of a mutex.

Time-out intervals are measured relative to the system clock, and the accuracy with which the operating system can detect the end of a time-out interval is limited by the granularity of the system clock. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/jj602805">Timer Accuracy</a>.

The <i>Alertable</i> parameter determines when the thread can be alerted and its wait state consequently aborted. For additional information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565592">Waits and APCs</a>.

The array pointed to by the <i>Objects</i> parameter must reside in nonpaged system memory. Typically, a driver allocates the storage for the <i>Objects</i> array on the local stack. The <i>Objects</i> array can be allocated on the local stack regardless of the value of the <i>WaitMode</i> parameter.

The dispatcher objects pointed to by the elements in the <i>Objects</i> array must reside in nonpaged system memory. If the <i>WaitMode</i> parameter is <b>UserMode</b>, the kernel stack can be swapped out during the wait. Consequently, a caller must <u>never</u> attempt to pass parameters on the stack when calling <b>KeWaitForMultipleObjects</b> with the <b>UserMode</b> argument. If you allocate the event on the stack, you must set the <i>WaitMode</i> parameter to <b>KernelMode</b>.

A special consideration applies when the <i>Object</i> parameter passed to <b>KeWaitForMultipleObjects</b> is a mutex. If the dispatcher object waited on is a mutex, APC delivery is the same as for all other dispatcher objects <u>during the wait</u>. However, after <b>KeWaitForMultipleObjects</b> returns with STATUS_SUCCESS and the thread actually holds the mutex, only special kernel-mode APCs are delivered. Delivery of all other APCs, both kernel-mode and user-mode, is disabled. This restriction on the delivery of APCs persists until the mutex is released.

It is especially important to check the return value of <b>KeWaitForMultipleObjects</b> when the <i>WaitMode</i> parameter is <b>UserMode</b> or <i>Alertable</i> is <b>TRUE</b>, because <b>KeWaitForMultipleObjects</b> might return early with a status of STATUS_USER_APC or STATUS_ALERTED. 

All long term waits that can be aborted by a user should be <b>UserMode</b> waits and <i>Alertable</i> should be set to <b>FALSE</b>.

Where possible, <i>Alertable</i> should be set to <b>FALSE</b> and <i>WaitMode</i> should be set to <b>KernelMode</b>, in order to reduce driver complexity. The principal exception to this is when the wait is a long-term wait.

A mutex can be recursively acquired only MINLONG times. If this limit is exceeded, the routine raises a STATUS_MUTANT_LIMIT_EXCEEDED exception.

Callers of <b>KeWaitForMultipleObjects</b> can be running at IRQL &lt;= DISPATCH_LEVEL. However, if <i>Timeout</i> = <b>NULL</b> or *<i>Timeout</i> != 0, the caller must be running at IRQL &lt;= APC_LEVEL and in a nonarbitrary thread context. (If <i>Timeout</i> != <b>NULL</b> and *<i>Timeout</i> = 0, the caller must be running at IRQL &lt;= DISPATCH_LEVEL.)




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff553344">KeWaitForMutexObject</a>



<a href="..\wdm\nf-wdm-keinitializeevent.md">KeInitializeEvent</a>



<a href="..\wdm\nf-wdm-exinitializefastmutex.md">ExInitializeFastMutex</a>



<a href="..\wdm\nf-wdm-kewaitforsingleobject.md">KeWaitForSingleObject</a>



<a href="..\wdm\nf-wdm-keinitializesemaphore.md">KeInitializeSemaphore</a>



<a href="..\wdm\nf-wdm-keinitializetimer.md">KeInitializeTimer</a>



<a href="..\wdm\nf-wdm-keinitializemutex.md">KeInitializeMutex</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeWaitForMultipleObjects routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

