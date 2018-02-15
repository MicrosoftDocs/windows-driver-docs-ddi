---
UID: NS:usbspec._USB_DEVICE_QUALIFIER_DESCRIPTOR
title: "_USB_DEVICE_QUALIFIER_DESCRIPTOR"
author: windows-driver-content
description: The USB_DEVICE_QUALIFIER_DESCRIPTOR structure is used by USB client drivers to retrieve a USB-defined device qualifier descriptor.
old-location: buses\usb_device_qualifier_descriptor.htm
old-project: usbref
ms.assetid: f96e4305-ec07-4df8-8fdf-f840598dd938
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: "_USB_DEVICE_QUALIFIER_DESCRIPTOR, *PUSB_DEVICE_QUALIFIER_DESCRIPTOR, USB_DEVICE_QUALIFIER_DESCRIPTOR structure [Buses], PUSB_DEVICE_QUALIFIER_DESCRIPTOR, buses.usb_device_qualifier_descriptor, usbspec/PUSB_DEVICE_QUALIFIER_DESCRIPTOR, usbspec/USB_DEVICE_QUALIFIER_DESCRIPTOR, USB_DEVICE_QUALIFIER_DESCRIPTOR, usbstrct_af615085-b822-4342-b1dd-950a0ff61d99.xml, PUSB_DEVICE_QUALIFIER_DESCRIPTOR structure pointer [Buses]"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usbspec.h
req.include-header: Usb200.h
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
-	USB_DEVICE_QUALIFIER_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: "*PUSB_DEVICE_QUALIFIER_DESCRIPTOR, USB_DEVICE_QUALIFIER_DESCRIPTOR"
req.product: Windows 10 or later.
---

# _USB_DEVICE_QUALIFIER_DESCRIPTOR structure


## -description


The <b>USB_DEVICE_QUALIFIER_DESCRIPTOR</b> structure is used by USB client drivers to retrieve a USB-defined device qualifier descriptor.


## -syntax


````
typedef struct _USB_DEVICE_QUALIFIER_DESCRIPTOR {
  UCHAR  bLength;
  UCHAR  bDescriptorType;
  USHORT bcdUSB;
  UCHAR  bDeviceClass;
  UCHAR  bDeviceSubClass;
  UCHAR  bDeviceProtocol;
  UCHAR  bMaxPacketSize0;
  UCHAR  bNumConfigurations;
  UCHAR  bReserved;
} USB_DEVICE_QUALIFIER_DESCRIPTOR, *PUSB_DEVICE_QUALIFIER_DESCRIPTOR;
````


## -struct-fields




### -field bLength

Specifies the length, in bytes, of this descriptor.


### -field bDescriptorType

Specifies the descriptor type. Must be set to <b>USB_DEVICE_QUALIFIER_DESCRIPTOR_TYPE</b>.


### -field bcdUSB

Identifies the version of the USB specification that this descriptor structure complies with. This value is a binary-coded decimal number.


### -field bDeviceClass

Specifies the class code of the device as assigned by the USB specification group.


### -field bDeviceSubClass

Specifies the subclass code of the device as assigned by the USB specification group.


### -field bDeviceProtocol

Specifies the protocol code of the device as assigned by the USB specification group.


### -field bMaxPacketSize0

Specifies the maximum packet size, in bytes, for endpoint zero of the device. The value must be set to 8, 16, 32, or 64.


### -field bNumConfigurations

Specifies the total number of possible configurations for the device.


### -field bReserved

Reserved.


## -remarks



This structure is similar to <a href="..\usbspec\ns-usbspec-_usb_device_descriptor.md">USB_DEVICE_DESCRIPTOR</a>, but it contains only those members that can change when the device switches from full-speed operation to high-speed operation or vice versa. If the device is operating at full speed, querying for this descriptor will contain information about how the device would operate at high-speed. If, on the other hand, the device is operating at high-speed, this descriptor will contain information about how the device would operate at full-speed.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538943">UsbBuildGetDescriptorRequest</a>



<a href="..\usb\ns-usb-_urb_control_descriptor_request.md">_URB_CONTROL_DESCRIPTOR_REQUEST</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USB_DEVICE_QUALIFIER_DESCRIPTOR structure%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

