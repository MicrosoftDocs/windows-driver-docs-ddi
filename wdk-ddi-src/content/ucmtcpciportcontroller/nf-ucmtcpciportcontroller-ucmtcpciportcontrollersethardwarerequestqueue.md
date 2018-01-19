---
UID: NF:ucmtcpciportcontroller.UcmTcpciPortControllerSetHardwareRequestQueue
title: UcmTcpciPortControllerSetHardwareRequestQueue function
author: windows-driver-content
description: Assigns a framework queue object to which the UcmTcpciCx dispatches hardware requests for the port controller.
old-location: buses\ucmtcpciportcontrollersethardwarerequestqueue.htm
old-project: usbref
ms.assetid: 47142adb-4d22-41eb-b455-93409bbffffb
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: UcmTcpciPortControllerSetHardwareRequestQueue
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ucmtcpciportcontroller.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: UcmTcpciPortControllerSetHardwareRequestQueue
req.alt-loc: ucmtcpciportcontroller.h
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
req.typenames: UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE
req.product: Windows 10 or later.
---

# UcmTcpciPortControllerSetHardwareRequestQueue function



## -description


                Assigns a framework queue object to which the UcmTcpciCx dispatches hardware requests for the port controller.



## -syntax

````
VOID UcmTcpciPortControllerSetHardwareRequestQueue(
   UCMTCPCIPORTCONTROLLER PortControllerObject,
   WDFQUEUE               HardwareRequestQueue
);
````


## -parameters

### -param PortControllerObject 

Handle to the port controller object that the client driver received in the previous call to <a href="..\ucmtcpciportcontroller\nf-ucmtcpciportcontroller-ucmtcpciportcontrollercreate.md">UcmTcpciPortControllerCreate</a>.


### -param HardwareRequestQueue 

A handle to the framework queue object to assign.


## -returns
This method does not return a value.


## -remarks
The client driver must call <b>UcmTcpciPortControllerSetHardwareRequestQueue</b> after creating the port controller object. The driver must call this method only once before calling <a href="..\ucmtcpciportcontroller\nf-ucmtcpciportcontroller-ucmtcpciportcontrollerstart.md">UcmTcpciPortControllerStart</a>.

The parent of the queue object is the port controller object. 


A client driver may choose to use the same queue across multiple port controller objects. However, in that case the driver must make sure that the port controller objects do not outlive the queue object. The queue object must be deleted only after all the port controllers have been stopped. UcmTcpciCx guarantees  that only one request is processed in the queue at a time per port controller object.


## -see-also
<dl>
<dt>
<a href="..\ucmtcpciportcontroller\nf-ucmtcpciportcontroller-ucmtcpciportcontrollercreate.md">UcmTcpciPortControllerCreate</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UcmTcpciPortControllerSetHardwareRequestQueue method%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

