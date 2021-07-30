---
UID: NF:wdm.KeReleaseSemaphore
title: KeReleaseSemaphore function (wdm.h)
description: The KeReleaseSemaphore routine releases the specified semaphore object.
old-location: kernel\kereleasesemaphore.htm
tech.root: kernel
ms.date: 07/29/2021
keywords: ["KeReleaseSemaphore function"]
ms.keywords: KeReleaseSemaphore, KeReleaseSemaphore routine [Kernel-Mode Driver Architecture], k105_43c9caa4-267a-43c4-8b48-f030e1c2f0d5.xml, kernel.kereleasesemaphore, wdm/KeReleaseSemaphore
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: HwStorPortProhibitedDDIs
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
 - KeReleaseSemaphore
 - wdm/KeReleaseSemaphore
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - KeReleaseSemaphore
---

# KeReleaseSemaphore function

## -description

The **KeReleaseSemaphore** routine releases the specified semaphore object.

## -parameters

### -param Semaphore

[in, out] A pointer to an initialized semaphore object for which the caller provides the storage.

### -param Increment

[in] Specifies the priority increment to be applied if releasing the semaphore causes a wait to be satisfied.

### -param Adjustment

[in] Specifies a value to be added to the current semaphore count. This value must be positive.

### -param Wait

[in] Specifies whether the call to **KeReleaseSemaphore** is to be followed immediately by a call to one of the **KeWait*Xxx*** routines. If **TRUE**, the **KeReleaseSemaphore** call must be followed by a call to [KeWaitForMultipleObjects](/windows-hardware/drivers/ddi/wdm/nf-wdm-kewaitformultipleobjects), **KeWaitForMutexObject**, or [KeWaitForSingleObject](/windows-hardware/drivers/ddi/wdm/nf-wdm-kewaitforsingleobject). For more information, see the following Remarks section.

## -returns

If the return value is zero, the previous state of the semaphore object is not-signaled.

## -remarks

**KeReleaseSemaphore** supplies a run-time priority boost for waiting threads. If this call sets the semaphore to the signaled state, the semaphore count is augmented by the specified value. The caller can also specify whether it will call one of the **KeWait*Xxx*** routines as soon as **KeReleaseSemaphore** returns control.

Releasing a semaphore object causes the semaphore count to be augmented by the value of the *Adjustment* parameter. If the resulting value is greater than the limit of the semaphore object, the count is not adjusted and an exception, STATUS_SEMAPHORE_LIMIT_EXCEEDED, is raised.

Augmenting the semaphore object count causes the semaphore to attain a signaled state, and an attempt is made to satisfy as many waits as possible on the semaphore object.

The **KeReleaseSemaphore** routine might temporarily raise the IRQL. If the *Wait* parameter is **FALSE**, the routine, before it returns, restores the IRQL to the original value that it had at the start of the call.

If *Wait* = **TRUE**, the routine returns without lowering the IRQL. In this case, the **KeReleaseSemaphore** call must be immediately followed by a **KeWait*Xxx*** call. By setting *Wait* = **TRUE**, the caller can prevent an unnecessary context switch from occurring between the **KeReleaseSemaphore** call and the **KeWait*Xxx*** call. The **KeWait*Xxx*** routine, before it returns, restores the IRQL to its original value at the start of the **KeReleaseSemaphore** call. Although the IRQL disables context switches between the two calls, these calls cannot reliably be used as the start and end of an atomic operation. For example, between these two calls, a thread that is running at the same time on another processor might change the state of the semaphore object or of the target of the wait.

For more information about semaphore objects, see [Semaphore Objects](/windows-hardware/drivers/kernel/semaphore-objects).

Callers of **KeReleaseSemaphore** must be running at IRQL <= DISPATCH_LEVEL provided that *Wait* is set to **FALSE**. Otherwise, the caller must be running at IRQL = PASSIVE_LEVEL.

## -see-also

[KeInitializeSemaphore](/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializesemaphore)

[KeReadStateSemaphore](/windows-hardware/drivers/ddi/wdm/nf-wdm-kereadstatesemaphore)

[KeWaitForMultipleObjects](/windows-hardware/drivers/ddi/wdm/nf-wdm-kewaitformultipleobjects)

[KeWaitForSingleObject](/windows-hardware/drivers/ddi/wdm/nf-wdm-kewaitforsingleobject)
