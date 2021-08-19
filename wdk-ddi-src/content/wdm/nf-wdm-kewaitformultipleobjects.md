---
UID: NF:wdm.KeWaitForMultipleObjects
title: KeWaitForMultipleObjects function (wdm.h)
description: The KeWaitForMultipleObjects routine puts the current thread into an alertable or nonalertable wait state until any or all of a number of dispatcher objects are set to a signaled state or (optionally) until the wait times out.
old-location: kernel\kewaitformultipleobjects.htm
tech.root: kernel
ms.date: 07/29/2021
keywords: ["KeWaitForMultipleObjects function"]
ms.keywords: KeWaitForMultipleObjects, KeWaitForMultipleObjects routine [Kernel-Mode Driver Architecture], k105_03342f87-b6a7-4e26-a7e8-5a8157026c4a.xml, kernel.kewaitformultipleobjects, wdm/KeWaitForMultipleObjects
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
targetos: Windows
req.typenames: 
f1_keywords:
 - KeWaitForMultipleObjects
 - wdm/KeWaitForMultipleObjects
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - KeWaitForMultipleObjects
---

# KeWaitForMultipleObjects function

## -description

The **KeWaitForMultipleObjects** routine puts the current thread into an alertable or nonalertable wait state until any or all of a number of dispatcher objects are set to a signaled state or (optionally) until the wait times out.

## -parameters

### -param Count

[in] The number of objects to be waited on. This parameter specifies the number of elements in the array pointed to by the *Object* parameter.

### -param Object

[in] A pointer to an array of pointers to dispatcher objects (events, mutexes, semaphores, threads, and timers) for which the caller supplies the storage. Both the pointer array and the dispatcher objects must reside in nonpaged system memory. For more information, see Remarks.

### -param WaitType

[in] The type of wait operation to perform. Specify either **WaitAll**, indicating that all of the specified objects must attain a signaled state before the wait is satisfied; or **WaitAny**, indicating that any one of the objects must attain a signaled state before the wait is satisfied.

### -param WaitReason

[in] The reason for the wait. Drivers should set this value to **Executive** or, if the driver is doing work on behalf of a user and is running in the context of a user thread, to **UserRequest**.

### -param WaitMode

[in] Whether the caller waits in **KernelMode** or **UserMode**. Intermediate and lowest-level drivers should specify **KernelMode**. If the set of objects waited on includes a mutex, the caller must specify **KernelMode**.

### -param Alertable

[in] A Boolean value that indicates whether the thread can be alerted while it is in the waiting state.

### -param Timeout

[in, optional] A pointer to a time-out value that specifies the absolute or relative time, in 100-nanosecond units, at which the wait is to be completed.

A positive value specifies an absolute time, relative to January 1, 1601. A negative value specifies an interval relative to the current time. Absolute expiration times track any changes in the system time; relative expiration times are not affected by system time changes.

If **Timeout* = 0, the routine returns without waiting. If the caller supplies a **NULL** pointer, the routine waits indefinitely until any or all of the dispatcher objects are set to the signaled state. For more information, see the following Remarks section.

### -param WaitBlockArray

[out, optional] A pointer to a caller-allocated **KWAIT_BLOCK** array. If *Count* <= THREAD_WAIT_OBJECTS, then *WaitBlockArray* can be **NULL**. Otherwise, this parameter must point to a memory buffer of **sizeof**(**KWAIT_BLOCK**) \* *Count* bytes. The routine uses this buffer for record-keeping while performing the wait operation. The *WaitBlockArray* buffer must reside in nonpaged system memory. For more information, see Remarks.

## -returns

**KeWaitForMultipleObjects** can return one of the following:

| Return code | Description |
|--|--|
| **STATUS_SUCCESS** | The caller specified **WaitAll** for the _WaitType_ parameter and all dispatcher objects in the _Object_ array have been set to the signaled state. |
| **STATUS_ALERTED** | The wait was interrupted to deliver an alert to the calling thread. |
| **STATUS_USER_APC** | The wait was interrupted to deliver a user asynchronous procedure call (APC) to the calling thread. |
| **STATUS_TIMEOUT** | A time-out occurred before the specified set of wait conditions was met. This value can be returned when an explicit time-out value of zero is specified, but the specified set of wait conditions cannot be met immediately. |
| **STATUS_WAIT_0** through **STATUS_WAIT_63** | The caller specified **WaitAny** for _WaitType_ and one of the dispatcher objects in the _Object_ array has been set to the signaled state. The lower six bits of the return value encode the zero-based index of the object that satisfied the wait. |
| **STATUS_ABANDONED_WAIT_0** through **STATUS_ABANDONED_WAIT_63** | The caller attempted to wait for a mutex that has been abandoned. The lower six bits of the return value encode the zero-based index of the mutex in the _Object_ array. |

Note that the NT_SUCCESS macro recognizes all of these status values as "success" values.

## -syntax

```cpp
NTSTATUS
KeWaitForMultipleObjects (
    ULONG Count,
    PVOID Object[],
    WaitType,
    KWAIT_REASON WaitReason,
    KPROCESSOR_MODE WaitMode,
    BOOLEAN Alertable,
    PLARGE_INTEGER Timeout,
    PKWAIT_BLOCK WaitBlockArray
    );
```

