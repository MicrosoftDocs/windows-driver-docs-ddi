---
UID: NS:usbioctl._USB_ROOT_HUB_NAME
title: _USB_ROOT_HUB_NAME (usbioctl.h)
description: The USB_ROOT_HUB_NAME structure stores the root hub's symbolic device name.
old-location: buses\usb_root_hub_name.htm
tech.root: usbref
ms.assetid: bd9697ce-bd05-4169-9b0f-13877307c0d7
ms.date: 05/07/2018
ms.keywords: "*PUSB_ROOT_HUB_NAME, PUSB_ROOT_HUB_NAME, PUSB_ROOT_HUB_NAME structure pointer [Buses], USB_ROOT_HUB_NAME, USB_ROOT_HUB_NAME structure [Buses], _USB_ROOT_HUB_NAME, buses.usb_root_hub_name, usbioctl/PUSB_ROOT_HUB_NAME, usbioctl/USB_ROOT_HUB_NAME, usbstrct_a285af0b-6144-46a0-bfbf-640b3073047a.xml"
f1_keywords:
 - "usbioctl/USB_ROOT_HUB_NAME"
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
- USB_ROOT_HUB_NAME
product:
- Windows
targetos: Windows
req.typenames: USB_ROOT_HUB_NAME, *PUSB_ROOT_HUB_NAME
---

# _USB_ROOT_HUB_NAME structure


## -description


The <b>USB_ROOT_HUB_NAME</b> structure stores the root hub's symbolic device name.


## -struct-fields




### -field ActualLength

Size of the entire data structure in bytes.


### -field RootHubName

Specifies the Unicode string containing the root hub's symbolic device name.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_internal_usb_get_hub_name">IOCTL_INTERNAL_USB_GET_HUB_NAME</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">USB Structures</a>
 

 

