---
UID: NF:wdm.IoCallDriver
title: IoCallDriver macro (wdm.h)
description: The IoCallDriver routine sends an IRP to the driver associated with a specified device object.
old-location: kernel\iocalldriver.htm
tech.root: kernel
ms.assetid: 5d1fff23-f1e8-41a5-9cd6-a20bd4a7883e
ms.date: 04/30/2018
ms.keywords: IoCallDriver, IoCallDriver routine [Kernel-Mode Driver Architecture], k104_8579a946-2f96-455f-825c-c3f86caba99c.xml, kernel.iocalldriver, wdm/IoCallDriver
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


The <b>IoCallDriver</b> routine, wraps **IofCallDriver** that sends an IRP to the driver associated with a specified device object. For more information, see [**IofCallDriver**](nf-wdm-iofcalldriver.md).

>Do not call **IofCallDriver**. Call **IoCallDriver** instead.


## -parameters




### -param a [in]

See [**IofCallDriver**](nf-wdm-iofcalldriver.md).

### -param b [in, out]

See [**IofCallDriver**](nf-wdm-iofcalldriver.md).

## -returns
See [**IofCallDriver**](nf-wdm-iofcalldriver.md).

## -remarks

see [**IofCallDriver**](nf-wdm-iofcalldriver.md).


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548257">IoAllocateIrp</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548310">IoBuildAsynchronousFsdRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548318">IoBuildDeviceIoControlRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548330">IoBuildSynchronousFsdRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549679">IoSetCompletionRoutine</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559654">PoCallDriver</a>
 

 

