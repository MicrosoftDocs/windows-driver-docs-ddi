---
UID: NF:wdm.IoMarkIrpPending
title: IoMarkIrpPending function (wdm.h)
description: The IoMarkIrpPending routine marks the specified IRP, indicating that a driver's dispatch routine subsequently returned STATUS_PENDING because further processing is required by other driver routines.
tech.root: kernel
ms.date: 12/12/2022
keywords: ["IoMarkIrpPending function"]
ms.keywords: IoMarkIrpPending, IoMarkIrpPending routine [Kernel-Mode Driver Architecture], k104_478903ab-e597-4df6-a66e-e0c1fbea49d9.xml, kernel.iomarkirppending, wdm/IoMarkIrpPending
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt:
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
req.lib: 
req.dll: 
req.irql: Any level
targetos: Windows
req.typenames: 
f1_keywords:
 - IoMarkIrpPending
 - wdm/IoMarkIrpPending
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - IoMarkIrpPending
---

## -description

The **IoMarkIrpPending** routine marks the specified IRP, indicating that a driver's dispatch routine subsequently returned STATUS_PENDING because further processing is required by other driver routines.

## -parameters

### -param Irp [in, out]

Pointer to the IRP to be marked as pending.

## -remarks

Unless the driver's dispatch routine completes the IRP (by calling [IoCompleteRequest](./nf-wdm-iocompleterequest.md)) or passes the IRP on to lower drivers, it must call **IoMarkIrpPending** with the IRP. Otherwise, the I/O manager attempts to complete the IRP as soon as the dispatch routine returns control.

After calling **IoMarkIrpPending**, the dispatch routine must return STATUS_PENDING, even if some routine completes the IRP (by calling [IoCompleteRequest](./nf-wdm-iocompleterequest.md)) before the dispatch routine that called **IoMarkIrpPending** returns.

If a driver queues incoming IRPs, it should call **IoMarkIrpPending** before it queues each IRP. Otherwise, an IRP could be dequeued, completed by another driver routine, and freed by the system before the call to **IoMarkIrpPending** occurs, thereby causing a crash.

If a driver sets an [IoCompletion](./nc-wdm-io_completion_routine.md) routine for an IRP and then passes the IRP down to a lower driver, the *IoCompletion* routine should check the **IRP->PendingReturned** flag. If the flag is set, the *IoCompletion* routine must call **IoMarkIrpPending** with the IRP. *IoCompletion* routines do not return STATUS_PENDING. For more information, see [Implementing an IoCompletion Routine](/windows-hardware/drivers/kernel/implementing-an-iocompletion-routine).

Drivers that create the IRP and send it to another stack must not call **IoMarkIrpPending** in their completion routine. This call will corrupt the pool header of the next allocation because there is no stack location for those drivers.

A driver that passes down the IRP and then waits on an event should not mark the IRP pending. Instead, its *IoCompletion* routine should signal the event and return STATUS_MORE_PROCESSING_REQUIRED.

If your driver calls [IoSkipCurrentIrpStackLocation](./nf-wdm-ioskipcurrentirpstacklocation.md), be careful not to modify the [IO_STACK_LOCATION](./ns-wdm-_io_stack_location.md) structure in a way that could unintentionally affect the lower driver or the system's behavior with respect to that driver. In particular, your driver should not modify the **IO_STACK_LOCATION** structure's **Parameters** union, and should not call **IoMarkIrpPending**.

## -see-also

[**IO_STACK_LOCATION**](./ns-wdm-_io_stack_location.md)

[**IRP**](./ns-wdm-_irp.md)

[IoCompleteRequest](./nf-wdm-iocompleterequest.md)

[IoSkipCurrentIrpStackLocation](./nf-wdm-ioskipcurrentirpstacklocation.md)

[IoStartPacket](../ntifs/nf-ntifs-iostartpacket.md)