---
UID: NF:fltkernel.FltCancellableWaitForMultipleObjects
title: FltCancellableWaitForMultipleObjects function (fltkernel.h)
description: The FltCancellableWaitForMultipleObjects executes a cancelable wait operation (a wait that can be terminated) on one or more dispatcher objects.
old-location: ifsk\fltcancellablewaitformultipleobjects.htm
tech.root: ifsk
ms.date: 04/02/2021
keywords: ["FltCancellableWaitForMultipleObjects function"]
ms.keywords: FltApiRef_a_to_d_3f130d06-8af0-46c1-9db3-bd70d1cbabe1.xml, FltCancellableWaitForMultipleObjects, FltCancellableWaitForMultipleObjects function [Installable File System Drivers], ifsk.fltcancellablewaitformultipleobjects, ntifs/FltCancellableWaitForMultipleObjects
req.header: fltkernel.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Microsoft Windows Vista
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
req.lib: Fltmgr.lib
req.dll: 
req.irql: See Remarks section.
targetos: Windows
req.typenames: 
f1_keywords:
 - FltCancellableWaitForMultipleObjects
 - fltkernel/FltCancellableWaitForMultipleObjects
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - fltmgr.lib
 - fltmgr.dll
api_name:
 - FltCancellableWaitForMultipleObjects
---

# FltCancellableWaitForMultipleObjects function

## -description

The **FltCancellableWaitForMultipleObjects** executes a cancelable wait operation (a wait that can be terminated) on one or more dispatcher objects.

## -parameters

### -param Count

[in] The number of objects to be waited on.

### -param ObjectArray

[in] A pointer to an array of pointers to dispatcher objects (events, mutexes, semaphores, threads, and timers) for which the caller supplies the storage.

### -param WaitType

[in] An enumumeration with the value of either **WaitAll**, which indicates that all of the specified objects must attain a signaled state before the wait is satisfied; or **WaitAny**, which indicates that any one of the objects must attain a signaled state before the wait is satisfied.

### -param Timeout

[in, optional] A pointer to an optional time-out value. This parameter specifies the absolute or relative time in 100 nanosecond units at which the wait is to be completed.

If Timeout points to a zero value (that is, *Timeout == 0), the routine returns without waiting. If the caller supplies a NULL pointer (that is, Timeout == NULL), the routine waits indefinitely until any or all of the dispatcher objects are set to the signaled state.

A positive value specifies an absolute time, relative to January 1, 1601. A negative value specifies an interval relative to the current time. Absolute expiration times track any changes in the system time; relative expiration times are not affected by system time changes.

If Timeout is specified, the wait is automatically satisfied if none of the specified wait conditions are met when the given interval expires.

A time-out value of zero (that is, *Timeout == 0) allows you to test a set of wait conditions, and to conditionally perform any additional actions if the wait can be immediately satisfied, as in the acquisition of a mutex.

### -param WaitBlockArray

[in, optional] If Count <= THREAD_WAIT_OBJECTS, WaitBlockArray can be NULL. Otherwise, this parameter must point to a memory buffer of ```sizeof(KWAIT_BLOCK) * Count``` bytes. The routine uses this buffer for record-keeping while performing the wait operation.

### -param CallbackData

[in] A pointer to the [**FLT_CALLBACK_DATA**](ns-fltkernel-_flt_callback_data.md) structure that represents the I/O operation that was issued by the user and that can be canceled by the user. The caller must ensure that the I/O operation will remain valid for the duration of this routine and that the I/O must not have a cancel routine set (for example, [**FltSetCancelCompletion**](nf-fltkernel-fltsetcancelcompletion.md) function must not have been called on the I/O operation). Note that the **CallbackData** must be held by the caller as it cannot be passed to a lower-level driver. This parameter is optional and can be NULL.

## -returns

**FltCancellableWaitForMultipleObjects** can return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt>**STATUS_SUCCESS**</dt>
</dl>
</td>
<td width="60%">
The caller specified **WaitAll** for the **WaitType** parameter and all dispatcher objects in the **ObjectArray** array have been set to the signaled state. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>**STATUS_TIMEOUT**</dt>
</dl>
</td>
<td width="60%">
A time-out occurred before the specified set of wait conditions was met. This value can also be returned when the specified set of wait conditions cannot be immediately met and Timeout is set to zero. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>**STATUS_WAIT_0 through STATUS_WAIT_63**</dt>
</dl>
</td>
<td width="60%">
The caller specified **WaitAny** for **WaitType** and one of the dispatcher objects in the **ObjectArray** array has been set to the signaled state. The lower six bits of the return value encode the zero-based index of the object that satisfied the wait. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>**STATUS_ABANDONED_WAIT_0 through STATUS_ABANDONED_WAIT_63**</dt>
</dl>
</td>
<td width="60%">
The caller attempted to wait for a mutex that has been abandoned. The lower six bits of the return value encode the zero-based index of the mutex in the **ObjectArray** array. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>**STATUS_CANCELLED**</dt>
</dl>
</td>
<td width="60%">
The wait was interrupted by a pending cancel request on the I/O operation. Note that this value is returned only if **CallbackData** that corresponds to an IRP based operation is passed to <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcancellablewaitformultipleobjects">FltCancellableWaitForMultipleObjects**]() and the I/O was canceled by a routine such as <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcancelio">FltCancelIo**]().

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>**STATUS_THREAD_IS_TERMINATING**</dt>
</dl>
</td>
<td width="60%">
The wait was interrupted because an application or the user has terminated the thread.

