---
UID: NF:wdm.KeInitializeEvent
title: KeInitializeEvent function (wdm.h)
description: The KeInitializeEvent routine initializes an event object as a synchronization (single waiter) or notification type event and sets it to a signaled or not-signaled state.
old-location: kernel\keinitializeevent.htm
tech.root: kernel
ms.assetid: 0b59056c-6e73-4078-b8b3-32ced29ff7b0
ms.date: 04/30/2018
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

The <b>KeInitializeEvent</b> routine initializes an event object as a synchronization (single waiter) or notification type event and sets it to a signaled or not-signaled state.

## -parameters

### -param Event 

[out]
Pointer to an event object, for which the caller provides the storage.

### -param Type 

[in]
Specifies the event type, either <b>NotificationEvent</b> or <b>SynchronizationEvent</b>.

### -param State 

[in]
Specifies the initial state of the event. <b>TRUE</b> indicates a signaled state.

## -remarks

Storage for an event object must be resident: in the device extension of a driver-created device object, in the controller extension of a driver-created controller object, or in nonpaged pool allocated by the caller. If you allocate the event on the stack, you must specify a <b>KernelMode</b> wait when calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kewaitforsingleobject">KeWaitForSingleObject</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff553344">KeWaitForMutexObject</a>, or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kewaitformultipleobjects">KeWaitForMultipleObjects</a>. During a <b>KernelMode</b> wait, the stack containing the event will not be paged out.

Drivers typically use a <b>NotificationEvent</b> to wait for an I/O operation to complete. When a notification event is set to the signaled state, all threads that were waiting for the event to be set to the signaled state become eligible for execution. The event remains in the signaled state until a thread calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keresetevent">KeResetEvent</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keclearevent">KeClearEvent</a> to set the event in the not-signaled state.

A <b>SynchronizationEvent</b> is also called an <i>autoreset</i> or <i>autoclearing</i> event. When such an event is set, a single waiting thread becomes eligible for execution. The kernel automatically resets the event to the not-signaled state each time a wait is satisfied. A driver might use a synchronization event to protect a shared resource that is used in synchronizing the operations of several threads. Synchronization events are rarely used in a typical driver.

For more information about event objects, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/event-objects">Event Objects</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keclearevent">KeClearEvent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kereadstateevent">KeReadStateEvent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keresetevent">KeResetEvent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kesetevent">KeSetEvent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kewaitformultipleobjects">KeWaitForMultipleObjects</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kewaitforsingleobject">KeWaitForSingleObject</a>

