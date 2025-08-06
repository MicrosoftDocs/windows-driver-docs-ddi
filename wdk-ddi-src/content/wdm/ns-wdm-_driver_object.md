---
UID: NS:wdm._DRIVER_OBJECT
title: DRIVER_OBJECT (wdm.h)
description: Each driver object represents the image of a loaded kernel-mode driver.
tech.root: kernel
ms.date: 07/31/2025
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
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
req.irql: 
targetos: Windows
req.typenames: DRIVER_OBJECT, *PDRIVER_OBJECT
f1_keywords:
 - _DRIVER_OBJECT
 - wdm/_DRIVER_OBJECT
 - PDRIVER_OBJECT
 - wdm/PDRIVER_OBJECT
 - DRIVER_OBJECT
 - wdm/DRIVER_OBJECT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - _DRIVER_OBJECT
 - PDRIVER_OBJECT
 - DRIVER_OBJECT
---

## -description

Each driver object represents the image of a loaded kernel-mode driver. The I/O manager allocates the **DRIVER_OBJECT** structure and passes it as an input parameter to a driver's [DriverEntry](nc-wdm-driver_initialize.md), [AddDevice](nc-wdm-driver_add_device.md), and optional [Reinitialize](../ntddk/nc-ntddk-driver_reinitialize.md) routines and to its [Unload](nc-wdm-driver_unload.md) routine, if any.

A driver object is partially opaque. Driver writers must know about certain members of a driver object to initialize a driver and to unload it if the driver is unloadable. The following members of the driver object are accessible to drivers.

## -struct-fields

### -field Type

Specifies the object type identifier for the driver object. The I/O manager sets this field when it allocates the driver object. Drivers shouldn't use or modify this field.

### -field Size

Specifies the size, in bytes, of the driver object structure. The I/O manager sets this field when it allocates the driver object. Drivers shouldn't use or modify this field.

### -field DeviceObject

Pointer to the first device object in a linked list of device objects created by the driver. This field links all devices created by a single driver together on a list. This member is automatically updated by the I/O manager when the driver calls [IoCreateDevice](./nf-wdm-iocreatedevice.md) successfully. A driver can use this member and the **NextDevice** member of [**DEVICE_OBJECT**](./ns-wdm-_device_object.md) to traverse the complete list of all device objects that the driver has created. This is particularly useful during driver unload to ensure all device objects are properly cleaned up.

### -field Flags

Contains system-defined flags that describe various attributes and states of the driver. This field provides an extensible flag location for driver objects. These flags are set and maintained by the I/O manager and other system components.  Drivers should not directly modify this field.

### -field DriverStart

Points to the base virtual address where the driver image is loaded in system memory. This address represents the beginning of the driver's code section in the kernel address space. The I/O manager sets this value when the driver is loaded.

### -field DriverSize

Specifies the size, in bytes, of the driver image in memory. This value represents the total memory footprint of the loaded driver, including code, data, and other sections. The I/O manager sets this value when the driver is loaded.

### -field DriverSection

Points to the driver's section object, which represents the driver image in the memory manager. This is an opaque system structure used internally by the memory manager and loader. Drivers should not access or modify this member.

### -field DriverExtension

Pointer to the driver extension. The only accessible member of the driver extension is **DriverExtension->AddDevice**, into which a driver's **DriverEntry** routine stores the driver's [AddDevice](./nc-wdm-driver_add_device.md) routine.

### -field DriverName

Contains the Unicode string name of the driver. This field is used by the error log thread to determine the name of the driver that an I/O request is or was bound to. This is typically of the form *\\Driver\\DriverName*, where *DriverName* corresponds to the driver's service name in the registry. The I/O manager sets this value based on the driver's registry configuration.

### -field HardwareDatabase

Pointer to the **\Registry\Machine\Hardware** path to the hardware configuration information in the registry.

### -field FastIoDispatch

Pointer to a [FAST_IO_DISPATCH](ns-wdm-_fast_io_dispatch.md) structure defining the driver's fast I/O entry points. This optional pointer points to an array of alternate entry points to a driver for "fast I/O" support. Fast I/O is performed by invoking the driver routine directly with separate parameters, rather than using the standard IRP call mechanism. Note that these functions may only be used for synchronous I/O, and when the file is cached. This member is used only by file system drivers (FSDs) and network transport drivers.

### -field DriverInit

The entry point address for the driver's [DriverEntry](nc-wdm-driver_initialize.md) routine. The I/O manager sets this field to point to the driver's initialization function when the driver is loaded. This is the first function called in the driver when it is loaded into memory, and it is responsible for initializing the driver object and setting up dispatch routines.

### -field DriverStartIo

