---
UID: NF:wdm.KeSetEvent
title: KeSetEvent function (wdm.h)
description: The KeSetEvent routine sets an event object to a signaled state if the event was not already signaled, and returns the previous state of the event object.
old-location: kernel\kesetevent.htm
tech.root: kernel
ms.assetid: a2017660-f001-449c-9c33-e26c2897ead1
ms.date: 04/30/2018
keywords: ["KeSetEvent function"]
ms.keywords: KeSetEvent, KeSetEvent routine [Kernel-Mode Driver Architecture], k105_0b9a87b5-bdf2-4449-81f6-1836ea47f038.xml, kernel.kesetevent, wdm/KeSetEvent
f1_keywords:
 - "wdm/KeSetEvent"
 - "KeSetEvent"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- KeSetEvent
product:
- Windows
targetos: Windows
req.typenames: 
---

# KeSetEvent function


## -description


The <b>KeSetEvent</b> routine sets an event object to a signaled state if the event was not already signaled, and returns the previous state of the event object. 


## -parameters




### -param Event [in, out]

A pointer to an initialized event object for which the caller provides the storage.


### -param Increment [in]

Specifies the priority increment to be applied if setting the event causes a wait to be satisfied.


### -param Wait [in]

Specifies whether the call to <b>KeSetEvent</b> is to be followed immediately by a call to one of the <b>KeWait<i>Xxx</i></b> routines. If <b>TRUE</b>, the <b>KeSetEvent</b> call must be followed by a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kewaitformultipleobjects">KeWaitForMultipleObjects</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff553344">KeWaitForMutexObject</a>, or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kewaitforsingleobject">KeWaitForSingleObject</a>. For more information, see the following Remarks section.


## -returns



If the previous state of the event object was signaled, a nonzero value is returned.




## -remarks



Calling <b>KeSetEvent</b> causes the event to attain a signaled state. If the event is a notification event, the system attempts to satisfy as many waits as possible on the event object. The event remains signaled until a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keclearevent">KeClearEvent</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keresetevent">KeResetEvent</a> clears it. If the event is a synchronization event, one wait is satisfied before the system automatically clears the event.

The <b>KeSetEvent</b> routine might temporarily raise the IRQL. If the <i>Wait</i> parameter is <b>FALSE</b>, the routine, before it returns, restores the IRQL to the original value that it had at the start of the call.

If <i>Wait</i> = <b>TRUE</b>, the routine returns without lowering the IRQL. In this case, the <b>KeSetEvent</b> call must be immediately followed by a <b>KeWait<i>Xxx</i></b> call. By setting <i>Wait</i> = <b>TRUE</b>, the caller can prevent an unnecessary context switch from occurring between the <b>KeSetEvent</b> call and the <b>KeWait<i>Xxx</i></b> call. The <b>KeWait<i>Xxx</i></b> routine, before it returns, restores the IRQL to its original value at the start of the <b>KeSetEvent</b> call. Although the IRQL disables context switches between the two calls, these calls cannot reliably be used as the start and end of an atomic operation. For example, between these two calls, a thread that is running at the same time on another processor might change the state of the event object or of the target of the wait.

A pageable thread or pageable driver routine that runs at IRQL = PASSIVE_LEVEL should never call <b>KeSetEvent</b> with the <i>Wait</i> parameter set to TRUE. Such a call causes a fatal page fault if the caller happens to be paged out between the calls to <b>KeSetEvent</b> and <b>KeWait<i>Xxx</i></b>.

For more information about event objects, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/event-objects">Event Objects</a>.

If <i>Wait</i> is set to <b>FALSE</b>, the caller can be running at IRQL <= DISPATCH_LEVEL. Otherwise, callers of <b>KeSetEvent</b> must be running at IRQL <= APC_LEVEL and in a nonarbitrary thread context.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keclearevent">KeClearEvent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializeevent">KeInitializeEvent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kereadstateevent">KeReadStateEvent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keresetevent">KeResetEvent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kewaitformultipleobjects">KeWaitForMultipleObjects</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553344">KeWaitForMutexObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kewaitforsingleobject">KeWaitForSingleObject</a>



<a href="https://go.microsoft.com/fwlink/p/?linkid=838602">Specifying Priority Boosts When Completing I/O Requests</a>
 

 

