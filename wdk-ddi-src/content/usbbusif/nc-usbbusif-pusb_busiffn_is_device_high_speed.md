---
UID: NC:usbbusif.PUSB_BUSIFFN_IS_DEVICE_HIGH_SPEED
title: PUSB_BUSIFFN_IS_DEVICE_HIGH_SPEED
author: windows-driver-content
description: The USB_BUSIFFN_IS_DEVICE_HIGH_SPEED routine returns TRUE if the device is operating at high speed.
old-location: buses\isdevicehighspeed.htm
old-project: usbref
ms.assetid: 36e0041d-700f-44db-84b6-3745026cb6f7
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: buses.isdevicehighspeed, IsDeviceHighSpeed, PUSB_BUSIFFN_IS_DEVICE_HIGH_SPEED, IsDeviceHighSpeed callback function [Buses], IsDeviceHighSpeed, USB_BUSIFFN_IS_DEVICE_HIGH_SPEED, USB_BUSIFFN_IS_DEVICE_HIGH_SPEED, usbbusif/IsDeviceHighSpeed, usbinterKR_eaf122ed-eee1-4924-a186-b0474b8c9816.xml
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
-	IsDeviceHighSpeed
product: Windows
targetos: Windows
req.typenames: "*PUSBD_VERSION_INFORMATION, USBD_VERSION_INFORMATION"
req.product: Windows 10 or later.
---

# PUSB_BUSIFFN_IS_DEVICE_HIGH_SPEED callback


## -description


The USB_BUSIFFN_IS_DEVICE_HIGH_SPEED routine returns <b>TRUE</b> if the device  is operating at high speed. 


## -prototype


````
USB_BUSIFFN_IS_DEVICE_HIGH_SPEED IsDeviceHighSpeed;

BOOLEAN IsDeviceHighSpeed(
  _In_opt_ PVOID BusContext
)
{ ... }
````


## -parameters












#### - BusContext [in, optional]

Handle returned in the <b>BusContext</b> member of the <a href="..\usbbusif\ns-usbbusif-_usb_bus_interface_usbdi_v1.md">USB_BUS_INTERFACE_USBDI_V1</a> structure by an IRP_MN_QUERY_INTERFACE request. 


## -returns




            USB_BUSIFFN_IS_DEVICE_HIGH_SPEED implementation returns <b>TRUE</b> if the USB device is operating at high speed USB 2.0 compliant device; <b>FALSE</b> otherwise.  




## -remarks



The function definition that is provided on this reference page is an example routine whose parameters are just placeholder names. The actual prototype of the function is declared in usbbusif.h as follows:

<pre class="syntax" xml:space="preserve"><code>typedef BOOLEAN
  (USB_BUSIFFN *PUSB_BUSIFFN_IS_DEVICE_HIGH_SPEED) (
    IN PVOID
  );</code></pre>



## -see-also

<a href="..\usbbusif\ns-usbbusif-_usb_bus_interface_usbdi_v1.md">USB_BUS_INTERFACE_USBDI_V1</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USB_BUSIFFN_IS_DEVICE_HIGH_SPEED callback function%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

