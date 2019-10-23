---
UID: NS:usbioctl._USB_NODE_INFORMATION
title: _USB_NODE_INFORMATION (usbioctl.h)
description: The USB_NODE_INFORMATION structure is used with the IOCTL_USB_GET_NODE_INFORMATION I/O control request to retrieve information about a parent device.
old-location: buses\usb_node_information.htm
tech.root: usbref
ms.assetid: 56d30c25-00e7-4edf-af06-64519eb5f755
ms.date: 05/07/2018
ms.keywords: "*PUSB_NODE_INFORMATION, PUSB_NODE_INFORMATION, PUSB_NODE_INFORMATION structure pointer [Buses], USB_NODE_INFORMATION, USB_NODE_INFORMATION structure [Buses], _USB_NODE_INFORMATION, buses.usb_node_information, usbioctl/PUSB_NODE_INFORMATION, usbioctl/USB_NODE_INFORMATION, usbstrct_c3f807a8-2895-4a43-bfd3-84092fb4115e.xml"
ms.topic: struct
f1_keywords:
 - "usbioctl/USB_NODE_INFORMATION"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- usbioctl.h
api_name:
- USB_NODE_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: USB_NODE_INFORMATION, *PUSB_NODE_INFORMATION
---

# _USB_NODE_INFORMATION structure


## -description


The <b>USB_NODE_INFORMATION</b> structure is used with the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_usb_get_node_information">IOCTL_USB_GET_NODE_INFORMATION</a> I/O control request to retrieve information about a parent device.


## -struct-fields




### -field NodeType

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ne-usbioctl-_usb_hub_node">USB_HUB_NODE</a> enumerator that indicates whether the parent device is a hub or a non-hub composite device.


### -field u

The members of the <b>u</b> union are as follows:


### -field u.HubInformation

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_hub_information">USB_HUB_INFORMATION</a> structure that contains information about a parent hub device.


### -field u.MiParentInformation

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_mi_parent_information">USB_MI_PARENT_INFORMATION</a> structure that contains information about a parent non-hub, composite device.


## -remarks



A parent device can be either a hub or a composite device. The USB stack treats the interfaces of a composite device as though they were children of the composite device. The <b>USB_NODE_INFORMATION</b> structure can hold information about either kind of parent device (both hubs and composite devices).




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_usb_get_node_information">IOCTL_USB_GET_NODE_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">USB Structures</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_hub_information">USB_HUB_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ne-usbioctl-_usb_hub_node">USB_HUB_NODE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_mi_parent_information">USB_MI_PARENT_INFORMATION</a>
 

 

