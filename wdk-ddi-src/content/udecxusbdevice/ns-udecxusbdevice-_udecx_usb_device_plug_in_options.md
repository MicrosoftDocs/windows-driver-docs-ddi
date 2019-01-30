---
UID: NS:udecxusbdevice._UDECX_USB_DEVICE_PLUG_IN_OPTIONS
title: "_UDECX_USB_DEVICE_PLUG_IN_OPTIONS" (udecxusbdevice.h)
description: Contains the port numbers to which a virtual USB device is connected. Initialize this structure by calling the UDECX_USB_DEVICE_PLUG_IN_OPTIONS_INIT method.
old-location: buses\udecx_usb_device_plug_in_options.htm
tech.root: usbref
ms.assetid: D09A124A-82F6-4B0A-B60F-E60EB54B0EC1
ms.date: 05/07/2018
ms.keywords: "*PUDECX_USB_DEVICE_PLUG_IN_OPTIONS, PUDECX_USB_DEVICE_PLUG_IN_OPTIONS, PUDECX_USB_DEVICE_PLUG_IN_OPTIONS structure pointer [Buses], UDECX_USB_DEVICE_PLUG_IN_OPTIONS, UDECX_USB_DEVICE_PLUG_IN_OPTIONS structure [Buses], _UDECX_USB_DEVICE_PLUG_IN_OPTIONS, buses.udecx_usb_device_plug_in_options, udecxusbdevice/ PUDECX_USB_DEVICE_PLUG_IN_OPTIONS, udecxusbdevice/UDECX_USB_DEVICE_PLUG_IN_OPTIONS"
ms.topic: struct
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	UdecxUsbDevice.h
api_name:
-	UDECX_USB_DEVICE_PLUG_IN_OPTIONS
product:
- Windows
targetos: Windows
req.typenames: UDECX_USB_DEVICE_PLUG_IN_OPTIONS, *PUDECX_USB_DEVICE_PLUG_IN_OPTIONS
---

# _UDECX_USB_DEVICE_PLUG_IN_OPTIONS structure


## -description


Contains the port numbers to which a virtual USB device is connected. Initialize this structure by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/mt628001">UDECX_USB_DEVICE_PLUG_IN_OPTIONS_INIT</a> method.


## -struct-fields




### -field Size

The size of this structure.


### -field Usb20PortNumber

The USB 2.0 port number.


### -field Usb30PortNumber

The USB 2.0 port number.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt627975">UdecxUsbDevicePlugIn</a>
 

 

