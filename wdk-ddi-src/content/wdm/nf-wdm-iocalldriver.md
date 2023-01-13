---
UID: NF:wdm.IoCallDriver
title: IoCallDriver macro (wdm.h)
description: The IoCallDriver routine sends an IRP to the driver associated with a specified device object.
tech.root: kernel
ms.date: 01/05/2023
keywords: ["IoCallDriver macro"]
ms.keywords: IoCallDriver, IoCallDriver routine [Kernel-Mode Driver Architecture], k104_8579a946-2f96-455f-825c-c3f86caba99c.xml, kernel.iocalldriver, wdm/IoCallDriver
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt:
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
req.irql: IRQL <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IoCallDriver
 - wdm/IoCallDriver
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoCallDriver
---

## -description

The **IoCallDriver** routine, wraps **IofCallDriver** that sends an IRP to the driver associated with a specified device object.

Do not call **IofCallDriver**. Call **IoCallDriver** instead. For more information, see [**IofCallDriver**](nf-wdm-iofcalldriver.md).

## -parameters

### -param a [in]

See [**IofCallDriver**](nf-wdm-iofcalldriver.md).

### -param b [in, out]

See [**IofCallDriver**](nf-wdm-iofcalldriver.md).

## -syntax

```cpp
#define IoCallDriver(a,b)   \
        IofCallDriver(a,b)
);
```

## -see-also

See [**IofCallDriver**](nf-wdm-iofcalldriver.md).

[IoAllocateIrp](./nf-wdm-ioallocateirp.md)

[IoBuildAsynchronousFsdRequest](./nf-wdm-iobuildasynchronousfsdrequest.md)

[IoBuildDeviceIoControlRequest](./nf-wdm-iobuilddeviceiocontrolrequest.md)

[IoBuildSynchronousFsdRequest](./nf-wdm-iobuildsynchronousfsdrequest.md)

[IoSetCompletionRoutine](./nf-wdm-iosetcompletionroutine.md)

[PoCallDriver](../ntifs/nf-ntifs-pocalldriver.md)