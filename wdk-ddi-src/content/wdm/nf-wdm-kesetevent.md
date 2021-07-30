---
UID: NF:wdm.KeSetEvent
title: KeSetEvent function (wdm.h)
description: The KeSetEvent routine sets an event object to a signaled state if the event was not already signaled, and returns the previous state of the event object.
old-location: kernel\kesetevent.htm
tech.root: kernel
ms.date: 07/29/2021
keywords: ["KeSetEvent function"]
ms.keywords: KeSetEvent, KeSetEvent routine [Kernel-Mode Driver Architecture], k105_0b9a87b5-bdf2-4449-81f6-1836ea47f038.xml, kernel.kesetevent, wdm/KeSetEvent
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: CompletionEventChecking, IoAllocateIrpSignalEventInCompletion, IoBuildDeviceIoControlSetEvent, IoBuildFsdIrpSignalEventInCompletion, IrqlKeSetEvent, SignalEventInCompletion, DoubleKeSetEvent, HwStorPortProhibitedDDIs
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
 - KeSetEvent
 - wdm/KeSetEvent
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - KeSetEvent
---

# KeSetEvent function

## -description

The **KeSetEvent** routine sets an event object to a signaled state if the event was not already signaled, and returns the previous state of the event object.

## -parameters

### -param Event

[in, out] A pointer to an initialized event object for which the caller provides the storage.

### -param Increment

[in] Specifies the priority increment to be applied if setting the event causes a wait to be satisfied.

### -param Wait

[in] Specifies whether the call to **KeSetEvent** is to be followed immediately by a call to one of the **KeWait*Xxx*** routines. If **TRUE**, the **KeSetEvent** call must be followed by a call to [KeWaitForMultipleObjects](/windows-hardware/drivers/ddi/wdm/nf-wdm-kewaitformultipleobjects), **KeWaitForMutexObject**, or [KeWaitForSingleObject](/windows-hardware/drivers/ddi/wdm/nf-wdm-kewaitforsingleobject). For more information, see the following Remarks section.

## -returns

If the previous state of the event object was signaled, a nonzero value is returned.

## -remarks

Calling **KeSetEvent** causes the event to attain a signaled state. If the event is a notification event, the system attempts to satisfy as many waits as possible on the event object. The event remains signaled until a call to [KeClearEvent](/windows-hardware/drivers/ddi/wdm/nf-wdm-keclearevent) or [KeResetEvent](/windows-hardware/drivers/ddi/wdm/nf-wdm-keresetevent) clears it. If the event is a synchronization event, one wait is satisfied before the system automatically clears the event.

The **KeSetEvent** routine might temporarily raise the IRQL. If the *Wait* parameter is **FALSE**, the routine, before it returns, restores the IRQL to the original value that it had at the start of the call.

If *Wait* = **TRUE**, the routine returns without lowering the IRQL. In this case, the **KeSetEvent** call must be immediately followed by a **KeWait*Xxx*** call. By setting *Wait* = **TRUE**, the caller can prevent an unnecessary context switch from occurring between the **KeSetEvent** call and the **KeWait*Xxx*** call. The **KeWait*Xxx*** routine, before it returns, restores the IRQL to its original value at the start of the **KeSetEvent** call. Although the IRQL disables context switches between the two calls, these calls cannot reliably be used as the start and end of an atomic operation. For example, between these two calls, a thread that is running at the same time on another processor might change the state of the event object or of the target of the wait.

A pageable thread or pageable driver routine that runs at IRQL = PASSIVE_LEVEL should never call **KeSetEvent** with the *Wait* parameter set to TRUE. Such a call causes a fatal page fault if the caller happens to be paged out between the calls to **KeSetEvent** and **KeWait*Xxx***.

For more information about event objects, see [Event Objects](/windows-hardware/drivers/kernel/event-objects).

If *Wait* is set to **FALSE**, the caller can be running at IRQL <= DISPATCH_LEVEL. Otherwise, callers of **KeSetEvent** must be running at IRQL <= APC_LEVEL and in a nonarbitrary thread context.

## -see-also

[KeClearEvent](/windows-hardware/drivers/ddi/wdm/nf-wdm-keclearevent)

[KeInitializeEvent](/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializeevent)

[KeReadStateEvent](/windows-hardware/drivers/ddi/wdm/nf-wdm-kereadstateevent)

[KeResetEvent](/windows-hardware/drivers/ddi/wdm/nf-wdm-keresetevent)

[KeWaitForMultipleObjects](/windows-hardware/drivers/ddi/wdm/nf-wdm-kewaitformultipleobjects)

[KeWaitForSingleObject](/windows-hardware/drivers/ddi/wdm/nf-wdm-kewaitforsingleobject)

[Specifying Priority Boosts When Completing I/O Requests](/windows-hardware/drivers/wdf/specifying-priority-boosts-when-completing-i-o-requests)
