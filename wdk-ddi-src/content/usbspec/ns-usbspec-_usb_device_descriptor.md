---
UID: NS:usbspec._USB_DEVICE_DESCRIPTOR
title: "_USB_DEVICE_DESCRIPTOR"
author: windows-driver-content
description: The USB_DEVICE_DESCRIPTOR structure is used by USB client drivers to retrieve a USB-defined device descriptor.
old-location: buses\usb_device_descriptor.htm
tech.root: usbref
ms.assetid: 124184ef-7410-4e04-abb2-e07db4ae2cbf
ms.date: 5/7/2018
ms.keywords: "*PUSB_DEVICE_DESCRIPTOR, PUSB_DEVICE_DESCRIPTOR, PUSB_DEVICE_DESCRIPTOR structure pointer [Buses], USB_DEVICE_DESCRIPTOR, USB_DEVICE_DESCRIPTOR structure [Buses], _USB_DEVICE_DESCRIPTOR, buses.usb_device_descriptor, usbspec/PUSB_DEVICE_DESCRIPTOR, usbspec/USB_DEVICE_DESCRIPTOR, usbstrct_40e68471-a1e1-4e2e-8bea-77c8f7085589.xml"
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
-	USB_DEVICE_DESCRIPTOR
product:
- Windows
targetos: Windows
req.typenames: USB_DEVICE_DESCRIPTOR, *PUSB_DEVICE_DESCRIPTOR
---

# _USB_DEVICE_DESCRIPTOR structure


## -description


The <b>USB_DEVICE_DESCRIPTOR</b> structure is used by USB client drivers to retrieve a USB-defined device descriptor.
The members of this structure are described in the Universal Serial Bus 3.1 Specification available at [USB Document Library](www.usb.org/developers/docs). See section 9.6.1.

## -struct-fields




### -field bLength

Specifies the length, in bytes, of this descriptor.


### -field bDescriptorType

Specifies the descriptor type. Must be set to <b>USB_DEVICE_DESCRIPTOR_TYPE</b>.


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


### -field idVendor

Specifies the vendor identifier for the device as assigned by the USB specification committee.


### -field idProduct

Specifies the product identifier. This value is assigned by the manufacturer and is device-specific.


### -field bcdDevice

Identifies the version of the device. This value is a binary-coded decimal number.


### -field iManufacturer

Specifies a device-defined index of the string descriptor that provides a string containing the name of the manufacturer of this device.


### -field iProduct

Specifies a device-defined index of the string descriptor that provides a string that contains a description of the device.


### -field iSerialNumber

Specifies a device-defined index of the string descriptor that provides a string that contains a manufacturer-determined serial number for the device.


### -field bNumConfigurations

Specifies the total number of possible configurations for the device.


## -remarks



This structure is used to hold a retrieved USB-defined device descriptor. This information can then be used to further configure or retrieve information about the device. Device descriptors are retrieved by submitting a get-descriptor URB.

The <b>iManufacturer</b>, <b>iProduct</b>, and <b>iSerialNumber</b> values, when returned from the host controller driver, contain index values into an array of string descriptors maintained by the device. To retrieve these strings, a string descriptor request can be sent to the device using these index values.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538943">UsbBuildGetDescriptorRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540357">_URB_CONTROL_DESCRIPTOR_REQUEST</a>
 

 

