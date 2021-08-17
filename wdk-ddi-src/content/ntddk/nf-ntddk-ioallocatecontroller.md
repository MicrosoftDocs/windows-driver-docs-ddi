---
UID: NF:ntddk.IoAllocateController
title: IoAllocateController function (ntddk.h)
description: The IoAllocateController routine sets up the call to a driver-supplied ControllerControl routine as soon as the device controller, represented by the given controller object, is available to carry out an I/O operation for the target device, represented by the given device object.
old-location: kernel\ioallocatecontroller.htm
tech.root: kernel
ms.date: 07/30/2021
keywords: ["IoAllocateController function"]
ms.keywords: IoAllocateController, IoAllocateController routine [Kernel-Mode Driver Architecture], k104_b550c6ff-9d5c-4497-98bb-6781b4e6abd8.xml, kernel.ioallocatecontroller, ntddk/IoAllocateController
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlDispatch, HwStorPortProhibitedDDIs, IrqlDispatch(storport), SpNoWait, StorPortStartIo
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IoAllocateController
 - ntddk/IoAllocateController
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoAllocateController
---

# IoAllocateController function

## -description

The **IoAllocateController** routine sets up the call to a driver-supplied [ControllerControl](/windows-hardware/drivers/kernel/writing-controllercontrolroutines) routine as soon as the device controller, represented by the given controller object, is available to carry out an I/O operation for the target device, represented by the given device object.

## -parameters

### -param ControllerObject

[in]
Pointer to a driver-created controller object, usually representing a physical controller to be allocated for an I/O operation on an attached device.

### -param DeviceObject

[in]
Pointer to the device object, representing the target device of the current IRP.

### -param ExecutionRoutine

[in]
Pointer to the driver-supplied [ControllerControl](/windows-hardware/drivers/kernel/writing-controllercontrolroutines) routine.

### -param Context

[in, optional]
Pointer to a driver-determined context, passed to the driver's *ControllerControl* routine when it is called.

## -remarks

This routine reserves exclusive access to the hardware controller for the specified device.

The [ControllerControl](/windows-hardware/drivers/kernel/writing-controllercontrolroutines) routine returns a value indicating whether the controller remains allocated to the device, either **DeallocateObject** or **KeepObject**. If it returns **KeepObject**, the driver must subsequently call **IoFreeController** to release the controller object.

## -see-also

[ControllerControl](/windows-hardware/drivers/kernel/writing-controllercontrolroutines)

[IoCreateController](./nf-ntddk-iocreatecontroller.md)

[IoDeleteController](./nf-ntddk-iodeletecontroller.md)

[IoFreeController](./nf-ntddk-iofreecontroller.md)