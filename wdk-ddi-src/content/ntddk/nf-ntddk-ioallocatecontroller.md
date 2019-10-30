---
UID: NF:ntddk.IoAllocateController
title: IoAllocateController function (ntddk.h)
description: The IoAllocateController routine sets up the call to a driver-supplied ControllerControl routine as soon as the device controller, represented by the given controller object, is available to carry out an I/O operation for the target device, represented by the given device object.
old-location: kernel\ioallocatecontroller.htm
tech.root: kernel
ms.assetid: bfeec8b1-48fb-420e-b602-699a5f2d659a
ms.date: 04/30/2018
ms.keywords: IoAllocateController, IoAllocateController routine [Kernel-Mode Driver Architecture], k104_b550c6ff-9d5c-4497-98bb-6781b4e6abd8.xml, kernel.ioallocatecontroller, ntddk/IoAllocateController
ms.topic: function
f1_keywords:
 - "ntddk/IoAllocateController"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- IoAllocateController
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoAllocateController function


## -description


The <b>IoAllocateController</b> routine sets up the call to a driver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff542049">ControllerControl</a> routine as soon as the device controller, represented by the given controller object, is available to carry out an I/O operation for the target device, represented by the given device object.


## -parameters




### -param ControllerObject [in]

Pointer to a driver-created controller object, usually representing a physical controller to be allocated for an I/O operation on an attached device.


### -param DeviceObject [in]

Pointer to the device object, representing the target device of the current IRP.


### -param ExecutionRoutine [in]

Pointer to the driver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff542049">ControllerControl</a> routine.


### -param Context [in, optional]

Pointer to a driver-determined context, passed to the driver's <i>ControllerControl</i> routine when it is called. 


## -returns



None




## -remarks



This routine reserves exclusive access to the hardware controller for the specified device.

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff542049">ControllerControl</a> routine returns a value indicating whether the controller remains allocated to the device, either <b>DeallocateObject</b> or <b>KeepObject</b>. If it returns <b>KeepObject</b>, the driver must subsequently call <b>IoFreeController</b> to release the controller object.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542049">ControllerControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iocreatecontroller">IoCreateController</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iodeletecontroller">IoDeleteController</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iofreecontroller">IoFreeController</a>
 

 

