---
UID: NS:ucxusbdevice._USB_DEVICE_PORT_PATH
title: _USB_DEVICE_PORT_PATH (ucxusbdevice.h)
description: Contains the port path of a USB device.
old-location: buses\_usb_device_port_path.htm
tech.root: usbref
ms.assetid: 75C7DB08-F831-43ED-8373-F3F4C7AF89E8
ms.date: 05/07/2018
keywords: ["_USB_DEVICE_PORT_PATH structure"]
ms.keywords: "*PUSB_DEVICE_PORT_PATH, P_USB_DEVICE_PORT_PATH, P_USB_DEVICE_PORT_PATH structure pointer [Buses], USB_DEVICE_PORT_PATH, USB_DEVICE_PORT_PATH structure [Buses], _USB_DEVICE_PORT_PATH, buses._usb_device_port_path, ucxusbdevice/P_USB_DEVICE_PORT_PATH, ucxusbdevice/_USB_DEVICE_PORT_PATH"
f1_keywords:
 - "ucxusbdevice/USB_DEVICE_PORT_PATH"
 - "USB_DEVICE_PORT_PATH"
req.header: ucxusbdevice.h
req.include-header: Ucxclass.h
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ucxusbdevice.h
api_name:
- USB_DEVICE_PORT_PATH
targetos: Windows
req.typenames: USB_DEVICE_PORT_PATH, *PUSB_DEVICE_PORT_PATH
---

# _USB_DEVICE_PORT_PATH structure


## -description


Contains the port path of a USB device.


## -struct-fields




### -field Size

The size in bytes of this structure.


### -field PortPathDepth

The depth of path in the USB topology tree, consisting of host controller, hubs, and devices.


### -field TTHubDepth

The depth of path in the USB topology tree from a TT hub. 


### -field PortPath

The index of connected USB port on the hub.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucxusbdevice/ns-ucxusbdevice-_ucxusbdevice_info">UCXUSBDEVICE_INFO</a>
 

 

