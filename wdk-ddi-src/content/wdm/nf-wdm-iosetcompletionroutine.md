---
UID: NF:wdm.IoSetCompletionRoutine
title: IoSetCompletionRoutine function (wdm.h)
description: The IoSetCompletionRoutine routine registers an IoCompletion routine, which will be called when the next-lower-level driver has completed the requested operation for the given IRP.
tech.root: kernel
ms.date: 12/12/2022
keywords: ["IoSetCompletionRoutine function"]
ms.keywords: IoSetCompletionRoutine, IoSetCompletionRoutine routine [Kernel-Mode Driver Architecture], k104_cbc51352-796e-4b64-9725-7d8a08c4aea9.xml, kernel.iosetcompletionroutine, wdm/IoSetCompletionRoutine
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt:
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: CompleteRequest, CompleteRequestStatusCheck, CompletionRoutineRegistered, IoAllocateForward, IoAllocateIrpSignalEventInCompletion, IoAllocateIrpSignalEventInCompletion2, IoAllocateIrpSignalEventInCompletion3, IoAllocateIrpSignalEventInCompletionTimeout, IoBuildFsdForward, IoBuildFsdIrpSignalEventInCompletion, IoBuildFsdIrpSignalEventInCompletion2, IoBuildFsdIrpSignalEventInCompletion3, IoBuildFsdIrpSignalEventInCompletionTimeout, IoSetCompletionRoutineNonPnpDriver, LowerDriverReturn, MarkPower, MarkPowerDown, MarkQueryRelations, MarkStartDevice, PendedCompletedRequest, SignalEventInCompletion, SignalEventInCompletion2, SignalEventInCompletion3, StartDeviceWait, StartDeviceWait3, SetCompletionRoutineFromDispatch, IoFreeIrp
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: IRQL <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IoSetCompletionRoutine
 - wdm/IoSetCompletionRoutine
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - IoSetCompletionRoutine
---

## -description

The **IoSetCompletionRoutine** routine registers an [IoCompletion](/windows-hardware/drivers/ddi/wdm/nc-wdm-io_completion_routine) routine, which will be called when the next-lower-level driver has completed the requested operation for the given IRP.

## -parameters

### -param Irp [in]

Pointer to the [IRP](/windows-hardware/drivers/ddi/wdm/ns-wdm-_irp) that the driver is processing.

### -param CompletionRoutine [in, optional]

Specifies the entry point for the driver-supplied [IoCompletion](/windows-hardware/drivers/ddi/wdm/nc-wdm-io_completion_routine) routine, which is called when the next-lower driver completes the packet.

### -param Context [in, optional]

Pointer to a driver-determined context to pass to the [IoCompletion](/windows-hardware/drivers/ddi/wdm/nc-wdm-io_completion_routine) routine. Context information must be stored in nonpaged memory, because the *IoCompletion* routine is called at IRQL <= DISPATCH_LEVEL.

### -param InvokeOnSuccess [in]

Specifies whether the completion routine is called if the IRP is completed with a success status value in the IRP's [**IO_STATUS_BLOCK**](/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_status_block) structure, based on results of the **NT_SUCCESS** macro (see [Using NTSTATUS values](/windows-hardware/drivers/kernel/using-ntstatus-values)).

### -param InvokeOnError [in]

Specifies whether the completion routine is called if the IRP is completed with a nonsuccess status value in the IRP's **IO_STATUS_BLOCK** structure.

### -param InvokeOnCancel [in]

Specifies whether the completion routine is called if a driver or the kernel has called [IoCancelIrp](/windows-hardware/drivers/ddi/wdm/nf-wdm-iocancelirp) to cancel the IRP.

## -remarks

Only a driver that can guarantee it will not be unloaded before its completion routine finishes can use **IoSetCompletionRoutine**. Otherwise, the driver must use [IoSetCompletionRoutineEx](/windows-hardware/drivers/ddi/wdm/nf-wdm-iosetcompletionroutineex), which prevents the driver from unloading until its completion routine executes.

This routine sets the transfer address of the [IoCompletion](/windows-hardware/drivers/ddi/wdm/nc-wdm-io_completion_routine) routine in the given IRP. The lowest-level driver in a chain of layered drivers cannot call this routine.

**IoSetCompletionRoutine** registers the specified routine to be called when the next-lower-level driver has completed the requested operation in any or all of the following ways:

- With a success status value

- With a nonsuccess status value

- By canceling the IRP

Usually, the I/O status block is set by the underlying device driver. It is read but not altered by any higher-level drivers' *IoCompletion* routines.

Higher-level drivers that allocate IRP's with [IoAllocateIrp](/windows-hardware/drivers/ddi/wdm/nf-wdm-ioallocateirp) or [IoBuildAsynchronousFsdRequest](/windows-hardware/drivers/ddi/wdm/nf-wdm-iobuildasynchronousfsdrequest) must call this routine with all *InvokeOn*Xxx parameters set to **TRUE** before passing the driver-allocated IRP to [IoCallDriver](/windows-hardware/drivers/ddi/wdm/nf-wdm-iocalldriver). When the *IoCompletion* routine is called with such an IRP, it must free the driver-allocated IRP and any other resources that the driver set up for the request, such as MDLs with [IoBuildPartialMdl](/windows-hardware/drivers/ddi/wdm/nf-wdm-iobuildpartialmdl). Such a driver should return STATUS_MORE_PROCESSING_REQUIRED when it calls [IoFreeIrp](/windows-hardware/drivers/devtest/storport-iofreeirp) to forestall the I/O manager's completion processing for the driver-allocated IRP.

Non-PnP drivers that might be unloaded before their *IoCompletion* routines run should use [IoSetCompletionRoutineEx](/windows-hardware/drivers/ddi/wdm/nf-wdm-iosetcompletionroutineex) instead.

## -see-also

[**IO_STACK_LOCATION**](/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_stack_location)

[**IRP**](/windows-hardware/drivers/ddi/wdm/ns-wdm-_irp)

[IoAllocateIrp](/windows-hardware/drivers/ddi/wdm/nf-wdm-ioallocateirp)

[IoBuildAsynchronousFsdRequest](/windows-hardware/drivers/ddi/wdm/nf-wdm-iobuildasynchronousfsdrequest)

[IoBuildPartialMdl](/windows-hardware/drivers/ddi/wdm/nf-wdm-iobuildpartialmdl)

[IoFreeIrp](/windows-hardware/drivers/devtest/storport-iofreeirp)

[IoSetCompletionRoutineEx](/windows-hardware/drivers/ddi/wdm/nf-wdm-iosetcompletionroutineex)
