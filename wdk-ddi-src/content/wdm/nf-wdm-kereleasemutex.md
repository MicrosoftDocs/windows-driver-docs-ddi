---
UID: NF:wdm.KeReleaseMutex
title: KeReleaseMutex function (wdm.h)
description: The KeReleaseMutex routine releases a mutex object, and specifies whether the caller is to call one of the KeWaitXxx routines as soon as KeReleaseMutex returns control.
old-location: kernel\kereleasemutex.htm
tech.root: kernel
ms.date: 07/29/2021
keywords: ["KeReleaseMutex function"]
ms.keywords: KeReleaseMutex, KeReleaseMutex routine [Kernel-Mode Driver Architecture], k105_4237a9e6-715b-4e40-aab8-9b1458a220ae.xml, kernel.kereleasemutex, wdm/KeReleaseMutex
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlKeDispatchLte, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - KeReleaseMutex
 - wdm/KeReleaseMutex
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - KeReleaseMutex
---

# KeReleaseMutex function

## -description

The **KeReleaseMutex** routine releases a mutex object, and specifies whether the caller is to call one of the **KeWait*Xxx*** routines as soon as **KeReleaseMutex** returns control.

## -parameters

### -param Mutex

[in, out] A pointer to an initialized mutex object for which the caller provides the storage.

### -param Wait

[in] Specifies whether the call to **KeReleaseMutex** is to be immediately followed by a call to one of the **KeWait*Xxx*** routines. If **TRUE**, the **KeReleaseMutex** call must be followed by a call to [KeWaitForMultipleObjects](./nf-wdm-kewaitformultipleobjects.md), **KeWaitForMutexObject**, or [KeWaitForSingleObject](./nf-wdm-kewaitforsingleobject.md). For more information, see the following Remarks section.

## -returns

If the return value is zero, the mutex object was released and attained a state of *signaled*.

## -remarks

For better performance, use fast mutexes or guarded mutexes. For more information, see [Alternatives to Mutex Objects](/windows-hardware/drivers/kernel/alternatives-to-mutex-objects).

If the mutex object attains a signaled state, an attempt is made to satisfy a wait for the mutex object.

A mutex object can be released only by the thread that currently holds the mutex. If an attempt is made to release a mutex that the thread does not hold or if a mutex was acquired at IRQL = DISPATCH_LEVEL and the thread is not running at DISPATCH_LEVEL (and vice versa), the routine raises a STATUS_ABANDONED or STATUS_MUTEX_NOT_OWNED exception.

When a mutex object attains a signaled state, it is removed from the list of the mutexes that are held by that thread. If this list contains no more entries, the original priority for the thread is restored.

The **KeReleaseMutex** routine might temporarily raise the IRQL. If the *Wait* parameter is **FALSE**, the routine, before it returns, restores the IRQL to the original value that it had at the start of the call.

If *Wait* = **TRUE**, the routine returns without lowering the IRQL. In this case, the **KeReleaseMutex** call must be immediately followed by a **KeWait*Xxx*** call. By setting *Wait* = **TRUE**, the caller can prevent an unnecessary context switch from occurring between the **KeReleaseMutex** call and the **KeWait*Xxx*** call. The **KeWait*Xxx*** routine, before it returns, restores the IRQL to its original value at the start of the **KeReleaseMutex** call. Although the IRQL disables context switches between the two calls, these calls cannot reliably be used as the start and end of an atomic operation. For example, between these two calls, a thread that is running at the same time on another processor might change the state of the event object or of the target of the wait.

If the caller is executing at IRQL = DISPATCH_LEVEL or in an arbitrary thread context, the *Timeout* parameter to **KeWait*Xxx*** must be zero.

If a mutex is acquired recursively, the holding thread must call **KeReleaseMutex** as many times as it acquired the mutex to set it to the signaled state.

For more information about mutex objects, see [Mutex Objects](/windows-hardware/drivers/kernel/mutex-objects).

## -see-also

[ExReleaseFastMutex](/previous-versions/windows/hardware/drivers/ff545549(v=vs.85))

[ExReleaseFastMutexUnsafe](/previous-versions/windows/hardware/drivers/ff545567(v=vs.85))

[KeInitializeMutex](./nf-wdm-keinitializemutex.md)

[KeReadStateMutex](./nf-wdm-kereadstatemutex.md)

[KeWaitForMultipleObjects](./nf-wdm-kewaitformultipleobjects.md)

[KeWaitForSingleObject](./nf-wdm-kewaitforsingleobject.md)
