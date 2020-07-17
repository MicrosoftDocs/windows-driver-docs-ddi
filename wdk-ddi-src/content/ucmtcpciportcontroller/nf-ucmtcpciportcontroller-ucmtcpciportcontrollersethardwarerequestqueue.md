---
UID: NF:ucmtcpciportcontroller.UcmTcpciPortControllerSetHardwareRequestQueue
title: UcmTcpciPortControllerSetHardwareRequestQueue function (ucmtcpciportcontroller.h)
description: Assigns a framework queue object to which the UcmTcpciCx dispatches hardware requests for the port controller.
old-location: buses\ucmtcpciportcontrollersethardwarerequestqueue.htm
tech.root: usbref
ms.assetid: 47142adb-4d22-41eb-b455-93409bbffffb
ms.date: 05/07/2018
keywords: ["UcmTcpciPortControllerSetHardwareRequestQueue function"]
ms.keywords: UcmTcpciPortControllerSetHardwareRequestQueue, UcmTcpciPortControllerSetHardwareRequestQueue method [Buses], buses.ucmtcpciportcontrollersethardwarerequestqueue, ucmtcpciportcontroller/UcmTcpciPortControllerSetHardwareRequestQueue
f1_keywords:
 - "ucmtcpciportcontroller/UcmTcpciPortControllerSetHardwareRequestQueue"
 - "UcmTcpciPortControllerSetHardwareRequestQueue"
req.header: ucmtcpciportcontroller.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ucmtcpciportcontroller.h
api_name:
- UcmTcpciPortControllerSetHardwareRequestQueue
product:
- Windows
targetos: Windows
req.typenames: 
---

# UcmTcpciPortControllerSetHardwareRequestQueue function


## -description




                Assigns a framework queue object to which the UcmTcpciCx dispatches hardware requests for the port controller.


## -parameters




### -param PortControllerObject

Handle to the port controller object that the client driver received in the previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmtcpciportcontroller/nf-ucmtcpciportcontroller-ucmtcpciportcontrollercreate">UcmTcpciPortControllerCreate</a>.


### -param HardwareRequestQueue

A handle to the framework queue object to assign.


## -remarks



The client driver must call <b>UcmTcpciPortControllerSetHardwareRequestQueue</b> after creating the port controller object. The driver must call this method only once before calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmtcpciportcontroller/nf-ucmtcpciportcontroller-ucmtcpciportcontrollerstart">UcmTcpciPortControllerStart</a>.

The parent of the queue object is the port controller object. 


A client driver may choose to use the same queue across multiple port controller objects. However, in that case the driver must make sure that the port controller objects do not outlive the queue object. The queue object must be deleted only after all the port controllers have been stopped. UcmTcpciCx guarantees  that only one request is processed in the queue at a time per port controller object.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmtcpciportcontroller/nf-ucmtcpciportcontroller-ucmtcpciportcontrollercreate">UcmTcpciPortControllerCreate</a>
 

 

