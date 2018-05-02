---
UID: NF:wdm.IoCallDriver
title: IoCallDriver macro
author: windows-driver-content
description: The IoCallDriver routine sends an IRP to the driver associated with a specified device object.
old-location: kernel\iocalldriver.htm
old-project: kernel
ms.assetid: 5d1fff23-f1e8-41a5-9cd6-a20bd4a7883e
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: IoCallDriver, IoCallDriver routine [Kernel-Mode Driver Architecture], k104_8579a946-2f96-455f-825c-c3f86caba99c.xml, kernel.iocalldriver, wdm/IoCallDriver
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: wdm.h
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoCallDriver
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoCallDriver macro


## -description


The <b>IoCallDriver</b> routine sends an IRP to the driver associated with a specified device object.


## -parameters




### -param a

TBD


### -param b

TBD






#### - DeviceObject [in]

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff597563">device object</a>, representing the target device for the requested I/O operation.


#### - Irp [in, out]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550694">IRP</a>. 


## -remarks



Before calling <b>IoCallDriver</b>, the calling driver must set up the I/O stack location in the IRP for the target driver. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558781">Passing IRPs Down the Driver Stack</a>.

<b>IoCallDriver</b> assigns the <i>DeviceObject</i> input parameter to the <i>DeviceObject</i> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550659">IO_STACK_LOCATION</a> structure for the driver being called.

An IRP passed in a call to <b>IoCallDriver</b> becomes inaccessible to the higher-level driver, unless the higher-level driver has called <a href="https://msdn.microsoft.com/library/windows/hardware/ff549679">IoSetCompletionRoutine</a> to set up an <a href="https://msdn.microsoft.com/library/windows/hardware/ff548354">IoCompletion</a> routine for the IRP. If it has, the IRP input to the <i>IoCompletion</i> routine has its I/O status block set by the lower drivers, and all lower-level drivers' I/O stack locations are filled with zeros.

Drivers for Windows Server 2003, Windows XP, and Windows 2000 must use <a href="https://msdn.microsoft.com/library/windows/hardware/ff559654">PoCallDriver</a> rather than <b>IoCallDriver</b> to pass power IRPs (<a href="https://msdn.microsoft.com/library/windows/hardware/ff550784">IRP_MJ_POWER</a>). For more information, see <a href="https://msdn.microsoft.com/a47e2310-e89b-4552-bbe3-d4984ae8b564">Calling IoCallDriver vs. Calling PoCallDriver</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548257">IoAllocateIrp</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548310">IoBuildAsynchronousFsdRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548318">IoBuildDeviceIoControlRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548330">IoBuildSynchronousFsdRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549679">IoSetCompletionRoutine</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559654">PoCallDriver</a>
 

 

