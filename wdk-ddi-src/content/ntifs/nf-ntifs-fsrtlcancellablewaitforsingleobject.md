---
UID: NF:ntifs.FsRtlCancellableWaitForSingleObject
title: FsRtlCancellableWaitForSingleObject function
author: windows-driver-content
description: The FsRtlCancellableWaitForSingleObject routine executes a cancelable wait operation (a wait that can be terminated) on a dispatcher object.
old-location: ifsk\fsrtlcancellablewaitforsingleobject.htm
old-project: ifsk
ms.assetid: b29d35bd-d27d-4507-9fa7-5648bcb1f825
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FsRtlCancellableWaitForSingleObject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available starting with Windows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FsRtlCancellableWaitForSingleObject
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: See Remarks section.
req.typenames: TOKEN_TYPE
---

# FsRtlCancellableWaitForSingleObject function



## -description
The <b>FsRtlCancellableWaitForSingleObject</b> routine executes a cancelable wait operation (a wait that can be terminated) on a dispatcher object.



## -syntax

````
NTSTATUS FsRtlCancellableWaitForSingleObject(
  _In_     PVOID          Object,
  _In_opt_ PLARGE_INTEGER Timeout,
  _In_opt_ PIRP           Irp
);
````


## -parameters

### -param Object [in]

A pointer to an initialized dispatcher object (event, mutex, semaphore, thread, or timer) for which the caller supplies the storage.


### -param Timeout [in, optional]

A pointer to an optional time-out value. This parameter specifies the absolute or relative time, in 100 nanosecond units, at which the wait is to be completed. 

If <i>Timeout</i> points to a zero value (that is, <i>*Timeout</i> == 0), the routine returns without waiting. If the caller supplies a <b>NULL</b> pointer (that is, <i>Timeout</i> == <b>NULL</b>), the routine waits indefinitely until the object is set to the signaled state. 

A positive <i>Timeout</i> value specifies an absolute time, relative to January 1, 1601. A negative <i>Timeout</i> value specifies an interval relative to the current time. Absolute expiration times track any changes in the system time. Relative expiration times are not affected by system time changes.

If <i>Timeout</i> is specified, the wait will be automatically satisfied if the object is not set to the signaled state when the given interval expires.

A time-out value of zero (that is, <i>*Timeout</i> == 0) allows you to test a set of wait conditions, and to conditionally perform any additional actions if the wait can be immediately satisfied, as in the acquisition of a mutex.


### -param Irp [in, optional]

A pointer to the original IRP that corresponds to the I/O operation that was issued by the user and that can be canceled by the user.  The caller must ensure that the IRP will remain valid for the duration of this routine and that the IRP must not have a cancel routine set (for example, <a href="..\wdm\nf-wdm-iosetcancelroutine.md">IoSetCancelRoutine</a> must not have been called on the IRP).  Note that the IRP must be held by the caller, it cannot be passed to a lower-level driver.


## -returns
<b>FsRtlCancellableWaitForSingleObject</b> can return one of the following values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The dispatcher object that is specified by the <i>Object</i> parameter satisfied the wait.
<dl>
<dt><b>STATUS_TIMEOUT</b></dt>
</dl>A time-out occurred before the object was set to a signaled state. This value can be returned when the specified set of wait conditions cannot be immediately met and <i>Timeout</i> is set to zero.
<dl>
<dt><b>STATUS_ABANDONED_WAIT_0</b></dt>
</dl>The caller attempted to wait for a mutex that has been abandoned.
<dl>
<dt><b>STATUS_CANCELLED</b></dt>
</dl>The wait was interrupted by a pending cancel request on the specified IRP.  Note that this value is returned only if a valid IRP is passed to <b>FsRtlCancellableWaitForSingleObject</b> and the IRP was canceled by <a href="http://go.microsoft.com/fwlink/p/?linkid=64526">CancelSynchronousIo</a>.
<dl>
<dt><b>STATUS_THREAD_IS_TERMINATING</b></dt>
</dl>The wait was interrupted as the thread has been terminated by an application or the user.

 

The return value only indicates the status of the wait. If applicable, the actual status of the I/O request should be obtained directly from another IRP generated in the process of handling the original user-mode IRP.

