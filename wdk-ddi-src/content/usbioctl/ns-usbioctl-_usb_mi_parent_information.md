---
UID: NS:usbioctl._USB_MI_PARENT_INFORMATION
title: _USB_MI_PARENT_INFORMATION (usbioctl.h)
description: The USB_MI_PARENT_INFORMATION structure contains information about a composite device.
old-location: buses\usb_mi_parent_information.htm
tech.root: usbref
ms.assetid: 9697f739-0eef-4b58-a9f3-8613f71c18be
ms.date: 05/07/2018
ms.keywords: "*PUSB_MI_PARENT_INFORMATION, PUSB_MI_PARENT_INFORMATION, PUSB_MI_PARENT_INFORMATION structure pointer [Buses], USB_MI_PARENT_INFORMATION, USB_MI_PARENT_INFORMATION structure [Buses], _USB_MI_PARENT_INFORMATION, buses.usb_mi_parent_information, usbioctl/PUSB_MI_PARENT_INFORMATION, usbioctl/USB_MI_PARENT_INFORMATION, usbstrct_710c4241-48d7-4fe7-bd1b-268c7c0f2b41.xml"
f1_keywords:
 - "usbioctl/USB_MI_PARENT_INFORMATION"
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
- USB_MI_PARENT_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: USB_MI_PARENT_INFORMATION, *PUSB_MI_PARENT_INFORMATION
---

# _USB_MI_PARENT_INFORMATION structure


## -description


The <b>USB_MI_PARENT_INFORMATION</b> structure contains information about a composite device.


## -struct-fields




### -field NumberOfInterfaces

The number of interfaces on the composite device.


## -remarks



A composite device is a device with multiple interfaces (MI). The USB stack treats the interfaces of a composite device as child devices of the composite device and creates a separate PDO for each interface.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">USB Structures</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_node_information">USB_NODE_INFORMATION</a>
 

 

