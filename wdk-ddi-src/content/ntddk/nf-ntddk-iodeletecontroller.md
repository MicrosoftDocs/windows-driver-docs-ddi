---
UID: NF:ntddk.IoDeleteController
title: IoDeleteController function
author: windows-driver-content
description: The IoDeleteController routine removes a given controller object from the system, for example, when the driver that created it is being unloaded.
old-location: kernel\iodeletecontroller.htm
old-project: kernel
ms.assetid: bfab32ea-05fd-44c7-b264-221e4e3a7830
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: IoDeleteController, IoDeleteController routine [Kernel-Mode Driver Architecture], k104_c4d57e2c-d596-4c3d-a912-48792010837e.xml, ntddk/IoDeleteController, kernel.iodeletecontroller
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	IoDeleteController
product: Windows
targetos: Windows
req.typenames: "*PWHEA_RAW_DATA_FORMAT, WHEA_RAW_DATA_FORMAT"
---

# IoDeleteController function


## -description


The <b>IoDeleteController</b> routine removes a given controller object from the system, for example, when the driver that created it is being unloaded.


## -syntax


````
VOID IoDeleteController(
  _In_ PCONTROLLER_OBJECT ControllerObject
);
````


## -parameters




### -param ControllerObject [in]

Pointer to the controller object to be released. 


## -returns



None




## -remarks



<b>IoDeleteController</b> deallocates the memory for the controller object, including the controller extension.

This routine must be called when a driver that created a controller object is being unloaded or when the driver encounters a fatal error during device start-up, such as being unable to properly initialize a physical device.

A driver must release certain resources for which the driver supplied storage in its controller extension before it calls <b>IoDeleteController</b>. For example, if the driver stores the pointer to its interrupt object(s) in the controller extension, it must call <a href="..\wdm\nf-wdm-iodisconnectinterrupt.md">IoDisconnectInterrupt</a> before <b>IoDeleteController</b>. 




## -see-also

<a href="..\ntddk\nf-ntddk-iocreatecontroller.md">IoCreateController</a>



<a href="..\wdm\nf-wdm-iodisconnectinterrupt.md">IoDisconnectInterrupt</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoDeleteController routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

