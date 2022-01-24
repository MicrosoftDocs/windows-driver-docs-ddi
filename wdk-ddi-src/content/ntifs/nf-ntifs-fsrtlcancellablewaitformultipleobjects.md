---
UID: NF:ntifs.FsRtlCancellableWaitForMultipleObjects
title: FsRtlCancellableWaitForMultipleObjects function (ntifs.h)
description: The FsRtlCancellableWaitForMultipleObjects routine executes a cancelable wait operation (a wait that can be terminated) on one or more dispatcher objects.
old-location: ifsk\fsrtlcancellablewaitformultipleobjects.htm
tech.root: ifsk
ms.date: 12/16/2021
keywords: ["FsRtlCancellableWaitForMultipleObjects function"]
ms.keywords: FsRtlCancellableWaitForMultipleObjects, FsRtlCancellableWaitForMultipleObjects routine [Installable File System Drivers], fsrtlref_8a221e67-4344-401f-9e56-8fac66bb03b7.xml, ifsk.fsrtlcancellablewaitformultipleobjects, ntifs/FsRtlCancellableWaitForMultipleObjects
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Windows Vista
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
req.irql: See Remarks section.
targetos: Windows
req.typenames: 
f1_keywords:
 - FsRtlCancellableWaitForMultipleObjects
 - ntifs/FsRtlCancellableWaitForMultipleObjects
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlCancellableWaitForMultipleObjects
---

# FsRtlCancellableWaitForMultipleObjects function

## -description

The **FsRtlCancellableWaitForMultipleObjects** routine executes a cancelable wait operation (a wait that can be terminated) on one or more dispatcher objects.

## -parameters

### -param Count [in]

The number of objects to be waited on.

### -param ObjectArray [in]

A pointer to an array of pointers to dispatcher objects (events, mutexes, semaphores, threads, and timers) for which the caller supplies the storage.

### -param WaitType [in]

Either **WaitAll**, which indicates that all of the specified objects must attain a signaled state before the wait is satisfied; or **WaitAny**, which indicates that any one of the objects must attain a signaled state before the wait is satisfied.

### -param Timeout [in, optional]

A pointer to an optional time-out value. This parameter specifies the absolute or relative time, in 100 nanosecond units, at which the wait is to be completed.

If **Timeout** points to a zero value (that is, ***Timeout** == 0), the routine returns without waiting. If the caller supplies a NULL pointer (that is, **Timeout** == NULL), the routine waits indefinitely until any or all of the dispatcher objects are set to the signaled state.

A positive value specifies an absolute time, relative to January 1, 1601. A negative value specifies an interval relative to the current time. Absolute expiration times track any changes in the system time; relative expiration times are not affected by system time changes.

If **Timeout** is specified, the wait will be automatically satisfied if none of the specified wait conditions are met when the given interval expires.

A time-out value of zero (that is, ***Timeout** == 0) allows you to test a set of wait conditions, and to conditionally perform any additional actions if the wait can be immediately satisfied, as in the acquisition of a mutex.

### -param WaitBlockArray [in, optional]

If **Count** <= THREAD_WAIT_OBJECTS, **WaitBlockArray** can be NULL. Otherwise, this parameter must point to a memory buffer of ```sizeof(KWAIT_BLOCK * Count)``` bytes. The routine uses this buffer for record-keeping while performing the wait operation.

### -param Irp [in, optional]

A pointer to the original IRP that corresponds to the I/O operation that was issued by the user and that can be canceled by the user.  The caller must ensure that the IRP will remain valid for the duration of this routine and that the IRP must not have a cancel routine set (for example, [**IoSetCancelRoutine**](../wdm/nf-wdm-iosetcancelroutine.md) must not have been called on the IRP).  Note that the IRP must be held by the caller, it cannot be passed to a lower-level driver.

## -returns

**FsRtlCancellableWaitForMultipleObjects** can return one of the following values:

| Return code | Description |
| ----------- | ----------- |
| STATUS_SUCCESS  | The caller specified **WaitAll** for the **WaitType** parameter and all dispatcher objects in the **ObjectArray** array have been set to the signaled state. |
| STATUS_TIMEOUT  | A time-out occurred before the specified set of wait conditions was met. This value can be returned when the specified set of wait conditions cannot be immediately met and **Timeout** is set to zero. |
| STATUS_WAIT_0 through STATUS_WAIT_63 | The caller specified **WaitAny** for **WaitType** and one of the dispatcher objects in the **ObjectArray** array has been set to the signaled state.  The lower six bits of the return value encode the zero-based index of the object that satisfied the wait. |
| STATUS_ABANDONED_WAIT_0 through STATUS_ABANDONED_WAIT_63 | The caller attempted to wait for a mutex that has been abandoned.  The lower six bits of the return value encode the zero-based index of the mutex in the **ObjectArray** array. |
| STATUS_CANCELLED | The wait was interrupted by a pending cancel request on the specified IRP.  Note that this value is returned only if a valid IRP is passed to **FsRtlCancellableWaitForMultipleObjects** and the IRP was canceled by [**CancelSynchronousIo**](/windows/win32/api/ioapiset/nf-ioapiset-cancelsynchronousio). |
| STATUS_THREAD_IS_TERMINATING | The wait was interrupted because the thread has been terminated by an application or the user. |

