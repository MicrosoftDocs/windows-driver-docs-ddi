---
UID: NF:wdm.KeInitializeEvent
title: KeInitializeEvent function (wdm.h)
description: The KeInitializeEvent routine initializes an event object as a synchronization (single waiter) or notification type event and sets it to a signaled or not-signaled state.
old-location: kernel\keinitializeevent.htm
tech.root: kernel
ms.date: 07/29/2021
keywords: ["KeInitializeEvent function"]
ms.keywords: KeInitializeEvent, KeInitializeEvent routine [Kernel-Mode Driver Architecture], k105_cc0b9273-d817-4853-b8ee-2337f53585f1.xml, kernel.keinitializeevent, wdm/KeInitializeEvent
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IoAllocateIrpSignalEventInCompletion, IoAllocateIrpSignalEventInCompletion2, IoAllocateIrpSignalEventInCompletion3, IoAllocateIrpSignalEventInCompletionTimeout, IoBuildDeviceControlWait, IoBuildDeviceControlWaitTimeout, IoBuildDeviceIoControlSetEvent, IoBuildFsdIrpSignalEventInCompletion, IoBuildFsdIrpSignalEventInCompletion2, IoBuildFsdIrpSignalEventInCompletion3, IoBuildFsdIrpSignalEventInCompletionTimeout, IoBuildSynchronousFsdRequestWait, IoBuildSynchronousFsdRequestWaitTimeout, PendedCompletedRequest, PendedCompletedRequestEx, SignalEventInCompletion, SignalEventInCompletion2, SignalEventInCompletion3, StartDeviceWait, StartDeviceWait2, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level
targetos: Windows
req.typenames: 
f1_keywords:
 - KeInitializeEvent
 - wdm/KeInitializeEvent
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - KeInitializeEvent
---

# KeInitializeEvent function

## -description

The **KeInitializeEvent** routine initializes an event object as a synchronization (single waiter) or notification type event and sets it to a signaled or not-signaled state.

## -parameters

### -param Event

[out] Pointer to an event object, for which the caller provides the storage.

### -param Type

[in] Specifies the event type, either **NotificationEvent** or **SynchronizationEvent**.

### -param State

[in] Specifies the initial state of the event. **TRUE** indicates a signaled state.

## -remarks

Storage for an event object must be resident: in the device extension of a driver-created device object, in the controller extension of a driver-created controller object, or in nonpaged pool allocated by the caller. If you allocate the event on the stack, you must specify a **KernelMode** wait when calling [KeWaitForSingleObject](./nf-wdm-kewaitforsingleobject.md), **KeWaitForMutexObject**, or [KeWaitForMultipleObjects](./nf-wdm-kewaitformultipleobjects.md). During a **KernelMode** wait, the stack containing the event will not be paged out.

Drivers typically use a **NotificationEvent** to wait for an I/O operation to complete. When a notification event is set to the signaled state, all threads that were waiting for the event to be set to the signaled state become eligible for execution. The event remains in the signaled state until a thread calls [KeResetEvent](./nf-wdm-keresetevent.md) or [KeClearEvent](./nf-wdm-keclearevent.md) to set the event in the not-signaled state.

A **SynchronizationEvent** is also called an *autoreset* or *autoclearing* event. When such an event is set, a single waiting thread becomes eligible for execution. The kernel automatically resets the event to the not-signaled state each time a wait is satisfied. A driver might use a synchronization event to protect a shared resource that is used in synchronizing the operations of several threads. Synchronization events are rarely used in a typical driver.

For more information about event objects, see [Event Objects](/windows-hardware/drivers/kernel/event-objects).

## -see-also

[KeClearEvent](./nf-wdm-keclearevent.md)

[KeReadStateEvent](./nf-wdm-kereadstateevent.md)

[KeResetEvent](./nf-wdm-keresetevent.md)

[KeSetEvent](./nf-wdm-kesetevent.md)

[KeWaitForMultipleObjects](./nf-wdm-kewaitformultipleobjects.md)

[KeWaitForSingleObject](./nf-wdm-kewaitforsingleobject.md)
