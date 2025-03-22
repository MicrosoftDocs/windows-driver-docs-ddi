---
UID: NS:usbioctl._USB_NODE_CONNECTION_DRIVERKEY_NAME
title: _USB_NODE_CONNECTION_DRIVERKEY_NAME (usbioctl.h)
description: The USB_NODE_CONNECTION_DRIVERKEY_NAME structure is used with the IOCTL_USB_GET_NODE_CONNECTION_DRIVERKEY_NAME I/O control request to retrieve the driver key name for the device that is connected to the indicated port.
old-location: buses\usb_node_connection_driverkey_name.htm
tech.root: usbref
ms.date: 05/15/2024
keywords: ["USB_NODE_CONNECTION_DRIVERKEY_NAME structure"]
ms.keywords: "*PUSB_NODE_CONNECTION_DRIVERKEY_NAME, PUSB_NODE_CONNECTION_DRIVERKEY_NAME, PUSB_NODE_CONNECTION_DRIVERKEY_NAME structure pointer [Buses], USB_NODE_CONNECTION_DRIVERKEY_NAME, USB_NODE_CONNECTION_DRIVERKEY_NAME structure [Buses], _USB_NODE_CONNECTION_DRIVERKEY_NAME, buses.usb_node_connection_driverkey_name, usbioctl/PUSB_NODE_CONNECTION_DRIVERKEY_NAME, usbioctl/USB_NODE_CONNECTION_DRIVERKEY_NAME, usbstrct_561b9eb1-d580-48c5-ac16-c87647f7a342.xml"
req.header: usbioctl.h
req.construct-type: structure
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
req.typenames: USB_NODE_CONNECTION_DRIVERKEY_NAME, *PUSB_NODE_CONNECTION_DRIVERKEY_NAME
f1_keywords:
 - _USB_NODE_CONNECTION_DRIVERKEY_NAME
 - usbioctl/_USB_NODE_CONNECTION_DRIVERKEY_NAME
 - PUSB_NODE_CONNECTION_DRIVERKEY_NAME
 - usbioctl/PUSB_NODE_CONNECTION_DRIVERKEY_NAME
 - USB_NODE_CONNECTION_DRIVERKEY_NAME
 - usbioctl/USB_NODE_CONNECTION_DRIVERKEY_NAME
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - usbioctl.h
api_name:
 - _USB_NODE_CONNECTION_DRIVERKEY_NAME
 - PUSB_NODE_CONNECTION_DRIVERKEY_NAME
 - USB_NODE_CONNECTION_DRIVERKEY_NAME
---

# USB_NODE_CONNECTION_DRIVERKEY_NAME structure (usbioctl.h)



## -description

The **USB_NODE_CONNECTION_DRIVERKEY_NAME** structure is used with the [IOCTL_USB_GET_NODE_CONNECTION_DRIVERKEY_NAME](/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_usb_get_node_connection_driverkey_name) I/O control request to retrieve the driver key name for the device that is connected to the indicated port.

## -struct-fields

### -field ConnectionIndex

On input, the port number that the device is connected to.

### -field ActualLength

On output, the length of this structure, in bytes.

### -field DriverKeyName

On output, the driver key name for the device that is attached to the port that is indicated by **ConnectionIndex**. This name is represented as a Unicode string.

## -see-also

- [IOCTL_USB_GET_NODE_CONNECTION_DRIVERKEY_NAME](/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_usb_get_node_connection_driverkey_name)
- [USB Structures](/windows-hardware/drivers/ddi/_usbref/#structures)
