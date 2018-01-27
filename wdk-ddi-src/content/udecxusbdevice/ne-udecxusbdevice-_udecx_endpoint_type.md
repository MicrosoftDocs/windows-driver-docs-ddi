---
UID: NE:udecxusbdevice._UDECX_ENDPOINT_TYPE
title: _UDECX_ENDPOINT_TYPE
author: windows-driver-content
description: Defines values for endpoint types supported by a virtual USB device.
old-location: buses\udecx_endpoint_type.htm
old-project: usbref
ms.assetid: EFA5DDC0-9E6B-450E-B191-1DA9FBAC269C
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: *PUDECX_ENDPOINT_TYPE, udecxusbdevice/UdecxEndpointTypeDynamic, UDECX_ENDPOINT_TYPE enumeration [Buses], udecxusbdevice/UdecxEndpointTypeInvalid, buses.udecx_endpoint_type, udecxusbdevice/UdecxEndpointTypeSimple, UdecxEndpointTypeDynamic, _UDECX_ENDPOINT_TYPE, UDECX_ENDPOINT_TYPE, UdecxEndpointTypeSimple, udecxusbdevice/UDECX_ENDPOINT_TYPE, UdecxEndpointTypeInvalid
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
req.irql: <=DISPATCH_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	UdecxUsbDevice.h
apiname: 
-	UDECX_ENDPOINT_TYPE
product: Windows
targetos: Windows
req.typenames: *PUDECX_ENDPOINT_TYPE, UDECX_ENDPOINT_TYPE
req.product: Windows 10 or later.
---

# _UDECX_ENDPOINT_TYPE enumeration


## -description


Defines values for endpoint types supported by a virtual USB device.


## -syntax


````
typedef enum _UDECX_ENDPOINT_TYPE { 
  UdecxEndpointTypeInvalid  = 0,
  UdecxEndpointTypeSimple   = ,
  UdecxEndpointTypeDynamic  = 
} UDECX_ENDPOINT_TYPE;
````


## -enum-fields




### -field UdecxEndpointTypeInvalid

The endpoint is not of a valid type.


### -field UdecxEndpointTypeSimple

The endpoint is defined in the first (and only) interface setting of the interface. That device has only one configuration. The client driver creates all endpoints before the device is detected. 


### -field UdecxEndpointTypeDynamic

The endpoint is dynamically created in the client driver's implementation of the <a href="..\udecxusbdevice\nc-udecxusbdevice-evt_udecx_usb_device_endpoints_configure.md">EVT_UDECX_USB_DEVICE_ENDPOINTS_CONFIGURE</a> callback.


## -see-also

<a href="..\udecxusbdevice\nf-udecxusbdevice-udecxusbdeviceinitsetendpointstype.md">UdecxUsbDeviceInitSetEndpointsType</a>

<a href="https://msdn.microsoft.com/4DABCC96-F3F5-43D9-9BCF-A2663ED30137">USB endpoints</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UDECX_ENDPOINT_TYPE enumeration%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