</td>
</tr>
</table>
 

The return value only indicates the status of the wait.

Note that the NT_SUCCESS macro returns **FALSE** ("failure") for the STATUS_CANCELLED and STATUS_THREAD_IS_TERMINATING status values and **TRUE** ("success") for all other status values.

## -remarks

The **FltCancellableWaitForMultipleObjects** executes a cancelable wait operation on dispatcher objects. If the user or the application terminates the thread, or if an I/O operation associated with the thread was canceled by a routine such as <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcancelio">FltCancelIo**](), the wait is canceled.

The routine is designed to support the <a href="/previous-versions/windows/hardware/design/dn613954(v=vs.85)">I/O Completion/Cancellation Guidelines**](). The goal of these guidelines is to allow users to quickly terminate applications. This, in turn, requires that applications have the ability to quickly terminate threads that are executing I/O and any current I/O operations. This routine provides a way for user threads to block (that is, wait) in the kernel for I/O completion, dispatcher objects, or synchronization variables in a way that allows the wait to be readily canceled. This routine also permits the thread's wait to be terminated if the thread is terminated by a user or an application.

For example, a redirector may need to create one or more secondary I/O operations in order to process a user-mode I/O and synchronously wait for the secondary requests to complete. One way to do this is to set up an event that will be signaled by the completion routine of the secondary I/O operations and then wait for the event to be signaled. Then, to perform a cancelable wait operation, **FltCancellableWaitForMultipleObjects** is called passing in the events associated with the secondary I/O operations, and the original user-mode I/O operation. The thread's wait for the event to be signaled is canceled if a pending termination event occurs or if the original user-mode I/O operation is canceled.

Note that terminating the wait does not automatically cancel any I/O operation that was issued by the caller - that must be handled separately by the caller.

Each thread object has a built-in array of wait blocks that you can use to wait on several objects concurrently. Whenever possible, you should use the built-in array of wait blocks in a wait-multiple operation because no additional wait block storage needs to be allocated and later deallocated. However, if the number of objects that you must wait on concurrently is greater than the number of built-in wait blocks, use the **WaitBlockArray** parameter to specify an alternate set of wait blocks to be used in the wait operation. Drivers only need to allocate a sufficiently-large memory buffer for **WaitBlockArray**. You do not need to initialize the buffer, and the drivers can treat it as an opaque structure. You can free the buffer once the routine returns.

If either Count is greater than MAXIMUM_WAIT_OBJECTS or if **WaitBlockArray** is NULL and Count is greater than THREAD_WAIT_OBJECTS, the system issues <a href="/windows-hardware/drivers/debugger/bug-check-0xc--maximum-wait-objects-exceeded">Bug Check 0xC: MAXIMUM_WAIT_OBJECTS_EXCEEDED**]().

A special consideration applies when one or more of the elements in the **ObjectArray** parameter passed to **FltCancellableWaitForMultipleObjects** refers to a mutex. If the dispatcher object that is waited on is a mutex, APC delivery is the same as for all other dispatcher objects during the wait. However, once **FltCancellableWaitForMultipleObjects** returns with STATUS_SUCCESS and the thread actually holds the mutex, only special kernel-mode APCs are delivered. Delivery of all other APCs, both kernel-mode and user-mode, is disabled. This restriction on the delivery of APCs persists until the mutex is released.

A mutex can be recursively acquired only MINLONG times. If this limit is exceeded, the routine raises a STATUS_MUTANT_LIMIT_EXCEEDED exception. 

The **FltCancellableWaitForMultipleObjects** routine must be called at IRQL PASSIVE_LEVEL if the **CallbackData** parameter represents a valid filter manager IRP. Otherwise, the routine can be called at IRQL less or equal to APC_LEVEL. Normal kernel APCs can be disabled by the caller, if needed, by calling the <a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-keentercriticalregion">KeEnterCriticalRegion**]() or <a href="/windows-hardware/drivers/ifs/fsrtlenterfilesystem">FsRtlEnterFileSystem**]() routines. However, special kernel APCs must not be disabled. 

**FltCancellableWaitForMultipleObjects** will assert on debug builds if the **CallbackData** represents a Filter Manager IRP operation, but the IRP in the **CallbackData** structure is NULL.

## -see-also

<a href="/windows-hardware/drivers/ddi">ExInitializeFastMutex**](../wdm/nf-wdm-exinitializefastmutex.md)



<a href="/windows-hardware/drivers/ddi/fltkernel/">FltCancelIo**](nf-fltkernel-fltcancelio.md)



<a href="/windows-hardware/drivers/ddi/fltkernel/">FltCancellableWaitForSingleObject**](nf-fltkernel-fltcancellablewaitforsingleobject.md)



[**FltSetCancelCompletion**](nf-fltkernel-fltsetcancelcompletion.md)


<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlcancellablewaitformultipleobjects">FsRtlCancellableWaitForMultipleObjects**]()



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializeevent">KeInitializeEvent**]()



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializemutex">KeInitializeMutex**]()



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializesemaphore">KeInitializeSemaphore**]()



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializetimer">KeInitializeTimer**]()



**KeWaitForMultipleObjects**



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553344">KeWaitForMutexObject**]()



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-kewaitforsingleobject">KeWaitForSingleObject**]()
