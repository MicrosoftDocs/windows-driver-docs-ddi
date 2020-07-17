---
UID: NF:wdm.IofCallDriver
title: IofCallDriver function (wdm.h)
description: Call **IoCallDriver** instead. Sends an IRP to the driver associated with a specified device object.
ms.assetid: e241d188-273d-430a-9c27-403ddc6fa450
ms.date: 04/30/2018
keywords: ["IofCallDriver function"]
f1_keywords:
 - "wdm/IofCallDriver"
 - "IofCallDriver"
ms.keywords: IofCallDriver, IoCallDriver, IoCallDriver routine [Kernel-Mode Driver Architecture], k104_8579a946-2f96-455f-825c-c3f86caba99c.xml, kernel.iocalldriver, wdm/IoCallDriver
req.header: wdm.h
req.include-header:  Wdm.h, Ntddk.h, Ntifs.h
req.target-type:
req.target-min-winverclnt:  Available starting with Windows 2000.
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= DISPATCH_LEVEL
req.ddi-compliance: CompleteRequestStatusCheck, CompletionRoutineRegistered, DeleteDevice, ForwardedAtBadIrql, ForwardedAtBadIrqlAllocate, ForwardedAtBadIrqlFsdAsync, ForwardedAtBadIrqlFsdSync, IoAllocateForward, IoAllocateIrpSignalEventInCompletionTimeout, IoBuildDeviceControlWait, IoBuildDeviceControlWaitTimeout, IoBuildFsdForward, IoBuildSynchronousFsdRequestWait, IoBuildSynchronousFsdRequestWaitTimeout, IoSetCompletionRoutineExCheck, IrpProcessingComplete, LowerDriverReturn, MarkDevicePower, MarkingQueuedIrps, MarkIrpPending, MarkIrpPending2, MarkPower, MarkPowerDown, MarkQueryRelations, MarkStartDevice, PendedCompletedRequest, PendedCompletedRequest2, PendedCompletedRequest3, PendedCompletedRequestEx, PnpIrpCompletion, PowerDownFail, PowerUpFail, RemoveLockForward, RemoveLockForward2, RemoveLockForwardDeviceControl, RemoveLockForwardDeviceControl2, RemoveLockForwardDeviceControlInternal, RemoveLockForwardDeviceControlInternal2, RemoveLockForwardRead, RemoveLockForwardRead2, RemoveLockForwardWrite, RemoveLockForwardWrite2, RemoveLockMnRemove2, RemoveLockMnSurpriseRemove, RemoveLockQueryMnRemove, TargetRelationNeedsRef, WmiForward, HwStorPortProhibitedDDIs
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
- kbSyntax
api_type: 
- DllExport
api_location: 
- Ntoskrnl.exe
api_name: 
- IofCallDriver
- IoCallDriver
product:
- Windows
targetos: Windows


ms.custom: RS5
---

# IofCallDriver function


## -description

Call [**IoCallDriver**](nf-wdm-iocalldriver.md) instead. Sends an IRP to the driver associated with a specified device object.

## -parameters

### -param DeviceObject
Pointer to a device object, representing the target device for the requested I/O operation.

### -param Irp
Pointer to the [**IRP**](ns-wdm-_irp.md).

## -returns
Returns an appropriate [NTSTATUS value](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks
Before calling <b>IoCallDriver</b>, the calling driver must set up the I/O stack location in the IRP for the target driver. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/passing-irps-down-the-driver-stack">Passing IRPs Down the Driver Stack</a>.

<b>IoCallDriver</b> assigns the <i>DeviceObject</i> input parameter to the <i>DeviceObject</i> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_stack_location">IO_STACK_LOCATION</a> structure for the driver being called.

An IRP passed in a call to <b>IoCallDriver</b> becomes inaccessible to the higher-level driver, unless the higher-level driver has called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iosetcompletionroutine">IoSetCompletionRoutine</a> to set up an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-io_completion_routine">IoCompletion</a> routine for the IRP. If it has, the IRP input to the <i>IoCompletion</i> routine has its I/O status block set by the lower drivers, and all lower-level drivers' I/O stack locations are filled with zeros.

Drivers for Windows Server 2003, Windows XP, and Windows 2000 must use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-pocalldriver">PoCallDriver</a> rather than <b>IoCallDriver</b> to pass power IRPs (<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-power">IRP_MJ_POWER</a>). For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/calling-iocalldriver-versus-calling-pocalldriver">Calling IoCallDriver vs. Calling PoCallDriver</a>. 

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioallocateirp">IoAllocateIrp</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iobuildasynchronousfsdrequest">IoBuildAsynchronousFsdRequest</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iobuilddeviceiocontrolrequest">IoBuildDeviceIoControlRequest</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iobuildsynchronousfsdrequest">IoBuildSynchronousFsdRequest</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iosetcompletionroutine">IoSetCompletionRoutine</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-pocalldriver">PoCallDriver</a>
