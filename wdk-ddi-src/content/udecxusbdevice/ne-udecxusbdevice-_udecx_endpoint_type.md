---
UID: NE:udecxusbdevice._UDECX_ENDPOINT_TYPE
title: "_UDECX_ENDPOINT_TYPE"
author: windows-driver-content
description: Defines values for endpoint types supported by a virtual USB device.
old-location: buses\udecx_endpoint_type.htm
old-project: usbref
ms.assetid: EFA5DDC0-9E6B-450E-B191-1DA9FBAC269C
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PUDECX_ENDPOINT_TYPE, UDECX_ENDPOINT_TYPE, UDECX_ENDPOINT_TYPE enumeration [Buses], UdecxEndpointTypeDynamic, UdecxEndpointTypeInvalid, UdecxEndpointTypeSimple, _UDECX_ENDPOINT_TYPE, buses.udecx_endpoint_type, udecxusbdevice/UDECX_ENDPOINT_TYPE, udecxusbdevice/UdecxEndpointTypeDynamic, udecxusbdevice/UdecxEndpointTypeInvalid, udecxusbdevice/UdecxEndpointTypeSimple"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: udecxusbdevice.h
req.include-header: Udecx.h
req.target-type: Windows
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	UdecxUsbDevice.h
api_name:
-	UDECX_ENDPOINT_TYPE
product:
- Windows
targetos: Windows
req.typenames: UDECX_ENDPOINT_TYPE, *PUDECX_ENDPOINT_TYPE
req.product: Windows 10 or later.
---

# _UDECX_ENDPOINT_TYPE enumeration


## -description


Defines values for endpoint types supported by a virtual USB device.


## -enum-fields




### -field UdecxEndpointTypeInvalid

The endpoint is not of a valid type.


### -field UdecxEndpointTypeSimple

The endpoint is defined in the first (and only) interface setting of the interface. That device has only one configuration. The client driver creates all endpoints before the device is detected. 


### -field UdecxEndpointTypeDynamic

The endpoint is dynamically created in the client driver's implementation of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt595913">EVT_UDECX_USB_DEVICE_ENDPOINTS_CONFIGURE</a> callback.


## -see-also




<a href="https://msdn.microsoft.com/4DABCC96-F3F5-43D9-9BCF-A2663ED30137">USB endpoints</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt627970">UdecxUsbDeviceInitSetEndpointsType</a>
 

 

