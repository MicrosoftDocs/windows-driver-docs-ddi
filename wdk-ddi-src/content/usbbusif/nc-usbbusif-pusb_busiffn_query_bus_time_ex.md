---
UID: NC:usbbusif.PUSB_BUSIFFN_QUERY_BUS_TIME_EX
title: USB_BUSIFFN_QUERY_BUS_TIME_EX
author: windows-driver-content
description: The QueryBusTimeEx routine gets the current 32-bit USB micro-frame number.
old-location: buses\querybustimeex.htm
old-project: usbref
ms.assetid: 8a9718eb-59f3-441a-b482-c2a376a48ac1
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: PUSB_BUSIFFN_QUERY_BUS_TIME_EX, QueryBusTimeEx, QueryBusTimeEx callback function [Buses], USB_BUSIFFN_QUERY_BUS_TIME_EX, buses.querybustimeex, usbbusif/QueryBusTimeEx
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	usbbusif.h
apiname:
-	QueryBusTimeEx
product: Windows
targetos: Windows
req.typenames: USBD_VERSION_INFORMATION, *PUSBD_VERSION_INFORMATION
req.product: Windows 10 or later.
---

# PUSB_BUSIFFN_QUERY_BUS_TIME_EX callback


## -description


This request is not supported.
      

The <b>QueryBusTimeEx</b> routine gets the current 32-bit USB micro-frame number. 


## -prototype


````
USB_BUSIFFN_QUERY_BUS_TIME_EX QueryBusTimeEx;

NTSTATUS QueryBusTimeEx(
  _In_  PVOID    BusContext,
  _Out_ PULONG   CurrentMicroFrame
)
{ ... }
````


## -parameters












#### - BusContext [in]

Handle returned in the <b>BusContext</b> member of the <a href="..\usbbusif\ns-usbbusif-_usb_bus_interface_usbdi_v3.md">USB_BUS_INTERFACE_USBDI_V3</a> structure by an IRP_MN_QUERY_INTERFACE request. 


#### - CurrentMicroFrame [out]

Receives the current USB micro-frame number.


## -returns



<b>QueryBusTimeEx</b> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The call completed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_SUPPORTED </b></dt>
</dl>
</td>
<td width="60%">
The function was called for a USB host controller that does not support USB 2.0. 

</td>
</tr>
</table>
 




## -remarks



<b>QueryBusTimeEx</b> gets the current USB 2.0 frame/micro-frame number when called for a USB device attached to a USB 2.0 host controller.  


The lowest 3 bits of the returned micro-frame value will contain the current 125us micro-frame, while the upper 29 bits will contain the current 1ms USB frame number.


The function definition that is provided on this reference page is an example function whose parameters are just placeholder names. The actual prototype of the function is declared in usbbusif.h as follows:



<pre class="syntax" xml:space="preserve"><code>typedef NTSTATUS
  (USB_BUSIFFN *PUSB_BUSIFFN_QUERY_BUS_TIME_EX) (
    IN PVOID,
    IN PULONG</code></pre>



## -see-also

<a href="..\usbbusif\ns-usbbusif-_usb_bus_interface_usbdi_v3.md">USB_BUS_INTERFACE_USBDI_V3</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USB_BUSIFFN_QUERY_BUS_TIME_EX callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

