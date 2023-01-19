---
UID: NS:wdm._DRIVER_OBJECT
title: DRIVER_OBJECT (wdm.h)
description: Each driver object represents the image of a loaded kernel-mode driver.
tech.root: kernel
ms.date: 01/18/2023
keywords: ["DRIVER_OBJECT structure"]
ms.keywords: "*PDRIVER_OBJECT, DRIVER_OBJECT, DRIVER_OBJECT structure [Kernel-Mode Driver Architecture], PDRIVER_OBJECT, PDRIVER_OBJECT structure pointer [Kernel-Mode Driver Architecture], _DRIVER_OBJECT, kernel.driver_object, kstruct_a_dfe1b66c-d3bf-43ff-b3ee-b6edfd4f1616.xml, wdm/DRIVER_OBJECT, wdm/PDRIVER_OBJECT"
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

Each driver object represents the image of a loaded kernel-mode driver. A pointer to the driver object is an input parameter to a driver's [DriverEntry](/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver), [AddDevice](/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_add_device), and optional [Reinitialize](/windows-hardware/drivers/ddi/ntddk/nc-ntddk-driver_reinitialize) routines and to its [Unload](/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_unload) routine, if any.

A driver object is partially opaque. Driver writers must know about certain members of a driver object to initialize a driver and to unload it if the driver is unloadable. The following members of the driver object are accessible to drivers.

## -struct-fields

### -field Type

Defines the **CSHORT** member **Type**.

### -field Size

Defines the **CSHORT** member **Size**.

### -field DeviceObject

Pointer to the device objects created by the driver. This member is automatically updated when the driver calls [IoCreateDevice](/windows-hardware/drivers/ddi/wdm/nf-wdm-iocreatedevice) successfully. A driver can use this member and the **NextDevice** member of [**DEVICE_OBJECT**](/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object) to step through a list of all the device objects that the driver created.

### -field Flags

Defines the **ULONG** member **Flags**.

### -field DriverStart

Defines the **PVOID** member **DriverStart**.

### -field DriverSize

Defines the **ULONG** member **DriverSize**.

### -field DriverSection

Defines the **PVOID** member **DriverSection**.

### -field DriverExtension

Pointer to the driver extension. The only accessible member of the driver extension is **DriverExtension->AddDevice**, into which a driver's **DriverEntry** routine stores the driver's [AddDevice](/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_add_device) routine.

### -field DriverName

Defines the **UNICODE_STRING** member **DriverName**.

### -field HardwareDatabase

Pointer to the **\Registry\Machine\Hardware** path to the hardware configuration information in the registry.

### -field FastIoDispatch

Pointer to a structure defining the driver's fast I/O entry points. This member is used only by FSDs and network transport drivers.

### -field DriverInit

The entry point for the [DriverEntry](/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver) routine, which is set up by the I/O manager.

### -field DriverStartIo

The entry point for the driver's [StartIo](/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_startio) routine, if any, which is set by the **DriverEntry** routine when the driver initializes. If a driver has no *StartIo* routine, this member is **NULL**.

### -field DriverUnload

The entry point for the driver's [Unload](/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_unload) routine, if any, which is set by the **DriverEntry** routine when the driver initializes. If a driver has no *Unload* routine, this member is **NULL**.

### -field MajorFunction

A dispatch table consisting of an array of entry points for the driver's *DispatchXxx* routines. The array's index values are the **IRP_MJ_*XXX*** values representing each [IRP major function code](/windows-hardware/drivers/kernel/irp-major-function-codes). Each driver must set entry points in this array for the **IRP_MJ_*XXX*** requests that the driver handles. For more information, see [Writing Dispatch Routines](/windows-hardware/drivers/kernel/writing-dispatch-routines).

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

Each kernel-mode driver's initialization routine should be named [DriverEntry](/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver) so the system will load the driver automatically. If this routine's name is something else, the driver writer must define the name of the initialization routine for the linker; otherwise, the system loader or I/O manager cannot find the driver's transfer address. The names of other standard driver routines can be chosen at the discretion of the driver writer.

A driver must set its *DispatchXxx* entry points in the driver object that is passed in to the **DriverEntry** routine when the driver is loaded. A device driver must set one or more *DispatchXxx* entry points for the **IRP_MJ_*XXX*** that any driver of the same type of device is required to handle. A higher-level driver must set one or more *DispatchXxx* entry points for all the **IRP_MJ_*XXX*** that it must pass on to the underlying device driver. Otherwise, a driver is not sent IRPs for any **IRP_MJ_*XXX*** for which it does not set up a *DispatchXxx* routine in the driver object. For more information about the set of **IRP_MJ_*XXX*** that drivers for different types of underlying devices are required to handle, see [IRP Major Function Codes](/windows-hardware/drivers/kernel/irp-major-function-codes).

The **DriverEntry** routine also sets the driver's *AddDevice*, *StartIo* and/or [Unload](/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_unload) entry points, if any, in the driver object.

The **HardwareDatabase** string can be used by device drivers to get hardware configuration information from the registry when the driver is loaded. A driver is given read-only access to this string.

The *RegistryPath* input to the **DriverEntry** routine points to the **\Registry\Machine\System\CurrentControlSet\Services\\*DriverName*** key, where the value entry of *DriverName* identifies the driver. As for the **HardwareDatabase** in the input driver object, a driver is given read-only access to this string.

Undocumented members within a driver object should be considered inaccessible. Drivers with dependencies on object member locations or on access to undocumented members might not remain portable and interoperable with other drivers over time.

## -see-also

[DriverEntry](/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver)

[IoCreateDevice](/windows-hardware/drivers/ddi/wdm/nf-wdm-iocreatedevice)

[IoDeleteDevice](/windows-hardware/drivers/ddi/wdm/nf-wdm-iodeletedevice)

[StartIo](/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_startio)

[Unload](/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_unload)
