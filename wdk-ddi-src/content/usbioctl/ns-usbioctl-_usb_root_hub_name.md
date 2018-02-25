---
UID: NS:usbioctl._USB_ROOT_HUB_NAME
title: "_USB_ROOT_HUB_NAME"
author: windows-driver-content
description: The USB_ROOT_HUB_NAME structure stores the root hub's symbolic device name.
old-location: buses\usb_root_hub_name.htm
old-project: UsbRef
ms.assetid: bd9697ce-bd05-4169-9b0f-13877307c0d7
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: ",  , *, *PUSB_ROOT_HUB_NAME, ,, A, B, E, H, M, N, O, P, PUSB_ROOT_HUB_NAME, PUSB_ROOT_HUB_NAME structure pointer [Buses], R, S, T, U, USB_ROOT_HUB_NAME, USB_ROOT_HUB_NAME structure [Buses], _, _USB_ROOT_HUB_NAME, buses.usb_root_hub_name, usbioctl/PUSB_ROOT_HUB_NAME, usbioctl/USB_ROOT_HUB_NAME, usbstrct_a285af0b-6144-46a0-bfbf-640b3073047a.xml"
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
-	USB_ROOT_HUB_NAME
product: Windows
targetos: Windows
req.typenames: USB_ROOT_HUB_NAME, *PUSB_ROOT_HUB_NAME
req.product: Windows 10 or later.
---

# _USB_ROOT_HUB_NAME structure


## -description


The <b>USB_ROOT_HUB_NAME</b> structure stores the root hub's symbolic device name.


## -syntax


````
typedef struct _USB_ROOT_HUB_NAME {
  ULONG ActualLength;
  WCHAR RootHubName[1];
} USB_ROOT_HUB_NAME, *PUSB_ROOT_HUB_NAME;
````


## -struct-fields




### -field ActualLength

Size of the entire data structure in bytes.


### -field RootHubName

Specifies the Unicode string containing the root hub's symbolic device name.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>



<a href="..\usbioctl\ni-usbioctl-ioctl_internal_usb_get_hub_name.md">IOCTL_INTERNAL_USB_GET_HUB_NAME</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [UsbRef\buses]:%20USB_ROOT_HUB_NAME structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

