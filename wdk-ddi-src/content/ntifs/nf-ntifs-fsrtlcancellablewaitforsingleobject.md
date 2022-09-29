---
UID: NF:ntifs.FsRtlCancellableWaitForSingleObject
title: FsRtlCancellableWaitForSingleObject function (ntifs.h)
description: The FsRtlCancellableWaitForSingleObject routine executes a cancelable wait operation (a wait that can be terminated) on a dispatcher object.
old-location: ifsk\fsrtlcancellablewaitforsingleobject.htm
tech.root: ifsk
ms.date: 12/16/2021
keywords: ["FsRtlCancellableWaitForSingleObject function"]
ms.keywords: FsRtlCancellableWaitForSingleObject, FsRtlCancellableWaitForSingleObject routine [Installable File System Drivers], fsrtlref_5515496d-6e38-488c-8fbf-439aa4ac555a.xml, ifsk.fsrtlcancellablewaitforsingleobject, ntifs/FsRtlCancellableWaitForSingleObject
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
 - FsRtlCancellableWaitForSingleObject
 - ntifs/FsRtlCancellableWaitForSingleObject
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlCancellableWaitForSingleObject
---

# FsRtlCancellableWaitForSingleObject function

## -description

The **FsRtlCancellableWaitForSingleObject** routine executes a cancelable wait operation (a wait that can be terminated) on a dispatcher object.

## -parameters

### -param Object [in]

A pointer to an initialized dispatcher object (event, mutex, semaphore, thread, or timer) for which the caller supplies the storage.

### -param Timeout [in, optional]

A pointer to an optional time-out value. This parameter specifies the absolute or relative time, in 100 nanosecond units, at which the wait is to be completed.

If **Timeout** points to a zero value (that is, ***Timeout** == 0), the routine returns without waiting. If the caller supplies a NULL pointer (that is, **Timeout** == NULL), the routine waits indefinitely until the object is set to the signaled state.

A positive **Timeout** value specifies an absolute time, relative to January 1, 1601. A negative **Timeout** value specifies an interval relative to the current time. Absolute expiration times track any changes in the system time. Relative expiration times are not affected by system time changes.

If **Timeout** is specified, the wait will be automatically satisfied if the object is not set to the signaled state when the given interval expires.

A time-out value of zero (that is, ***Timeout** == 0) allows you to test a set of wait conditions, and to conditionally perform any additional actions if the wait can be immediately satisfied, as in the acquisition of a mutex.

### -param Irp [in, optional]

A pointer to the original IRP that corresponds to the I/O operation that was issued by the user and that can be canceled by the user.  The caller must ensure that the IRP will remain valid for the duration of this routine and that the IRP must not have a cancel routine set (for example, [**IoSetCancelRoutine**](../wdm/nf-wdm-iosetcancelroutine.md) must not have been called on the IRP).  Note that the IRP must be held by the caller, it cannot be passed to a lower-level driver.

## -returns

**FsRtlCancellableWaitForSingleObject** can return one of the following values:

| Return code | Description |
| ----------- | ----------- |
| STATUS_SUCCESS  | The dispatcher object that is specified by the **Object** parameter satisfied the wait. |
| STATUS_TIMEOUT  | A time-out occurred before the object was set to a signaled state. This value can be returned when the specified set of wait conditions cannot be immediately met and **Timeout** is set to zero. |
| STATUS_ABANDONED_WAIT_0 | The caller attempted to wait for a mutex that has been abandoned. |
| STATUS_CANCELLED | The wait was interrupted by a pending cancel request on the specified IRP.  Note that this value is returned only if a valid IRP is passed to **FsRtlCancellableWaitForSingleObject** and the IRP was canceled by [**CancelSynchronousIo**](/windows/win32/api/ioapiset/nf-ioapiset-cancelsynchronousio). |
| STATUS_THREAD_IS_TERMINATING | The wait was interrupted as the thread has been terminated by an application or the user. |

The return value only indicates the status of the wait. If applicable, the actual status of the I/O request should be obtained directly from another IRP generated in the process of handling the original user-mode IRP.

Note that the NT_SUCCESS macro returns FALSE ("failure") for the STATUS_CANCELLED and STATUS_THREAD_IS_TERMINATING status values and TRUE ("success") for all other status values.

## -remarks

The **FsRtlCancellableWaitForSingleObject** routine executes a cancelable wait operation on a dispatcher object.  If the thread is terminated by the user or by the application, or if [**CancelSynchronousIo**](/windows/win32/api/ioapiset/nf-ioapiset-cancelsynchronousio) posts a cancel request on a threaded IRP (synchronous IRP) associated with the thread, the wait is canceled.

The **FsRtlCancellableWaitForSingleObject** routine was designed for support of the [I/O Completion/Cancellation Guidelines](/windows/win32/fileio/canceling-pending-i-o-operations) starting with Windows Vista. The goal of these guidelines is to allow users (or applications) to quickly terminate applications.  This, in turn, requires that applications have the ability to quickly terminate threads that are executing I/O as well as any current I/O operations. This routine provides a way for user threads to block (that is, wait) in the kernel for I/O completion, a dispatcher object, or a synchronization variable in a way that allows the wait to be readily canceled. This routine also permits the thread's wait to be terminated if the thread is terminated by a user or an application.

For example, a redirector may need to create one or more secondary IRPs in order to process a user-mode IRP and synchronously wait for the secondary IRPs to complete. One way to do this is to set up an event that will be signaled by the completion routine of the secondary IRP and then wait for the event to be signaled. Then, to perform a cancelable wait operation, **FsRtlCancellableWaitForSingleObject** is called passing in the event associated with the secondary IRP, as well as the original user-mode IRP.  The thread's wait for the event to be signaled is canceled if a pending termination event occurs or if the original user-mode IRP is canceled.

