---
UID: NS:usbspec._USB_STRING_DESCRIPTOR
title: _USB_STRING_DESCRIPTOR (usbspec.h)
description: The USB_STRING_DESCRIPTOR structure is used by USB client drivers to hold a USB-defined string descriptor.
old-location: buses\usb_string_descriptor.htm
tech.root: usbref
ms.assetid: 20d76582-4138-4a45-940b-a8e9207946a5
ms.date: 05/07/2018
ms.keywords: "*PUSB_STRING_DESCRIPTOR, PUSB_STRING_DESCRIPTOR, PUSB_STRING_DESCRIPTOR structure pointer [Buses], USB_STRING_DESCRIPTOR, USB_STRING_DESCRIPTOR structure [Buses], _USB_STRING_DESCRIPTOR, buses.usb_string_descriptor, usbspec/PUSB_STRING_DESCRIPTOR, usbspec/USB_STRING_DESCRIPTOR, usbstrct_b0740c7e-9042-4426-be26-20b8620a0e7e.xml"
ms.topic: struct
req.header: usbspec.h
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	usbspec.h
api_name:
-	USB_STRING_DESCRIPTOR
product:
- Windows
targetos: Windows
req.typenames: USB_STRING_DESCRIPTOR, *PUSB_STRING_DESCRIPTOR
---

# _USB_STRING_DESCRIPTOR structure


## -description


The <b>USB_STRING_DESCRIPTOR</b> structure is used by USB client drivers to hold a USB-defined string descriptor.
The members of this structure are described in the Universal Serial Bus 3.1 Specification available at [USB Document Library](https://www.usb.org/developers/docs). See section 9.6.9.

## -struct-fields




### -field bLength

Specifies the length, in bytes, of the descriptor.


### -field bDescriptorType

Specifies the descriptor type. Must always be USB_STRING_DESCRIPTOR_TYPE.


### -field bString

Pointer to a client-allocated buffer that contains, on return from the host controller driver, a Unicode string with the requested string descriptor.


## -remarks



This structure is used to hold a device, configuration, interface, class, vendor, endpoint, or device string descriptor. The string descriptor provides a human-readable description of the component.

Strings returned in <b>bString</b> are in Unicode format and the contents of the strings are device-defined.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538943">UsbBuildGetDescriptorRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540357">_URB_CONTROL_DESCRIPTOR_REQUEST</a>
 

 

