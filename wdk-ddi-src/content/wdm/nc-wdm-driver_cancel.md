---
UID: NC:wdm.DRIVER_CANCEL
title: DRIVER_CANCEL (wdm.h)
description: The Cancel routine cancels an I/O operation.
tech.root: kernel
ms.date: 01/09/2023
keywords: ["DRIVER_CANCEL callback function"]
ms.keywords: Cancel, Cancel routine [Kernel-Mode Driver Architecture], DRIVER_CANCEL, DrvrRtns_790a0e91-0752-42ac-a5f0-4fee193765f0.xml, kernel.cancel, wdm/Cancel
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Called at DISPATCH_LEVEL (see Remarks section).
targetos: Windows
req.typenames: 
f1_keywords:
 - DRIVER_CANCEL
 - wdm/DRIVER_CANCEL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdm.h
api_name:
 - DRIVER_CANCEL
---

## -description

The *Cancel* routine cancels an I/O operation.

## -parameters

### -param DeviceObject [in, out]

Caller-supplied pointer to a [DEVICE_OBJECT](./ns-wdm-_device_object.md) structure. This is the device object for the target device, previously created by the driver's [AddDevice](./nc-wdm-driver_add_device.md) routine.

### -param Irp [in, out]

Caller-supplied pointer to an [IRP](./ns-wdm-_irp.md) structure that describes the I/O operation to be canceled.

## -remarks

When a driver or other system component calls [IoCancelIrp](./nf-wdm-iocancelirp.md), the I/O manager calls the IRP's *Cancel* routine, if one has been registered for the IRP.

To register a *Cancel* routine for an IRP, a driver can use either of the following two methods:

1. A driver that provides a [StartIo](./nc-wdm-driver_startio.md) routine and uses the I/O manager-supplied device queue can specify a *Cancel* routine when calling [IoStartPacket](../ntifs/nf-ntifs-iostartpacket.md).

1. A driver that creates and manages supplemental device queues can register a *Cancel* routine by calling [IoSetCancelRoutine](./nf-wdm-iosetcancelroutine.md).

Only one *Cancel* routine can be registered for an IRP at one time.

The I/O manager calls [IoAcquireCancelSpinLock](/previous-versions/windows/hardware/drivers/ff548196(v=vs.85)) before calling a driver's *Cancel* routine, so the *Cancel* routine must call [IoReleaseCancelSpinLock](/previous-versions/windows/hardware/drivers/ff549550(v=vs.85)) at some point. The routine should not hold the spin lock longer than necessary.

The *Cancel* routine executes in an arbitrary thread context at IRQL = DISPATCH_LEVEL until it calls **IoReleaseCancelSpinLock**, which changes the IRQL to a caller-supplied value. The driver should specify **Irp->CancelIrql** for this value.

The *Cancel* routine must set the I/O status block's **Status** member to STATUS_CANCELLED, and set its **Information** member to zero. The routine must then complete the specified IRP by calling [IoCompleteRequest](./nf-wdm-iocompleterequest.md).

For detailed information about implementing a driver's *Cancel* routine, see [Canceling IRPs](/windows-hardware/drivers/kernel/canceling-irps).

### Examples

To define a *Cancel* callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps [Code Analysis for Drivers](/windows-hardware/drivers/devtest/code-analysis-for-drivers), [Static Driver Verifier](/windows-hardware/drivers/devtest/static-driver-verifier) (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a *Cancel* callback routine that is named `MyCancel`, use the DRIVER_CANCEL type as shown in this code example:

```cpp
DRIVER_CANCEL MyCancel;
```

Then, implement your callback routine as follows:

```cpp
_Use_decl_annotations_
VOID
  MyCancel(
    struct _DEVICE_OBJECT  *DeviceObject,
    struct _IRP  *Irp
    )
  {
      // Function body
  }
```

The DRIVER_CANCEL function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the `_Use_decl_annotations_` annotation to your function definition. The `_Use_decl_annotations_` annotation ensures that the annotations that are applied to the DRIVER_CANCEL function type in the header file are used. For more information about the requirements for function declarations, see [Declaring Functions by Using Function Role Types for WDM Drivers](/windows-hardware/drivers/devtest/declaring-functions-using-function-role-types-for-wdm-drivers). For information about `_Use_decl_annotations_`, see [Annotating Function Behavior](/visualstudio/code-quality/annotating-function-behavior).