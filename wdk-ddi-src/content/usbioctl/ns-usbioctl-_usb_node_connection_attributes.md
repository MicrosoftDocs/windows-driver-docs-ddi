---
UID: NS:usbioctl._USB_NODE_CONNECTION_ATTRIBUTES
title: _USB_NODE_CONNECTION_ATTRIBUTES (usbioctl.h)
description: The USB_NODE_CONNECTION_ATTRIBUTES structure is used with the IOCTL_USB_GET_NODE_CONNECTION_ATTRIBUTES I/O control request to retrieve the attributes of a connection.
old-location: buses\usb_node_connection_attributes.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["USB_NODE_CONNECTION_ATTRIBUTES structure"]
ms.keywords: "*PUSB_NODE_CONNECTION_ATTRIBUTES, PUSB_NODE_CONNECTION_ATTRIBUTES, PUSB_NODE_CONNECTION_ATTRIBUTES structure pointer [Buses], USB_NODE_CONNECTION_ATTRIBUTES, USB_NODE_CONNECTION_ATTRIBUTES structure [Buses], _USB_NODE_CONNECTION_ATTRIBUTES, buses.usb_node_connection_attributes, usbioctl/PUSB_NODE_CONNECTION_ATTRIBUTES, usbioctl/USB_NODE_CONNECTION_ATTRIBUTES, usbstrct_20423110-ee37-4637-8202-e712bb13d43b.xml"
req.header: usbioctl.h
req.include-header: Usbioctl.h
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
targetos: Windows
req.typenames: USB_NODE_CONNECTION_ATTRIBUTES, *PUSB_NODE_CONNECTION_ATTRIBUTES
f1_keywords:
 - _USB_NODE_CONNECTION_ATTRIBUTES
 - usbioctl/_USB_NODE_CONNECTION_ATTRIBUTES
 - PUSB_NODE_CONNECTION_ATTRIBUTES
 - usbioctl/PUSB_NODE_CONNECTION_ATTRIBUTES
 - USB_NODE_CONNECTION_ATTRIBUTES
 - usbioctl/USB_NODE_CONNECTION_ATTRIBUTES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - usbioctl.h
api_name:
 - USB_NODE_CONNECTION_ATTRIBUTES
---

# _USB_NODE_CONNECTION_ATTRIBUTES structure


## -description

The <b>USB_NODE_CONNECTION_ATTRIBUTES</b> structure is used with the <a href="/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_usb_get_node_connection_attributes">IOCTL_USB_GET_NODE_CONNECTION_ATTRIBUTES</a> I/O control request to retrieve the attributes of a connection.

## -struct-fields

### -field ConnectionIndex

On input to the <a href="/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_usb_get_node_connection_attributes">IOCTL_USB_GET_NODE_CONNECTION_ATTRIBUTES</a> I/O control request, this member contains the number of the port.

### -field ConnectionStatus

On output from the <a href="/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_usb_get_node_connection_attributes">IOCTL_USB_GET_NODE_CONNECTION_ATTRIBUTES</a> I/O control request, this member contains a <a href="/windows-hardware/drivers/ddi/usbioctl/ne-usbioctl-_usb_connection_status">USB_CONNECTION_STATUS</a> enumerator that indicates the connection status.

### -field PortAttributes

On output from the <a href="/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_usb_get_node_connection_attributes">IOCTL_USB_GET_NODE_CONNECTION_ATTRIBUTES</a> I/O control request, this member contains the Microsoft-extended port attributes.

For Windows Vista, Windows Server 2008, and Windows 7 the Microsoft-extended port attributes field will always be zero.  

For Windows XP and Windows Server 2003, <b>PortAttributes</b> value might be set to the  Microsoft-extended port attributes, USB_PORTATTR_NO_OVERCURRENT_UI. This attribute indicates that no user-visible interface will be displayed when overcurrent occurs on the port.

## -see-also

<a href="/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_usb_get_node_connection_attributes">IOCTL_USB_GET_NODE_CONNECTION_ATTRIBUTES</a>



<a href="/windows-hardware/drivers/ddi/_usbref/#structures">USB Structures</a>



<a href="/windows-hardware/drivers/ddi/usbioctl/ne-usbioctl-_usb_connection_status">USB_CONNECTION_STATUS</a>
