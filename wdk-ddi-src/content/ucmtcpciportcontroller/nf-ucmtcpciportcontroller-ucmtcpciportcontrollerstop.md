---
UID: NF:ucmtcpciportcontroller.UcmTcpciPortControllerStop
title: UcmTcpciPortControllerStop function
author: windows-driver-content
description: Indicates to the UcmTcpciCx class extension to stop sending hardware requests to the port controller object.
old-location: buses\ucmtcpciportcontrollerstop.htm
old-project: usbref
ms.assetid: 5d1dd418-5a2f-448f-ae65-695c4f97ff29
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: UcmTcpciPortControllerStop, UcmTcpciPortControllerStop method [Buses], buses.ucmtcpciportcontrollerstop, ucmtcpciportcontroller/UcmTcpciPortControllerStop
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ucmtcpcicxstub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ucmtcpcicxstub.lib
-	ucmtcpcicxstub.dll
api_name:
-	UcmTcpciPortControllerStop
product: Windows
targetos: Windows
req.typenames: UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE
req.product: Windows 10 or later.
---

# UcmTcpciPortControllerStop function


## -description


Indicates to the UcmTcpciCx class extension to stop sending hardware requests to the port controller object. 


## -syntax


````
VOID UcmTcpciPortControllerStop(
   UCMTCPCIPORTCONTROLLER PortControllerObject
);
````


## -parameters




### -param PortControllerObject

Handle to the port controller object that the client driver received in the previous call to <a href="..\ucmtcpciportcontroller\nf-ucmtcpciportcontroller-ucmtcpciportcontrollercreate.md">UcmTcpciPortControllerCreate</a>.


## -returns



This method does not return a value.




## -remarks



After calling <b>UcmTcpciPortControllerStop</b>, the client driver stops processing all requests on the port controller object. This call is synchronous, so it is guaranteed that the class extension will not invoke callback functions or send requests after it returns. The driver must not call this method within a port controller callback, or while any non-cancelable hardware requests are pending.

A client driver calls this method from its <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_release_hardware.md">EVT_WDF_DEVICE_RELEASE_HARDWARE</a> callback implementation. After doing so, it should also call <a href="..\wdfobject\nf-wdfobject-wdfobjectdelete.md">WdfObjectDelete</a>, in case <i>EVT_WDF_DEVICE_RELEASE_HARDWARE</i> is invoked to resource rebalancing. Failure to do so causes the driver to leak objects associated with the port controller object when a resource rebalance occurs. Parenting the UCMPORTCONTROLLER handle to the WDFDEVICE handle is not sufficient, because a WDFDEVICE is not deleted across a resource rebalance.

If the driver is transitioning to a Dx state due to S0-Idle, the driver must not call this method from its <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_d0_exit.md">EVT_WDF_DEVICE_D0_EXIT</a> callback function.  Synchronization with the driver's power state can be achieved by using a power-managed queue to receive hardware requests.

It is safe to call <b>UcmTcpciPortControllerStop</b> on a port controller that has already been stopped. After this method returns, no other method except for <a href="..\ucmtcpciportcontroller\nf-ucmtcpciportcontroller-ucmtcpciportcontrollerstart.md">UcmTcpciPortControllerStart</a> can be called on the port controller.

The client driver must call this method if it needs to stop all actions on the port controller so that it can perform error recovery if it detected any issues during its operation. After the recovery process has been completed, the driver must restart the port controller.


Stopping the controller ends any active PD contract and the Type-C connection. 




## -see-also

<a href="..\ucmtcpciportcontroller\nf-ucmtcpciportcontroller-ucmtcpciportcontrollerstart.md">UcmTcpciPortControllerStart</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UcmTcpciPortControllerStop method%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