The entry point for the driver's [StartIo](./nc-wdm-driver_startio.md) routine, if any, which is set by the **DriverEntry** routine when the driver initializes. If a driver has no *StartIo* routine, this member is **NULL**.

### -field DriverUnload

The entry point for the driver's [Unload](./nc-wdm-driver_unload.md) routine, if any, which is set by the **DriverEntry** routine when the driver initializes. If a driver has no *Unload* routine, this member is **NULL**.

### -field MajorFunction

A dispatch table consisting of an array of entry points for the driver's *DispatchXxx* routines. The array's index values are the **IRP_MJ_*XXX*** values representing each [IRP major function code](/windows-hardware/drivers/kernel/irp-major-function-codes). This major function dispatch table must be the last field in the object so that it remains extensible. Each driver must set entry points in this array for the **IRP_MJ_*XXX*** requests that the driver handles. For more information, see [Writing Dispatch Routines](/windows-hardware/drivers/kernel/writing-dispatch-routines).

To help [Code Analysis for Drivers](/windows-hardware/drivers/devtest/code-analysis-for-drivers), [Static Driver Verifier](/windows-hardware/drivers/devtest/static-driver-verifier) (SDV), and other verification tools, each *DispatchXxx* routine is declared using the DRIVER_DISPATCH type, as shown in this code example:

```cpp
DRIVER_DISPATCH DispatchXxx;
```

Then, the callback routine is implemented as follows:

```cpp
_Use_decl_annotations_
NTSTATUS
  DispatchXxx(
    struct _DEVICE_OBJECT  *DeviceObject,
    struct _IRP  *Irp
    )
  {
      // Function body
  }
```

The DRIVER_DISPATCH function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the `_Use_decl_annotations`_ annotation to your function definition. The `_Use_decl_annotations_` annotation ensures that the annotations that are applied to the DRIVER_DISPATCH function type in the header file are used. For more information about the requirements for function declarations, see [Declaring Functions by Using Function Role Types for WDM Drivers](/windows-hardware/drivers/devtest/declaring-functions-using-function-role-types-for-wdm-drivers). For information about `_Use_decl_annotations_`, see [Annotating Function Behavior](/visualstudio/code-quality/annotating-function-behavior).

## -remarks

Each kernel-mode driver's initialization routine should be named [**DriverEntry**](/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver) so the system will load the driver automatically. If this routine's name is something else, the driver writer must define the name of the initialization routine for the linker; otherwise, the system loader or I/O manager can't find the driver's transfer address. The names of other standard driver routines can be chosen at the discretion of the driver writer.

A driver must set its *DispatchXxx* entry points in the driver object that is passed in to the **DriverEntry** routine when the driver is loaded. A device driver must set one or more *DispatchXxx* entry points for the **IRP_MJ_*XXX*** that any driver of the same type of device is required to handle. A higher-level driver must set one or more *DispatchXxx* entry points for all the **IRP_MJ_*XXX*** that it must pass on to the underlying device driver. Otherwise, a driver is not sent IRPs for any **IRP_MJ_*XXX*** for which it does not set up a *DispatchXxx* routine in the driver object. For more information about the set of **IRP_MJ_*XXX*** that drivers for different types of underlying devices are required to handle, see [IRP Major Function Codes](/windows-hardware/drivers/kernel/irp-major-function-codes).

The **DriverEntry** routine also sets the driver's *AddDevice*, *StartIo* and/or [Unload](./nc-wdm-driver_unload.md) entry points, if any, in the driver object.

The **HardwareDatabase** string can be used by device drivers to get hardware configuration information from the registry when the driver is loaded. A driver is given read-only access to this string.

The *RegistryPath* input to the **DriverEntry** routine points to the **\Registry\Machine\System\CurrentControlSet\Services\\*DriverName*** key, where the value entry of *DriverName* identifies the driver. This registry key contains the driver's service configuration, including values such as:

- **Start**: When the driver should be loaded (boot, system, automatic, demand, or disabled)
- **Type**: The type of service (kernel driver, file system driver, etc.)
- **ErrorControl**: How the system should respond if the driver fails to load
- **ImagePath**: The path to the driver binary file

Drivers can store additional configuration data under the **Parameters** subkey of their service key. As for the **HardwareDatabase** in the input driver object, a driver is given read-only access to this string.

Undocumented members within a driver object should be considered inaccessible. Drivers with dependencies on object member locations or on access to undocumented members might not remain portable and interoperable with other drivers over time.

## -see-also

[DriverEntry](/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver)

[IoCreateDevice](./nf-wdm-iocreatedevice.md)

[IoDeleteDevice](./nf-wdm-iodeletedevice.md)

[StartIo](./nc-wdm-driver_startio.md)

[Unload](./nc-wdm-driver_unload.md)
