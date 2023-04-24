---
UID: NC:wdm.IO_COMPLETION_ROUTINE
title: IO_COMPLETION_ROUTINE (wdm.h)
description: The IoCompletion routine completes the processing of I/O operations.
tech.root: kernel
ms.date: 01/09/2023
keywords: ["IO_COMPLETION_ROUTINE callback function"]
ms.keywords: DrvrRtns_aa2b6363-e3c1-4243-87d8-8a1bb575974b.xml, IO_COMPLETION_ROUTINE, IoCompletion, IoCompletion routine [Kernel-Mode Driver Architecture], kernel.iocompletion, wdm/IoCompletion
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
req.irql: Called at IRQL <= DISPATCH_LEVEL (see Remarks section).
targetos: Windows
req.typenames: 
f1_keywords:
 - IO_COMPLETION_ROUTINE
 - wdm/IO_COMPLETION_ROUTINE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdm.h
api_name:
 - IO_COMPLETION_ROUTINE
---

## -description

The *IoCompletion* routine completes the processing of I/O operations.

## -parameters

### -param DeviceObject [in]

Caller-supplied pointer to a [DEVICE_OBJECT](./ns-wdm-_device_object.md) structure. This is the device object for the target device, previously created by the driver's [AddDevice](./nc-wdm-driver_add_device.md) routine.

### -param Irp [in]

Caller-supplied pointer to an [IRP](./ns-wdm-_irp.md) structure that describes the I/O operation.

### -param Context [in, optional]

Caller-supplied pointer to driver-specific context information, previously supplied when calling [IoSetCompletionRoutine](./nf-wdm-iosetcompletionroutine.md) or [IoSetCompletionRoutineEx](./nf-wdm-iosetcompletionroutineex.md). Context information must be stored in nonpaged memory, since an *IoCompletion* routine can be called at DISPATCH_LEVEL. For more information, see the following Remarks section.

## -returns

If the *IoCompletion* routine determines that additional processing is required for the IRP, it must return STATUS_MORE_PROCESSING_REQUIRED. For more information, see the following Remarks section. Otherwise, it should return STATUS_SUCCESS. (The I/O manager only checks for the presence or absence of STATUS_MORE_PROCESSING_REQUIRED.)

## -remarks

A driver's *IoCompletion* routine executes in an arbitrary thread or DPC context, and at an IRQL that is less than or equal to DISPATCH_LEVEL. Because code written to execute at DISPATCH_LEVEL will also execute at lower levels, *IoCompletion* routines should be designed for execution at DISPATCH_LEVEL. However, because these routines are not guaranteed to run at DISPATCH_LEVEL, they must not call system routines that actually require execution at DISPATCH_LEVEL. (For more information about IRQLs, see [Managing Hardware Priorities](/windows-hardware/drivers/kernel/managing-hardware-priorities).)

To register an *IoCompletion* routine for a specific IRP, a driver must call [IoSetCompletionRoutine](./nf-wdm-iosetcompletionroutine.md) or [IoSetCompletionRoutineEx](./nf-wdm-iosetcompletionroutineex.md), which stores the *IoCompletion* routine's address in the next-lower driver's I/O stack location. (Thus, a lowest-level driver cannot register an *IoCompletion* routine.) A driver typically calls **IoSetCompletionRoutine** or **IoSetCompletionRoutineEx** from one of its dispatch routines, each time an IRP is received. Most drivers, including all PnP drivers, can use **IoSetCompletionRoutine** to register their *IoCompletion* routine. Non-PnP drivers that may be unloaded before their *IoCompletion* routine executes should use **IoSetCompletionRoutineEx** instead.

When any driver completes an IRP, it calls [IoCompleteRequest](./nf-wdm-iocompleterequest.md), which in turn calls the *IoCompletion* routine of each higher-level driver, from the next-highest to the highest, until all higher *IoCompletion* routines have been called or until one routine returns STATUS_MORE_PROCESSING_REQUIRED.

When you create the IRP, allocate a stack location for the current driver as well as any lower drivers. If you do not allocate sufficient stack locations, the *DeviceObject* pointer might be set to **NULL** when the completion routine is called. You can avoid allocating extra stack location for the current driver if you use the *Context* field to pass information to *IoCompletion* rather then relying on the *DeviceObject* parameter.

If an *IoCompletion* routine returns STATUS_MORE_PROCESSING_REQUIRED, the lower driver's call to **IoCompleteRequest** immediately returns. In this case, a higher-level driver will have to call **IoCompleteRequest** to complete the IRP.

For more information about implementing *IoCompletion* routines, see [Completing IRPs](/windows-hardware/drivers/kernel/completing-irps).

### Examples

To define an *IoCompletion* callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps [Code Analysis for Drivers](/windows-hardware/drivers/devtest/code-analysis-for-drivers), [Static Driver Verifier](/windows-hardware/drivers/devtest/static-driver-verifier) (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an *IoCompletion* callback routine that is named `MyIoCompletion`, use the IO_COMPLETION_ROUTINE type as shown in this code example:

```cpp
IO_COMPLETION_ROUTINE MyIoCompletion;
```

Then, implement your callback routine as follows:

```cpp
_Use_decl_annotations_
NTSTATUS
  MyIoCompletion(
    PDEVICE_OBJECT  DeviceObject,
    PIRP  Irp,
    PVOID  Context
    )
  {
      // Function body
  }
```

The IO_COMPLETION_ROUTINE function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the `_Use_decl_annotations_` annotation to your function definition. The `_Use_decl_annotations_` annotation ensures that the annotations that are applied to the IO_COMPLETION_ROUTINE function type in the header file are used. For more information about the requirements for function declarations, see [Declaring Functions by Using Function Role Types for WDM Drivers](/windows-hardware/drivers/devtest/declaring-functions-using-function-role-types-for-wdm-drivers). For information about `_Use_decl_annotations_`, see [Annotating Function Behavior](/visualstudio/code-quality/annotating-function-behavior).