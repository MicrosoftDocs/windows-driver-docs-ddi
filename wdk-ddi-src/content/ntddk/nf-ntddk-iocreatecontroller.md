---
UID: NF:ntddk.IoCreateController
title: IoCreateController function
author: windows-driver-content
description: The IoCreateController routine allocates memory for and initializes a controller object with a controller extension of a driver-determined size.
old-location: kernel\iocreatecontroller.htm
old-project: kernel
ms.assetid: 7db268a4-d1ef-4d23-9b5d-cd24612d547e
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: IoCreateController, IoCreateController routine [Kernel-Mode Driver Architecture], k104_a7ec4f8c-84d0-4fec-9f9e-40c5d57036f1.xml, kernel.iocreatecontroller, ntddk/IoCreateController
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
req.ddi-compliance: IrqlIoPassive2, PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoCreateController
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# IoCreateController function


## -description


The <b>IoCreateController</b> routine allocates memory for and initializes a controller object with a controller extension of a driver-determined size.


## -syntax


````
PCONTROLLER_OBJECT IoCreateController(
  _In_ ULONG Size
);
````


## -parameters




### -param Size [in]

Specifies the number of bytes to be allocated for the controller extension.


## -returns



<b>IoCreateController</b> returns a pointer to the controller object or a <b>NULL</b> pointer if memory could not be allocated for the requested device extension.




## -remarks



A controller object usually represents a physical device controller with attached devices on which a single driver carries out I/O requests. The controller extension is allocated from nonpaged pool and is guaranteed to be accessible by any driver routine and in an arbitrary thread context.

The controller object is used to synchronize I/O operations to target devices for which I/O requests can come in concurrently to a single, monolithic driver. A driver also might use a controller object to synchronize operations through device channels.

If <b>IoCreateController</b> returns <b>NULL</b>, the driver should fail device start-up. 




## -see-also

<a href="..\ntddk\nf-ntddk-iofreecontroller.md">IoFreeController</a>



<a href="..\ntddk\nf-ntddk-iodeletecontroller.md">IoDeleteController</a>



<a href="..\ntddk\ns-ntddk-_controller_object.md">CONTROLLER_OBJECT</a>



<a href="..\ntddk\nf-ntddk-ioallocatecontroller.md">IoAllocateController</a>



 

 


