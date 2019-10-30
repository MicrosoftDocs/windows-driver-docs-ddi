---
UID: NF:ntddk.IoFreeController
title: IoFreeController function (ntddk.h)
description: The IoFreeController routine releases a previously allocated controller object when the driver has completed an I/O request.
old-location: kernel\iofreecontroller.htm
tech.root: kernel
ms.assetid: a9b0ca27-dc46-4f9b-a3f9-51bbd759afc1
ms.date: 04/30/2018
ms.keywords: IoFreeController, IoFreeController routine [Kernel-Mode Driver Architecture], k104_42ed98f0-34b1-45d9-981e-e3e62411ad70.xml, kernel.iofreecontroller, ntddk/IoFreeController
ms.topic: function
f1_keywords:
 - "ntddk/IoFreeController"
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlDispatch, HwStorPortProhibitedDDIs, IrqlDispatch(storport)
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
- IoFreeController
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoFreeController function


## -description


The <b>IoFreeController</b> routine releases a previously allocated controller object when the driver has completed an I/O request.


## -parameters




### -param ControllerObject [in]

Pointer to the driver's controller object, which was allocated for the current I/O operation on a particular device by calling <b>IoAllocateController</b>. 


## -returns



None




## -remarks



The connection between the current target device object and the controller object is released only if no requests are currently queued to the same device. Otherwise, the driver's ControllerControl routine is called with the next IRP bound through the device controller to the target device. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-ioallocatecontroller">IoAllocateController</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iocreatecontroller">IoCreateController</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iodeletecontroller">IoDeleteController</a>
 

 

