---
UID: NF:ntifs.PoCallDriver
title: PoCallDriver function (ntifs.h)
description: The PoCallDriver routine in ntifs.h passes a power IRP to the next-lower driver in the device stack. (Windows Server 2003, Windows XP, and Windows 2000 only.).
old-location: kernel\pocalldriver.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["PoCallDriver function"]
ms.keywords: PoCallDriver, PoCallDriver routine [Kernel-Mode Driver Architecture], kernel.pocalldriver, portn_2045d7d3-993d-49e6-aaf5-52d3c1316382.xml, wdm/PoCallDriver
req.header: ntifs.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: CompleteRequestStatusCheck, CompletionRoutineRegistered, DeleteDevice, ForwardedAtBadIrql, ForwardedAtBadIrqlAllocate, ForwardedAtBadIrqlFsdAsync, ForwardedAtBadIrqlFsdSync, IoAllocateForward, IoAllocateIrpSignalEventInCompletionTimeout, IoBuildDeviceControlWait, IoBuildDeviceControlWaitTimeout, IoBuildFsdForward, IoBuildSynchronousFsdRequestWait, IoBuildSynchronousFsdRequestWaitTimeout, IoSetCompletionRoutineExCheck, IrpProcessingComplete, LowerDriverReturn, MarkDevicePower, MarkingQueuedIrps, MarkIrpPending, MarkIrpPending2, MarkPower, MarkPowerDown, MarkQueryRelations, MarkStartDevice, PendedCompletedRequest, PendedCompletedRequest2, PendedCompletedRequest3, PendedCompletedRequestEx, PnpIrpCompletion, PowerDownFail, PowerUpFail, RemoveLockForward, RemoveLockForward2, RemoveLockForwardDeviceControl, RemoveLockForwardDeviceControl2, RemoveLockForwardDeviceControlInternal, RemoveLockForwardDeviceControlInternal2, RemoveLockForwardRead, RemoveLockForwardRead2, RemoveLockForwardWrite, RemoveLockForwardWrite2, RemoveLockMnRemove2, RemoveLockMnSurpriseRemove, RemoveLockQueryMnRemove, TargetRelationNeedsRef, WmiForward, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: See Remarks section.
targetos: Windows
req.typenames: 
f1_keywords:
 - PoCallDriver
 - ntifs/PoCallDriver
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - PoCallDriver
---

# PoCallDriver function (ntifs.h)


## -description

The <b>PoCallDriver</b> routine passes a power <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_irp">IRP</a> to the next-lower driver in the device stack. (Windows Server 2003, Windows XP, and Windows 2000 only.)

## -parameters

### -param DeviceObject 

[in]
A pointer to the driver-created <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a> to which the IRP is to be routed.

### -param Irp 

[in, out]
A pointer to an IRP.

## -returns

<b>PoCallDriver</b> returns STATUS_SUCCESS to indicate success. It returns STATUS_PENDING if it has queued the IRP.

## -remarks

Beginning with Windows Vista, drivers should call <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iocalldriver">IoCallDriver</a>, not <b>PoCallDriver</b> to pass a power IRP to the next-lower driver. However, on Windows Server 2003, Windows XP, and Windows 2000, drivers must call <b>PoCallDriver</b>, not <b>IoCallDriver</b>  to pass a power IRP to the next-lower driver. On Windows Server 2003, Windows XP, an Windows 2000, drivers must also call <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-postartnextpowerirp">PoStartNextPowerIrp</a> before calling <b>PoCallDriver</b>.

A driver that requires a new IRP should call <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-porequestpowerirp">PoRequestPowerIrp</a>. A driver must not allocate its own power IRP.

When passing a power IRP down to the next-lower driver, the caller should use [IoSkipCurrentIrpStackLocation](../wdm/nf-wdm-ioskipcurrentirpstacklocation.md) or <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iocopycurrentirpstacklocationtonext">IoCopyCurrentIrpStackLocationToNext</a> to set the IRP stack location, then call <b>PoCallDriver</b>. Use <b>IoCopyCurrentIrpStackLocationToNext</b> if processing the IRP requires setting an <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-io_completion_routine">IoCompletion</a> routine, or <b>IoSkipCurrentStackLocation</b> if no <i>IoCompletion</i> routine is required.

When a device is powering up, its drivers must set <i>IoCompletion</i> routines to perform start-up tasks (initializing the device, restoring context, and so on) after the bus driver has set the device in the working state. Set <i>IoCompletion</i> routines before calling <b>PoCallDriver</b>.

When a device is powering down, its drivers must perform necessary power-down tasks before passing the IRP to the next lower driver. After the IRP has reached the bus driver, the device will be powered off and its drivers will no longer have access to it. On Windows Server 2003, Windows XP, and Windows 2000, an <i>IoCompletion</i> routine that is associated with a power-down IRP is only required to call <b>PoStartNextPowerIrp</b>.

Only one inrush IRP can be active in the system at a time. When passing a power-up IRP for a device that requires inrush current (in other words, the DO_POWER_INRUSH flag is set in the device object), <b>PoCallDriver</b> checks whether another inrush IRP is already active. If so, <b>PoCallDriver</b> queues the current IRP for handling after the previous IRP completes, and then returns STATUS_PENDING. For more information about inrush IRPs, see <a href="/windows-hardware/drivers/kernel/setting-device-object-flags-for-power-management">Setting Device Object Flags for Power Management</a>. 

If an <a href="/windows-hardware/drivers/kernel/irp-mn-set-power">IRP_MN_SET_POWER</a> or <a href="/windows-hardware/drivers/kernel/irp-mn-query-power">IRP_MN_QUERY_POWER</a> request is already active for <i>DeviceObject</i>, <b>PoCallDriver</b> queues this IRP and returns STATUS_PENDING.

On Windows 2000 and later systems, pageable drivers (the DO_POWER_PAGABLE flag is set in the device object) must call <b>PoCallDriver</b> at IRQL = PASSIVE_LEVEL. Drivers that cannot be paged (DO_POWER_PAGABLE is not set in the device object) or that require inrush current (DO_POWER_INRUSH is set in the device object) can call <b>PoCallDriver</b> at IRQL = PASSIVE_LEVEL or DISPATCH_LEVEL.

On Windows 98/Me, all drivers call <b>PoCallDriver</b> at IRQL = PASSIVE_LEVEL.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_irp">IRP</a>



<a href="/windows-hardware/drivers/kernel/irp-mn-query-power">IRP_MN_QUERY_POWER</a>



<a href="/windows-hardware/drivers/kernel/irp-mn-set-power">IRP_MN_SET_POWER</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iocalldriver">IoCallDriver</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-io_completion_routine">IoCompletion</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iocopycurrentirpstacklocationtonext">IoCopyCurrentIrpStackLocationToNext</a>



[IoSkipCurrentIrpStackLocation](../wdm/nf-wdm-ioskipcurrentirpstacklocation.md)



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-porequestpowerirp">PoRequestPowerIrp</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-postartnextpowerirp">PoStartNextPowerIrp</a>