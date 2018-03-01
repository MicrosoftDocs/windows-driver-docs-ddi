---
UID: NS:usbioctl._USB_NODE_INFORMATION
title: "_USB_NODE_INFORMATION"
author: windows-driver-content
description: The USB_NODE_INFORMATION structure is used with the IOCTL_USB_GET_NODE_INFORMATION I/O control request to retrieve information about a parent device.
old-location: buses\usb_node_information.htm
old-project: usbref
ms.assetid: 56d30c25-00e7-4edf-af06-64519eb5f755
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PUSB_NODE_INFORMATION, PUSB_NODE_INFORMATION, PUSB_NODE_INFORMATION structure pointer [Buses], USB_NODE_INFORMATION, USB_NODE_INFORMATION structure [Buses], _USB_NODE_INFORMATION, buses.usb_node_information, usbioctl/PUSB_NODE_INFORMATION, usbioctl/USB_NODE_INFORMATION, usbstrct_c3f807a8-2895-4a43-bfd3-84092fb4115e.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	usbioctl.h
api_name:
-	USB_NODE_INFORMATION
product: Windows
targetos: Windows
req.typenames: USB_NODE_INFORMATION, *PUSB_NODE_INFORMATION
req.product: Windows 10 or later.
---

# _USB_NODE_INFORMATION structure


## -description


The <b>USB_NODE_INFORMATION</b> structure is used with the <a href="..\usbioctl\ni-usbioctl-ioctl_usb_get_node_information.md">IOCTL_USB_GET_NODE_INFORMATION</a> I/O control request to retrieve information about a parent device.


## -syntax


````
typedef struct _USB_NODE_INFORMATION {
  USB_HUB_NODE NodeType;
  union {
    USB_HUB_INFORMATION       HubInformation;
    USB_MI_PARENT_INFORMATION MiParentInformation;
  } u;
} USB_NODE_INFORMATION, *PUSB_NODE_INFORMATION;
````


## -struct-fields




### -field NodeType

A <a href="..\usbioctl\ne-usbioctl-_usb_hub_node.md">USB_HUB_NODE</a> enumerator that indicates whether the parent device is a hub or a non-hub composite device.


### -field u

The members of the <b>u</b> union are as follows:



#### HubInformation

A <a href="..\usbioctl\ns-usbioctl-_usb_hub_information.md">USB_HUB_INFORMATION</a> structure that contains information about a parent hub device.



#### MiParentInformation

A <a href="..\usbioctl\ns-usbioctl-_usb_mi_parent_information.md">USB_MI_PARENT_INFORMATION</a> structure that contains information about a parent non-hub, composite device.


## -remarks



A parent device can be either a hub or a composite device. The USB stack treats the interfaces of a composite device as though they were children of the composite device. The <b>USB_NODE_INFORMATION</b> structure can hold information about either kind of parent device (both hubs and composite devices).




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>



<a href="..\usbioctl\ns-usbioctl-_usb_mi_parent_information.md">USB_MI_PARENT_INFORMATION</a>



<a href="..\usbioctl\ni-usbioctl-ioctl_usb_get_node_information.md">IOCTL_USB_GET_NODE_INFORMATION</a>



<a href="..\usbioctl\ns-usbioctl-_usb_hub_information.md">USB_HUB_INFORMATION</a>



<a href="..\usbioctl\ne-usbioctl-_usb_hub_node.md">USB_HUB_NODE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USB_NODE_INFORMATION structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

