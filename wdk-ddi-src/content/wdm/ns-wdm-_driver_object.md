---
UID: NS:wdm._DRIVER_OBJECT
title: _DRIVER_OBJECT (wdm.h)
description: Each driver object represents the image of a loaded kernel-mode driver.
old-location: kernel\driver_object.htm
tech.root: kernel
ms.date: 04/30/2018
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
 - DRIVER_OBJECT
---

# _DRIVER_OBJECT structure


## -description

Each driver object represents the image of a loaded kernel-mode driver. A pointer to the driver object is an input parameter to a driver's <a href="/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a>, <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_add_device">AddDevice</a>, and optional <a href="/windows-hardware/drivers/ddi/ntddk/nc-ntddk-driver_reinitialize">Reinitialize</a> routines and to its <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_unload">Unload</a> routine, if any.

A driver object is partially opaque. Driver writers must know about certain members of a driver object to initialize a driver and to unload it if the driver is unloadable. The following members of the driver object are accessible to drivers.

## -struct-fields

### -field Type

### -field Size

### -field DeviceObject

Pointer to the device objects created by the driver. This member is automatically updated when the driver calls <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iocreatedevice">IoCreateDevice</a> successfully. A driver can use this member and the <b>NextDevice</b> member of <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a> to step through a list of all the device objects that the driver created.

### -field Flags

### -field DriverStart

### -field DriverSize

### -field DriverSection

### -field DriverExtension

Pointer to the driver extension. The only accessible member of the driver extension is <b>DriverExtension->AddDevice</b>, into which a driver's <b>DriverEntry</b> routine stores the driver's <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_add_device">AddDevice</a> routine.

### -field DriverName

### -field HardwareDatabase

Pointer to the <b>\Registry\Machine\Hardware</b> path to the hardware configuration information in the registry.

### -field FastIoDispatch

Pointer to a structure defining the driver's fast I/O entry points. This member is used only by FSDs and network transport drivers.

### -field DriverInit

The entry point for the <a href="/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> routine, which is set up by the I/O manager.

### -field DriverStartIo

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_startio">StartIo</a> routine, if any, which is set by the <b>DriverEntry</b> routine when the driver initializes. If a driver has no <i>StartIo</i> routine, this member is <b>NULL</b>.

### -field DriverUnload

The entry point for the driver's <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_unload">Unload</a> routine, if any, which is set by the <b>DriverEntry</b> routine when the driver initializes. If a driver has no <i>Unload</i> routine, this member is <b>NULL</b>.

### -field MajorFunction

A dispatch table consisting of an array of entry points for the driver's <i>DispatchXxx</i> routines. The array's index values are the <b>IRP_MJ_<i>XXX</i></b> values representing each <a href="/windows-hardware/drivers/kernel/irp-major-function-codes">IRP major function code</a>. Each driver must set entry points in this array for the <b>IRP_MJ_<i>XXX</i></b> requests that the driver handles. For more information, see <a href="/windows-hardware/drivers/kernel/writing-dispatch-routines">Writing Dispatch Routines</a>.

To help <a href="/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools, each <i>DispatchXxx</i> routine is declared using the DRIVER_DISPATCH type, as shown in this code example:


```

DRIVER_DISPATCH DispatchXxx;
```

Then, the callback routine is implemented as follows:


```

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

The DRIVER_DISPATCH function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the DRIVER_DISPATCH function type in the header file are used. For more information about the requirements for function declarations, see <a href="/windows-hardware/drivers/devtest/declaring-functions-using-function-role-types-for-wdm-drivers">Declaring Functions by Using Function Role Types for WDM Drivers</a>. For information about _Use_decl_annotations_, see <a href="/visualstudio/code-quality/annotating-function-behavior">Annotating Function Behavior</a>.

## -remarks

Each kernel-mode driver's initialization routine should be named <a href="/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> so the system will load the driver automatically. If this routine's name is something else, the driver writer must define the name of the initialization routine for the linker; otherwise, the system loader or I/O manager cannot find the driver's transfer address. The names of other standard driver routines can be chosen at the discretion of the driver writer.

A driver must set its <i>DispatchXxx</i> entry points in the driver object that is passed in to the <b>DriverEntry</b> routine when the driver is loaded. A device driver must set one or more <i>DispatchXxx</i> entry points for the <b>IRP_MJ_<i>XXX</i></b> that any driver of the same type of device is required to handle. A higher-level driver must set one or more <i>DispatchXxx</i> entry points for all the <b>IRP_MJ_<i>XXX</i></b> that it must pass on to the underlying device driver. Otherwise, a driver is not sent IRPs for any <b>IRP_MJ_<i>XXX</i></b> for which it does not set up a <i>DispatchXxx</i> routine in the driver object. For more information about the set of <b>IRP_MJ_<i>XXX</i></b> that drivers for different types of underlying devices are required to handle, see <a href="/windows-hardware/drivers/kernel/irp-major-function-codes">IRP Major Function Codes</a>.

The <b>DriverEntry</b> routine also sets the driver's <i>AddDevice</i>, <i>StartIo</i> and/or <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_unload">Unload</a> entry points, if any, in the driver object.

The <b>HardwareDatabase</b> string can be used by device drivers to get hardware configuration information from the registry when the driver is loaded. A driver is given read-only access to this string.

The <i>RegistryPath</i> input to the <b>DriverEntry</b> routine points to the <b>\Registry\Machine\System\CurrentControlSet\Services\\<i>DriverName</i></b> key, where the value entry of <i>DriverName</i> identifies the driver. As for the <b>HardwareDatabase</b> in the input driver object, a driver is given read-only access to this string.

Undocumented members within a driver object should be considered inaccessible. Drivers with dependencies on object member locations or on access to undocumented members might not remain portable and interoperable with other drivers over time.

## -see-also

<a href="/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iocreatedevice">IoCreateDevice</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iodeletedevice">IoDeleteDevice</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_startio">StartIo</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_unload">Unload</a>
