---
UID: NS:usbspec._USB_INTERFACE_DESCRIPTOR
title: "_USB_INTERFACE_DESCRIPTOR"
author: windows-driver-content
description: The USB_INTERFACE_DESCRIPTOR structure is used by USB client drivers to retrieve a USB-defined interface descriptor.
old-location: buses\usb_interface_descriptor.htm
old-project: usbref
ms.assetid: 12378915-fa3d-4054-bb06-6eb8b292559c
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PUSB_INTERFACE_DESCRIPTOR, PUSB_INTERFACE_DESCRIPTOR, PUSB_INTERFACE_DESCRIPTOR structure pointer [Buses], USB_INTERFACE_DESCRIPTOR, USB_INTERFACE_DESCRIPTOR structure [Buses], _USB_INTERFACE_DESCRIPTOR, buses.usb_interface_descriptor, usbspec/PUSB_INTERFACE_DESCRIPTOR, usbspec/USB_INTERFACE_DESCRIPTOR, usbstrct_2b4503ac-895a-4e94-87b5-10f286ed0b90.xml"
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
-	USB_INTERFACE_DESCRIPTOR
product:
- Windows
targetos: Windows
req.typenames: USB_INTERFACE_DESCRIPTOR, *PUSB_INTERFACE_DESCRIPTOR
req.product: Windows 10 or later.
---

# _USB_INTERFACE_DESCRIPTOR structure


## -description


The <b>USB_INTERFACE_DESCRIPTOR</b> structure is used by USB client drivers to retrieve a USB-defined interface descriptor.


## -struct-fields




### -field bLength

The length, in bytes, of the descriptor.


### -field bDescriptorType

The descriptor type. <b>bDescriptor</b> must be set to USB_INTERFACE_DESCRIPTOR_TYPE.


### -field bInterfaceNumber

The index number of the interface.


### -field bAlternateSetting

The index number of the alternate setting of the interface.


### -field bNumEndpoints

The number of endpoints that are used by the interface, excluding the default status endpoint.


### -field bInterfaceClass

The class code of the device that the USB specification group assigned.


### -field bInterfaceSubClass

The subclass code of the device that the USB specification group assigned.


### -field bInterfaceProtocol

The protocol code of the device that the USB specification group assigned.


### -field iInterface

The index of a string descriptor that describes the interface. For information about this field, see section 9.6.5 in the "Universal Serial Bus Revision 2.0" specification  at <a href="http://www.usb.org/developers/docs/">USB Technology</a>.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538943">UsbBuildGetDescriptorRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540357">_URB_CONTROL_DESCRIPTOR_REQUEST</a>
 

 

