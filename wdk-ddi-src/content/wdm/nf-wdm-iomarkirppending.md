---
UID: NF:wdm.IoMarkIrpPending
title: IoMarkIrpPending function
author: windows-driver-content
description: The IoMarkIrpPending routine marks the specified IRP, indicating that a driver's dispatch routine subsequently returned STATUS_PENDING because further processing is required by other driver routines.
old-location: kernel\iomarkirppending.htm
old-project: kernel
ms.assetid: 424d5ebd-c871-40d8-b5b7-3a4a04fe60fa
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: k104_478903ab-e597-4df6-a66e-e0c1fbea49d9.xml, IoMarkIrpPending, kernel.iomarkirppending, IoMarkIrpPending routine [Kernel-Mode Driver Architecture], wdm/IoMarkIrpPending
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: CompleteRequestStatusCheck, CompletionEventChecking, IrpCancelField, LowerDriverReturn, MarkDevicePower, MarkingInterlockedQueuedIrps, MarkingQueuedIrps, MarkIrpPending, MarkIrpPending2, MarkPower, MarkPowerDown, MarkQueryRelations, MarkStartDevice, PendedCompletedRequest3
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
req.dll: 
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wdm.h
apiname:
-	IoMarkIrpPending
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoMarkIrpPending function


## -description


The <b>IoMarkIrpPending</b> routine marks the specified IRP, indicating that a driver's dispatch routine subsequently returned STATUS_PENDING because further processing is required by other driver routines.


## -syntax


````
VOID IoMarkIrpPending(
  _Inout_ PIRP Irp
);
````


## -parameters




#### - Irp [in, out]

Pointer to the IRP to be marked as pending.


## -returns


None



## -remarks


Unless the driver's dispatch routine completes the IRP (by calling <a href="..\wdm\nf-wdm-iocompleterequest.md">IoCompleteRequest</a>) or passes the IRP on to lower drivers, it must call <b>IoMarkIrpPending</b> with the IRP. Otherwise, the I/O manager attempts to complete the IRP as soon as the dispatch routine returns control.

After calling <b>IoMarkIrpPending</b>, the dispatch routine must return STATUS_PENDING, even if some routine completes the IRP (by calling <a href="..\wdm\nf-wdm-iocompleterequest.md">IoCompleteRequest</a>) before the dispatch routine that called <b>IoMarkIrpPending</b> returns.

If a driver queues incoming IRPs, it should call <b>IoMarkIrpPending</b> before it queues each IRP. Otherwise, an IRP could be dequeued, completed by another driver routine, and freed by the system before the call to <b>IoMarkIrpPending</b> occurs, thereby causing a crash.

If a driver sets an <a href="..\wdm\nc-wdm-io_completion_routine.md">IoCompletion</a> routine for an IRP and then passes the IRP down to a lower driver, the <i>IoCompletion</i> routine should check the <b>IRP-&gt;PendingReturned</b> flag. If the flag is set, the <i>IoCompletion</i> routine must call <b>IoMarkIrpPending</b> with the IRP. (<i>IoCompletion</i> routines do not return STATUS_PENDING, however. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff547084">Implementing an IoCompletion Routine</a>.) 
<div class="alert"><b>Note</b>  Drivers that create the IRP and send it to another stack must not call <b>IoMarkIrpPending</b> in their completion routine. This call will corrupt the pool header of the next allocation because there is no stack location for those drivers.</div><div> </div>A driver that passes down the IRP and then waits on an event should not mark the IRP pending. Instead, its <i>IoCompletion</i> routine should signal the event and return STATUS_MORE_PROCESSING_REQUIRED.

If your driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff550355">IoSkipCurrentIrpStackLocation</a>, be careful not to modify the <a href="..\wdm\ns-wdm-_io_stack_location.md">IO_STACK_LOCATION</a> structure in a way that could unintentionally affect the lower driver or the system's behavior with respect to that driver. In particular, your driver should not modify the <b>IO_STACK_LOCATION</b> structure's <b>Parameters</b> union, and should not call <b>IoMarkIrpPending</b>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550355">IoSkipCurrentIrpStackLocation</a>

<a href="..\wdm\nf-wdm-iocompleterequest.md">IoCompleteRequest</a>

<a href="..\wdm\ns-wdm-_io_stack_location.md">IO_STACK_LOCATION</a>

<a href="..\wdm\nf-wdm-iostartpacket.md">IoStartPacket</a>

<a href="..\wdm\ns-wdm-_irp.md">IRP</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoMarkIrpPending routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

