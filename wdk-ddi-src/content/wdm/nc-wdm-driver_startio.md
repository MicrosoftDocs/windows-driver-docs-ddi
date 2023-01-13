---
UID: NC:wdm.DRIVER_STARTIO
title: DRIVER_STARTIO (wdm.h)
description: The StartIo routine starts the I/O operation described by an IRP.
tech.root: kernel
ms.date: 01/09/2023
keywords: ["DRIVER_STARTIO callback function"]
ms.keywords: DRIVER_STARTIO, DrvrRtns_3227d9e5-10b6-449f-af47-48574e7a00d5.xml, StartIo, StartIo routine [Kernel-Mode Driver Architecture], kernel.startio, wdm/StartIo
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
req.irql: Called at DISPATCH_LEVEL.
targetos: Windows
req.typenames: 
f1_keywords:
 - DRIVER_STARTIO
 - wdm/DRIVER_STARTIO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdm.h
api_name:
 - DRIVER_STARTIO
---

## -description

The *StartIo* routine starts the I/O operation described by an IRP.

## -parameters

### -param DeviceObject [in, out]

Caller-supplied pointer to a [DEVICE_OBJECT](/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object) structure. This is the device object for the target device, previously created by the driver's [AddDevice](/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_add_device) routine.

### -param Irp [in, out]

Caller-supplied pointer to an [IRP](/windows-hardware/drivers/ddi/wdm/ns-wdm-_irp) structure that describes the requested I/O operation.

## -remarks

A driver's *StartIo* routine executes in an arbitrary thread context at IRQL = DISPATCH_LEVEL.

The *StartIo* routine is optional. A driver's *StartIo* routine, if supplied, should be named *Xxx***StartIo**, where *Xxx* is a driver-specific prefix. The driver's [DriverEntry](/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver) routine must store the *StartIo* routine's address in **DriverObject->DriverStartIo**. (If no routine is supplied, this pointer must be **NULL**.)

A driver can use [IoSetStartIoAttributes](/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iosetstartioattributes) to set attributes on when its *StartIo* routine is called.

For detailed information about implementing a driver's *StartIo* routine, see [Writing a StartIo Routine](/windows-hardware/drivers/kernel/writing-a-startio-routine).

### Examples

To define a *StartIo* callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps [Code Analysis for Drivers](/windows-hardware/drivers/devtest/code-analysis-for-drivers), [Static Driver Verifier](/windows-hardware/drivers/devtest/static-driver-verifier) (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a *StartIo* callback routine that is named `MyStartIo`, use the DRIVER_STARTIO type as shown in this code example:

```cpp
DRIVER_STARTIO MyStartIo;
```

Then, implement your callback routine as follows:

```cpp
_Use_decl_annotations_
VOID
  MyStartIo(
    struct _DEVICE_OBJECT  *DeviceObject,
    struct _IRP  *Irp 
    )
  {
      // Function body
  }
```

The DRIVER_STARTIO function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the `_Use_decl_annotations_` annotation to your function definition. The `_Use_decl_annotations_` annotation ensures that the annotations that are applied to the DRIVER_STARTIO function type in the header file are used. For more information about the requirements for function declarations, see [Declaring Functions by Using Function Role Types for WDM Drivers](/windows-hardware/drivers/devtest/declaring-functions-using-function-role-types-for-wdm-drivers). For information about `_Use_decl_annotations_`, see [Annotating Function Behavior](/visualstudio/code-quality/annotating-function-behavior).