The return value only indicates the status of the wait. If applicable, the actual status of the I/O request should be obtained directly from another IRP generated in the process of handling the original user-mode IRP.

Note that the NT_SUCCESS macro returns FALSE ("failure") for the STATUS_CANCELLED and STATUS_THREAD_IS_TERMINATING status values and TRUE ("success") for all other status values.

## -remarks

The **FsRtlCancellableWaitForMultipleObjects** routine executes a cancelable wait operation on dispatcher objects.  If the thread is terminated by the user or by the application, or if [**CancelSynchronousIo**](/windows/win32/api/ioapiset/nf-ioapiset-cancelsynchronousio) posts a cancel request on a threaded IRP (synchronous IRP) associated with the thread, the wait is canceled.

The **FsRtlCancellableWaitForMultipleObjects** routine was designed  for support of the [I/O Completion/Cancellation Guidelines](/windows/win32/fileio/canceling-pending-i-o-operations) starting with Windows Vista. The goal of these guidelines is to allow users (or applications) to quickly terminate applications.  This, in turn, requires that applications have the ability to quickly terminate threads that are executing I/O as well as any current I/O operations. This routine provides a way for user threads to block (that is, wait) in the kernel for I/O completion, dispatcher objects, or synchronization variables in a way that allows the wait to be readily canceled. This routine also permits the thread's wait to be terminated if the thread is terminated by a user or an application.

For example, a redirector may need to create one or more secondary IRPs in order to process a user-mode IRP and synchronously wait for the secondary IRPs to complete. One way to do this is to set up an event that will be signaled by the completion routine of the secondary IRP and then wait for the event to be signaled. Then, to perform a cancelable wait operation, **FsRtlCancellableWaitForMultipleObjects** is called passing in the event associated with the secondary IRP, as well as the original user-mode IRP.  The thread's wait for the event to be signaled is canceled if a pending termination event occurs or if the original user-mode IRP is canceled.

Note that terminating the wait does not automatically cancel any I/O operation that is issued by the caller - that must be handled separately by the caller.

Each thread object has a built-in array of wait blocks that can be used to wait on several objects concurrently. Whenever possible, the built-in array of wait blocks should be used in a wait-multiple operation because no additional wait block storage needs to be allocated and later deallocated. However, if the number of objects that must be waited on concurrently is greater than the number of built-in wait blocks, use the **WaitBlockArray** parameter to specify an alternate set of wait blocks to be used in the wait operation. Drivers only need to allocate a sufficiently-large memory buffer for **WaitBlockArray**. The buffer does not need to be initialized, and the drivers can treat it as an opaque structure. The buffer can be freed once the routine returns.

If either **Count** is greater than MAXIMUM_WAIT_OBJECTS or if **WaitBlockArray** is NULL and Count is greater than THREAD_WAIT_OBJECTS, the system issues [Bug Check 0xC: MAXIMUM_WAIT_OBJECTS_EXCEEDED](/windows-hardware/drivers/debugger/bug-check-0xc--maximum-wait-objects-exceeded).

A special consideration applies when the **ObjectArray** parameter passed to **FsRtlCancellableWaitForMultipleObjects** is a mutex. If the dispatcher object that is waited on is a mutex, APC delivery is the same as for all other dispatcher objects during the wait. However, once **FsRtlCancellableWaitForMultipleObjects** returns with STATUS_SUCCESS and the thread actually holds the mutex, only special kernel-mode APCs are delivered. Delivery of all other APCs, both kernel-mode and user-mode, is disabled. This restriction on the delivery of APCs persists until the mutex is released.

A mutex can be recursively acquired only MINLONG times.  If this limit is exceeded, the routine raises a STATUS_MUTANT_LIMIT_EXCEEDED exception.

**FsRtlCancellableWaitForMultipleObjects** must be called at IRQL PASSIVE_LEVEL if the optional **Irp** parameter points to a valid IRP. If the **Irp** parameter is not used, the routine can be called at IRQL less or equal to APC_LEVEL. Normal kernel APCs can be disabled by the caller, if needed, by calling the [**KeEnterCriticalRegion**](../ntddk/nf-ntddk-keentercriticalregion.md) or [**FsRtlEnterFileSystem**](/windows-hardware/drivers/ifs/fsrtlenterfilesystem) routines. However, special kernel APCs must not be disabled.

**FsRtlCancellableWaitForMultipleObjects** will assert on debug builds if the IRQL is greater or equal to APC_LEVEL and the **Irp** parameter points to a valid IRP.

## -see-also

[**ExInitializeFastMutex**](../wdm/nf-wdm-exinitializefastmutex.md)

[**FsRtlCancellableWaitForSingleObject**](nf-ntifs-fsrtlcancellablewaitforsingleobject.md)

[**KeInitializeEvent**](../wdm/nf-wdm-keinitializeevent.md)

[**KeInitializeMutex**](../wdm/nf-wdm-keinitializemutex.md)

[**KeInitializeSemaphore**](../wdm/nf-wdm-keinitializesemaphore.md)

[**KeInitializeTimer**](../wdm/nf-wdm-keinitializetimer.md)

[**KeWaitForMultipleObjects**](../wdm/nf-wdm-kewaitformultipleobjects.md)

[**KeWaitForSingleObject**](../wdm/nf-wdm-kewaitforsingleobject.md)

[**KeWaitForMutexObject**](../wdm/nf-wdm-kewaitforsingleobject.md)
