---
UID: NC:usbbusif.PUSB_BUSIFFN_QUERY_BUS_TIME
title: PUSB_BUSIFFN_QUERY_BUS_TIME (usbbusif.h)
description: The QueryBusTime function gets the current 32-bit USB frame number.
old-location: buses\querybustime.htm
tech.root: usbref
ms.assetid: 6a0a1953-070d-4335-a906-4ca3fe8a04e1
ms.date: 05/07/2018
ms.keywords: PUSB_BUSIFFN_QUERY_BUS_TIME, QueryBusTime, QueryBusTime callback function [Buses], USB_BUSIFFN_QUERY_BUS_TIME, USB_BUSIFFN_QUERY_BUS_TIME callback, buses.querybustime, usbbusif/QueryBusTime, usbinterKR_857e67cf-8b61-43e3-b07f-25968e2672d4.xml
ms.topic: callback
f1_keywords:
 - "usbbusif/QueryBusTime"
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- usbbusif.h
api_name:
- QueryBusTime
product:
- Windows
targetos: Windows
req.typenames: 
---

# PUSB_BUSIFFN_QUERY_BUS_TIME callback function


## -description


The <i>QueryBusTime</i> function gets the current 32-bit USB frame number. 


## -parameters












#### - BusContext [in]

Handle returned in the <b>BusContext</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbbusif/ns-usbbusif-_usb_bus_interface_usbdi_v0">USB_BUS_INTERFACE_USBDI_V0</a> structure by an IRP_MN_QUERY_INTERFACE request. 


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




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbbusif/ns-usbbusif-_usb_bus_interface_usbdi_v0">USB_BUS_INTERFACE_USBDI_V0</a>
 

 

