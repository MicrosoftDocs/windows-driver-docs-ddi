---
UID: NS:usbioctl._USB_PORT_PROPERTIES
title: _USB_PORT_PROPERTIES (usbioctl.h)
description: The USB_PORT_PROPERTIES union is used to report the capabilities of a Universal Serial Bus (USB) port.The port capabilities are retrieved in the USB_PORT_CONNECTOR_PROPERTIES structure by the IOCTL_USB_GET_PORT_CONNECTOR_PROPERTIES I/O control request.
old-location: buses\usb_port_properties.htm
tech.root: usbref
ms.assetid: BCADC907-3770-4FBE-AEB3-96F93502E899
ms.date: 05/07/2018
keywords: ["_USB_PORT_PROPERTIES structure"]
ms.keywords: "*PUSB_PORT_PROPERTIES, PUSB_PORT_PROPERTIES, PUSB_PORT_PROPERTIES union pointer [Buses], USB_PORT_PROPERTIES, USB_PORT_PROPERTIES union [Buses], _USB_PORT_PROPERTIES, buses.usb_port_properties, usbioctl/PUSB_PORT_PROPERTIES, usbioctl/USB_PORT_PROPERTIES"
f1_keywords:
 - "usbioctl/USB_PORT_PROPERTIES"
 - "USB_PORT_PROPERTIES"
req.header: usbioctl.h
req.include-header: Usbioctl.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: None supported
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
- usbioctl.h
api_name:
- USB_PORT_PROPERTIES
targetos: Windows
req.typenames: USB_PORT_PROPERTIES, *PUSB_PORT_PROPERTIES
---

# _USB_PORT_PROPERTIES structure


## -description


The <b>USB_PORT_PROPERTIES</b> union is used to report the capabilities of a Universal Serial Bus (USB) port.

The  port capabilities are retrieved in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_port_connector_properties">USB_PORT_CONNECTOR_PROPERTIES</a> structure by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_usb_get_port_connector_properties">IOCTL_USB_GET_PORT_CONNECTOR_PROPERTIES</a> I/O control request.


## -struct-fields




### -field ul

A bitmask that indicates the properties and capabilities of the port.


### -field PortIsUserConnectable

If <b>TRUE</b>, the port is visible to the user and a USB device can be attached to or detached from the port.


### -field PortIsDebugCapable

If <b>TRUE</b>, the port supports debugging over a USB connection.


### -field PortHasMultipleCompanions

 


### -field PortConnectorIsTypeC

 


### -field ReservedMBZ

Reserved. Do not use.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_usb_get_port_connector_properties">IOCTL_USB_GET_PORT_CONNECTOR_PROPERTIES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_port_connector_properties">USB_PORT_CONNECTOR_PROPERTIES</a>
 

 