Note that the NT_SUCCESS macro returns <b>FALSE</b> ("failure") for the STATUS_CANCELLED and STATUS_THREAD_IS_TERMINATING status values and <b>TRUE</b> ("success") for all other status values.


## -remarks
The <b>FsRtlCancellableWaitForSingleObject</b> routine executes a cancelable wait operation on a dispatcher object.  If the thread is terminated by the user or by the application, or if <a href="http://go.microsoft.com/fwlink/p/?linkid=64526">CancelSynchronousIo</a> posts a cancel request on a threaded IRP (synchronous IRP) associated with the thread, the wait is canceled.

The <b>FsRtlCancellableWaitForSingleObject</b> routine was designed for support of the <a href="http://go.microsoft.com/fwlink/p/?linkid=51436">I/O Completion/Cancellation Guidelines</a> starting with Windows Vista. The goal of these guidelines is to allow users (or applications) to quickly terminate applications.  This, in turn, requires that applications have the ability to quickly terminate threads that are executing I/O as well as any current I/O operations. This routine provides a way for user threads to block (that is, wait) in the kernel for I/O completion, a dispatcher object, or a synchronization variable in a way that allows the wait to be readily canceled. This routine also permits the thread's wait to be terminated if the thread is terminated by a user or an application.

For example, a redirector may need to create one or more secondary IRPs in order to process a user-mode IRP and synchronously wait for the secondary IRPs to complete. One way to do this is to set up an event that will be signaled by the completion routine of the secondary IRP and then wait for the event to be signaled. Then, to perform a cancelable wait operation, <b>FsRtlCancellableWaitForSingleObject</b> is called passing in the event associated with the secondary IRP, as well as the original user-mode IRP.  The thread's wait for the event to be signaled is canceled if a pending termination event occurs or if the original user-mode IRP is canceled.

Note that terminating the wait does not automatically cancel any I/O operation that is issued by the caller - that must be handled separately by the caller.

A special consideration applies when the <i>Object</i> parameter passed to <b>FsRtlCancellableWaitForSingleObject</b> is a mutex. If the dispatcher object that is waited on is a mutex, APC delivery is the same as for all other dispatcher objects during the wait. However, once <b>FsRtlCancellableWaitForSingleObjects</b> returns with STATUS_SUCCESS and the thread actually holds the mutex, only special kernel-mode APCs are delivered. Delivery of all other APCs, both kernel-mode and user-mode, is disabled. This restriction on the delivery of APCs persists until the mutex is released.

A mutex can be recursively acquired only MINLONG times.  If this limit is exceeded, the routine raises a STATUS_MUTANT_LIMIT_EXCEEDED exception.

The following is an example of how to use <b>FsRtlCancellableWaitForSingleObject </b>in support of the <a href="http://go.microsoft.com/fwlink/p/?linkid=51436">I/O Completion/Cancellation Guidelines</a>.

<b>FsRtlCancellableWaitForSingleObject</b> must be called at IRQL PASSIVE_LEVEL if the optional <i>Irp</i> parameter points to a valid IRP. If the <i>Irp</i> parameter is not used, the routine can be called at IRQL less or equal to APC_LEVEL. Normal kernel APCs can be disabled by the caller, if needed, by calling the <a href="..\ntddk\nf-ntddk-keentercriticalregion.md">KeEnterCriticalRegion</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff545900">FsRtlEnterFileSystem</a> routines. However, special kernel APCs must not be disabled. 

<b>FsRtlCancellableWaitForSingleObject</b> will assert on debug builds if the IRQL is greater or equal to APC_LEVEL and the optional <i>Irp</i> parameter points to a valid IRP.


## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-exinitializefastmutex.md">ExInitializeFastMutex</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-fsrtlcancellablewaitformultipleobjects.md">FsRtlCancellableWaitForMultipleObjects</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-keinitializeevent.md">KeInitializeEvent</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-keinitializemutex.md">KeInitializeMutex</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-keinitializesemaphore.md">KeInitializeSemaphore</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-keinitializetimer.md">KeInitializeTimer</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-kewaitformultipleobjects.md">KeWaitForMultipleObjects</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553344">KeWaitForMutexObject</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-kewaitforsingleobject.md">KeWaitForSingleObject</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlCancellableWaitForSingleObject routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

