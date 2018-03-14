---
UID: NF:ntddk.IoFreeController
title: IoFreeController function
author: windows-driver-content
description: The IoFreeController routine releases a previously allocated controller object when the driver has completed an I/O request.
old-location: kernel\iofreecontroller.htm
old-project: kernel
ms.assetid: a9b0ca27-dc46-4f9b-a3f9-51bbd759afc1
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: IoFreeController, IoFreeController routine [Kernel-Mode Driver Architecture], k104_42ed98f0-34b1-45d9-981e-e3e62411ad70.xml, kernel.iofreecontroller, ntddk/IoFreeController
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoFreeController
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# IoFreeController function


## -description


The <b>IoFreeController</b> routine releases a previously allocated controller object when the driver has completed an I/O request.


## -syntax


````
VOID IoFreeController(
  _In_ PCONTROLLER_OBJECT ControllerObject
);
````


## -parameters




### -param ControllerObject [in]

Pointer to the driver's controller object, which was allocated for the current I/O operation on a particular device by calling <b>IoAllocateController</b>. 


## -returns



None




## -remarks



The connection between the current target device object and the controller object is released only if no requests are currently queued to the same device. Otherwise, the driver's ControllerControl routine is called with the next IRP bound through the device controller to the target device. 




## -see-also

<a href="..\ntddk\nf-ntddk-iocreatecontroller.md">IoCreateController</a>



<a href="..\ntddk\nf-ntddk-iodeletecontroller.md">IoDeleteController</a>



<a href="..\ntddk\nf-ntddk-ioallocatecontroller.md">IoAllocateController</a>



 

 


