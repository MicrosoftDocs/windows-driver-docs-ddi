---
UID: NC:wdm.DRIVER_STARTIO
title: DRIVER_STARTIO (wdm.h)
description: The StartIo routine starts the I/O operation described by an IRP.
old-location: kernel\startio.htm
tech.root: kernel
ms.date: 04/30/2018
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
 - StartIo
---

# DRIVER_STARTIO callback function


## -description

The <i>StartIo</i> routine starts the I/O operation described by an IRP.

## -parameters

### -param DeviceObject 

[in, out]
Caller-supplied pointer to a <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a> structure. This is the device object for the target device, previously created by the driver's <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_add_device">AddDevice</a> routine.

### -param Irp 

[in, out]
Caller-supplied pointer to an <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_irp">IRP</a> structure that describes the requested I/O operation.

## -remarks

A driver's <i>StartIo</i> routine executes in an arbitrary thread context at IRQL = DISPATCH_LEVEL.

The <i>StartIo</i> routine is optional. A driver's <i>StartIo</i> routine, if supplied, should be named <i>Xxx</i><b>StartIo</b>, where <i>Xxx</i> is a driver-specific prefix. The driver's <a href="/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> routine must store the <i>StartIo</i> routine's address in <b>DriverObject->DriverStartIo</b>. (If no routine is supplied, this pointer must be <b>NULL</b>.)

A driver can use <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iosetstartioattributes">IoSetStartIoAttributes</a> to set attributes on when its <i>StartIo</i> routine is called.

For detailed information about implementing a driver's <i>StartIo</i> routine, see <a href="/windows-hardware/drivers/kernel/writing-a-startio-routine">Writing a StartIo Routine</a>.


#### Examples

To define a <i>StartIo</i> callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>StartIo</i> callback routine that is named <code>MyStartIo</code>, use the DRIVER_STARTIO type as shown in this code example:


```
DRIVER_STARTIO MyStartIo;
```

Then, implement your callback routine as follows:


```
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

The DRIVER_STARTIO function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the DRIVER_STARTIO function type in the header file are used. For more information about the requirements for function declarations, see <a href="/windows-hardware/drivers/devtest/declaring-functions-using-function-role-types-for-wdm-drivers">Declaring Functions by Using Function Role Types for WDM Drivers</a>. For information about _Use_decl_annotations_, see <a href="/visualstudio/code-quality/annotating-function-behavior">Annotating Function Behavior</a>.

<div class="code"></div>