## -remarks

Each thread object has a built-in array of wait blocks that can be used to wait for several objects to be set concurrently. Whenever possible, the built-in array of wait blocks should be used in a wait-multiple operation because no additional wait block storage needs to be allocated and later deallocated. However, if the number of objects that must be waited on concurrently is greater than the number of built-in wait blocks, use the *WaitBlockArray* parameter to specify an alternate set of wait blocks to be used in the wait operation. Drivers only need to allocate a sufficiently large memory buffer for *WaitBlockArray*. The buffer does not need to be initialized; however, it must be allocated from nonpaged system memory. If the *WaitMode* parameter is **UserMode**, the *WaitBlockArray* buffer must not be allocated on the local stack because the stack might be swapped out of memory. Drivers can treat this buffer as an opaque structure and can free it after the routine returns. If either *Count* > MAXIMUM_WAIT_OBJECTS or if *WaitBlockArray* is **NULL** and *Count* > THREAD_WAIT_OBJECTS, the system issues [Bug Check 0xC (MAXIMUM_WAIT_OBJECTS_EXCEEDED)](/windows-hardware/drivers/debugger/bug-check-0xc--maximum-wait-objects-exceeded).

The current state for each of the specified objects is examined to determine whether the wait can be satisfied immediately. If the necessary side effects are performed on the objects, an appropriate value is returned.

If the wait cannot be satisfied immediately and either no time-out value or a nonzero time-out value has been specified, the current thread is put in a waiting state and a new thread is selected for execution on the current processor. If no *Timeout* is supplied, the calling thread will remain in a wait state until the conditions specified by *Object* and *WaitType* are satisfied.

If *Timeout* is specified, the wait will be automatically satisfied if none of the specified wait conditions is met when the given interval expires.

A time-out value of zero allows the testing of a set of wait conditions, conditionally performing any side effects if the wait can be immediately satisfied, as in the acquisition of a mutex.

Time-out intervals are measured relative to the system clock, and the accuracy with which the operating system can detect the end of a time-out interval is limited by the granularity of the system clock. For more information, see [Timer Accuracy](/windows-hardware/drivers/kernel/timer-accuracy).

The *Alertable* parameter determines when the thread can be alerted and its wait state consequently aborted. For additional information, see [Waits and APCs](/windows-hardware/drivers/kernel/waits-and-apcs).

The array pointed to by the *Objects* parameter must reside in nonpaged system memory. Typically, a driver allocates the storage for the *Objects* array on the local stack. The *Objects* array can be allocated on the local stack regardless of the value of the *WaitMode* parameter.

The dispatcher objects pointed to by the elements in the *Objects* array must reside in nonpaged system memory. If the *WaitMode* parameter is **UserMode**, the kernel stack can be swapped out during the wait. Consequently, a caller must never attempt to pass parameters on the stack when calling **KeWaitForMultipleObjects** with the **UserMode** argument. If you allocate the event on the stack, you must set the *WaitMode* parameter to **KernelMode**.

A special consideration applies when the *Object* parameter passed to **KeWaitForMultipleObjects** is a mutex. If the dispatcher object waited on is a mutex, APC delivery is the same as for all other dispatcher objects during the wait. However, after **KeWaitForMultipleObjects** returns with STATUS_SUCCESS and the thread actually holds the mutex, only special kernel-mode APCs are delivered. Delivery of all other APCs, both kernel-mode and user-mode, is disabled. This restriction on the delivery of APCs persists until the mutex is released.

It is especially important to check the return value of **KeWaitForMultipleObjects** when the *WaitMode* parameter is **UserMode** or *Alertable* is **TRUE**, because **KeWaitForMultipleObjects** might return early with a status of STATUS_USER_APC or STATUS_ALERTED.

All long term waits that can be aborted by a user should be **UserMode** waits and *Alertable* should be set to **FALSE**.

Where possible, *Alertable* should be set to **FALSE** and *WaitMode* should be set to **KernelMode**, in order to reduce driver complexity. The principal exception to this is when the wait is a long-term wait.

A mutex can be recursively acquired only MINLONG times. If this limit is exceeded, the routine raises a STATUS_MUTANT_LIMIT_EXCEEDED exception.

Callers of **KeWaitForMultipleObjects** can be running at IRQL <= DISPATCH_LEVEL. However, if *Timeout* = **NULL** or **Timeout* != 0, the caller must be running at IRQL <= APC_LEVEL and in a nonarbitrary thread context. (If *Timeout* != **NULL** and **Timeout* = 0, the caller must be running at IRQL <= DISPATCH_LEVEL.)

## -see-also

[ExInitializeFastMutex](./nf-wdm-exinitializefastmutex.md)

[KeInitializeEvent](./nf-wdm-keinitializeevent.md)

[KeInitializeMutex](./nf-wdm-keinitializemutex.md)

[KeInitializeSemaphore](./nf-wdm-keinitializesemaphore.md)

[KeInitializeTimer](./nf-wdm-keinitializetimer.md)

[KeWaitForSingleObject](./nf-wdm-kewaitforsingleobject.md)