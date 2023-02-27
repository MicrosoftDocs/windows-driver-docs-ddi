---
UID: NC:wdm.IO_TIMER_ROUTINE
title: IO_TIMER_ROUTINE (wdm.h)
description: The IoTimer routine is a DPC that, if registered, is called once per second.
tech.root: kernel
ms.date: 01/09/2023
keywords: ["IO_TIMER_ROUTINE callback function"]
ms.keywords: DrvrRtns_e0e54c40-37d6-41b3-8374-b1a7763d54ed.xml, IO_TIMER_ROUTINE, IoTimer, IoTimer routine [Kernel-Mode Driver Architecture], kernel.iotimer, wdm/IoTimer
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
 - IO_TIMER_ROUTINE
 - wdm/IO_TIMER_ROUTINE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdm.h
api_name:
 - IO_TIMER_ROUTINE
---

## -description

The *IoTimer* routine is a DPC that, if registered, is called once per second.

## -parameters

### -param DeviceObject [in]

Caller-supplied pointer to a [DEVICE_OBJECT](./ns-wdm-_device_object.md) structure. This is the device object for the target device, previously created by the driver's [AddDevice](./nc-wdm-driver_add_device.md) routine.

### -param Context [in, optional]

Caller-supplied pointer to driver-defined context information, specified in a previous call to [IoInitializeTimer](./nf-wdm-ioinitializetimer.md).

## -remarks

A driver's *IoTimer* routine executes in a DPC context, at IRQL = DISPATCH_LEVEL.

A driver can associate an *IoTimer* routine with each device object it creates. (You can use a single *IoTimer* routine with multiple device objects, or a separate routine with each device object.) To register an *IoTimer* routine, a driver must call [IoInitializeTimer](./nf-wdm-ioinitializetimer.md), supplying the *IoTimer* routine's address and a device object pointer.

To queue an *IoTimer* routine for execution, a driver routine must call [IoStartTimer](../ntifs/nf-ntifs-iostarttimer.md). The system calls the *IoTimer* routine once per second until the driver calls [IoStopTimer](../ntifs/nf-ntifs-iostoptimer.md).

For more information about *IoTimer* routines, see [IoTimer Routines](/windows-hardware/drivers/kernel/iotimer-routines).

### Examples

To define an *IoTimer* callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps [Code Analysis for Drivers](/windows-hardware/drivers/devtest/code-analysis-for-drivers), [Static Driver Verifier](/windows-hardware/drivers/devtest/static-driver-verifier) (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an *IoTimer* callback routine that is named `MyIoTimer`, use the IO_TIMER_ROUTINE type as shown in this code example:

```cpp
IO_TIMER_ROUTINE MyIoTimer;
```

Then, implement your callback routine as follows:

```cpp
_Use_decl_annotations_
VOID
  MyIoTimer(
    struct DEVICE_OBJECT  *DeviceObject,
    PVOID  Context
    )
  {
      // Function body
  }
```

The IO_TIMER_ROUTINE function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the `_Use_decl_annotations_` annotation to your function definition. The `_Use_decl_annotations_` annotation ensures that the annotations that are applied to the IO_TIMER_ROUTINE function type in the header file are used. For more information about the requirements for function declarations, see [Declaring Functions by Using Function Role Types for WDM Drivers](/windows-hardware/drivers/devtest/declaring-functions-using-function-role-types-for-wdm-drivers). For information about `_Use_decl_annotations_`, see [Annotating Function Behavior](/visualstudio/code-quality/annotating-function-behavior).