Note that terminating the wait does not automatically cancel any I/O operation that is issued by the caller - that must be handled separately by the caller.

A special consideration applies when the **Object** parameter passed to **FsRtlCancellableWaitForSingleObject** is a mutex. If the dispatcher object that is waited on is a mutex, APC delivery is the same as for all other dispatcher objects during the wait. However, once **FsRtlCancellableWaitForSingleObjects** returns with STATUS_SUCCESS and the thread actually holds the mutex, only special kernel-mode APCs are delivered. Delivery of all other APCs, both kernel-mode and user-mode, is disabled. This restriction on the delivery of APCs persists until the mutex is released.

A mutex can be recursively acquired only MINLONG times.  If this limit is exceeded, the routine raises a STATUS_MUTANT_LIMIT_EXCEEDED exception.

The following is an example of how to use **FsRtlCancellableWaitForSingleObject** in support of the [I/O Completion/Cancellation Guidelines](/windows/win32/fileio/canceling-pending-i-o-operations).

``` C
//
// sample calling routine
//
NTSTATUS ProcessIrpFromUserMode( PIRP pOriginalIrp, ... )
{
NTSTATUS  Status;
NTSTATUS  WaitStatus;
KEVENT   Event;
LARGE_INTEGERTimeout;
PIRP   pAdditionalIrp;
BOOLEAN  Cancelled;

 //
 // Allocate the additional IRP here:
 //
KeInitializeEvent( &Event,
            SynchronizationEvent,
    FALSE );
pContext->pEvent = &Event; // Driver specific context structure.
 IoSetCompletionRoutine( pAdditionalIrp,
 FunctionCompletionRoutine,
 pContext,
 TRUE,
 TRUE,
 TRUE);
 Status = IoCallDriver( pDeviceObject, pAdditionalIrp );
  if (Status == STATUS_PENDING) {
   //
   // Initialize Timeout variable here. If no timeout is needed, pass NULL for 
   // that parameter instead.
   //
  WaitStatus = FsRtlCancellableWaitForSingleObject( &Event, 
          &Timeout,
               pOriginalIrp );
   if ((WaitStatus == STATUS_CANCELLED) || (WaitStatus == STATUS_THREAD_IS_TERMINATING)) {
    //
    // Thread is terminating. IRP was canceled.       
    // Cancel the additional IRP passed to the lower level driver, cleanup, and return quickly.
    //
   Cancelled = IoCancelIrp( pAdditionalIrp );
    if (!Cancelled || KeReadStateEvent( &Event ) == 0) {
     //
     //  Wait for the IRP to complete. 
     // If cancel was posted successfully on the IRP, this shouldn't take a long time.
     //
    (VOID) KeWaitForSingleObject( &Event,
             Executive,
             KernelMode,        // WaitMode
             FALSE,             // Alertable
             (PLARGE_INTEGER) NULL );
   }
  } else if (WaitStatus == STATUS_TIMEOUT) {
    //
    // Wait timed out. The IRP was canceled or the API 
    // waited for the I/O to complete.
    // 
  } else {
   ASSERT( WaitStatus == STATUS_SUCCESS );
    //
    // The wait completed without timeout
    // or being canceled.
    //
  }
}
 //
 // IRP is valid and needs to be handled here.
 // pAdditionalIrp->IoStatus.Status contains the status of the IRP.
 // Finally, pOriginal IRP needs to be completed appropriately as well.
 //
}

//
// Sample completion routine:
//
NTSTATUS
FunctionCompletionRoutine(
  IN PDEVICE_OBJECT  pDeviceObject,
  INOUT PIRP  pAdditionalIrp,
  IN PVOID  pContext)
{
 if (pAdditionalIrp->PendingReturned) {
 KeSetEvent( pContext->pEvent, 0, FALSE );
}

 //
 // Discontinue I/O completion.
 // Dispatch routine will deal with IRP.
 //
 return STATUS_MORE_PROCESSING_REQUIRED;
}
```

**FsRtlCancellableWaitForSingleObject** must be called at IRQL PASSIVE_LEVEL if the optional **Irp** parameter points to a valid IRP. If the **Irp** parameter is not used, the routine can be called at IRQL less or equal to APC_LEVEL. Normal kernel APCs can be disabled by the caller, if needed, by calling the [**KeEnterCriticalRegion**](../ntddk/nf-ntddk-keentercriticalregion.md) or [**FsRtlEnterFileSystem**](/windows-hardware/drivers/ifs/fsrtlenterfilesystem) routines. However, special kernel APCs must not be disabled.

**FsRtlCancellableWaitForSingleObject** will assert on debug builds if the IRQL is greater or equal to APC_LEVEL and the optional **Irp** parameter points to a valid IRP.

## -see-also

[**ExInitializeFastMutex**](../wdm/nf-wdm-exinitializefastmutex.md)

[**FsRtlCancellableWaitForMultipleObjects**](nf-ntifs-fsrtlcancellablewaitformultipleobjects.md)

[**KeInitializeEvent**](../wdm/nf-wdm-keinitializeevent.md)

[**KeInitializeMutex**](../wdm/nf-wdm-keinitializemutex.md)

[**KeInitializeSemaphore**](../wdm/nf-wdm-keinitializesemaphore.md)

[**KeInitializeTimer**](../wdm/nf-wdm-keinitializetimer.md)

[**KeWaitForMultipleObjects**](../wdm/nf-wdm-kewaitformultipleobjects.md)

[**KeWaitForSingleObject**](../wdm/nf-wdm-kewaitforsingleobject.md)
