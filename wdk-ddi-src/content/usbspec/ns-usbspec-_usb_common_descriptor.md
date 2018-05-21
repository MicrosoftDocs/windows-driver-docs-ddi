---
UID: NS:usbspec._USB_COMMON_DESCRIPTOR
title: "_USB_COMMON_DESCRIPTOR"
author: windows-driver-content
description: The USB_COMMON_DESCRIPTOR structure contains the head of the first descriptor that matches the search criteria in a call to USBD_ParseDescriptors.
old-location: buses\usb_common_descriptor.htm
old-project: usbref
ms.assetid: 1ea51976-c786-4ca3-aaa3-a44fa8697efa
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: "*PUSB_COMMON_DESCRIPTOR, PUSB_COMMON_DESCRIPTOR, PUSB_COMMON_DESCRIPTOR structure pointer [Buses], USB_COMMON_DESCRIPTOR, USB_COMMON_DESCRIPTOR structure [Buses], _USB_COMMON_DESCRIPTOR, buses.usb_common_descriptor, usbspec/PUSB_COMMON_DESCRIPTOR, usbspec/USB_COMMON_DESCRIPTOR, usbstrct_be74945b-60a4-44cc-9c7b-e1eb5cc25525.xml"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	usbspec.h
api_name:
-	USB_COMMON_DESCRIPTOR
product:
- Windows
targetos: Windows
req.typenames: USB_COMMON_DESCRIPTOR, *PUSB_COMMON_DESCRIPTOR
---

# _USB_COMMON_DESCRIPTOR structure


## -description


The <b>USB_COMMON_DESCRIPTOR</b> structure contains the head of the first descriptor that matches the search criteria in a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff539109">USBD_ParseDescriptors</a>. 


## -struct-fields




### -field bLength

Specifies the entire length of the descriptor, not of this structure.


### -field bDescriptorType

Specifies the descriptor type code, as assigned by USB, for this descriptor.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539109">USBD_ParseDescriptors</a>
 

 

