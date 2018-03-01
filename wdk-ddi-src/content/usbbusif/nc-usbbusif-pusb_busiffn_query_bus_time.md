---
UID: NC:usbbusif.PUSB_BUSIFFN_QUERY_BUS_TIME
title: USB_BUSIFFN_QUERY_BUS_TIME
author: windows-driver-content
description: The QueryBusTime function gets the current 32-bit USB frame number.
old-location: buses\querybustime.htm
old-project: usbref
ms.assetid: 6a0a1953-070d-4335-a906-4ca3fe8a04e1
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: PUSB_BUSIFFN_QUERY_BUS_TIME, QueryBusTime, QueryBusTime callback function [Buses], USB_BUSIFFN_QUERY_BUS_TIME, buses.querybustime, usbbusif/QueryBusTime, usbinterKR_857e67cf-8b61-43e3-b07f-25968e2672d4.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: usbbusif.h
req.include-header: Usbbusif.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
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
req.irql: "< = DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	usbbusif.h
api_name:
-	QueryBusTime
product: Windows
targetos: Windows
req.typenames: USBD_VERSION_INFORMATION, *PUSBD_VERSION_INFORMATION
req.product: Windows 10 or later.
---

# PUSB_BUSIFFN_QUERY_BUS_TIME callback


## -description


The <i>QueryBusTime</i> function gets the current 32-bit USB frame number. 


## -prototype


````
USB_BUSIFFN_QUERY_BUS_TIME QueryBusTime;

NTSTATUS QueryBusTime(
  _In_      PVOID  BusContext,
  _Out_opt_ PULONG CurrentFrame
)
{ ... }
````


## -parameters












#### - BusContext [in]

Handle returned in the <b>BusContext</b> member of the <a href="..\usbbusif\ns-usbbusif-_usb_bus_interface_usbdi_v0.md">USB_BUS_INTERFACE_USBDI_V0</a> structure by an IRP_MN_QUERY_INTERFACE request. 


#### - CurrentFrame [out, optional]

Receives the current USB frame number.


## -returns



Returns STATUS_SUCCESS on success, and the appropriate error code on failure. 




## -remarks



This routine replaces the <b>USBD_QueryBusTime</b>  library function provided by usbd.sys. 

The function definition that is provided on this reference page is an example function whose parameters are just placeholder names. The actual prototype of the function is declared in usbbusif.h as follows:

<pre class="syntax" xml:space="preserve"><code>typedef NTSTATUS
  (USB_BUSIFFN *PUSB_BUSIFFN_QUERY_BUS_TIME) (
    IN PVOID,
    IN PULONG</code></pre>
  );




## -see-also

<a href="..\usbbusif\ns-usbbusif-_usb_bus_interface_usbdi_v0.md">USB_BUS_INTERFACE_USBDI_V0</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USB_BUSIFFN_QUERY_BUS_TIME callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

