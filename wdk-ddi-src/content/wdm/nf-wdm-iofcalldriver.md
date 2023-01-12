---
UID: NF:wdm.IofCallDriver
title: IofCallDriver function (wdm.h)
description: Call **IoCallDriver** instead. Sends an IRP to the driver associated with a specified device object.
tech.root: kernel
ms.date: 01/06/2023
keywords: ["IofCallDriver function"]
ms.keywords: IofCallDriver, IoCallDriver, IoCallDriver routine [Kernel-Mode Driver Architecture], k104_8579a946-2f96-455f-825c-c3f86caba99c.xml, kernel.iocalldriver, wdm/IoCallDriver
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: 
req.target-min-winverclnt:
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: IRQL <= DISPATCH_LEVEL
req.ddi-compliance: CompleteRequestStatusCheck, CompletionRoutineRegistered, DeleteDevice, ForwardedAtBadIrql, ForwardedAtBadIrqlAllocate, ForwardedAtBadIrqlFsdAsync, ForwardedAtBadIrqlFsdSync, IoAllocateForward, IoAllocateIrpSignalEventInCompletionTimeout, IoBuildDeviceControlWait, IoBuildDeviceControlWaitTimeout, IoBuildFsdForward, IoBuildSynchronousFsdRequestWait, IoBuildSynchronousFsdRequestWaitTimeout, IoSetCompletionRoutineExCheck, IrpProcessingComplete, LowerDriverReturn, MarkDevicePower, MarkingQueuedIrps, MarkIrpPending, MarkIrpPending2, MarkPower, MarkPowerDown, MarkQueryRelations, MarkStartDevice, PendedCompletedRequest, PendedCompletedRequest2, PendedCompletedRequest3, PendedCompletedRequestEx, PnpIrpCompletion, PowerDownFail, PowerUpFail, RemoveLockForward, RemoveLockForward2, RemoveLockForwardDeviceControl, RemoveLockForwardDeviceControl2, RemoveLockForwardDeviceControlInternal, RemoveLockForwardDeviceControlInternal2, RemoveLockForwardRead, RemoveLockForwardRead2, RemoveLockForwardWrite, RemoveLockForwardWrite2, RemoveLockMnRemove2, RemoveLockMnSurpriseRemove, RemoveLockQueryMnRemove, TargetRelationNeedsRef, WmiForward, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
f1_keywords:
 - IofCallDriver
 - wdm/IofCallDriver
topic_type:
 - apiref
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Ntoskrnl.exe
api_name:
 - IofCallDriver
---

## -description

> [!CAUTION]
> Call [IoCallDriver](./nf-wdm-iocalldriver.md) instead.

Sends an IRP to the driver associated with a specified device object.

## -parameters

### -param DeviceObject

Pointer to a device object, representing the target device for the requested I/O operation.

### -param Irp

Pointer to the [**IRP**](ns-wdm-_irp.md).

## -returns

Returns an appropriate [NTSTATUS value](/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

Before calling IoCallDriver, the calling driver must set up the I/O stack location in the IRP for the target driver. For more information, see [Passing IRPs Down the Driver Stack](/windows-hardware/drivers/kernel/passing-irps-down-the-driver-stack).

IoCallDriver assigns the *DeviceObject* input parameter to the DeviceObject member of the [IO_STACK_LOCATION](/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_stack_location) structure for the driver being called.

An IRP passed in a call to IoCallDriver becomes inaccessible to the higher-level driver, unless the higher-level driver has called [IoSetCompletionRoutine](/windows-hardware/drivers/ddi/wdm/nf-wdm-iosetcompletionroutine) to set up an [IoCompletion](/windows-hardware/drivers/ddi/wdm/nc-wdm-io_completion_routine) routine for the IRP. If it has, the IRP input to the IoCompletion routine has its I/O status block set by the lower drivers, and all lower-level drivers' I/O stack locations are filled with zeros.

Drivers for Windows Server 2003, Windows XP, and Windows 2000 must use [PoCallDriver](/windows-hardware/drivers/ddi/ntifs/nf-ntifs-pocalldriver) rather than IoCallDriver to pass power IRPs ([IRP_MJ_POWER](/windows-hardware/drivers/kernel/irp-mj-power)).

For more information, see [Calling IoCallDriver vs. Calling PoCallDriver](/windows-hardware/drivers/kernel/calling-iocalldriver-versus-calling-pocalldriver).

## -see-also

[IoAllocateIrp](/windows-hardware/drivers/ddi/wdm/nf-wdm-ioallocateirp)

[IoBuildAsynchronousFsdRequest](/windows-hardware/drivers/ddi/wdm/nf-wdm-iobuildasynchronousfsdrequest)

[IoBuildDeviceIoControlRequest](/windows-hardware/drivers/ddi/wdm/nf-wdm-iobuilddeviceiocontrolrequest)

[IoBuildSynchronousFsdRequest](/windows-hardware/drivers/ddi/wdm/nf-wdm-iobuildsynchronousfsdrequest)

[IoSetCompletionRoutine](/windows-hardware/drivers/ddi/wdm/nf-wdm-iosetcompletionroutine)

[PoCallDriver](/windows-hardware/drivers/ddi/ntifs/nf-ntifs-pocalldriver)
