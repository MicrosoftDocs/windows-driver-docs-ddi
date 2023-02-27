---
UID: NC:wdm.DRIVER_CONTROL
title: DRIVER_CONTROL (wdm.h)
description: This routine starts a DMA data-transfer or a data transfer operation.
tech.root: kernel
ms.date: 01/11/2023
keywords: ["DRIVER_CONTROL callback function"]
ms.keywords: AdapterControl, ControllerControl, DRIVER_CONTROL, DrvrRtns_1e3fb66d-8977-4894-a3ac-d310fdfa6515.xml, MyControl, MyControl routine [Kernel-Mode Driver Architecture], kernel.adaptercontrol, wdm/MyControl
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
 - DRIVER_CONTROL
 - wdm/DRIVER_CONTROL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdm.h
api_name:
 - DRIVER_CONTROL
---

## -description

This routine starts a DMA data-transfer or a data transfer operation.

## -parameters

### -param DeviceObject [in]

Caller-supplied pointer to a [**DEVICE_OBJECT**](./ns-wdm-_device_object.md) structure. This is the device object for the target device, previously created by the driver's *AddDevice* routine.

### -param Irp [in, out]

Caller-supplied pointer to an [IRP](./ns-wdm-_irp.md) structure. *Irp* is equal to the value of the **CurrentIrp** member of *DeviceObject* when the callback routine was registered.

### -param MapRegisterBase [in]

In the case of *AdapterControl*, this is a caller-supplied opaque value that represents  the map registers that the system has assigned for this transfer operation. The driver passes this value to [FlushAdapterBuffers](./nc-wdm-pflush_adapter_buffers.md), [FreeMapRegisters](./nc-wdm-pfree_map_registers.md), and [MapTransfer](./nc-wdm-pmap_transfer.md).

In the case of *ControllerControl*, this is not used.

### -param Context [in]

Caller-supplied pointer to driver-defined context information, specified in a previous call to [AllocateAdapterChannel](./nc-wdm-pallocate_adapter_channel.md).

## -returns

The routine must return one of the values defined by the [IO_ALLOCATION_ACTION](./ne-wdm-_io_allocation_action.md) enumeration. Drivers of bus-master devices return either **DeallocateObject** or **DeallocateObjectKeepRegisters**; drivers that use system DMA return **KeepObject**.

## -remarks

To register an *AdapterControl* routine for a specific device object, a driver must call [IoGetDmaAdapter](./nf-wdm-iogetdmaadapter.md) to obtain an adapter object, then call [AllocateAdapterChannel](./nc-wdm-pallocate_adapter_channel.md) to request use of the adapter and to supply the *AdapterControl* routine's address. When the adapter is free, the system calls the *AdapterControl* routine.

If *AdapterControl* has been registered by a [StartIo](./nc-wdm-driver_startio.md) routine, then the *Irp* parameter is guaranteed to point to the IRP currently being processed by the *StartIo* routine. Otherwise, drivers must set the **CurrentIrp** member of the device object structure before calling **AllocateAdapterChannel**.

For detailed information about implementing an *AdapterControl* routine, see [Writing AdapterControl Routines](/windows-hardware/drivers/kernel/writing-adaptercontrol-routines).

A driver's *ControllerControl* routine executes in an arbitrary thread context at IRQL = DISPATCH_LEVEL.

To register a *ControllerControl* routine for a specific device object, a driver must call [IoCreateController](../ntddk/nf-ntddk-iocreatecontroller.md) to obtain a controller object, then call [IoAllocateController](../ntddk/nf-ntddk-ioallocatecontroller.md) to request use of the controller and to supply the *ControllerControl* routine's address. When the controller is free, the system calls the *ControllerControl* routine.

For detailed information about implementing a *ControllerControl* routine, see [Writing ControllerControl Routines](/windows-hardware/drivers/kernel/writing-controllercontrolroutines). Also see [Controller Objects](/windows-hardware/drivers/kernel/using-controller-objects).

The DRIVER_CONTROL function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the `_Use_decl_annotations_` annotation to your function definition. The `_Use_decl_annotations_` annotation ensures that the annotations that are applied to the DRIVER_CONTROL function type in the header file are used. For more information about the requirements for function declarations, see [Declaring Functions by Using Function Role Types for WDM Drivers](/windows-hardware/drivers/devtest/declaring-functions-using-function-role-types-for-wdm-drivers). For information about `_Use_decl_annotations_`, see [Annotating Function Behavior](/visualstudio/code-quality/annotating-function-behavior).

### Examples

To define a callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps [Code Analysis for Drivers](/windows-hardware/drivers/devtest/code-analysis-for-drivers), [Static Driver Verifier](/windows-hardware/drivers/devtest/static-driver-verifier) (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an *AdapterControl* callback routine that is named `MyAdapterControl`, use the DRIVER_CONTROL type as shown in this code example:

```cpp
DRIVER_CONTROL MyAdapterControl;
```

Then, implement your callback routine as follows:

```cpp
_Use_decl_annotations_
IO_ALLOCATION_ACTION
 MyAdapterControl(
    struct _DEVICE_OBJECT  *DeviceObject,
    struct _IRP  *Irp,
    PVOID  MapRegisterBase,
    PVOID  Context
    )
  {
      // Function body
  }
```

## -see-also

[AllocateAdapterChannel](./nc-wdm-pallocate_adapter_channel.md)