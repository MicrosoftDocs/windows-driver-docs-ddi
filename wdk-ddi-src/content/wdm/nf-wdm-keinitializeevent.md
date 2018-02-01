---
UID: NF:wdm.KeInitializeEvent
title: KeInitializeEvent function
author: windows-driver-content
description: The KeInitializeEvent routine initializes an event object as a synchronization (single waiter) or notification type event and sets it to a signaled or not-signaled state.
old-location: kernel\keinitializeevent.htm
old-project: kernel
ms.assetid: 0b59056c-6e73-4078-b8b3-32ced29ff7b0
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: KeInitializeEvent routine [Kernel-Mode Driver Architecture], k105_cc0b9273-d817-4853-b8ee-2337f53585f1.xml, KeInitializeEvent, wdm/KeInitializeEvent, kernel.keinitializeevent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	KeInitializeEvent
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeInitializeEvent function


## -description


The <b>KeInitializeEvent</b> routine initializes an event object as a synchronization (single waiter) or notification type event and sets it to a signaled or not-signaled state.


## -syntax


````
VOID KeInitializeEvent(
  _Out_ PRKEVENT   Event,
  _In_  EVENT_TYPE Type,
  _In_  BOOLEAN    State
);
````


## -parameters




### -param Event [out]

Pointer to an event object, for which the caller provides the storage.


### -param Type [in]

Specifies the event type, either <b>NotificationEvent</b> or <b>SynchronizationEvent</b>.


### -param State [in]

Specifies the initial state of the event. <b>TRUE</b> indicates a signaled state.


## -returns


None



## -remarks


Storage for an event object must be resident: in the device extension of a driver-created device object, in the controller extension of a driver-created controller object, or in nonpaged pool allocated by the caller. If you allocate the event on the stack, you must specify a <b>KernelMode</b> wait when calling <a href="..\wdm\nf-wdm-kewaitforsingleobject.md">KeWaitForSingleObject</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff553344">KeWaitForMutexObject</a>, or <a href="..\wdm\nf-wdm-kewaitformultipleobjects.md">KeWaitForMultipleObjects</a>. During a <b>KernelMode</b> wait, the stack containing the event will not be paged out.

Drivers typically use a <b>NotificationEvent</b> to wait for an I/O operation to complete. When a notification event is set to the signaled state, all threads that were waiting for the event to be set to the signaled state become eligible for execution. The event remains in the signaled state until a thread calls <a href="..\wdm\nf-wdm-keresetevent.md">KeResetEvent</a> or <a href="..\wdm\nf-wdm-keclearevent.md">KeClearEvent</a> to set the event in the not-signaled state.

A <b>SynchronizationEvent</b> is also called an <i>autoreset</i> or <i>autoclearing</i> event. When such an event is set, a single waiting thread becomes eligible for execution. The kernel automatically resets the event to the not-signaled state each time a wait is satisfied. A driver might use a synchronization event to protect a shared resource that is used in synchronizing the operations of several threads. Synchronization events are rarely used in a typical driver.

For more information about event objects, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff544323">Event Objects</a>.



## -see-also

<a href="..\wdm\nf-wdm-kereadstateevent.md">KeReadStateEvent</a>

<a href="..\wdm\nf-wdm-kewaitforsingleobject.md">KeWaitForSingleObject</a>

<a href="..\wdm\nf-wdm-kewaitformultipleobjects.md">KeWaitForMultipleObjects</a>

<a href="..\wdm\nf-wdm-keresetevent.md">KeResetEvent</a>

<a href="..\wdm\nf-wdm-keclearevent.md">KeClearEvent</a>

<a href="..\wdm\nf-wdm-kesetevent.md">KeSetEvent</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeInitializeEvent routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

