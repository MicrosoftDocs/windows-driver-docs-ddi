---
UID: NS:usbspec._USB_COMMON_DESCRIPTOR
title: _USB_COMMON_DESCRIPTOR
author: windows-driver-content
description: The USB_COMMON_DESCRIPTOR structure contains the head of the first descriptor that matches the search criteria in a call to USBD_ParseDescriptors.
old-location: buses\usb_common_descriptor.htm
old-project: usbref
ms.assetid: 1ea51976-c786-4ca3-aaa3-a44fa8697efa
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: usbstrct_be74945b-60a4-44cc-9c7b-e1eb5cc25525.xml, usbspec/USB_COMMON_DESCRIPTOR, PUSB_COMMON_DESCRIPTOR structure pointer [Buses], usbspec/PUSB_COMMON_DESCRIPTOR, USB_COMMON_DESCRIPTOR structure [Buses], PUSB_COMMON_DESCRIPTOR, *PUSB_COMMON_DESCRIPTOR, buses.usb_common_descriptor, USB_COMMON_DESCRIPTOR, _USB_COMMON_DESCRIPTOR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usbspec.h
req.include-header: Usb100.h
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	usbspec.h
apiname: 
-	USB_COMMON_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: *PUSB_COMMON_DESCRIPTOR, USB_COMMON_DESCRIPTOR
req.product: Windows 10 or later.
---

# _USB_COMMON_DESCRIPTOR structure


## -description


The <b>USB_COMMON_DESCRIPTOR</b> structure contains the head of the first descriptor that matches the search criteria in a call to <a href="..\usbdlib\nf-usbdlib-usbd_parsedescriptors.md">USBD_ParseDescriptors</a>. 


## -syntax


````
typedef struct _USB_COMMON_DESCRIPTOR {
  UCHAR bLength;
  UCHAR bDescriptorType;
} USB_COMMON_DESCRIPTOR, *PUSB_COMMON_DESCRIPTOR;
````


## -struct-fields




### -field bLength

Specifies the entire length of the descriptor, not of this structure.


### -field bDescriptorType

Specifies the descriptor type code, as assigned by USB, for this descriptor.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>

<a href="..\usbdlib\nf-usbdlib-usbd_parsedescriptors.md">USBD_ParseDescriptors</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USB_COMMON_DESCRIPTOR structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

