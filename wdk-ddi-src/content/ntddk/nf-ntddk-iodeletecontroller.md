---
UID: NF:ntddk.IoDeleteController
title: IoDeleteController function (ntddk.h)
description: The IoDeleteController routine removes a given controller object from the system, for example, when the driver that created it is being unloaded.
old-location: kernel\iodeletecontroller.htm
tech.root: kernel
ms.assetid: bfab32ea-05fd-44c7-b264-221e4e3a7830
ms.date: 04/30/2018
ms.keywords: IoDeleteController, IoDeleteController routine [Kernel-Mode Driver Architecture], k104_c4d57e2c-d596-4c3d-a912-48792010837e.xml, kernel.iodeletecontroller, ntddk/IoDeleteController
ms.topic: function
f1_keywords:
 - "ntddk/IoDeleteController"
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlIoPassive4, PowerIrpDDis, HwStorPortProhibitedDDIs
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- IoDeleteController
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoDeleteController function


## -description


The <b>IoDeleteController</b> routine removes a given controller object from the system, for example, when the driver that created it is being unloaded.


## -parameters




### -param ControllerObject [in]

Pointer to the controller object to be released. 


## -returns



None




## -remarks



<b>IoDeleteController</b> deallocates the memory for the controller object, including the controller extension.

This routine must be called when a driver that created a controller object is being unloaded or when the driver encounters a fatal error during device start-up, such as being unable to properly initialize a physical device.

A driver must release certain resources for which the driver supplied storage in its controller extension before it calls <b>IoDeleteController</b>. For example, if the driver stores the pointer to its interrupt object(s) in the controller extension, it must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iodisconnectinterrupt">IoDisconnectInterrupt</a> before <b>IoDeleteController</b>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iocreatecontroller">IoCreateController</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iodisconnectinterrupt">IoDisconnectInterrupt</a>
 

 

