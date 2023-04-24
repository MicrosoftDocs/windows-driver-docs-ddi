---
UID: NC:wdm.DRIVER_ADD_DEVICE
title: DRIVER_ADD_DEVICE (wdm.h)
description: The AddDevice routine is responsible for creating functional device objects (FDO) or filter device objects (filter DO) for devices enumerated by the Plug and Play (PnP) manager.
tech.root: kernel
ms.date: 01/09/2023
keywords: ["DRIVER_ADD_DEVICE callback function"]
ms.keywords: AddDevice, AddDevice routine [Kernel-Mode Driver Architecture], DRIVER_ADD_DEVICE, DrvrRtns_a1c3dd70-7910-44e8-bca8-44b48cf6db04.xml, kernel.adddevice, wdm/AddDevice
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
req.irql: Called at PASSIVE_LEVEL (see Remarks section).
targetos: Windows
req.typenames: 
f1_keywords:
 - DRIVER_ADD_DEVICE
 - wdm/DRIVER_ADD_DEVICE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdm.h
api_name:
 - DRIVER_ADD_DEVICE
---

## -description

The *AddDevice* routine is responsible for creating functional device objects (FDO) or filter device objects (filter DO) for devices enumerated by the Plug and Play (PnP) manager.

## -parameters

### -param DriverObject [in]

Caller-supplied pointer to a [DRIVER_OBJECT](./ns-wdm-_driver_object.md) structure. This is the driver's driver object.

### -param PhysicalDeviceObject [in]

Caller-supplied pointer to a [DEVICE_OBJECT](./ns-wdm-_device_object.md) structure representing a physical device object (PDO) created by a lower-level driver.

## -returns

If the routine succeeds, it must return STATUS_SUCCESS. Otherwise, it must return one of the error status values defined in Ntstatus.h.

## -remarks

All kernel-mode drivers that support PnP must provide an *AddDevice* routine.

A driver's *AddDevice* routine should be named *Xxx*AddDevice, where *Xxx* is a driver-specific prefix. The driver's [DriverEntry](/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver) routine must store the *AddDevice* routine's address in **DriverObject->DriverExtension->AddDevice**.

An *AddDevice* routine's primary responsibilities are calling [IoCreateDevice](./nf-wdm-iocreatedevice.md) to create a device object, then calling [IoAttachDeviceToDeviceStack](./nf-wdm-ioattachdevicetodevicestack.md) to attach the device object to the device stack. For detailed information about implementing a driver's *AddDevice* routine, see [Writing an AddDevice Routine](/windows-hardware/drivers/kernel/writing-an-adddevice-routine).

An *AddDevice* routine runs in a system thread context at IRQL = PASSIVE_LEVEL.

### Examples

To define an *AddDevice* callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps [Code Analysis for Drivers](/windows-hardware/drivers/devtest/code-analysis-for-drivers), [Static Driver Verifier](/windows-hardware/drivers/devtest/static-driver-verifier) (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an *AddDevice* callback routine that is named `MyAddDevice<`, use the DRIVER_ADD_DEVICE type as shown in this code example:

```cpp
DRIVER_ADD_DEVICE MyAddDevice;
```

Then, implement your callback routine as follows:

```cpp
_Use_decl_annotations_
NTSTATUS
  MyAddDevice(
    struct _DRIVER_OBJECT  *DriverObject,
    struct _DEVICE_OBJECT  *PhysicalDeviceObject 
    )
  {
      // Function body
  }
```

The DRIVER_ADD_DEVICE function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the `_Use_decl_annotations_` annotation to your function definition. The `_Use_decl_annotations_` annotation ensures that the annotations that are applied to the DRIVER_ADD_DEVICE function type in the header file are used. For more information about the requirements for function declarations, see [Declaring Functions by Using Function Role Types for WDM Drivers](/windows-hardware/drivers/devtest/declaring-functions-using-function-role-types-for-wdm-drivers). For information about `_Use_decl_annotations_`, see [Annotating Function Behavior](/visualstudio/code-quality/annotating-function-behavior).