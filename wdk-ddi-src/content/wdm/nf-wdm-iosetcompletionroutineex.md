---
UID: NF:wdm.IoSetCompletionRoutineEx
title: IoSetCompletionRoutineEx function (wdm.h)
description: The IoSetCompletionRoutineEx routine registers an IoCompletion routine, which is called when the next-lower-level driver has completed the requested operation for the given IRP.
tech.root: kernel
ms.date: 12/12/2022
keywords: ["IoSetCompletionRoutineEx function"]
ms.keywords: IoSetCompletionRoutineEx, IoSetCompletionRoutineEx routine [Kernel-Mode Driver Architecture], k104_b574c1f0-f1e7-4c34-93ee-4681ec9e1046.xml, kernel.iosetcompletionroutineex, wdm/IoSetCompletionRoutineEx
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: CompleteRequest, CompleteRequestStatusCheck, CompletionRoutineRegistered, IoAllocateForward, IoAllocateIrpSignalEventInCompletion, IoAllocateIrpSignalEventInCompletion2, IoAllocateIrpSignalEventInCompletion3, IoAllocateIrpSignalEventInCompletionTimeout, IoBuildFsdForward, IoBuildFsdIrpSignalEventInCompletion, IoBuildFsdIrpSignalEventInCompletion2, IoBuildFsdIrpSignalEventInCompletion3, IoBuildFsdIrpSignalEventInCompletionTimeout, IoSetCompletionExCompleteIrp, IoSetCompletionRoutineExCheck, IoSetCompletionRoutineExCheckDeviceObject, LowerDriverReturn, MarkPower, MarkPowerDown, MarkQueryRelations, MarkStartDevice, PendedCompletedRequestEx, SignalEventInCompletion, SignalEventInCompletion2, SignalEventInCompletion3, StartDeviceWait2, StartDeviceWait4, SetCompletionRoutineFromDispatch, HwStorPortProhibitedDDIs
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
 - IoSetCompletionRoutineEx
 - wdm/IoSetCompletionRoutineEx
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoSetCompletionRoutineEx
---

## -description

The **IoSetCompletionRoutineEx** routine registers an [IoCompletion](./nc-wdm-io_completion_routine.md) routine, which is called when the next-lower-level driver has completed the requested operation for the given IRP.

## -parameters

### -param DeviceObject [in]

Pointer to the driver's device object.

### -param Irp [in]

Pointer to the [**IRP**](./ns-wdm-_irp.md) that the driver is processing.

### -param CompletionRoutine [in]

Specifies the entry point for the driver-supplied [IoCompletion](./nc-wdm-io_completion_routine.md) routine, which is called when the next-lower driver completes the packet.

### -param Context [in, optional]

Pointer to a driver-determined context to pass to the *IoCompletion* routine. Context information must be stored in nonpaged memory, because the *IoCompletion* routine is called at IRQL <= DISPATCH_LEVEL.

### -param InvokeOnSuccess [in]

Specifies whether the completion routine is called if the IRP is completed with a success status value in the IRP's [**IO_STATUS_BLOCK**](./ns-wdm-_io_status_block.md) structure, based on results of the NT_SUCCESS macro (see [Using NTSTATUS values](/windows-hardware/drivers/kernel/using-ntstatus-values)).

### -param InvokeOnError [in]

Specifies whether the completion routine is called if the IRP is completed with a nonsuccess status value in the IRP's **IO_STATUS_BLOCK** structure.

### -param InvokeOnCancel [in]

Specifies whether the completion routine is called if a driver or the kernel has called [IoCancelIrp](./nf-wdm-iocancelirp.md) to cancel the IRP.

## -returns

This routine returns STATUS_SUCCESS on success, or STATUS_INSUFFICIENT_RESOURCES if insufficient memory is available for the operation.

## -remarks

Unlike [IoSetCompletionRoutine](./nf-wdm-iosetcompletionroutine.md), the **IoSetCompletionRoutineEx** routine returns an NTSTATUS value. The driver must check this value to determine if the [IoCompletion](./nc-wdm-io_completion_routine.md) routine was successfully registered. If the *IoCompletion* routine is successfully registered, **IoSetCompletionRoutineEx** allocates memory that remains allocated until the *IoCompletion* routine executes. Drivers must ensure that their *IoCompletion* routine executes by calling [IoCallDriver](./nf-wdm-iocalldriver.md); otherwise, the kernel will leak memory.

The *IoCompletion* routine must belong to the driver that owns the device object pointed to by *DeviceObject*. This requirement prevents the *IoCompletion* routine from being unloaded before it returns.

The behavior of **IoSetCompletionRoutineEx** is the same as the [IoSetCompletionRoutine](./nf-wdm-iosetcompletionroutine.md) routine, except that:

- **IoSetCompletionRoutineEx** guarantees that a non-Plug and Play driver is not unloaded before the *IoCompletion* routine runs.

- **IoSetCompletionRoutineEx** is a routine that returns an NTSTATUS value.

## -see-also

[**IO_STACK_LOCATION**](./ns-wdm-_io_stack_location.md)

[**IRP**](./ns-wdm-_irp.md)

[IoAllocateIrp](./nf-wdm-ioallocateirp.md)

[IoBuildAsynchronousFsdRequest](./nf-wdm-iobuildasynchronousfsdrequest.md)

[IoBuildPartialMdl](./nf-wdm-iobuildpartialmdl.md)

[IoCompletion](./nc-wdm-io_completion_routine.md)

[IoFreeIrp](/windows-hardware/drivers/devtest/storport-iofreeirp)

[IoSetCompletionRoutine](./nf-wdm-iosetcompletionroutine.md)