---
UID: NS:usbioctl._USB_PORT_PROPERTIES
title: _USB_PORT_PROPERTIES
author: windows-driver-content
description: The USB_PORT_PROPERTIES union is used to report the capabilities of a Universal Serial Bus (USB) port.The port capabilities are retrieved in the USB_PORT_CONNECTOR_PROPERTIES structure by the IOCTL_USB_GET_PORT_CONNECTOR_PROPERTIES I/O control request.
old-location: buses\usb_port_properties.htm
old-project: usbref
ms.assetid: BCADC907-3770-4FBE-AEB3-96F93502E899
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _USB_PORT_PROPERTIES, USB_PORT_PROPERTIES, *PUSB_PORT_PROPERTIES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usbioctl.h
req.include-header: Usbioctl.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: None supported
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: USB_PORT_PROPERTIES
req.alt-loc: usbioctl.h
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
req.typenames: USB_PORT_PROPERTIES, *PUSB_PORT_PROPERTIES
req.product: Windows 10 or later.
---

# _USB_PORT_PROPERTIES structure



## -description
The <b>USB_PORT_PROPERTIES</b> union is used to report the capabilities of a Universal Serial Bus (USB) port.

The  port capabilities are retrieved in the <a href="..\usbioctl\ns-usbioctl-_usb_port_connector_properties.md">USB_PORT_CONNECTOR_PROPERTIES</a> structure by the <a href="..\usbioctl\ni-usbioctl-ioctl_usb_get_port_connector_properties.md">IOCTL_USB_GET_PORT_CONNECTOR_PROPERTIES</a> I/O control request.



## -syntax

````
typedef union _USB_PORT_PROPERTIES {
  ULONG  ul;
  struct {
    ULONG PortIsUserConnectable  :1;
    ULONG PortIsDebugCapable  :1;
    ULONG ReservedMBZ  :30;
  };
} USB_PORT_PROPERTIES, *PUSB_PORT_PROPERTIES;
````


## -struct-fields

### -field ul

A bitmask that indicates the properties and capabilities of the port.


### -field PortIsUserConnectable

If <b>TRUE</b>, the port is visible to the user and a USB device can be attached to or detached from the port.


### -field PortIsDebugCapable

If <b>TRUE</b>, the port supports debugging over a USB connection.


### -field ReservedMBZ

Reserved. Do not use.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\usbioctl\ns-usbioctl-_usb_port_connector_properties.md">USB_PORT_CONNECTOR_PROPERTIES</a>
</dt>
<dt>
<a href="..\usbioctl\ni-usbioctl-ioctl_usb_get_port_connector_properties.md">IOCTL_USB_GET_PORT_CONNECTOR_PROPERTIES</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USB_PORT_PROPERTIES union%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

