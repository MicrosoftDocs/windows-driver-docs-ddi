---
UID: NF:wdm.IoSetCancelRoutine
title: IoSetCancelRoutine function (wdm.h)
description: The IoSetCancelRoutine routine sets up a driver-supplied Cancel routine to be called if a given IRP is canceled.
tech.root: kernel
ms.date: 01/12/2023
keywords: ["IoSetCancelRoutine function"]
ms.keywords: IoSetCancelRoutine, IoSetCancelRoutine routine [Kernel-Mode Driver Architecture], k104_a9ac44bc-fe8a-4392-b9f8-d9a90a03fbc0.xml, kernel.iosetcancelroutine, wdm/IoSetCancelRoutine
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt:
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrpCancelField, StartIoCancel
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: DISPATCH_LEVEL (see Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - IoSetCancelRoutine
 - wdm/IoSetCancelRoutine
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoSetCancelRoutine
---

## -description

The **IoSetCancelRoutine** routine sets up a driver-supplied [Cancel](./nc-wdm-driver_cancel.md) routine to be called if a given IRP is canceled.

## -parameters

### -param Irp [in]

Pointer to the IRP being put into or removed from a cancelable state.

### -param CancelRoutine [in]

Specifies the entry point of the caller-supplied [Cancel](./nc-wdm-driver_cancel.md) routine to be called if the specified IRP is canceled or is **NULL** if the given IRP is being removed from the cancelable state. This routine is declared as follows:

```cpp
VOID
(*PDRIVER_CANCEL)(
    IN PDEVICE_OBJECT DeviceObject,
    IN PIRP Irp
    );
```

## -returns

**IoSetCancelRoutine** returns the previous value of *Irp*->**CancelRoutine**. If no *Cancel* routine was previously set, or if IRP cancellation is already in progress, **IoSetCancelRoutine** returns **NULL**.

## -remarks

This routine can disable the *Cancel* routine currently set in an IRP.

A driver must hold the system cancel spin lock when calling this routine if the driver uses the I/O manager-supplied device queue in the device object. The driver runs at IRQL = DISPATCH_LEVEL after calling [IoAcquireCancelSpinLock](/previous-versions/windows/hardware/drivers/ff548196(v=vs.85)) until it releases the cancel spin lock with [IoReleaseCancelSpinLock](/previous-versions/windows/hardware/drivers/ff549550(v=vs.85)).

If the driver manages its own queues of IRPs, then the driver need not hold the cancel spin lock when calling this routine. **IoSetCancelRoutine** uses an interlocked exchange intrinsic to set the address of the *Cancel* routine as an atomic operation. Reduced usage of the cancel spin lock can improve driver performance and overall system performance.

Driver *Cancel* routines are called at IRQL = DISPATCH_LEVEL with the cancel spin lock held. The *Cancel* routine must release the cancel spin lock before it returns control.

## -see-also

[IoAcquireCancelSpinLock](/previous-versions/windows/hardware/drivers/ff548196(v=vs.85))

[IoReleaseCancelSpinLock](/previous-versions/windows/hardware/drivers/ff549550(v=vs.85))