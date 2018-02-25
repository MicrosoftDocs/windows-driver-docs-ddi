---
UID: NS:usbioctl._USB_MI_PARENT_INFORMATION
title: "_USB_MI_PARENT_INFORMATION"
author: windows-driver-content
description: The USB_MI_PARENT_INFORMATION structure contains information about a composite device.
old-location: buses\usb_mi_parent_information.htm
old-project: UsbRef
ms.assetid: 9697f739-0eef-4b58-a9f3-8613f71c18be
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: ",  , *, *PUSB_MI_PARENT_INFORMATION, ,, A, B, E, F, I, M, N, O, P, PUSB_MI_PARENT_INFORMATION, PUSB_MI_PARENT_INFORMATION structure pointer [Buses], R, S, T, U, USB_MI_PARENT_INFORMATION, USB_MI_PARENT_INFORMATION structure [Buses], _, _USB_MI_PARENT_INFORMATION, buses.usb_mi_parent_information, usbioctl/PUSB_MI_PARENT_INFORMATION, usbioctl/USB_MI_PARENT_INFORMATION, usbstrct_710c4241-48d7-4fe7-bd1b-268c7c0f2b41.xml"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	usbioctl.h
apiname:
-	USB_MI_PARENT_INFORMATION
product: Windows
targetos: Windows
req.typenames: USB_MI_PARENT_INFORMATION, *PUSB_MI_PARENT_INFORMATION
req.product: Windows 10 or later.
---

# _USB_MI_PARENT_INFORMATION structure


## -description


The <b>USB_MI_PARENT_INFORMATION</b> structure contains information about a composite device.


## -syntax


````
typedef struct _USB_MI_PARENT_INFORMATION {
  ULONG NumberOfInterfaces;
} USB_MI_PARENT_INFORMATION, *PUSB_MI_PARENT_INFORMATION;
````


## -struct-fields




### -field NumberOfInterfaces

The number of interfaces on the composite device.


## -remarks



A composite device is a device with multiple interfaces (MI). The USB stack treats the interfaces of a composite device as child devices of the composite device and creates a separate PDO for each interface.




## -see-also

<a href="..\usbioctl\ns-usbioctl-_usb_node_information.md">USB_NODE_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [UsbRef\buses]:%20USB_MI_PARENT_INFORMATION structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

