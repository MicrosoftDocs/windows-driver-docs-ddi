---
UID: NC:usbbusif.PUSB_BUSIFFN_IS_DEVICE_HIGH_SPEED
title: PUSB_BUSIFFN_IS_DEVICE_HIGH_SPEED
author: windows-driver-content
description: The USB_BUSIFFN_IS_DEVICE_HIGH_SPEED routine returns TRUE if the device is operating at high speed.
old-location: buses\isdevicehighspeed.htm
old-project: usbref
ms.assetid: 36e0041d-700f-44db-84b6-3745026cb6f7
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IsDeviceHighSpeed, IsDeviceHighSpeed callback function [Buses], PUSB_BUSIFFN_IS_DEVICE_HIGH_SPEED, USB_BUSIFFN_IS_DEVICE_HIGH_SPEED, buses.isdevicehighspeed, usbbusif/IsDeviceHighSpeed, usbinterKR_eaf122ed-eee1-4924-a186-b0474b8c9816.xml
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
-	IsDeviceHighSpeed
product:
- Windows
targetos: Windows
req.typenames: USBD_VERSION_INFORMATION, *PUSBD_VERSION_INFORMATION
req.product: Windows 10 or later.
---

# PUSB_BUSIFFN_IS_DEVICE_HIGH_SPEED callback


## -description


The USB_BUSIFFN_IS_DEVICE_HIGH_SPEED routine returns <b>TRUE</b> if the device  is operating at high speed. 


## -parameters












#### - BusContext [in, optional]

Handle returned in the <b>BusContext</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff539213">USB_BUS_INTERFACE_USBDI_V1</a> structure by an IRP_MN_QUERY_INTERFACE request. 


## -returns




            USB_BUSIFFN_IS_DEVICE_HIGH_SPEED implementation returns <b>TRUE</b> if the USB device is operating at high speed USB 2.0 compliant device; <b>FALSE</b> otherwise.  




## -remarks



The function definition that is provided on this reference page is an example routine whose parameters are just placeholder names. The actual prototype of the function is declared in usbbusif.h as follows:

<pre class="syntax" xml:space="preserve"><code>typedef BOOLEAN
  (USB_BUSIFFN *PUSB_BUSIFFN_IS_DEVICE_HIGH_SPEED) (
    IN PVOID
  );</code></pre>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff539213">USB_BUS_INTERFACE_USBDI_V1</a>
 

 

